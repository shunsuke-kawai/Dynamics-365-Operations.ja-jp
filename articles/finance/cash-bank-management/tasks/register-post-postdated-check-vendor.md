---
title: 仕入先の先日付小切手の登録および転記
description: 仕訳伝票を使用して、ベンダーに小切手を発行する前に先日付小切手の詳細を登録できます。
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fe29e106055177dbd12c39ee3fc9de609059f73b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178673"
---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a>仕入先の先日付小切手の登録および転記

[!include [task guide banner](../../includes/task-guide-banner.md)]

仕訳伝票を使用して、ベンダーに小切手を発行する前に先日付小切手の詳細を登録できます。 先日付小切手を転記して財務トランザクションを生成することもできます。 仕入先からの先日付小切手を登録および転記する前に、次のタスクを完了します。 

[現金および銀行管理] ページで、先日付小切手を設定します。 



このタスク ガイドのロールは会計登録者です。 このタスクでは、USMF というデモ会社を使用します。

1. [買掛金勘定] > [支払] > [支払仕訳帳] の順に移動します。
2. [新規] をクリックします。
3. [名前] フィールドに、「VendaPay」と入力します。
4. [明細行] をクリックします。
5. [勘定] フィールドで、任意の値を指定します。
6. 一覧で、選択された行をマークします。
7. [借方] フィールドに数値を入力します。
8. [支払方法] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
    * 先日付小切手に対する支払方法を選択します。  
9. 一覧で、目的のレコードを見つけ、選択します。
10. 一覧で、選択された行のリンクをクリックします。
11. [先日付小切手] タブをクリックします。
12. [小切手番号] フィールドに値を入力します。
    * 先日付小切手番号を入力または変更します。  
13. [発行銀行名] フィールドに、値を入力します。
    * 発行銀行の銀行詳細を入力します。  
14. [一覧] をクリックします。
15. [転記] をクリックします。
16. ページを閉じます。
17. [先日付小切手] タブをクリックします。

