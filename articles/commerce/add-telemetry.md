---
title: サイト ページにスクリプト コードを追加してテレメトリをサポートする
description: このトピックでは、クライアント側のテレメトリの収集をサポートするクライアント側のスクリプト コードをサイト ページに追加する方法について説明します。
author: bicyclingfool
manager: annbe
ms.date: 10/31/2019
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a5f82426d87cd2e0faa0195a841899bb03f9df08
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697339"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>サイト ページにスクリプト コードを追加してテレメトリをサポートする

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

このトピックでは、クライアント側のテレメトリの収集をサポートするクライアント側のスクリプト コードをサイト ページに追加する方法について説明します。

## <a name="overview"></a>概要

Web Analytics は、顧客がサイトとどのように対話するかを理解し、最大のコンバージョンのためにエクスペリエンスを最適化するのに役立つ決定を下したい場合に、重要なツールとなります。 Google Analytics、Clicky、Moz Analytics、KISSMetrics など、これらの目標を達成するために、多くの Web Analytics パッケージが用意されています。 ほとんどの Web Analytics パッケージでは、サイトのすべてのページの HTML の **\<head\>** 要素にクライアント側のスクリプト コードを追加する必要があります。

> [!NOTE]
> このトピックの手順は、Microsoft Dynamics 365 Commerce がネイティブに提供していない他のカスタム クライアント側機能にも適用されます。

## <a name="create-a-reusable-fragment-for-your-script-code"></a>スクリプ トコードに再利用可能なフラグメントを作成する

スクリプト コードのフラグメントを作成すると、サイトのすべてのページで再利用できるようになります。

1. **フラグメント \> 新しいページ フラグメント**に移動します。
2. **外部スクリプト**を選択し、フラグメントの名前を入力して、**OK** を選択します。
3. フラグメント階層で、作成したフラグメントの**スクリプトの挿入**モジュールの子を選択します。
4. 右側のプロパティ ウィンドウで、クライアント側のスクリプトを追加し、必要に応じてその他のコンフィギュレーション オプションを設定します。

## <a name="add-the-fragment-to-templates"></a>フラグメントのテンプレートへの追加

1. **テンプレート**に移動して、スクリプト コードを追加するページのテンプレートを開きます。
2. 左ウィンドウでテンプレート階層を展開し、**HTML ヘッド** スロットを表示します。
3. **HTML Head** スロットの省略ボタン (**...**) を選択し、**フラグメントの追加**を選択します。
4. スクリプト コードに対して作成したフラグメントを選択します。
5. テンプレートを保存し、チェックインします。

> [!NOTE]
> 作業が完了したら、フラグメントとマスタ テンプレートを公開する必要があります。 

## <a name="additional-resources"></a>追加リソース

[ロゴの追加](add-logo.md)

[サイト テーマの選択](select-site-theme.md)

[お気に入りの追加](add-favicon.md)

[ようこそメッセージの追加](add-welcome-message.md)

[著作権に関する注意事項の追加](add-copyright-notice.md)

[サイトに言語を追加する](add-languages-to-site.md)

