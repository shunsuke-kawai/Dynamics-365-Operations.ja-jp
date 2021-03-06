---
title: 新しい Retail Server 拡張機能の作成
description: このトピックでは、新しい Retail Server 拡張機能の作成方法について説明します。
author: mugunthanm
manager: AnnBe
ms.date: 08/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations, Retail
ms.custom: 28021
ms.assetid: ''
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2019-08-2019
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: bce65b42c6d87fd57e7fc1d45eca5d6afe9610c7
ms.sourcegitcommit: 0262a19e32b2c0c84c731d9f4fbe8ba91822afa3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "2622586"
---
# <a name="create-a-new-retail-server-extension"></a>新しい Retail Server 拡張機能の作成

[!include [banner](../includes/banner.md)]

このドキュメントでは、新しい Retail Server アプリケーション プログラミング インターフェイス (API) の作成方法、および POS または他のクライアントがそれを使用できるようにするための公開方法について説明します。 既存の Retail Server API の変更はサポートされていません。

Retail ソフトウェア開発キット (SDK) には、Commerce Runtime (CRT) を含む、エンドツーエンドの Retail Server 拡張機能のサンプルがいくつか用意されているのみです。 これらのサンプルをテンプレートとして使用して、拡張機能を起動できます。 サンプル拡張機能は、RetailSDK\\SampleExtensions\\RetailServer フォルダーで見つけることができます。

## <a name="end-to-end-sample-repository-in-the-retail-sdk"></a>Retail SDK のエンドツーエンド サンプル リポジトリ

| サンプル拡張機能<br>(RetailSDK\\SampleExtensions\\RetailServer) | CRT サンプル<br>(RetailSDK\\SampleExtensions\\CommerceRuntime) | POS サンプル<br>(RetailSDK\\POS\\Extensions) |
|---------------------------------------------|--------------------------------------------|----------------------------------------|
| Extensions.StoreHoursSample                 | Extensions.StoreHoursSample                | StoreHoursSample                       |
| Extensions.SalesTransactionSignatureSample  | Extensions.SalesTransactionSignatureSample | SalesTransactionSignatureSample        |
| Extensions.PrintPackingSlipSample           | Extensions.PrintPackingSlipSample          |                                        |
| Extensions.CrossLoyaltySample               | Extensions.CrossLoyaltySample              |                                        |

## <a name="create-a-new-retail-server-extension"></a>新しい Retail Server 拡張機能の作成

このセクションの手順に従って、新しい Retail Server 拡張機能を作成します。

### <a name="end-to-end-flow"></a>エンド ツー エンド フロー

次の図は、拡張機能のフローを示しています。

![Retail Server の拡張機能フロー](media/RSExtensionFlow.png)

### <a name="retail-server-extension-class-diagram"></a>Retail Server の拡張機能クラス ダイアグラム

次の図は、拡張機能のクラス ダイアグラムを示しています。

![Retail Server の拡張機能クラス ダイアグラム](media/RSClassFlow.png)

### <a name="steps"></a>ステップ

1. Retail Server 拡張機能を作成する前に、CRT 拡張機能を作成します。 Retail Server API には、パラメーターで CRT を呼び出すロジック以外のロジックはありません。
2. Microsoft .NET フレームワーク バージョン 4.6.1 以降をターゲット フレームワークとして使用する、新しい C\#クラス ライブラリ プロジェクトを作成します。
3. Retail Server 拡張機能プロジェクトで、CRT 拡張機能ライブラリまたはプロジェクトへの参照を追加します。 この参照を使用して、CRT 要求と応答を呼び出すことができます。 また、Retail Server 拡張機能プロジェクトからのエンティティを使用することもできます。
4. Retail Server 拡張機能プロジェクトで、**NonBindableOperationController** または **CommerceController** を拡張する新しいコントローラー クラスを作成します。 基本クラスは、シナリオによって異なります。 このコントローラー クラスには、Retail Server API によって公開される必要のあるメソッドが含まれています。 コントローラー クラス内で、CRT 要求を呼び出すメソッドを追加します。

    ```C#
    /// <summary>;
    /// The controller to retrieve a new entity.
    /// <summary>
    [ComVisible(false)]
    public class SampleController : CommerceController<SampleEntity, long>;
    {
        ///<summary>;
        /// Gets the controller name used to load extended controller.
        /// <summary>
        public override string ControllerName
        {
            get { return "SampleEntity"; }
        }
        /// <summary>;
        /// Gets the sample entity.
        /// <summary>;
        /// <param name="parameters">The parameters to this action.</param>
        /// <returns>The list of sample entity.</returns>
        [HttpPost]
        [CommerceAuthorization(CommerceRoles.Anonymous, CommerceRoles.Customer, CommerceRoles.Device, CommerceRoles.Employee)]
        public System.Web.OData.PageResult<SampleEntity> GetSampleEntity(ODataActionParameters parameters)
        {
            if (parameters == null)
            {
                throw new ArgumentNullException("parameters");
            }
            var runtime = CommerceRuntimeManager.CreateRuntime(this.CommercePrincipal);
            QueryResultSettings queryResultSettings = QueryResultSettings.SingleRecord;
            queryResultSettings.Paging = new PagingInfo(10);
            var request = new CRTDataRequest((string)parameters["key"]) { QueryResultSettings = queryResultSettings };
            PagedResult<SampleEntity> sample = runtime.Execute<CRTDataResponse>(request, null);
            return this.ProcessPagedResults(sample);
        }
    }
    ```

