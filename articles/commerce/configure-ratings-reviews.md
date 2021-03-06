---
title: 評価とレビューのコンフィギュレーション
description: このトピックでは、Microsoft Dynamics 365 Commerce で顧客の評価とレビューを表示するように E コマース サイトを構成する方法について説明します。
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0612b32e7751b32ad851f627a53bce2ac491870f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770484"
---
# <a name="configure-ratings-and-reviews"></a>評価とレビューのコンフィギュレーション

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

このトピックでは、Microsoft Dynamics 365 Commerce で顧客の評価とレビューを表示するように E コマース サイトを構成する方法について説明します。

## <a name="overview"></a>概要

E コマース Web サイトの評価およびレビューでは、それらの製品に対する他の顧客の意見を示すことによって顧客が購入決定を行う前に製品について学ぶことができます。 E コマース Web サイトは、評価とレビューも製品に関する顧客フィードバックを収集するためのメカニズムです。 

評価は、製品リスト ページ、カテゴリ リスト ページ、検索結果ページ、およびその他のサイト ページに表示されます。 ヒストグラムと製品レビューの評価は、製品の詳細ページ (PDP) に表示されます。 **レビューを書く**ボタンで、顧客は製品の評価およびレビューを送信できます。

## <a name="ratings-and-reviews-modules-on-pdps"></a>PDP 上の評価とレビュー モジュール 

3 つのモジュールは、PDP 上の評価とレビューの概要を表示します。

- レビューの書き込みモジュール
- 製品レビュー リスト モジュール
- 評価ヒストグラム モジュール
 
次の図は、PDP の評価とレビュー モジュールがどのようなものかを示しています。

