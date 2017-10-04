---
title: "発注書の承認および確認"
description: "この資料は、発注書 (PO) が作成された後の一連の状態と、変更管理の有効化の効果について説明します。"
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 93143
ms.assetid: cd12a944-c52c-4579-a301-7abe1d237c72
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 9a624e6153c08cc4f3f4d4f1b1785b22f736ae99
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="approve-and-confirm-purchase-orders"></a><span data-ttu-id="dd7d2-103">発注書の承認および確認</span><span class="sxs-lookup"><span data-stu-id="dd7d2-103">Approve and confirm purchase orders</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

<span data-ttu-id="dd7d2-104">この資料は、発注書 (PO) が作成された後の一連の状態と、変更管理の有効化の効果について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-104">This article describes the statuses that a purchase order (PO) goes through after it has been created, and the effect of enabling change management on POs.</span></span>

<span data-ttu-id="dd7d2-105">注文書 (PO) が作成された後は、承認プロセスを経る必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-105">After a purchase order (PO) has been created, it might have to go through an approval process.</span></span> <span data-ttu-id="dd7d2-106">仕入先が発注書に同意した後、発注書は [**確認済**] の状態に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-106">After the vendor has agreed to the order, the PO is set to a status of **Confirmed**.</span></span>

## <a name="approval-of-purchase-orders"></a><span data-ttu-id="dd7d2-107">発注書の状態</span><span class="sxs-lookup"><span data-stu-id="dd7d2-107">Approval of purchase orders</span></span>
<span data-ttu-id="dd7d2-108">変更管理を使用していない発注書では、作成後すぐに [**承認済**] の状態となります。一方、変更管理を使用している発注書の場合、初めて作成されるなら [**ドラフト**] の状態になります。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-108">POs that don’t use change management have a status of **Approved** as soon as they are created, whereas POs that use change management have a status of **Draft** when they are first created.</span></span> <span data-ttu-id="dd7d2-109">マスター プランから計画オーダーを確定することによって作成された発注書は、変更管理の設定に関係なく [**承認済**] に、常に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-109">A PO that has been created by firming a planned order from master planning is always set to a status of **Approved**, regardless of the change management settings.</span></span> <span data-ttu-id="dd7d2-110">発注書では、[**承認済**] 状態に達したときのみ、在庫トランザクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-110">A PO creates inventory transactions only when it reaches the **Approved** status.</span></span> <span data-ttu-id="dd7d2-111">したがってその在庫は注文が承諾されるまで、予約またはマーク向けに、在庫ありと表示されません。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-111">Therefore, that inventory doesn’t appear as available for reservation or marking until the order is accepted.</span></span>  

<span data-ttu-id="dd7d2-112">[**変更管理の有効化**] オプションを、[**調達パラメーター**] ページで設定することで、発注書の変更管理が可能になります。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-112">You enable change management for POs by setting the **Activate change management** option on the **Procurement and sourcing parameters** page.</span></span> <span data-ttu-id="dd7d2-113">変更管理が有効化されると発注書は作成完了後、承認ワークフローを経る必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-113">When change management is enabled, POs must go through an approval workflow after they have been completed.</span></span> <span data-ttu-id="dd7d2-114">Microsoft Dynamics 365 for Finance and Operations には、承認プロセスを表すワークフローを定義できるワークフロー プロセス エディターがあります。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-114">Microsoft Dynamics 365 for Finance and Operations has a workflow process editor where you can define a workflow to represent your approval process.</span></span> <span data-ttu-id="dd7d2-115">このワークフローには、自動承認のルールを特定の発注書に割り当てる承認を決定するルール、長期間承認待ちのワークフローのエスカレーション向けのルールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-115">This workflow can include rules for automatic approval, rules that determine who will be assigned to approve particular POs, and rules for escalating a workflow that has been waiting for approval for a long time.</span></span> <span data-ttu-id="dd7d2-116">すべての仕入先、または特定仕入先の変更管理プロセスを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-116">You can enable the change management process for all vendors or for specific vendors.</span></span> <span data-ttu-id="dd7d2-117">個々の発注書が上書きできるようプロセスを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-117">You can also set up the process so that it can be overridden for individual POs.</span></span>  

<span data-ttu-id="dd7d2-118">変更管理が有効化されると、発注書は、[**ドラフト**] から [**完了**] までの 6 つの承認状態へと変化していきます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-118">When change management is enabled, POs move through six approval statuses, from **Draft** to **Finalized**.</span></span> <span data-ttu-id="dd7d2-119">注文が承認されると、それを修正したいユーザーは [**変更の要求**] アクションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-119">After an order has been approved, users who want to modify it must use the **Request change** action.</span></span>

