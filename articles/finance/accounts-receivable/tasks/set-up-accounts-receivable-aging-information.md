---
title: 売掛金勘定のエイジング情報の設定および生成
description: このガイドでは、エイジング期間の定義、顧客残高のエイジング、および [指定の期間に達している残高] リストと [回収] ページでの残高表示の設定方法を説明します。
author: mikefalkner
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77b5dd5feb16cc3bd6d64b6520cc47087c5b5224
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188651"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>売掛金勘定のエイジング情報の設定および生成

[!include [task guide banner](../../includes/task-guide-banner.md)]

このガイドでは、エイジング期間の定義、顧客残高のエイジング、および [指定の期間に達している残高] リストと [回収] ページでの残高表示の設定方法を説明します。 このレコードでは、USMF デモ会社を使用します。


## <a name="create-an-aging-period-definition"></a>エイジング期間の定義の作成
1. **ナビゲーション ウィンドウ > モジュール > 与信および回収 > 設定 > エイジング期間の定義**に移動します。
2. **新規** をクリックします。
3. **エイジング期間の定義**フィールドに、値を入力します。
4. **説明**フィールドで、値を入力します。
5. **下に追加**をクリックし、新しいエイジング期間を挿入します。
6. **期間**フィールドで、エイジング レポートに表示する説明を入力します。
7. **単位**フィールドに、数値を入力します。
8. **間隔**フィールドで、オプションを選択します。 元帳期間は、元帳のカレンダーの期間に一致します。 日付タイプの間隔は、日、週、月、四半期、年で定義します。 無制限の場合、最初または最後の期間かに応じて、直前の期間の前または後のすべてのトランザクションを選択します。  
9. **エイジング インジケーター** フィールドで、オプションを選択します。
10. グリッドの上部で期間を選択します。 最も古いエイジング期間の定義の説明を更新
11. **期間**フィールドで、エイジング期間の新しい説明を入力します。
12. ページを閉じます。

## <a name="age-the-balances"></a>残高のエイジング
1. **与信および回収 > 定期処理のタスク > 指定の期間に達している顧客残高**の順に移動します。
2. **エイジング期間の定義**フィールドで、作成したエイジング期間の定義を選択します。
    + 各エイジング期間の定義に対して、有効なスナップショットを 1 つずつ持たせることができます。  
    + すべての顧客が既定で処理されます。 この選択を使用すると、顧客の回収プールを 1 つ計算できます。  
    + エイジングに対して使用するトランザクションから日付を選択します。  
    + エイジングに対する「現在」の日付を選択します。 既定では今日ですが、このフィールドを [選択した日付] に変更すると、使用する日付を選べます。 バッチ処理のために、今日の日付を使用します。  
3. **会社**範囲を展開します。 スナップショットに含む会社を選択します。 現在の会社が既定で選択されます。
4. **OK** をクリックしてスナップショットを処理します。 これには時間がかかるため、スライダーが消えるまでしばらく待ち、メッセージ センターからのメッセージを確認します。

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>[指定の期間に達している残高] リストと [回収] ページに残高を表示します。
1. **与信および回収 > 回収 > 指定の期間に達している残高**の順に移動します。 リスト ページには、顧客の残高が表示されます。 エイジング アイコンが、最も古いトランザクションのエイジング期間を示します。  
2. 残高を持つ顧客を選択します。
3. エイジングした残高を表示するには、**エイジング情報**ボックスの領域を展開します。 ファクト ボックスのエイジング期間の定義は、パラメータで指定されている既定のエイジング期間の定義から取得されます。 [収集] メニューを使用して変更できます。  

