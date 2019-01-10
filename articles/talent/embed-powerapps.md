---
title: "Core HR への PowerApps アプリの埋め込み"
description: "このトピックでは、PowerApps メニュー項目がシステム管理モジュールから消えてしまう問題を解決する方法について説明します。"
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 197b553f0b202ee29ad42274e2c0e03446ec782c
ms.contentlocale: ja-jp
ms.lasthandoff: 12/04/2018

---

# <a name="embed-powerapps-apps-in-core-hr"></a>Core HR への PowerApps アプリの埋め込み

[!include [banner](includes/banner.md)]

**払出**

**PowerApps** メニュー項目が**システム管理**モジュールから消えました。

**原因**

ユーザー インターフェイス (UI) のデザインが変更され、Microsoft PowerApps が標準の個人用設定モデルに含まれるようになりました。

**解像度**

PowerApps アプリが埋め込まれる方法が変更されました。 PowerApps アプリは個人用設定モデルによって追加されます。 PowerApps アプリは、Microsoft Dynamics 365 for Talent のほとんどすべてのページに追加できます。

PowerApps アプリを Talent に埋め込む方法の詳細については、[PowerApps アプリの埋め込み](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps) を参照してください。

変更前にアプリを埋め込んだ PowerApps の顧客は、新しいモデルにアップグレードする必要があります。

**PowerApps** ボタンは、Talent のほとんどすべてのページの右上隅にあります。 このボタンを使用して、PowerApps アプリを挿入することができます。

次に例を示します。

1. **人事管理\>リンク\>作業者\>従業員**に移動します。
2. **PowerApps** ボタンを選択してから、**PowerApp の挿入**を選択します。

    ![PowerApps ボタン](media/png.png)

3. **PowerApp の挿入**ダイアログ ボックスのフィールドを完了します。

    ![PowerApp の挿入ダイアログ ボックス](media/insert-powerapp.png)

または、次の手順に従います。

1. ページのアクション ウィンドウの**オプション**タブ上の**個人用設定**グループで、**このフォームのパーソナライズ**を選択します。

    ![オプション タブのグループをパーソナライズする](media/options.png)

    個人用設定ツール バーが表示されます。

2. ツール バーで、**挿入\>PowerApp** を選択します。

    ![個人用設定ツール バーを使用して PowerApps アプリを挿入する](media/powerapp-bar.png)