| <span data-ttu-id="dd7d2-120">承認状態</span><span class="sxs-lookup"><span data-stu-id="dd7d2-120">Approval status</span></span> | <span data-ttu-id="dd7d2-121">説明</span><span class="sxs-lookup"><span data-stu-id="dd7d2-121">Description</span></span>                                                                      | <span data-ttu-id="dd7d2-122">変更要求の有効化</span><span class="sxs-lookup"><span data-stu-id="dd7d2-122">Request change is enabled</span></span> |
|-----------------|----------------------------------------------------------------------------------|---------------------------|
| <span data-ttu-id="dd7d2-123">ドラフト</span><span class="sxs-lookup"><span data-stu-id="dd7d2-123">Draft</span></span>           | <span data-ttu-id="dd7d2-124">発注書はドラフトで、発注書ワークフローの承認用に送信されていません。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-124">The PO is a draft and hasn’t been submitted for approval in the PO workflow.</span></span>     | <span data-ttu-id="dd7d2-125">第        条</span><span class="sxs-lookup"><span data-stu-id="dd7d2-125">No</span></span>                        |
| <span data-ttu-id="dd7d2-126">確認中</span><span class="sxs-lookup"><span data-stu-id="dd7d2-126">In review</span></span>       | <span data-ttu-id="dd7d2-127">発注書は、発注書ワークフローの承認のため送信されました。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-127">The PO was submitted for approval in the PO workflow.</span></span> <span data-ttu-id="dd7d2-128">承認は保留中です。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-128">Approval is pending.</span></span>       | <span data-ttu-id="dd7d2-129">第        条</span><span class="sxs-lookup"><span data-stu-id="dd7d2-129">No</span></span>                        |
| <span data-ttu-id="dd7d2-130">拒否済</span><span class="sxs-lookup"><span data-stu-id="dd7d2-130">Rejected</span></span>        | <span data-ttu-id="dd7d2-131">発注書は、承認プロセス中に却下されました。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-131">The PO was rejected during the approval process.</span></span>                                 | <span data-ttu-id="dd7d2-132">第        条</span><span class="sxs-lookup"><span data-stu-id="dd7d2-132">No</span></span>                        |
| <span data-ttu-id="dd7d2-133">承認済</span><span class="sxs-lookup"><span data-stu-id="dd7d2-133">Approved</span></span>        | <span data-ttu-id="dd7d2-134">発注書が承認されました。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-134">The PO was approved.</span></span>                                                             | <span data-ttu-id="dd7d2-135">有</span><span class="sxs-lookup"><span data-stu-id="dd7d2-135">Yes</span></span>                       |
| <span data-ttu-id="dd7d2-136">確認済み</span><span class="sxs-lookup"><span data-stu-id="dd7d2-136">Confirmed</span></span>       | <span data-ttu-id="dd7d2-137">発注書が確認されました。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-137">The PO was confirmed.</span></span> <span data-ttu-id="dd7d2-138">発注書は承認されるまで確認できません。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-138">A PO can’t be confirmed until it has been approved.</span></span>        | <span data-ttu-id="dd7d2-139">有</span><span class="sxs-lookup"><span data-stu-id="dd7d2-139">Yes</span></span>                       |
| <span data-ttu-id="dd7d2-140">完了</span><span class="sxs-lookup"><span data-stu-id="dd7d2-140">Finalized</span></span>       | <span data-ttu-id="dd7d2-141">発注書は作成完了です。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-141">The PO was made final.</span></span> <span data-ttu-id="dd7d2-142">これは財務上決済されており変更できません。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-142">It’s now financially closed and can no longer be changed.</span></span> | <span data-ttu-id="dd7d2-143">第        条</span><span class="sxs-lookup"><span data-stu-id="dd7d2-143">No</span></span>                        |

