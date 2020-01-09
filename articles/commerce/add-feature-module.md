---
title: 機能モジュール
description: このトピックでは、機能モジュールと、Microsoft Dynamics 365 Commerce のサイト ページにそれを追加する方法について説明します。
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785287"
---
# <a name="feature-module"></a>機能モジュール 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

このトピックでは、機能モジュールと、Microsoft Dynamics 365 Commerce のサイト ページにそれを追加する方法について説明します。

## <a name="overview"></a>概要

画像とテキストの組み合わせを通じて製品またはプロモーションをマーケティングするために、機能モジュールが使用されます。 たとえば、小売業者は、製品の詳細ページに機能モジュールを追加して製品の機能を強調表示することができます。

機能モジュールは、コンテンツ管理システム (CMS) からのデータによって駆動します。 ページでその他の任意のモジュールに依存しないスタンドアロン モジュールです。 機能モジュールは、小売業者がマーケティングまたは販売促進を行う (製品、販売、機能など) サイト ページに配置することができます。

## <a name="examples-of-feature-modules-in-e-commerce"></a>E コマースの機能モジュールの例

機能モジュールは、次のページで使用できます。

- 製品の詳細ページで、製品機能について紹介する
- ホーム ページで、製品を販売促進する
- カテゴリ ページで、製品のカテゴリを強調表示する

## <a name="feature-module-properties"></a>機能モジュール プロパティ

| プロパティ名     | 値 | 説明 |
|-------------------|--------|-------------|
| 画像             | イメージ ファイル | 画像を使用して製品またはプロモーションのマーケティングを行うことができます。 画像を画像ギャラリーにアップロードしたり、既存の画像を使用したりできます。 |
| ヘッダー           | ヘッダー テキストとヘッダー タグ (**H1**、**H2**、**H3**、**H4**、**H5**、または **H6**) | 各機能モジュールにヘッダーを付けることができます。 既定では、**H2** ヘッダー タグがヘッダーに使用されます。 ただし、アクセシビリティ要件を満たすようにタグを変更できます。 |
| 段落         | 段落のテキスト | 機能モジュールは、リッチ テキスト形式の段落テキストをサポートします。 太字、下線付き、斜体、およびハイパーリンクなど、基本的なリッチ テキスト機能がいくつかサポートされます。 これらの機能の一部は、モジュールに適用されるページ テーマによって上書きされる場合があります。 |
| リンク              | リンク テキスト、リンク URL、アクセス可能リッチ インターネット アプリケーション (ARIA) ラベル、および **新しいタブでリンクを開く** | 機能モジュールは、1 つ以上の "アクションの呼び出し" リンクをサポートします。 リンクを追加すると、リンク テキスト、URL、および ARIA ラベルが必要になります。 ARIA ラベルは、アクセシビリティ要件を満たしていることを説明する必要があります。 リンクをコンフィギュレーションして、新しいタブで開くことができます。 |
| 画像の配置   | **右**、**左**、**上**、または**下** | このプロパティは、テキストに対する画像の位置を定義します。 たとえば、**右**が選択されている場合、テキストの右側に画像が表示されます。 |
| 画像の列サイズ | **1** から **12** までの値 | このプロパティは、テキストに対する画像のサイズを定義します。 サイズは、ページの列の数として表されます。 1 ページに 12 列あります。 既定では、画像とテキストのサイズは等しくなります (各 6 列)。 ただし、サイズは必要に応じて調整できます。 |

## <a name="add-a-feature-module-to-a-new-page"></a>機能モジュールを新しいページに追加する 

新しいページに機能モジュールを追加して必要なプロパティを設定するには、次の手順を実行します。

1. **テンプレート**に移動して、**機能テンプレート**という名前のページ テンプレートを作成します。
1. 既定のページの**メイン** スロットで、機能モジュールを追加します。
1. テンプレートをチェックインし、公開します。
1. 作成した機能テンプレートを使用して、**機能ページ**という名前のページを作成します。
1. 既定のページの**メイン** スロットで、省略記号ボタン (**...**) を選択してから、**モジュールの追加**を選択します。
1. **モジュールの追加**ダイアログ ボックスの、**モジュールの選択**で、機能モジュールを選択し、**OK** を選択します。
1. 左側のアウトライン ツリーで、機能モジュールを選択します。
1. 右側のプロパティ ウィンドウで、**画像の追加**を選択します。 次に、既存の画像を選択するか、新しい画像をアップロードします。
1. **ヘッダー**を選択します。
1. **ヘッダー** ダイアログ ボックスで、ヘッダー テキストを追加し、ヘッダー レベルを選択してから、**OK** を選択します。
1. **リッチ テキスト**で、必要に応じてテキストを追加します。
1. **アクション リンクの追加**を選択します。
1. **アクション リンク** ダイアログ ボックスで、リンク テキスト、リンク URL、およびリンクの ARIA ラベルを追加し、**OK** を選択します。
1. ページを保存して、プレビューを変更します。
1. ページをチェックインしてから公開します。

## <a name="additional-resources"></a>追加リソース

[スタート キットの概要](starter-kit-overview.md)

[警告モジュール](add-alert.md)

[カルーセル モジュール](add-carousel.md)

[コンテンツ リッチ ブロック モジュール](add-content-rich-block.md)

[コンテンツ配置モジュール](add-content-placement-modules.md)

[ヒーロー モジュール](add-hero-module.md)

[ビデオ プレーヤー モジュール](add-video-player.md)