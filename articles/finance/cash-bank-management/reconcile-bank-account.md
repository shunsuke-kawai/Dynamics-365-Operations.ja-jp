---
title: 銀行口座の調整
description: このトピックでは、銀行口座を調整する方法について説明します。
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3e1281171a656a73a35d4990fd8a34b35c1c6db8
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188283"
---
# <a name="reconcile-a-bank-account"></a>銀行口座の調整

[!include[banner](../includes/banner.md)]

口座取引明細書を受け取ったら、口座取引明細書の取引と法人の銀行取引を定期的に調整する必要があります。

明細書に記載されている小切手または預金伝票のいずれかの支払いの状態が現在**保留中**の場合、銀行明細書は銀行口座で調整できません。 レビュー担当者が小切手の取消または預金伝票の支払キャンセルを転記または拒否した後、ステータスは**取消の保留中**ではなくなり、銀行口座を照合できます。

1.  **現金および銀行管理** \> **銀行口座** \> **銀行口座**に移動します。 口座取引明細書と調整する銀行口座を選択し、**調整** > **口座調整**を選択します。

2.  **口座取引明細書日付**と**口座取引明細書**フィールドに情報を入力します。 **期末残高**フィールドには、口座取引明細書に表示される銀行口座の残高を入力できます。

3.  **トランザクション**を選択して、**口座調整**ページを開きます。

4.  口座取引明細書に含まれる取引ごとに、Dynamics 365 Finance の金額が口座取引明細書の金額に対応する場合、**精算済**チェックボックスを選択します。 **銀行トランザクション タイプ**フィールドでは値の入力や変更もできます。 このフィールドの値は、銀行取引統計や一部のレポートで重要な情報です。
    

    > [!NOTE]
    > <P>口座取引明細書にない取引については、<STRONG>精算済</STRONG>チェック ボックスを選択しないでください。 これらの取引は、後日、口座取引明細書と調整するまでこのページに表示され続けます。</P>
    > <P>トランザクションのステータスが<STRONG>取消の保留中</STRONG>の場合、<STRONG>精算済</STRONG>チェック ボックスは使用できません。 転記の前、取り消しまたはキャンセルがレビューに送信されているように Finance で設定されている場合、取引はこの状態になっている可能性があります。 レビュー担当者が取消またはキャンセルの転記や拒否をした後、状態は<STRONG>取消の保留中</STRONG>ではなくなり、銀行口座を口座取引明細書と調整できます。</P>

    
    口座取引明細書にすべてが表示されるチェックの間隔に対して**精算済**チェックボックスを選択するには、**小切手の期間にマーク**を選択し、間隔を指定します。

5.  銀行口座トランザクションの金額が口座取引明細書のトランザクションの金額と一致しない場合は、**訂正金額**フィールドに修正金額を入力します。
    

    > [!NOTE]
    > <P>修正するトランザクションの会計年度期間が終了している場合、<STRONG>訂正金額</STRONG>フィールドは使用できません。 代わりに、訂正用のオープン会計期間内の取引日を指定した明細行を作成します。 この場合、元のトランザクションで使用した財務分析コードと、相手方主勘定を追加する必要があります。</P>



6.  口座取引明細書には記載されていても Finance には記録されていない手数料や利息などの、エントリの取引を作成します。 **銀行トランザクション タイプ**と適切な財務分析コードを入力します。

7.  口座取引明細書のトランザクションは**精算済**としてマークされているため、変更するたびに再計算される**未調整**フィールドの金額がゼロに近づいていきます。 金額がゼロになったら、**口座を調整**を選択して、調整、および作成したトランザクションと訂正を転記します。
    
    調整を転記すると、関連の取引は変更や訂正ができなくなり、それ以降の口座調整には表示されません。

8.  未調整の銀行トランザクションを表示するには、**未調整銀行トランザクション**レポートを使用します。 銀行口座の口座取引明細書を表示するには、**口座取引明細書**レポートを使用します。

# <a name="cancel-bank-statement-reconciliation"></a>口座取引明細書調整のキャンセル 

口座取引明細書調整のキャンセル機能を使用すると、口座取引明細書調整をキャンセルできます。 この機能を使用するには、**機能管理**ワークスペースで**口座取引明細書調整のキャンセル**機能を有効にします。 また、**口座取引明細書の編集を許可**パラメーターを有効にする必要があります。 これを行うには、**現金および銀行管理 > 設定 > 現金および銀行管理パラメーター > 口座調整**の順に移動します。
 
口座取引明細書の調整は、入力された時系列でのみキャンセルすることができます。 口座取引明細書の調整がキャンセルされると、新しいトランザクションと修正が取り消され、他のすべてのトランザクションは未調整としてマークされます。
 
口座取引明細書の調整をキャンセルするには、口座取引明細書を選択し、**口座取引明細書 > 口座調整をキャンセル**を選択します。 **口座調整をキャンセル**ページで、**理由コード**、**理由コメント**、および**取消日**を入力します。 **OK** を選択してキャンセルを開始します。 なお、口座取引明細書の取消日は、口座取引明細書の日付以降である必要があります。 口座取引明細書の調整がキャンセルされた後、口座取引明細書の**取消日**フィールドは、指定された**取消日**に更新されます。 **トランザクション**ボタンを選択して、調整がキャンセルされたトランザクションを表示します。