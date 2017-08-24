--- 
title: "督促状順序の作成"
description: "このタスク ガイドを使用し、督促状順序を作成します。"
author: mikefalkner
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 3b050d47910c146b9691e7aae5b4a1a847ce716e
ms.contentlocale: ja-jp
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-collection-letter-sequence"></a>督促状順序の作成

[!include[task guide banner](../../includes/task-guide-banner.md)]

このタスク ガイドを使用し、督促状順序を作成します。 このタスクでは、USMF というデモ会社を使用します。

1. [貸方転記および取立] > [設定] > [督促状の順序の設定] の順に移動します。
2. [新規] をクリックします。
3. [督促状順序] フィールドに、順序を表す順序 ID を入力します。 転記プロファイルを設定するときに使用されます。
4. [説明] フィールドに値を入力します。
    * 支払条件はオプションです。 値をここに入力した場合、督促状手数料の請求書は、顧客に保存されている支払条件ではなく、これらの支払条件を使用します。  
5. [督促状コード] フィールドで、送信したい最初の督促状のコードを選択します。
    * 最初の督促状は、請求書の期日、この行の [日] フィールドに支払い猶予期間として入力した値、この行で入力したその他の情報に従って作成されます。  
6. [説明] フィールドに値を入力します。
    * 手数料の通貨の既定値は、顧客通貨となります。 この通貨コードは、請求書通貨とは異なります。  
7. 順番で送信される次の督促状を追加するには [追加] をクリックします。
    * 多くの場合、最初の督促状は警告目的のみです。 必要に応じて手数料を追加できます。  
8. [督促状コード] フィールドで、順番で送信される次の督促状を選択します。
9. [説明] フィールドで値を入力します。
10. 主勘定のフィールドで、手数料に使用される収益勘定を選択します。
11. この督促状の転記時に請求される手数料を入力します。
12. [品目売上税グループ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
    * 費用に基づいて売上税を計算する必要がある場合、品目売上税グループを選択します。  
13. 一覧で、選択された行のリンクをクリックします。
14. 督促状を送信する前に必要な最小期限切れ残高を入力します。
15. 支払猶予日数を入力します。
    * これは、督促状が生成される期日から数えた日数です。 計算に使用される期日は、督促状順序における督促状の位置によって異なります:   ⦁    督促状 1 の支払猶予期間は請求書の期日に関連しています。  ⦁ 督促状 2 以降の支払猶予期間は、売掛金勘定パラメータのページの [督促状コードの更新] フィールドの選択によって、以前の督促状が転記又は印刷される日付と連動しています。  
16. 順番で送信される最後の督促状を追加するには [追加] をクリックします。
    * 督促状順序の督促状コードは 5 つまで追加できます。  
17. [督促状コード] フィールドで、順番で送信される次の督促状を選択します。
18. [説明] フィールドで値を入力します。
19. [主勘定] フィールドに、目的の値を指定します。
20. [手数料] フィールドに数値を入力します。
21. [品目売上税グループ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
22. 一覧で、選択された行のリンクをクリックします。
23. [最小期限切れ残高] フィールドに数値を入力します。
24. [日] フィールドに数値を入力します。
25. このチェック ボックスをオンにすると、顧客の追加配送と請求が停止されます。
    * 顧客勘定をブロック解除するには、[顧客] ページの請求と出荷の保留中フィールドで [いいえ] を選択してください。  
26. クイック タブの [注記] セクションを展開します。
27. 選択した督促状コードの督促状に表示されるテキストを入力します。
    * メモ ボックスの上部にある [翻訳] メニューを使用して、このテキストを複数の言語に変換できます。  