## <a name="confirming-purchase-orders"></a><span data-ttu-id="dd7d2-144">発注書の確認</span><span class="sxs-lookup"><span data-stu-id="dd7d2-144">Confirming purchase orders</span></span>
<span data-ttu-id="dd7d2-145">[**承認済**] 状態の発注書では、確認前に追加の手順を実施できます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-145">POs that have an approval status of **Approved** can go through additional steps before they are confirmed.</span></span> <span data-ttu-id="dd7d2-146">例えば、価格、割引、配送日程について照会できるよう仕入先に購買の照会を送信する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-146">For example, you might have to send a purchase inquiry to the vendor to inquire about prices, discounts, or delivery dates.</span></span> <span data-ttu-id="dd7d2-147">この場合、[**購買の照会**] アクションを使用して、発注書を [**外部レビュー中**] の状態に設定できます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-147">In this case, you can set the PO to the **In external review** status by using the **Purchase inquiry** action.</span></span>  

<span data-ttu-id="dd7d2-148">仕入先ポータルを使用できるよう設定されている仕入先は、ポータルで発注書を確認、承認、または却下できます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-148">Vendors that are set up to use the Vendor portal can review orders on the portal, and approve or reject them.</span></span> <span data-ttu-id="dd7d2-149">このレビュー プロセス中、発注書は [**外部レビュー中**] の状態になります。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-149">During this review process, the PO has a status of **In external review**.</span></span> <span data-ttu-id="dd7d2-150">仕入先からの確認により Finance and Operations で注文が自動的に確定されるよう、仕入先ポータルをコンフィギュレーションできます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-150">The Vendor portal can be configured so that a confirmation from the vendor automatically confirms the order in Finance and Operations.</span></span> <span data-ttu-id="dd7d2-151">代わりに、仕入先からの確認を受信した後、発注書を手動で確認できます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-151">Alternatively, you can manually confirm a PO after you receive confirmation from the vendor.</span></span> <span data-ttu-id="dd7d2-152">仕入先が発注書を拒否する場合、この拒否と共に、拒否理由と変更提案もあわせて受信します。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-152">If a vendor rejects a PO, the rejection is received together with the reason for the rejection and suggestions for changes.</span></span> <span data-ttu-id="dd7d2-153">この場合、発注書の状態は [**外部レビュー中**] のままです。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-153">In this case, the status of the PO remains **In external review**.</span></span>  

<span data-ttu-id="dd7d2-154">実際の確認の処理が完了する前に、注文の見積確認を生成するオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-154">There is also an option to generate a pro-forma confirmation for an order before the actual confirmation has been processed.</span></span> <span data-ttu-id="dd7d2-155">このオプションでは、仕入先と共有できるレポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-155">This option just creates a report that you can share with the vendor.</span></span> <span data-ttu-id="dd7d2-156">仕訳帳情報は作成されません。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-156">It doesn’t create any journal information.</span></span>  

<span data-ttu-id="dd7d2-157">仕入先が注文に同意した後、次のステップは発注書が確定済みであることを記録することです。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-157">After the vendor has agreed to the order, the next step is to record the PO as committed.</span></span> <span data-ttu-id="dd7d2-158">[**確認**] アクション、または [**確認する**] アクションのどちらかを使用して、このステップを完了できます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-158">You can complete this step by using either the **Confirmation** action or the **Confirm** action.</span></span> <span data-ttu-id="dd7d2-159">これらの両方のアクションでは、注文の承認状態が [**確認済**] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-159">Both these actions set the approval status of the order to **Confirmed**.</span></span> <span data-ttu-id="dd7d2-160">注文の確認により 2 つの追加のプロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-160">Confirmation of an order initiates two additional processes:</span></span>

-   <span data-ttu-id="dd7d2-161">システムで確認された内容の正確なコピーを保存するため、仕訳帳が作成されます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-161">A journal is created to store an exact copy of what was confirmed in the system.</span></span> <span data-ttu-id="dd7d2-162">場合によっては、注文の変更を必要とし、更新された注文の確認後に追加の仕訳帳を作成します。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-162">Sometimes, orders require changes, and additional journals are created after the updated order is confirmed.</span></span> <span data-ttu-id="dd7d2-163">これらの仕訳帳を使用して、確認された注文のさまざまなバージョンの履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-163">These journals let you view the history of the various versions of the order that were confirmed.</span></span>
-   <span data-ttu-id="dd7d2-164">勘定配布が作成されこの機能が有効になっている場合、注文チェックと予算チェックが実施されます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-164">Accounting distributions are created, and order checks and budget checks occur if this functionality has been enabled.</span></span> <span data-ttu-id="dd7d2-165">いずれかのチェックが失敗した場合、もう一度確認を実行する前に、発注書の変更を行う必要がありますというエラー メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-165">If either check fails, you receive an error message that states that changes must be made to the PO before it can be confirmed again.</span></span>

