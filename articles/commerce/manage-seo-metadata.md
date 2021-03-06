---
title: SEO メタデータの管理
description: このトピックでは、Microsoft Dynamics 365 Commerce の検索エンジン最適化 (SEO) メタデータを管理する方法について説明します。
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b69d9d2769023967e2b94fef1b8fcf6b5b3357c5
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698352"
---
# <a name="manage-seo-metadata"></a>SEO メタデータの管理

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

このトピックでは、Microsoft Dynamics 365 Commerce の検索エンジン最適化 (SEO) メタデータを管理する方法について説明します。

## <a name="overview"></a>概要

サイトの SEO メタデータは、サイト マップとページ メタデータを使用して管理できます。
    
## <a name="site-maps"></a>サイト マップ

サイト マップは、Web サイト上のページにて、XML 形式の機械可読リストです。 検索エンジンによって使用されることを目的としており、サイトからの優れた検索結果を提供することができます。 サイトマップは、手動により検索エンジンで取得するか、または robots.txt ファイルに発行されます。

Dynamics 365 Commerce はサイトマップの自動生成をサポートします。 ページが発行および未発行の場合は、サイト マップが自動的に更新されます。

### <a name="turn-on-site-map-generation"></a>サイト マップの生成を有効化

1. オーサリング ツールにログインします。
1. **サイト**で、**Fabrikam** (またはサイトの名前) を選択します。
1. 左のナビゲーション ウィンドウで、**サイト管理**を選択します。
1. **サイト マップの有効化**オプションがオンになっていることを確認してください。

## <a name="page-metadata"></a>メタデータのページ

Dynamics 365 Commerce では、個々のページの SEO メタデータを管理できます。 ページ コンテナーの **SEO プロパティ**セクションで、この情報を表示および変更できます。 次の SEO メタデータのプロパティがサポートされています。

- 肩書き
- 説明
- SEO キーワード
- Aria ラベル
- noindex
- nofollow
- noarchive
- nocache
- noOpenDirectoryProject
- nosnippet
- noImageIndex
- unavailableAfter

### <a name="modify-page-metadata"></a>ページ メタデータの変更

ページ メタデータを変更するには、次の手順に従います。

1. **サイト**で、**Fabrikam** (またはサイトの名前) を選択します。
1. 左のナビゲーション ウィンドウで、**ページ**を選択します。
1. ホーム ページを選択して、ページ エディターで開きます。
1. アクション ウィンドウで、**チェック アウト**を選択します。
1. 右側のプロパティ ウィンドウで、**既定のメタタグ**を展開します。
1. 新しいメタタグを追加するには、**追加**を選択して、フィールドにタグを入力します。

    既存のメタタグを削除するには、その右側にあるごみ箱記号を選択します。

1. **保存**を選択してから、**チェックイン**を選択します。
1. **コメント**フィールドで、**メタタグの更新**と入力し、**OK** を選択します。
1. **プレビュー**を選択して、ページをプレビューします。 完了したら、プレビュー タブを閉じて、作成ツールに戻ります。
1. **公開**を選択します。

## <a name="additional-resources"></a>追加リソース

[既存のサイト ページの変更](modify-existing-page.md)

[新しいサイト ページの追加](add-new-page.md)

[ページ レイアウトの選択](select-page-layouts.md)

[ページの保存、プレビュー、および公開](save-preview-publish-page.md)

[製品ページの拡充](enrich-product-page.md)

[カテゴリ ランディング ページの拡充](enrich-category-page.md)

