---
title: 電子申告 (ER) のモデル マッピング コンフィギュレーションの作成
description: 新しい電子申告 (ER) モデル マッピング コンフィギュレーションをデザインして、効率的な集計計算の組み込み ER 機能を使用するには、この手順を使用します。
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bcfc258e7fe364779fd77cc79413e8d5e871e214
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182695"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a>電子申告 (ER) のモデル マッピング コンフィギュレーションの作成

[!include [task guide banner](../../includes/task-guide-banner.md)]

新しい電子申告 (ER) モデル マッピング コンフィギュレーションをデザインして、効率的な集計計算の組み込み ER 機能を使用するには、この手順を使用します。 この手順では、サンプル会社 Litware、Inc. のコンフィギュレーションを作成します。 

この手順は、「システム管理者」または「電子レポート開発者」ロールが割り当てられている使用のために作成されています。

これらのステップは、任意のデータ セットを使用して完了することができます。 これらの手順を完了するには、まず手順の「コンフィギュレーションプロバイダーを作成し、それを有効としてマークする」にある手順を完了する必要があります。

1. [組織管理] > [ワークスペース] > [電子申告] の順に移動します。
    * サンプル会社 Litware, Inc. のコンフィギュレーション プロバイダーが使用可能であり、アクティブとしてマークされていることを確認します。 このコンフィギュレーション プロバイダーが表示されない場合は、「コンフィギュレーション プロバイダーの作成および有効なプロバイダーとしてのマーク付け」という手順のステップを完了する必要があります。  
2. [コンフィギュレーションをレポートする] をクリックします。
3. [フィルターの表示] をクリックします。
4. [名前] フィールドでは、フィルター値「イントラスタット」を入力し、フィールド オペレーター「次の値で始まる」を使用します。
    * 「イントラスタット」データ モデルのコンフィギュレーションを検索するには、このフィルターを適用します。 このモデルは、既にコンフィギュレーション ツリー内に存在します。 存在する場合は、下位の次のタスクをスキップします。   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a>Microsoft 提供のイントラスタットのモデル コンフィギュレーションを取得
1. ページを閉じます。
2. ページを閉じます。
3. [組織管理] > [ワークスペース] > [電子申告] の順に移動します。
4. 一覧で、目的のレコードを見つけ、選択します。
    * Microsoft プロバイダー タイルを選択します。  
5. [リポジトリ] をクリックします。
    * Microsoft プロバイダー タイルで [リポジトリ] をクリックします。  
6. [フィルターの表示] をクリックします。
7. [タイプ名] フィールドでは、フィルター値「リソース」を入力し、フィールド オペレーター「次の値を含む」を使用します。 
8. [開く] をクリックします。
9. ツリーで、[イントラスタット モデル] を選択します。
10. [インポート] をクリックします。
11. [はい] をクリックします。
    * 新しい ER 機能の使用方法を調べるために、使用するデータ モデルを含む ER モデルのコンフィギュレーションがインポートされます。  
12. ページを閉じます。
13. ページを閉じます。
14. [コンフィギュレーションをレポートする] をクリックします。

## <a name="add-a-new-model-mapping-configuration"></a>新しいモデル マッピング コンフィギュレーションを追加
1. ツリーで、[イントラスタット モデル] を選択します。
2. [コンフィギュレーションの作成] をクリックすると、ドロップ ダイアログが開きます。
3. [新規] フィールドで、「データ モデル イントラスタットに基づいたモデル マッピング」と入力します。
4. [名前] フィールドで、「イントラスタットのサンプル マッピング」と入力します。
    * イントラスタットのサンプル マッピング  
5. [コンフィギュレーションの作成] をクリックします。
