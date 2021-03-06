---
title: 複数のアプリケーション テーブルからデータを取得するには、ER モデル マッピングで結合データ ソースを使用します。
description: このトピックでは、電子申告 (ER) で結合タイプのデータ ソースを使用する方法について説明します。
author: NickSelin
manager: AnnBe
ms.date: 10/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.openlocfilehash: 224acc19ee5dda430cd9471aa50e9d870a4f8c60
ms.sourcegitcommit: 564aa8eec89defdbe2abaf38d0ebc4cca3e28109
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "2667957"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>電子申告 (ER) モデル マッピングで複数のアプリケーション テーブルからデータを取得するには、結合データ ソースを使用します。

[!include[banner](../includes/banner.md)]

電子申告 (ER) モデル マッピングまたはフォーマットを構成する際、[追加](#review)することができるのは、**結合**タイプに必要なデータ ソースです。 デザイン時に、**結合**データ ソースは、それぞれレコードの一覧を返す複数のデータ ソースのセットとして構成されます。 最初のデータ ソースを除くすべてのソースについて、現在のデータ ソースと以前のデータ ソースのレコードを結合するために必要な条件を定義する必要があります。 実行時に、**結合**タイプの構成済みデータ ソースは、入れ子になったデータ ソースのレコードからフィールドを含むレコードの単一の結合リストを[返します](#executeERformat)。

次のタイプの結合が現在サポートされています:

- LEFT OUTER JOIN:
    - 最初 (左端) のデータ ソースのレコードをすべて結合してから、設定された条件に従って、2 番目 (右端) のデータ ソースのレコードに一致するものをすべて結合します。
- RIGHT INNER JOIN:
    - 設定された条件に従って、互いに一致する最初 (左端) のデータ ソースのレコードのみ、および 2 番目 (右端) のデータ ソースのみを結合します。

構成済み**結合**データ ソースでは、すべてのデータ ソースが**テーブル レコード**タイプの場合は、結合データ ソースの実行は、単一の SQL ステートメントを使用して[データベース レベルで実行](#analyze) できます。 これにより、データベース呼び出しの数が減り、モデル マッピングのパフォーマンスが向上します。 それ以外の場合、**結合データ**ソースはメモリ内で実行されます。

> [!NOTE]
> 結合タイプのデータ ソースで、レコードを結合するための条件を指定する ER 式で **VALUEIN** 関数を使用することは、まだサポートされていません。 この関数の詳細については、[電子申告のフォーミュラ デザイナー](general-electronic-reporting-formula-designer.md) を参照してください。

この機能の詳細を知るには、このトピックの例を実行します。

## <a name="example-use-join-data-sources-in-er-model-mappings"></a>例: ER モデル マッピングで結合データ ソースを使用する

次の手順では、システム管理者または電子申告開発者が、データ アクセスのパフォーマンスを向上させるために、**結合**タイプのデータ ソースを使用して、一度に複数のアプリケーション テーブルからデータを取得するように、電子申告 (ER) モデル マッピングを構成する方法について説明します。 これらの手順は、Dynamics 365 Finance または Regulatory Configuration Services (RCS) のどの会社向けにも実行できます。

### <a name="prerequisites"></a>必要条件

このトピックの例を実行するには、これらの手順を実行するために使用されているサービスに応じて、次のいずれかの方法にアクセスできる必要があります。

**次のいずれかのロールに対応する財務にアクセスします。**

- 電子申告開発者
- 電子申告機能コンサルタント
- システム管理者

**次のいずれかのロールに対応する RCS にアクセスします。**

- 電子申告開発者
- 電子申告機能コンサルタント
- システム管理者

また、まず[コンフィギュレーション プロバイダーを作成し、それを有効としてマークする](tasks/er-configuration-provider-mark-it-active-2016-11.md) にある手順を完了する必要もあります。

事前に [Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/?linkid=000000) からダウンロードして、次のサンプル ER 構成ファイルをローカルに保存しておく必要があります。

| **コンテンツの説明**  | **ファイル名**   |
|--------------------------|-----------------|
| データ ソースとして使用される、サンプル **ER データ モデル**構成ファイルの例を次に示します。| [結合データ ソース version.1.xml を知るためのモデル](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| ER データ モデルを実行する、サンプル **ER モデル マッピング**構成ファイルの例を次に示します。 | [結合データ ソース version.1.xml を知るためのマッピング](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| サンプル **ER フォーマット**構成ファイル。 このファイルでは、例として ER フォーマット コンポーネントを設定するデータについて説明します。 | [結合データ ソース version.1.xml を知るためのフォーマット](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

### <a name="activate-a-configurations-provider"></a>コンフィギュレーション プロバイダーの有効化

1. Web ブラウザーの最初のセッションで、Finance または RCS にアクセスします。
2. **組織管理  \> ワークスペース \> 電子申告** の順に移動します。
3. **ローカライズのコンフィギュレーション**ページの**コンフィギュレーション プロバイダー**セクションで、Litware, Inc. (http://www.litware.com) サンプル会社のコンフィギュレーション プロバイダーが一覧に表示されていること、および**有効**とマークされていることを確認します。 このコンフィギュレーション プロバイダーが表示されない場合は、[コンフィギュレーション プロバイダーの作成および有効なプロバイダーとしてのマーク付け](tasks/er-configuration-provider-mark-it-active-2016-11.md)手順のステップに従います。

    ![電子申告ワークスペース](./media/GER-JoinDS-ActiveProvider.PNG)

### <a name="import-sample-er-configuration-files"></a>サンプル ER 構成ファイルのインポート

1. **コンフィギュレーションをレポートする**を選択します。
2. ER データ モデルの構成ファイルをインポートします。
    1. **交換**を選択します。
    2. **XML ファイルから読み込む**を選択します。
    3. **参照**を選択して、**結合データ ソース version.1.1.xml を知るためのモデル**ファイルを見つけます。
    4. **OK** を選択します。
3. ER モデル マッピングの構成ファイルをインポートします。
    1. **交換**を選択します。
    2. **XML ファイルから読み込む**を選択します。
    3. **参照**を選択して、**結合データ ソース version.1.1.xml を知るためのマッピング**ファイルを見つけます。
    4. **OK** を選択します。
4.  ER フォーマットの構成ファイルをインポートします。
    1. **交換**を選択します。
    2. **XML ファイルから読み込む**を選択します。
    3. **参照**を選択して、**結合データ ソース version.1.1.xml を知るためのフォーマット**ファイルを見つけます。
    4. **OK** を選択します。
5.  構成ツリーで、 **結合データ ソースを知るためのモデル**項目を、その他のモデル項目 (使用可能な場合) と同様に展開します。
6.  **バージョン** クイック タブのバージョン詳細に加えて、ツリー内の ER 構成の一覧を確認します。これらはサンプル レポートのデータ ソースとして使用されます。

    ![電子申告構成のページ](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>実行追跡オプションを有効にする
1.  **コンフィギュレーション** を選択します。
2.  **ユーザー パラメーター**を選択します。
3.  次のスクリーンショットのように、実行追跡パラメーターを設定します。

    ![電子申告のユーザー パラメーター ページ](./media/GER-JoinDS-Parameters.PNG)

    これらのパラメーターを有効にすると、インポートされた ER フォーマット ファイルを実行するたびに、実行追跡が生成されます。 生成された実行追跡の詳細を使用して、ER フォーマットと ER モデル マッピング コンポーネントの実行を分析できます。 ER 実行追跡機能についての詳細は、[ER 形式の実行を追跡してパフォーマンス問題をトラブルシュートする](trace-execution-er-troubleshoot-perf.md) ページを参照してください。

### <a name="review-er-model-mapping-part-1"></a>ER モデル マッピング (1) を確認する

ER モデル マッピング コンポーネントの設定を確認します。 このコンポーネントは、ER 構成のバージョンに関する情報、コンフィギュレーションの詳細、および**結合**タイプのデータ ソースを使用しないコンフィギュレーション プロバイダーの情報にアクセスできるように構成されています。

1.  **結合データ ソースを知るためのマッピング**コンフィギュレーションを選択します。
2.  **デザイナー**を選択して、マッピングの一覧を開きます。
3.  **デザイナー**を選択して、マッピングの詳細を確認します。 
4.  **詳細を表示**を選択します。
5.  構成ツリーで、**Set1** および **Set1.Details** データ モデル項目を展開します。

    1. **Details: Record list = Versions**のバインドは、**Set1.Details** 項目が**バージョン**データ ソースにバインドされていて、**ERSolutionVersionTable** テーブルのレコードを返すことを示します。 このテーブルの各レコードは、ER コンフィギュレーションの 1 つのバージョンを表します。 このテーブルの内容は、**バージョン**クイック タブ (**コンフィギュレーション**ページ) に表示されます。
    2. **ConfigurationVersion: String = @.PublicVersionNumber** のバインドは、各 ER コンフィギュレーションのバージョンの公開バージョンの値が **PublicVersionNumber** フィールド (**ERSolutionVersionTable** テーブルの) から取得され、**ConfigurationVersion** 項目に配置されることを意味します。
    3. **ConfigurationTitle: String = @.'>Relations'.Solution.Name** のバインドは、ER コンフィギュレーションの名前が**名前**フィールド (**ERSolutionTable** テーブルの) から取得され、多対一の関係 (**> 関係**、**ERSolutionVersionTable** および **ERSolutionTable** テーブル間) を使用して評価することを示します。 現在のアプリケーション インスタンスの ER コンフィギュレーション名は、**コンフィギュレーション**ページの構成ツリーに表示されます。
    4. **@.'>Relations'.Solution.'>Relations'.SolutionVendor.Name** のバインドは、現在のコンフィギュレーションを所有するコンフィギュレーション プロバイダーの名前が、**名前**フィールド (**ERVendorTable** テーブルの) から取得され、多対一の関係 (**ERSolutionTable** および **ERVendorTable** テーブル間) を使用することで評価することを意味します。 ER コンフィギュレーション名は、各コンフィギュレーションのページ ヘッダーの、**コンフィギュレーション**ページの構成ツリーに表示されます。 ER コンフィギュレーション プロバイダーの一覧全体は、**組織管理\>電子申告\>コンフィギュレーション プロバイダー**テーブルページにあります。

    ![ER モデル マッピング デザイナーのページ](./media/GER-JoinDS-Set1Review.PNG)

6.  構成ツリーで、**Set1.Summary** データ モデル項目を展開します。

    1. **VersionsNumber: Integer = VersionsSummary.aggregated.VersionsNumber** は、**Set1.Summary.VersionsNumber** 項目が **VersionsNumber** アグリゲーション フィールドにバインドされていることを示します。これは **VersionsSummary** データ ソースの、**GroupBy** タイプで、**ERSolutionVersionTable** テーブルのレコード数を**バージョン**データ ソース経由で返すように構成されています。

    ![GROUPBY データ ソース パラメーター ページ](./media/GER-JoinDS-Set1GroupByReview.PNG)

7.  ページを閉じます。

### <a name="review"></a> ER モデル マッピング (2) を確認する

ER モデル マッピング コンポーネントの設定を確認します。 このコンポーネントは、ER 構成のバージョンに関する情報、コンフィギュレーションの詳細、および**結合**タイプのデータ ソースを使用するコンフィギュレーション プロバイダーの情報にアクセスできるように構成されています。

1.  構成ツリーで、**Set2** および **Set2.Details** データ モデル項目を展開します。 **Details: Record list = Details**のバインドは、**Set2.Details** 項目が**詳細**データ ソースにバインドされていることを示します。詳細データ ソースは**結合**タイプのデータ ソースとして構成されています。

    ![ER モデル マッピング デザイナーのページ](./media/GER-JoinDS-Set2Review.PNG)

    **結合**データ ソースは、**Functions\Join** データ ソースを選択することによって追加できます。

    ![ER モデル マッピング デザイナーのページ](./media/GER-JoinDS-AddJoinDS.PNG)

2.  **詳細**データ ソースを選択します。
3.  **編集**を、**データ ソース**ウィンドウで選択します。
4.  **結合を編集**を選択します。
5.  **詳細を表示**を選択します。

    ![結合データ ソース パラメーター ページ](./media/GER-JoinDS-JoinDSEditor.PNG)

    このページは、**結合タイプ**の必要なデータ ソースをデザインするために使用されます。 このデータ ソースは、実行時に、**結合リスト**グリッドのデータ ソースから 1 つの結合されたレコード リストを作成します。 レコードの結合は、グリッドで最初となる **ConfigurationProviders** データ ソースから始まります (**タイプ**列はそのために空白)。 したがって、他のすべてのデータ ソースのレコードは、このグリッドでの順序に基づいて、親データ ソースのレコードに結合されます。 すべての結合データ ソースは、ターゲット データ ソース下で入れ子になったデータ ソースとして構成される必要があります (**1Versions** データ ソースは **1Configurations** 下で、**1Configurations** データ ソースは、**ConfigurationProviders** 下で入れ子になっています)。 構成された各データ ソースには、結合の条件が含まれている必要があります。 この特定の**結合**データ ソースでは、次の結合が定義されています:

    - **ConfigurationProviders** データ ソース (**ERVendorTable** テーブル参照) の各レコードは、**1Configurations**(**ERSolutionTable** テーブル参照) のみに結合されます。**SolutionVendor** および **RecId** フィールドの値は同じになります。 **内部結合**タイプは、この結合に対して使用され、次の条件では、レコードの一致にも使用されます。 

    FILTER (Configurations, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - **1Configurations** データ ソース (**ERSolutionTable** テーブル参照) の各レコードは、**1Versions**(**ERSolutionVersionTable** テーブル参照) のみに結合されます。**Solution** および **RecId** フィールドの値は同じになります。 **内部結合**タイプは、この結合に対して使用され、次の条件では、レコードの一致にも使用されます。

    FILTER (ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.'1Configurations'.RecId)

    - **実行**オプションは、**クエリ**として構成され、この結合データ ソースは、SQL の直接呼び出しとしてデータベース レベルで実行されることを意味します。

    アプリケーション テーブルを表すデータ ソースのレコードを結合するには、これらのテーブル間で既存の AOT リレーションについて記述しているもの以外のフィールドのペアを使用して、結合条件を指定することができます。 この結合のタイプは、データベース レベルで実行するように構成することもできます。

6.  ページを閉じます。
7.  **キャンセル**を選択します。
8.  構成ツリーで、**Set2.Summary** データ モデル項目を展開します:

    - **VersionsNumber: Integer = DetailsSummary.aggregated.VersionsNumber** は、**Set2.Summary.VersionsNumber** 項目が **VersionsNumber** アグリゲーション フィールドにバインドされていることを示します。これは **DetailsSummary** データ ソース (**GroupBy** タイプ) で、**詳細**データ ソース (**結合**タイプ) の結合されたレコードを返すように構成されています。
    - **実行**ロケーション オプションは、**クエリ**として構成され、この **GroupBy** データ ソースは、SQL の直接呼び出しとしてデータベース レベルで実行されることを意味します。 これが可能なのは、**詳細** (**結合**タイプ) の基本データソースが、データベースレベルで実行されるように構成されているためです。

    ![GROUPBY データ ソース パラメーター ページ](./media/GER-JoinDS-Set2GroupByReview.PNG)

9.  ページを閉じます。
10. **キャンセル**を選択します。

### <a name="executeERformat"></a>ER 形式の実行

1.  最初のセッションと同じ資格情報と会社を使用して、Webブラウザーの 2 番目のセッションで Finance または RCS にアクセスします。
2.  **組織管理 \> 電子申告 \> コンフィギュレーション**の順に移動します。
3.  **結合データ ソースを知るためのモデル**構成を展開します。
4.  **結合データ ソースを知るための形式**構成を選択します。
5.  **デザイナー** をクリックします。
6.  **詳細を表示**を選択します。
7.  **マッピング**を選択します。
8.  **展開 / 折りたたみ**を選択します。

    この形式は、ER コンフィギュレーション のバージョン (**バージョン**順序) ごとに、生成されたテキスト ファイルに新しい行を挿入するように設計されています。 生成される各行には、現在のコンフィギュレーションを所有するコンフィギュレーション プロバイダー名、コンフィギュレーション名、およびセミコロン記号で区切られたコンフィギュレーション バージョンが含まれます。 生成されるファイルの最終行には、ER コンフィギュレーションの検出されたバージョン数が含まれます (**集計**シーケンス) 。

    ![ER 形式デザイナーのページ](./media/GER-JoinDS-FormatReview.PNG)

    **データ**および**集計**データ ソースは、生成されたファイルにコンフィギュレーション バージョンの詳細を設定するために使用されます:

    - **Set1** データ モデルの情報は、ER 形式実行時に、ユーザー ダイアログ ページで**いいえ**を**セレクター**データ ソースに対して選択する際に使用されます。
    - **Set2** データ モデルの情報は、ユーザー ダイアログ ページで**はい**を**セレクター**データ ソースに対して選択する際に使用されます。

    ![ER 形式デザイナーのページ](./media/GER-JoinDS-FormatMappingReview.PNG)

9.  **実行**を選択します。
10. ダイアログ ページで、**いいえ**を**結合データ ソースの使用**フィールドで選択します。
11. **OK** を選択します。
12. 生成されたファイルを確認します。

    ![ER ユーザー ダイアログ ページ](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>ER 形式実行追跡の分析

1.  Finance または RCS の最初のセッションで、**デザイナー**を選択します。
2.  **パフォーマンスの追跡**を選択します。
3.  **パフォーマンスの追跡**グリッドで、現在のモデル マッピング コンポーネントを使用した ER 形式の、最新の実行追跡の最上位レコードを選択します。
4.  **OK** を選択します。

    実行の統計は、アプリケーション テーブルへの重複した呼び出しについて通知します。

    - **ERSolutionTable** は、**ERSolutionVersionTable** テーブルに含まれるコンフィギュレーション バージョン レコードの数だけ呼び出されますが、そのような呼び出しの数はパフォーマンス向上のため、所用時間が減ることがあります。
    - **ERVendorTable** は、**ERSolutionVersionTable** テーブルで検出されるコンフィギュレーション バージョン レコードの 2 倍呼び出されますが、そのような呼び出しの数も減ることがあります。

    ![ER モデル マッピング デザイナーのページ](./media/GER-JoinDS-Set1Run2.PNG)

5.  ページを閉じます。

### <a name="execute-er-format"></a>ER 形式の実行

1.  Finance または RCS の 2 番目のセッションを使用して、Web ブラウザー タブに切り替えます。
2.  **実行**を選択します。
3.  ダイアログ ページで、**はい**を**結合データ ソースの使用**フィールドで選択します。
4.  **OK** を選択します。
5.  生成されたファイルを確認します。

    ![ER ユーザー ダイアログ ページ](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze"></a> ER 形式実行追跡の分析

1.  Finance または RCS の最初のセッションで、**デザイナー**を選択します。
2.  **パフォーマンスの追跡**を選択します。
3.  **パフォーマンスの追跡**グリッドで、現在のモデル マッピング コンポーネントを使用した ER 形式の、最新の実行追跡を表す最上位レコードを選択します。
4.  **OK** を選択します。

    実行の統計は、次の情報を通知します:

    - 必須フィールドにアクセスする、**ERVendorTable**、**ERSolutionTable**、および **ERSolutionVersionTable** テーブルからレコードを取得するため、アプリケーション データベースが 1 回呼び出されます。

    ![ER モデル マッピング デザイナーのページ](./media/GER-JoinDS-Set2Run2.PNG)

    - **詳細**データ ソースで構成された結合を使用して、コンフィギュレーション バージョン数を計算するのに、アプリケーション データベースが 1 回呼び出されます。

    ![ER モデル マッピング デザイナーのページ](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="additional-resources"></a>追加リソース

[電子申告のフォーミュラ デザイナー](general-electronic-reporting-formula-designer.md)

[パフォーマンス上の問題をトラブルシューティングするため ER 形式の追跡実行](trace-execution-er-troubleshoot-perf.md)