<span data-ttu-id="dd7d2-166">仕入先は、購買に提供される支払い保証のいくつかのタイプを要求するかもしれません。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-166">A vendor might request some type of assurance that payment will be provided for a purchase.</span></span> <span data-ttu-id="dd7d2-167">買掛金勘定プロセスでは、この保証を提供するためのさまざまなメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-167">There are various methods for providing this guarantee within accounts payable processes.</span></span> <span data-ttu-id="dd7d2-168">例えば、[**支払い**] アクションでは、発注資金が確保され、この支払いは発注書に記録されます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-168">For example, the **Prepayment** action reserves funds for the PO, and this prepayment is recorded on the PO.</span></span>

## <a name="changing-purchase-orders"></a><span data-ttu-id="dd7d2-169">発注書の変更</span><span class="sxs-lookup"><span data-stu-id="dd7d2-169">Changing purchase orders</span></span>
<span data-ttu-id="dd7d2-170">状況によっては、[**承認済**] または [**確認済**] の承認状態に達した後、発注書を変更する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-170">In some situations, you might have to change a PO after it has reached an approval status of **Approved** or **Confirmed**.</span></span>  

<span data-ttu-id="dd7d2-171">発注書が変更管理プロセスを使用して作成された場合、または注文が [**要求の変更**] アクションを使用してすでに承認されているなら、その注文を再度呼び出して変更できます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-171">If the PO was created by using a change management process, you can make changes by recalling the order or, if the order has already been approved, by using the **Request change** action.</span></span> <span data-ttu-id="dd7d2-172">この場合、承認状態は [**ドラフト**] に戻り、その注文を修正できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-172">In this case, the approval status is changed back to **Draft**, and you can then modify the order.</span></span> <span data-ttu-id="dd7d2-173">変更が終了した後、再承認のため発注書を再送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-173">After you’ve finished making changes, you might have to submit the PO for re-approval.</span></span> <span data-ttu-id="dd7d2-174">[**購買ポリシー**] ページにある [**発注書の再承認ルール**] ポリシー ルールを使用して、再承認を必要とする変更の種類をコンフィギュレートできます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-174">You can configure the types of changes that require re-approval by using a **Re-approval rule for purchase orders** policy rule on the **Purchasing policies** page.</span></span>  

<span data-ttu-id="dd7d2-175">発注書明細行の注文数量の一部が配送された場合、注文数量は変更できません。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-175">If part of the ordered quantity for a PO line has been delivered, you can’t change the ordered quantity.</span></span> <span data-ttu-id="dd7d2-176">ただし明細行の [**出荷更新待ち**] の数量を変更できます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-176">However, you can change the **Deliver remainder** quantity on the line.</span></span> <span data-ttu-id="dd7d2-177">明細行をキャンセルしそれ以降の処理を防ぐため、[**確定**] アクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-177">You can then use the **Finalize** action to cancel lines and prevent further processing.</span></span> 

<span data-ttu-id="dd7d2-178">注文が確認済になると削除はできません。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-178">After an order has been confirmed, you can no longer delete it.</span></span> <span data-ttu-id="dd7d2-179">ただし注文した数量が受領されていない、または請求書が送られていないなら、全数量か発注残の数量をキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="dd7d2-179">However, you can cancel the total quantity or any remaining quantity on an order, provided that the quantity hasn’t been received or invoiced.</span></span>

<a name="see-also"></a><span data-ttu-id="dd7d2-180">参照</span><span class="sxs-lookup"><span data-stu-id="dd7d2-180">See also</span></span>
--------

[<span data-ttu-id="dd7d2-181">発注書の概要</span><span class="sxs-lookup"><span data-stu-id="dd7d2-181">Purchase order overview</span></span>](purchase-order-overview.md)

[<span data-ttu-id="dd7d2-182">発注書の作成</span><span class="sxs-lookup"><span data-stu-id="dd7d2-182">Purchase order creation</span></span>](purchase-order-creation.md)

[<span data-ttu-id="dd7d2-183">発注書に対応する製品受領書</span><span class="sxs-lookup"><span data-stu-id="dd7d2-183">Product receipt against purchase orders</span></span>](product-receipt-against-purchase-orders.md)

[<span data-ttu-id="dd7d2-184">仕入先請求書の概要</span><span class="sxs-lookup"><span data-stu-id="dd7d2-184">Overview of vendor invoices</span></span>](/dynamics365/unified-operations/financials/accounts-payable/vendor-invoices-overview)