5. **IEdmModelExtender** インターフェイスを拡張する **EdmModelExtender** (EDM) クラスを作成します。 このクラスには、Retail Server API が公開するデータを説明するために使用される抽象データ モデルが含まれています。 オープン データ プロトコル (OData) メタデータ ドキュメントは、クライアントの消費に対して公開されるサービスのデータ モデルを表したものです。 EDM の中心となる概念は、エンティティ、リレーションシップ、エンティティ セット、アクション、および機能です。

    **IEdmModelExtender** インターフェイスには、抽象 **ExtendModel** メソッドが含まれています。 このインターフェイスを拡張する場合、**ExtendModel** メソッドを実装する必要があります。 **ExtendModel** メソッド内で、**CommerceModelBuilder** クラスを使用してクライアントに公開される EDM エンティティおよび機能を構築します。

    **CommerceModelBuilder** クラスには、エンティティおよび機能を構築するのに使用される構築メソッドが含まれています。

    | メソッド名                                                                 | 戻り値の型                              | 説明 |
    |-----------------------------------------------------------------------------|------------------------------------------|-------------|
    | BuildEntity\<TEntity\>() where TEntity : class                              | EntityTypeConfiguration\<TEntity\>       | このメソッドがエンティティを構築します。 |
    | BuildEntitySet\<TEntity\>(string entitySetName) where TEntity : class       | EntitySetConfiguration\<TEntity\>        | このメソッドがエンティティ セットを構築します。 |
    | BuildComplexType\<TComplexType\>() where TComplexType : class               | ComplexTypeConfiguration\<TComplexType\> | このメソッドが、複雑なエンティティ タイプを構築します。 |
    | BuildEnumType\<TEnumType\>()                                                | EnumTypeConfiguration\<TEnumType\>       | このメソッドが、列挙型を構築します。 |
    | BindAction(string actionName)                                               | ActionConfiguration                      | このメソッドが、モデル ビルダーのアクションをバインドします。 アクションは HTTP POST 要求を表します。 |
    | BindEntityAction\<TEntity\>(string actionName) where TEntity : class        | ActionConfiguration                      | このメソッドが、モデルのエンティティ アクションをバインドします。 アクションは HTTP POST 要求を表します。 |
    | BindEntitySetAction\<TEntity\>(string actionName) where TEntity : class     | ActionConfiguration                      | このメソッドがエンティティ セット アクションをバインドします。 アクションは HTTP POST 要求を表します。             |
    | BindFunction(string functionName)                                           | FunctionConfiguration                    | このメソッドが、モデル ビルダーの機能をバインドします。 機能は HTTP GET 要求を表します。 |
    | BindEntityFunction\<TEntity\>(string functionName) where TEntity : class    | FunctionConfiguration                    | このメソッドが、モデルのエンティティ機能をバインドします。 機能は HTTP GET 要求を表します。 |
    | BindEntitySetFunction\<TEntity\>(string functionName) where TEntity : class | FunctionConfiguration                    | このメソッドがエンティティ セット機能をバインドします。 機能は HTTP GET 要求を表します。 |

    次の例は、EDM モデルを拡張する方法を示しています。

    ```C#
    /// <summary>;
    /// The class to extend the EDM model.
    /// <summary>;
    [Export(typeof(IEdmModelExtender))]
    [ComVisible(false)]
    public class EdmModelExtender : IEdmModelExtender
    {
        /// <summary>;
        /// Extends the EDM model.
        /// <summary>;
        /// <param name="builder">The builder to build the EDM model.</param>
        public void ExtendModel(CommerceModelBuilder builder)
        {
            ThrowIf.Null(builder, "builder");
            // Extends entity sets.
            builder.BuildEntitySet<SampleEntity>("SampleEntity");
            // Extends entity set actions.
            var action = builder.BindEntitySetAction<SampleDataModel.StoreDayHours>("GetSampleEntity");
            action.Parameter<string>("Key");
            action.ReturnsCollectionFromEntitySet<SampleEntity>("SampleEntity");
        }
    }
    ```

6. 拡張機能プロジェクトをビルドし、バイナリを **\\RetailServer\\webroot\\bin\\Ext** フォルダーにドロップします。
7. **extensionComposition** セクションで新しい Retail Server 拡張ライブラリ名を追加して、**\\RetailServer\\Webroot** フォルダーの Retail Server web.config ファイルを更新します。

    ```
    <extensionComposition>
    <!-- Please use fully qualified assembly names for ALL if you need to support loading from the Global Assembly Cache.
    If you host in an application with a bin folder, this is not required. -->
    <add source="assembly" value="SampleExtension" >;
    </extensionComposition>
    ```

8. Microsoft インターネット インフォメーション サービス (IIS) で、Retail Server を再起動して、新しい Retail Server 拡張機能を読み込みます。
9. 拡張機能が正常に読み込まれたことを確認するには、Retail Server メタデータを参照し、エンティティとメソッドがリストに表示されていることを確認します。

    Retail Server メタデータを参照するには、Web ブラウザーの次の形式で URL を開きます。

    `https://Your Retail Server URL/Commerce/$metadata`

10. クライアントで Retail Server 拡張機能を呼び出すには、Retail プロキシを生成する必要があります。 その後、プロキシを使用して、クライアントから新しい Retail Server API を呼び出すことができます。

    Retail プロキシの生成方法については、[Retail プロキシの生成](typescript-proxy-retail-pos.md) を参照してください。
