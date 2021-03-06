---
title: フッター モジュール
description: このトピックでは、フッター モジュール、および Dynamics 365 Commerce での作成方法について説明します。
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7c253cd9620180b09f2f5cae232e46d236deabdd
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697316"
---
# <a name="footer-module"></a>フッター モジュール  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

このトピックでは、フッター モジュール、および Microsoft Dynamics 365 Commerce での作成方法について説明します。

## <a name="overview"></a>概要

フッター モジュールは、ページ フッターに表示されるモジュールをホストするために使用される特別なコンテナーです。 たとえば、**お問い合わせ**や**店舗ポリシー** ページなど、サイト内のさまざまなページへのリンクを含めることができます。

## <a name="footer-module-properties"></a>フッター モジュール プロパティ 

ほとんどのコンテナーと同様に、フッター モジュールでは見出しと幅のプロパティがサポートされています。 また、複数のフッター カテゴリ モジュールの追加もサポートされています。 追加された各フッター カテゴリ モジュールは、フッター モジュールの列としてレンダリングされます。

## <a name="modules-available-in-a-footer-module"></a>フッター モジュールで使用できるモジュール

**フッター項目** – フッター項目モジュールには、見出し、画像、およびリンクを含めることができます。 見出しは、単独で、または画像およびリンクと組み合わせて使用できます。 フッター内のすべてのリンクは、テキストのみ (「お問い合わせ」や「プライバシー」リンクなど)、またはテキストと画像 (ソーシャル メディア リンクなど) の両方を持つようにコンフィギュレーションできます。

**トップに戻る** – トップに戻るモジュールは、ページの上部にすばやく移動するためのリンクを提供します。 行先が必要です。 既定値は # で、ユーザーをページの先頭に移動します。

## <a name="author-a-footer-module"></a>フッター モジュールの作成

1. ナビゲーション ウィンドウで、**フラグメント**を選択し、**新しいページ フラグメント**を選択します。
1. **新しいページ フラグメント** ダイアログ ボックスで、フッター モジュールを選択し、ページ フラグメントの名前を入力して、**OK** を選択します。
1. 左側のアウトライン ツリーで、フッター モジュールの省略記号ボタン (**...**) を選択してから、**モジュールの追加**を選択します。
1. **モジュールの追加**ダイアログ ボックスで、フッター カテゴリ モジュールを選択してから、**OK** を選択します。
1. アウトライン ツリーで、フッター カテゴリ モジュールの省略記号ボタン (...) を選択してから、**モジュールの追加**を選択します。
1. **モジュールの追加**ダイアログ ボックスで、フッター項目モジュールを選択してから、**OK** を選択します。
1. アウトライン ツリーで、フッター項目モジュールを選択します。 その後、右側のプロパティ ウィンドウで、必要に応じて見出し、リンクとリンク テキスト、および画像をコンフィギュレーションします。
1. フッター項目をさらに追加する場合は、ステップ 5 から 7 を繰り返します。
1. フッターに「トップに戻る」リンクを追加するには、フッター カテゴリ モジュールの省略記号ボタン (...) を選択してから、**モジュールの追加**を選択します。
1. **モジュールの追加**ダイアログ ボックスで、トップに戻るモジュールを選択してから、**OK** を選択します。
1. アウトライン ツリーで、トップに戻るモジュールを選択します。 その後、右側のプロパティ ウィンドウで、トップに戻るモジュールを必要に応じてコンフィギュレーションします。
1. ページ フラグメントを保存し、チェック イン後に公開します。

サイトに対して作成されたすべてのページ テンプレートで、次の手順を実行します。

1. 既定ページの**メイン** スロットのフッターモジュールに、作成したフッター フラグメントを追加します。
1. テンプレートを保存し、チェック イン後に発行します。

ページ テンプレートにページ フラグメントを追加することにより、フッターがすべてのページにレンダリングされることを保証できます。

## <a name="additional-resources"></a>追加リソース

[スタート キットの概要](starter-kit-overview.md)

[コンテナー モジュール](add-container-module.md)

[購入ボックス モジュール](add-buy-box.md)

[カート モジュール](add-cart-module.md)

[チェックアウト モジュール](add-checkout-module.md)

[注文確認モジュール](order-confirmation-module.md)

[ヘッダー モジュール](author-header-module.md)

[フッター モジュール](author-footer-module.md)