![PDP 上の評価とレビュー モジュール](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> E コマース サイト上の複数の PDP 間で評価とレビュー モジュールのコンフィグレーションを共有できるように、PDP テンプレートとレイアウトを最適化する方法の詳細は、[テンプレートとレイアウトの概要](templates-layouts-overview.md) を参照してください。

次の図は、**モジュールの追加**ダイアログ ボックスがどのように Dynamics 365 Commerce の評価とレビュー モジュールで表示されるかを示しています。

![モジュールの追加ダイアログ ボックス](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>レビューの書き込みモジュール

レビューの書き込みモジュールには、ユーザーがサインインし、評価を割り当て、製品のレビューを書くことのできる**レビューを書く**ボタンが含まれています。 このモジュールで、ユーザーが以前に送信した評価またはレビューを編集することもできます。 このモジュールは通常、PDP 上の評価ヒストグラムおよび製品レビュー リスト モジュールの上に表示されます。

次の図は、顧客が**レビューを書く**を選択したときに表示される**レビューを書く**ダイアログ ボックスを示しています。 顧客は、このダイアログ ボックスを使用して評価およびレビューを送信できます。

![レビューを書くダイアログ ボックス](media/rnr-eCommerce-write-review-module.png)

次の表は、オーサリング ツールでコンフィギュレーションする必要がある レビューの書き込みモジュール プロパティを示します。

| プロパティ名 | 金額        | プロパティの説明                 |
|---------------|--------------|--------------------------------------|
| 氏名          | レビューの書き込み | レビューの書き込みモジュールの名前。 |

### <a name="ratings-histogram-module"></a>評価ヒストグラム モジュール

評価ヒストグラム モジュールは、評価ヒストグラムを表示します。 このモジュールは通常、レビューの書き込みモジュールと PDP の製品レビュー リスト モジュールの間に表示されます。

評価ヒストグラム モジュールには、コンフィギュレーションは必要ありません。 PDP テンプレートにモジュールを追加するだけです。 

次の図は、評価とレビュー モジュールが Dynamics 365 Commerce PDP 上で表示されるようコンフィギュレーションされているときに、どのような PDP テンプレートが表示されるかを示しています。

![PDP 上で表示されるよう評価とレビューがコンフィギュレーションされている場合の PDP テンプレート](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>製品レビュー リスト モジュール

製品レビュー リスト モジュールは、製品レビューのリストと共に並べ替え、フィルタ、およびページネーション オプションを表示します。 このモジュールは通常、PDP の評価ヒストグラム モジュールの後に表示されます。

次の表は、オーサリング ツールでコンフィギュレーションする必要がある 製品レビュー リスト モジュール プロパティを示しています。

| プロパティ名              | 金額 | プロパティの説明 |
|----------------------------|-------| ---------------------|
| 各ページに表示されるレビュー | 10    | PDP で一度に表示されるレビューの数 ユーザーがレビュー ページを移動できるように、**次へ**と**前へ**ボタンが含まれています。 |

#### <a name="ratings-histogram--summary-view"></a>評価ヒストグラム - 概要ビュー

製品レビュー リスト モジュールには、評価ヒストグラム モジュールを追加できるスロットが含まれています。 次の図は、Dynamics 365 Commerce の製品 レビュー リスト モジュールに評価ヒストグラム モジュールを追加する方法を示しています。

![製品レビュー リスト モジュールにおける評価ヒストグラム モジュールの追加](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>評価とレビューを表示するようサイトをコンフィギュレーションする

テナント ID、レビュー テキストの長さ、レビュー タイトルの長さなどの評価とレビューのコンフィギュレーション値は、サイト レベルでコンフィギュレーションされています。 

評価とレビューを表示するサイトをコンフィギュレーションするには、次の手順を実行します。 

1. **ホーム \> サイト**に移動します。
1. サイトの名前を選択します。 
1. **サイト管理 \> 拡張性**に移動します。 
1. **レビュー テキストの最大長**フィールドに、レビュー テキストに設定できる最大文字数を入力します (たとえば **1000**)。 
1. **レビュー タイトルの最大長**フィールドに、レビュー タイトルに設定できる最大文字数を入力します (たとえば、**55**)。 
1. **保存と公開**を選択します。 

次の図は、このコンフィグレーションが Dynamics 365 Commerce でどのように表示されるかを示しています。

![評価とレビューを表示するようサイトをコンフィギュレーションする](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>製品評価を PDP のレビュー セクションにリンクする

製品評価は、PDP 上部にある製品タイトルの下に表示されます。 製品評価は、同じ PDP の**レビュー** セクションにリンクされるようにコンフィギュレーションできます。 

製品評価を PDP の**レビュー**セクションにリンクするには、次の手順を実行します。

1. PDP テンプレートを開きます。 
1. **購入ボックス コンテナー モジュールの設定**に移動します。
1. **購入ボックス**の**製品評価**を選択し、**クリックして完全にレビュー モジュールにリンクする**チェック ボックスをオンにします。

次の図は、このコンフィグレーションが Dynamics 365 Commerce でどのように表示されるかを示しています。

![製品評価を PDP のレビュー セクションにリンクする](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>プライバシーおよびポリシー ページへのリンクをコンフィギュレーションします。

プライバシーおよびポリシー ページへのリンクをコンフィギュレーションするには次の手順を実行します。

1. **ホーム \> サイト**に移動します。
1. サイトの名前を選択します。 
1. **サイト管理 \> 拡張性**に移動します
1. **ルート** タブの**RNR プライバシーおよびポリシー**で**リンクの追加**を選択します。 リンクが既に入力されており、置き換えたい場合は、リンクを選択します。 
1. **リンクの追加**ダイアログ ボックスで、プライバシーおよびポリシー ページのリンクを選択し、**OK** を選択します。 
1. **保存と公開**を選択します。 

次の図は、このコンフィグレーションが Dynamics 365 Commerce でどのように表示されるかを示しています。

![プライバシーおよびポリシー ページへのリンクをコンフィギュレーションします。](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a>追加リソース

[評価とレビューの概要](ratings-reviews-overview.md)

[評価とレビューを使用するためのオプト イン](opt-in-ratings-reviews.md)

[評価とレビューの管理](manage-reviews.md)

[Dynamics 365 Retail の商品評価の同期](sync-product-ratings.md)
