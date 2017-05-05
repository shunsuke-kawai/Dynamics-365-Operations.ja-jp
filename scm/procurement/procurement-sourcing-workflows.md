---
title: "調達ワークフロー"
description: "組織によっては、取引を入力した個人以外のユーザーが購買要求と発注書を承認することを要求している場合があります。 承認プロセスを設定するには、ワークフローを作成できます。"
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 27c211e6ded17e085559add916c28a48c40e5b8e
ms.lasthandoff: 03/31/2017


---

# <a name="procurement-and-sourcing-workflows"></a>調達ワークフロー

[!include[banner](../includes/banner.md)]


組織によっては、取引を入力した個人以外のユーザーが購買要求と発注書を承認することを要求している場合があります。 承認プロセスを設定するには、ワークフローを作成できます。

1 つのワークフローは 1 つの業務プロセスを表します。 ここでは、ドキュメントの処理および承認に携わるべきユーザーを示すことによって、システムにおけるドキュメントの流れを定義します。 組織でワークフロー システムを使用することにはいくつかの利点があります。
-   **一貫したプロセス** - 購買要求や経費報告書などの特定のドキュメントの承認プロセスを定義できます。 ワークフロー システムを使用することで、ドキュメントが一貫した方法で効率的に処理および承認されます。
-   **プロセスの可視性** - 特定のワークフロー インスタンスのステータス、履歴およびパフォーマンス測定方法を追跡できます。 これは、効率を向上させるためにワークフローに変更するかどうかを決定するのに役立ちます。
-   [**集中化された作業一覧**] ユーザーはワークフローに参加するすべてのユーザーに割り当てられているワークフロー タスクおよび承認を表示するには、集中化された作業一覧を表示できます。 これは、[作業項目] ページで使用できます。

## <a name="the-types-of-workflows-that-you-can-create"></a>作成できるワークフローのタイプ
調達には、次のワークフロー タイプが使用できます。

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| **タイプ**                         | **このタイプは次の目的で使用します。**                                          |
| 購買要求の確認      | 購買要求の確認ワークフローを作成します。            |
| 購買要求明細行の確認 | 購買要求明細行の確認ワークフローを作成します。       |
| 発注書ワークフロー          | 発注書の確認および承認ワークフローを作成します。     |
| 購買注文明細行ワークフロー     | 発注書明細行の確認および承認ワークフローを作成します。 |

## <a name="creating-a-workflow"></a>ワークフローの作成
ワークフローを作成するには、[購買および調達 &gt; 設定 &gt; 購買および調達ワークフロー] に移動し、ワークフローのタイプを選択して新しいワークフローを作成します。  

ワークフローのキャンバスにワークフロー要素をデザイナーにドラッグし、要素をフローにリンクすることができます。 ワークフロー要素はコンフィギュレーションする必要があります。 承認とタスクのワークフロー要素において、どの参加者がアクションを実行する必要があるかを設定できます。
参加者のタイプ
----------------------

参加者の次のグループに承認ステップを割り当てることができます。

| ユーザー グループ    | 説明                                                               |
|---------------|---------------------------------------------------------------------------|
| 参加者   | グループまたはロールのメンバに承認ステップを割り当てます。                   |
| 階層     | 承認ステップを特定の組織階層のユーザーに割り当てます |
| ワークフロー ユーザー | このワークフローのユーザーに承認ステップを割り当てます。                       |
| キュー         | 作業項目キューに承認ステップを割り当てます。                            |
| ユーザー          | 承認ステップを特定のユーザーに割り当てます。                               |



<a name="see-also"></a>参照
--------

[購買要求のビジネス プロセスのワークフローの定義](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[購買要求ワークフロー](purchase-requisitions-workflow.md)



