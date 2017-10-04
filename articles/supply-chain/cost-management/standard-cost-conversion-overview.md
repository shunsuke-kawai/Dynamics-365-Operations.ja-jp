---
title: "標準原価換算の概要"
description: "この記事は、標準原価換算を設定および実行するのに役立つプロセスの概要を提供します。 説明されているステップは、標準原価換算の前提条件の完了後に実行することを意図しています。"
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 78212
ms.assetid: d601d9d5-1de3-4868-aff4-534dca01d624
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 2e59fd6e137d5f677ed4055385ef88922c8c42ba
ms.contentlocale: ja-jp
ms.lasthandoff: 07/18/2017

---

# <a name="standard-cost-conversion-overview"></a><span data-ttu-id="fd41c-104">標準原価換算の概要</span><span class="sxs-lookup"><span data-stu-id="fd41c-104">Standard cost conversion overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="fd41c-105">この記事は、標準原価換算を設定および実行するのに役立つプロセスの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-105">This article provides a process overview to help you set up and run a standard cost conversion.</span></span> <span data-ttu-id="fd41c-106">説明されているステップは、標準原価換算の前提条件の完了後に実行することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="fd41c-106">The steps listed are intended to be completed after you've completed the prerequisites for a standard cost conversion.</span></span> 

<span data-ttu-id="fd41c-107">[**標準原価換算**] ページを使用して、実績原価方法から標準原価方法に選択した品目のバッチの在庫モデルを換算します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-107">Use the **Standard cost conversions** page to convert the inventory model for a batch of selected items from an actual costing approach to a standard costing approach.</span></span> <span data-ttu-id="fd41c-108">換算プロセスには、必須の在庫決算、移行期間中のいくつかのステップ (移行開始日および予定換算日によって定義されます)、および換算と関連した在庫決算が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-108">The conversion process involves a prerequisite inventory close, several steps during a transition period, which is defined by a transition start date and a planned conversion date, and then the conversion and an associated inventory close.</span></span>

-   <span data-ttu-id="fd41c-109">移行期間前の在庫決算 – 在庫決算は、古い評価方法を使用する品目の未処理トランザクションを決算するので、前提条件として必須のステップです。</span><span class="sxs-lookup"><span data-stu-id="fd41c-109">Inventory close before the transition period – An inventory close represents a prerequisite step because it settles an item’s open transactions using the old valuation method.</span></span> <span data-ttu-id="fd41c-110">移行期間中には、前の期間を決算できるように、請求書などの過去日付のトランザクションを入力および転記できます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-110">During the transition period, you can enter and post backdated transactions, such as invoices, so that you can close the previous period.</span></span> <span data-ttu-id="fd41c-111">古い評価方法を完全に中断するために、在庫決算日はトランザクション開始日よりも 1 日前の日でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="fd41c-111">The inventory close date must be one day before the transition start date to ensure a clean break from the old valuation method.</span></span>
-   <span data-ttu-id="fd41c-112">移行期間中の換算手順 − [**標準原価換算**] ページを使用して、新しい原価バージョンのユーザー定義識別子も含む換算レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-112">Conversion steps during the transition period – Use the **Standard cost conversions** page to create a conversion record that also contains the user-defined identifier for a new costing version.</span></span> <span data-ttu-id="fd41c-113">次に、換算が必要な品目を特定して、その品目の保留中標準原価を、新しい原価バージョン内に入力します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-113">You identify the items that require conversion, and then enter the items’ pending standard costs in the new costing version.</span></span> <span data-ttu-id="fd41c-114">その後、選択した品目の確認を実行して、換算を妨げる問題を特定します。それらの問題を解決したら、再度確認を実行します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-114">You perform a check of the selected items to identify issues that might prevent conversion, resolve the issues, and then perform another check.</span></span> <span data-ttu-id="fd41c-115">品目が確認に合格したら、換算レコードのステータスを [**準備完了**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-115">After the items have successfully passed the checks, you change the status of the conversion record to **Ready**.</span></span> <span data-ttu-id="fd41c-116">計画換算日に、換算プロセスを実行します。換算プロセスに在庫原価計算を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-116">On the planned conversion date, you perform the conversion and optionally include an inventory close.</span></span> <span data-ttu-id="fd41c-117">移行期間中の品目の在庫移動は、古い在庫モデルによって転記および評価されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-117">An item’s inventory movements during the transition period are posted and valued according to the old inventory model.</span></span> <span data-ttu-id="fd41c-118">その後、換算が正常に完了したら、在庫移動は標準原価に再評価されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-118">Then, after the conversion is successfully completed, the inventory movements are revalued to standard cost.</span></span>
-   <span data-ttu-id="fd41c-119">換算前の在庫決算 – 在庫決算を予定換算日に換算の一部として含むことができます。または換算前に別のステップとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-119">Inventory close before the conversion – The inventory close can be included as part of the conversion on the planned conversion date, or it can be performed as a separate step before the conversion.</span></span>

<span data-ttu-id="fd41c-120">換算プロセスが正常に完了した後は、各品目の在庫モデルは標準原価に基づき、品目の標準原価が有効になります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-120">After the conversion process is successfully completed, the inventory model for each item is based on standard cost, and the item’s standard cost is enabled.</span></span> <span data-ttu-id="fd41c-121">その後の在庫トランザクションは品目の標準原価で評価されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-121">Subsequent inventory transactions will be valued at the item’s standard cost.</span></span> <span data-ttu-id="fd41c-122">また、品目の入庫と出庫の物理在庫トランザクションを換算日に基づいて標準原価に換算します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-122">In addition, the system converts the item’s physical inventory transactions for receipts and issues to standard cost based on the conversion date.</span></span> <span data-ttu-id="fd41c-123">また、品目の財務的手持在庫も標準原価に換算され、差異は在庫再評価として転記されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-123">The system also converts the item’s financial on-hand inventory to standard cost, and posts the difference in value as an inventory revaluation.</span></span> <span data-ttu-id="fd41c-124">換算後に発生するすべてのトランザクションは、品目の標準原価で評価されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-124">Any transactions that occur after the conversion are valued at the item’s standard cost.</span></span> <span data-ttu-id="fd41c-125">在庫決算はその換算日よりも 1 日前に実行されなければならないため、換算日よりも前の過去日付のトランザクションは入力できません。</span><span class="sxs-lookup"><span data-stu-id="fd41c-125">You cannot enter backdated transactions before the conversion date, because an inventory close must be performed one day before the conversion date.</span></span> <span data-ttu-id="fd41c-126">換算は、在庫決算が 1 日前に実行された場合にだけ実行することができます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-126">A conversion can only be performed if an inventory close was performed one day earlier.</span></span> <span data-ttu-id="fd41c-127">この在庫決算はキャンセルできません。</span><span class="sxs-lookup"><span data-stu-id="fd41c-127">This inventory close cannot be canceled.</span></span>

## <a name="1-define-a-standard-cost-conversion-record-and-the-associated-costing-version"></a><span data-ttu-id="fd41c-128">1. 標準原価換算レコードとそれに関連付けられた原価バージョンの定義</span><span class="sxs-lookup"><span data-stu-id="fd41c-128">1. Define a standard cost conversion record and the associated costing version</span></span>
<span data-ttu-id="fd41c-129">換算レコードを作成するには [**標準原価換算**] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-129">Use the **Standard cost conversions** page to create a conversion record.</span></span> <span data-ttu-id="fd41c-130">新しい換算レコードは、既存の換算レコードが完了したときにのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-130">You can create a new conversion record only when existing conversion records have been completed.</span></span> <span data-ttu-id="fd41c-131">予定の移行期間の長さは、移行の開始日と予定された換算日によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-131">The duration of the planned transition period is defined by the transition start date and the planned conversion date.</span></span> <span data-ttu-id="fd41c-132">予定の移行期間は最短で 1 日です。</span><span class="sxs-lookup"><span data-stu-id="fd41c-132">A planned transition period can be as short as one day.</span></span> <span data-ttu-id="fd41c-133">予定の移行期間は、換算プロセスがすべてのステップを実行するために十分な時間を保証するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-133">A planned transition period helps to ensure that the conversion process has enough time to complete all its steps.</span></span> <span data-ttu-id="fd41c-134">換算プロセスの開始前に決済を完了するのを保証するために、移行の開始日の前日に在庫決算を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-134">An inventory close must be performed on a date that is one day before the transition start date, to help ensure that settlements are completed before you start the conversion process.</span></span> <span data-ttu-id="fd41c-135">移行の開始日と在庫決算日の関係が正しくなるように、既存の在庫決算の翌日になるように移行の開始日を変更または在庫決算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-135">To make sure that the transition start date and inventory close date are correctly aligned, you can either change the transition start date to one day after an existing inventory close or perform an inventory close.</span></span> <span data-ttu-id="fd41c-136">換算レコードを入力すると、換算される品目に対する標準原価を含む新しい原価バージョンに対するユーザー定義の識別子も入力します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-136">When you enter a conversion record, you also enter a user-defined identifier for a new costing version that will contain the standard costs for converted items.</span></span> <span data-ttu-id="fd41c-137">換算レコード情報を保存すると、自動的に原価バージョンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-137">The costing version is generated automatically when you save the conversion record.</span></span>

## <a name="2-review-and-change-the-new-costing-version-for-the-conversion-record"></a><span data-ttu-id="fd41c-138">2. 換算レコードに対する新しい原価バージョンの確認および変更</span><span class="sxs-lookup"><span data-stu-id="fd41c-138">2. Review and change the new costing version for the conversion record</span></span>
<span data-ttu-id="fd41c-139">新しい原価バージョンは、[**換算**] の原価タイプが示すように、換算レコード専用です。</span><span class="sxs-lookup"><span data-stu-id="fd41c-139">The new costing version is dedicated to the conversion record, as the **Conversion** costing type indicates.</span></span> <span data-ttu-id="fd41c-140">専用の原価バージョンは標準原価の原価バージョンと同様に、換算レコードと関連付けられた品目の品目原価レコードを含みます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-140">The dedicated costing version is similar to a costing version for standard costs and contains the item cost records for items that are associated with the conversion record.</span></span> <span data-ttu-id="fd41c-141">換算レコード専用の原価バージョンには次の設定があり、必要に応じてこれらの点をさまざまなタブで確認および変更します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-141">The dedicated costing version for a conversion record has the following settings, which you should review and modify on the various tabs as required:</span></span>

-   <span data-ttu-id="fd41c-142">**原価タイプ:** このフィールドは [**標準原価**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-142">**Costing type:** This field should be set to **Standard cost**.</span></span>
-   <span data-ttu-id="fd41c-143">**バージョン** - この ID は、原価バージョン ID に対する換算レコードで入力された情報を反映します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-143">**Version:** The identifier reflects the information that is entered on the conversion record for the costing version ID.</span></span>
-   <span data-ttu-id="fd41c-144">**名前:** 既定では、名前は空白です。</span><span class="sxs-lookup"><span data-stu-id="fd41c-144">**Name:** By default, the name is blank.</span></span> <span data-ttu-id="fd41c-145">オプションで、名前を入力できます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-145">You can optionally enter a name.</span></span>
-   <span data-ttu-id="fd41c-146">**ブロック:** このフィールドは [**いいえ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-146">**Block:** This field should be set to **No**.</span></span> <span data-ttu-id="fd41c-147">換算レコードのステータスを [**準備完了**] に変更するまでは、原価バージョンに原価レコードを入力できます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-147">You can enter cost records into the costing version until you change the status of the conversion record to **Ready**.</span></span> <span data-ttu-id="fd41c-148">[**準備完了**] ステータスとは、選択した品目が確認済みで、原価レコードへの変更が許可されない状態を意味します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-148">A status of **Ready** indicates that the selected items have been checked, and that changes to cost records should not be permitted.</span></span>
-   <span data-ttu-id="fd41c-149">**有効化のブロック:** このフィールドは [**はい**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-149">**Block activation:** This field should be set to **Yes**.</span></span> <span data-ttu-id="fd41c-150">専用原価バージョン内の保留中の原価レコードを手動で有効化することはできません。</span><span class="sxs-lookup"><span data-stu-id="fd41c-150">You can't manually activate a pending cost record in the dedicated costing version.</span></span> <span data-ttu-id="fd41c-151">有効化は、換算を実行したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-151">Activation occurs when you perform the conversion.</span></span>
-   <span data-ttu-id="fd41c-152">**開始日:** 開始日は、換算レコードで入力された予定された換算日を反映します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-152">**From date:** The from date reflects the planned conversion date that is entered on the conversion record.</span></span>
-   <span data-ttu-id="fd41c-153">**サイト:** 任意のサイトに原価レコードを入力できるように、このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="fd41c-153">**Site:** Leave this field blank, so that cost records can be entered for any site.</span></span>
-   <span data-ttu-id="fd41c-154">**[価格タイプを許可] フィールド グループ:** 原価価格レコードのみ入力できるように、このフィールドを [**はい**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-154">**Allow price type field group:** Set this field to **Yes**, so that only cost price records can be entered.</span></span>
-   <span data-ttu-id="fd41c-155">**代替原則:** このフィールドは [**なし**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-155">**Fallback principle:** This field is set to **None**.</span></span> <span data-ttu-id="fd41c-156">他の原価バージョン内で有効化された原価情報が必要な場合、代替原則を [**有効**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-156">Change the fallback principle to **Active** if you require cost information that has been activated in other costing versions.</span></span> <span data-ttu-id="fd41c-157">たとえば、コンポーネント、原価カテゴリ、間接原価に関する原価情報は、製造品目の原価を計算するときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-157">For example, cost information about components, cost categories, and indirect costs might be required in order to calculate the costs of manufactured items.</span></span>
-   <span data-ttu-id="fd41c-158">**代替原価バージョン:** このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="fd41c-158">**Fallback costing version:** Leave this field blank.</span></span>

<span data-ttu-id="fd41c-159">専用原価バージョン内の品目原価情報は、[**標準原価換算**] ページでのみ管理できます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-159">Item cost information in the dedicated costing version can be maintained only from the **Standard cost conversions** page.</span></span> <span data-ttu-id="fd41c-160">[**原価バージョン設定**] ページまたは [**原価バージョンの保守**] は、原価バージョンの原価を変換中に計算するのに使用できません。</span><span class="sxs-lookup"><span data-stu-id="fd41c-160">You can't use the **Costing version setup** page or the **Costing version maintenance** page to calculate costs for the costing version during conversion.</span></span> <span data-ttu-id="fd41c-161">ただし、これらのページは、換算プロセスを完了した後で専用原価バージョンを保守するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-161">However, you can use these pages to maintain the dedicated costing version after you've completed the conversion process.</span></span>

## <a name="3-identify-the-items-to-convert-to-standard-cost"></a><span data-ttu-id="fd41c-162">3. 標準原価に換算する品目の識別</span><span class="sxs-lookup"><span data-stu-id="fd41c-162">3. Identify the items to convert to standard cost</span></span>
<span data-ttu-id="fd41c-163">標準原価に換算する個別の品目を識別するには、[**標準原価換算**] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-163">Use the **Standard cost conversions** page to identify the individual items that should be converted to standard cost.</span></span> <span data-ttu-id="fd41c-164">[**標準原価換算への品目の追加**] ページを使用して、複数の品目を追加できます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-164">You can add multiple items by using the **Add items to standard cost conversion** page.</span></span> <span data-ttu-id="fd41c-165">通常は、すべての製造品目を 1 つの換算レコードに含めて、原価が正しく計算されることを保証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-165">In general, you should include all manufactured items in a single conversion record to help ensure that costs are calculated correctly.</span></span>

## <a name="4-enter-or-calculate-the-pending-standard-cost-for-each-item-that-is-being-converted"></a><span data-ttu-id="fd41c-166">4. 換算されている各品目の保留中の標準原価を入力または計算</span><span class="sxs-lookup"><span data-stu-id="fd41c-166">4. Enter or calculate the pending standard cost for each item that is being converted</span></span>
<span data-ttu-id="fd41c-167">専用原価バージョン内の購買品目や転送品目に対する保留中の標準原価を入力するには、[**品目価格**] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-167">Use the **Item price** page to enter pending standard costs in the dedicated costing version for purchased items and transfer items.</span></span> <span data-ttu-id="fd41c-168">原価レコードはサイト固有で、各サイトに対して品目の保留中原価を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-168">Cost records are site-specific, and an item's pending costs must be entered for every site.</span></span> <span data-ttu-id="fd41c-169">製造品目の保留中の標準原価を計算するには、[**品目価格**] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-169">Use the **Item price** page to calculate pending standard costs for manufactured items.</span></span> <span data-ttu-id="fd41c-170">製造品目の保留中原価は、サイトが転送サイトを表している場合を除いて、それぞれの製造サイトに対して計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-170">A manufactured item's pending costs should be calculated for every manufacturing site, unless the site represents a transfer site.</span></span> <span data-ttu-id="fd41c-171">この場合、保留中の原価は手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-171">In this case, the pending costs should be entered manually.</span></span> <span data-ttu-id="fd41c-172">一部の品目には、色、サイズ、コンフィギュレーションの製品分析コードがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-172">Some items might have color, size, or configuration product dimensions.</span></span> <span data-ttu-id="fd41c-173">[**標準原価換算**] ページの [**バリアント別原価価格の使用**] チェック ボックスは、製品分析コードのすべての組み合わせに対する標準原価を表示します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-173">On the **Standard cost conversions** page, the **Use cost price by variant** check box shows the standard cost for every combination of product dimensions.</span></span> <span data-ttu-id="fd41c-174">このチェック ボックスがオフの場合は、品目に対する保留中原価のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-174">When this check box is cleared, you must enter only a pending cost for the item.</span></span>

## <a name="5-check-and-resolve-any-issues-for-the-items-that-are-being-converted"></a><span data-ttu-id="fd41c-175">5. 換算されている品目に対する問題があるかどうかの確認および解決</span><span class="sxs-lookup"><span data-stu-id="fd41c-175">5. Check and resolve any issues for the items that are being converted</span></span>
<span data-ttu-id="fd41c-176">換算されている品目に対する問題を識別するには、[**標準原価換算確認**] レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-176">Use the **Standard cost conversion checks** report to identify issues for the items that are being converted.</span></span> <span data-ttu-id="fd41c-177">品目に問題がない場合、換算レコード内のステータスは [**確認済**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-177">If an item doesn't have any issues, its status in the conversion record is changed to **Checked**.</span></span> <span data-ttu-id="fd41c-178">品目に問題がある場合は、その問題を解決し、品目のステータスが [**確認済**] に変更されるまで、レポートを再度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-178">If an item has issues, you must resolve the issues and then run the report again until the item's status is changed to **Checked**.</span></span> <span data-ttu-id="fd41c-179">直ちにその問題を解決できない場合は、換算レコードから品目を削除して、後でその品目を換算することもできます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-179">If you can't resolve an item's issues in a timely manner, you can optionally delete the item from the conversion record and then convert the item later.</span></span>

## <a name="6-change-the-status-of-the-conversion-record-to-ready"></a><span data-ttu-id="fd41c-180">6. 換算レコードのステータスを [確認済] に変更</span><span class="sxs-lookup"><span data-stu-id="fd41c-180">6. Change the status of the conversion record to Ready</span></span>
<span data-ttu-id="fd41c-181">換算レコードのステータスを [**確認済**] に変更すると、システムが標準原価換算を実行する前の最終チェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-181">When the status of the conversion record is changed to **Ready**, the system performs a final check before it runs a standard cost conversion.</span></span> <span data-ttu-id="fd41c-182">次の条件が満たされたときにのみ、ステータスが [**確認済**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-182">The status is changed to **Ready** only if the following conditions have been met:</span></span>

-   <span data-ttu-id="fd41c-183">換算レコード内のすべての品目のステータスが [**確認済**] です。</span><span class="sxs-lookup"><span data-stu-id="fd41c-183">Every item in the conversion record has a status of **Checked**.</span></span>
-   <span data-ttu-id="fd41c-184">移行の開始日前日に在庫決算が完了している。</span><span class="sxs-lookup"><span data-stu-id="fd41c-184">An inventory close was performed on a date that is one day before the transition start date.</span></span> <span data-ttu-id="fd41c-185">移行の開始日と在庫決算日の関係が正しくなるように、既存の在庫決算の翌日になるように移行の開始日を変更または在庫決算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-185">To make sure that the transition start date and inventory close date are correctly aligned, you can either change the transition start date to one day after an existing inventory close or perform an inventory close.</span></span>

## <a name="7-back-up-the-database-before-conversion"></a><span data-ttu-id="fd41c-186">7. 換算前のデータベースのバックアップ</span><span class="sxs-lookup"><span data-stu-id="fd41c-186">7. Back up the database before conversion</span></span>
<span data-ttu-id="fd41c-187">バックアップしておくと、換算中にエラーが発生した場合にデータベースを復元できます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-187">The backup lets you restore the database if errors are encountered during the conversion.</span></span>

## <a name="8-perform-the-conversion-when-the-conversion-record-has-a-ready-status"></a><span data-ttu-id="fd41c-188">8. 換算レコードが [準備完了] ステータスになった際の換算の実行</span><span class="sxs-lookup"><span data-stu-id="fd41c-188">8. Perform the conversion when the conversion record has a Ready status</span></span>
<span data-ttu-id="fd41c-189">換算プロセスを実行するには、予定された換算日の前日に在庫決算が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-189">The conversion process requires that an inventory close be performed on a date that is one day before the planned conversion date.</span></span> <span data-ttu-id="fd41c-190">この要件によって、移行期間中に日付を遡ったトランザクションを入力できないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-190">This requirement helps ensure that back-dated transactions can't be entered during the transition period.</span></span> <span data-ttu-id="fd41c-191">在庫決算が実行済みでない場合は、換算プロセスの一部としてそれを実行するかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-191">If an inventory close hasn't yet been performed, you will be asked if you want to perform it as part of the conversion process.</span></span> <span data-ttu-id="fd41c-192">換算プロセスは、一度に 1 つの品目を処理します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-192">The conversion process handles one item at a time.</span></span> <span data-ttu-id="fd41c-193">これは、品目の下位レベル コードに基づいて、製品構造の最下位の品目から開始します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-193">It starts with the lowest items in a product structure, based on the item's low-level code.</span></span> <span data-ttu-id="fd41c-194">品目が正常に換算された場合、換算レコードの状態は [**換算済**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-194">When an item has been successfully converted, its status in the conversion record is changed to **Converted**.</span></span> <span data-ttu-id="fd41c-195">換算プロセスが中断された場合、正常に換算されていないすべての品目のステータスは [**確認済**] のままです。</span><span class="sxs-lookup"><span data-stu-id="fd41c-195">If the conversion process is interrupted, any items that haven't been successfully converted will still have a status of **Checked**.</span></span> <span data-ttu-id="fd41c-196">換算プロセスが正常に完了すると、次の効果があります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-196">Successful completion of the conversion process has the following effects:</span></span>

-   <span data-ttu-id="fd41c-197">換算レコードのステータスが [**準備完了**] から [**完了**] に変更され、選択した品目のステータスが [**確認済**] から [**換算済**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-197">The status of the conversion record is changed from **Ready** to **Completed**, and the status of each selected item is changed from **Checked** to **Converted**.</span></span>
-   <span data-ttu-id="fd41c-198">換算された品目の品目モデル グループは、標準原価在庫モデルを持つ新しいグループを反映するように変更されます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-198">The item model group for converted items is changed so that it reflects a new group that has a standard cost inventory model.</span></span>
-   <span data-ttu-id="fd41c-199">換算された品目の標準原価は、専用の原価バージョン内で有効になります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-199">The standard costs for the converted items have been enabled in the dedicated costing version.</span></span>
-   <span data-ttu-id="fd41c-200">原価バージョンの原価タイプは、[**換算**] から [**標準原価**] に変更され、それによって原価バージョンは標準原価に対する他の原価バージョンと同じようになります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-200">The costing type of the costing version is changed from **Conversion** to **Standard cost**, and the costing version is now like other costing versions for standard costs.</span></span>

## <a name="9-validate-and-reconcile-the-inventory-values-for-the-converted-items"></a><span data-ttu-id="fd41c-201">9. 換算された品目の在庫金額の検証および調整</span><span class="sxs-lookup"><span data-stu-id="fd41c-201">9. Validate and reconcile the inventory values for the converted items</span></span>
<span data-ttu-id="fd41c-202">[**差異分析の明細書**] レポートにより再評価差異を分析、および [**在庫金額**] レポートにより特定の日付の在庫金額を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-202">The **Variance analysis statement** report lets you analyze revaluation variance and the **Inventory value** repot lets you view inventory value on a specific date.</span></span>

-   <span data-ttu-id="fd41c-203">再評価差異を分析します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-203">Analyze revaluation variances.</span></span> <span data-ttu-id="fd41c-204">換算された品目の在庫の再評価差異を表示するには、[**差異分析の明細書**] レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-204">Use the **Variance analysis statement** report to view inventory revaluation variances for the converted items.</span></span> <span data-ttu-id="fd41c-205">または **標準原価トランザクション**] ページを使用して、在庫を持つ換算された品目の在庫再評価トランザクションを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="fd41c-205">You can also use the **Standard cost transactions** page to view the inventory revaluation transactions for the converted items that have inventory.</span></span>
-   <span data-ttu-id="fd41c-206">移行の開始日前日の在庫金額を分析します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-206">Analyze the inventory value before the transition start date.</span></span> <span data-ttu-id="fd41c-207">換算された品目の在庫金額を表示するには、[**在庫金額**] レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-207">Use the **Inventory value** report to view inventory values for the converted items.</span></span> <span data-ttu-id="fd41c-208">レポートの [終了日] には、移行開始日の 1 日前になる日付を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-208">For the To date for the report, use a date that is one day before the transition start date.</span></span>
-   <span data-ttu-id="fd41c-209">換算日前日の在庫金額を分析します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-209">Analyze the inventory value before the conversion date.</span></span> <span data-ttu-id="fd41c-210">換算された品目の在庫金額を表示するには、[**在庫金額**] レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-210">Use the **Inventory value** report to view inventory values for the converted items.</span></span> <span data-ttu-id="fd41c-211">レポートの [終了日] として、換算日の 1 日前を反映する日付を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-211">As the To date for the report, use a date that reflects one day before the conversion date.</span></span>
-   <span data-ttu-id="fd41c-212">換算日の在庫金額を分析します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-212">Analyze the inventory value on the conversion date.</span></span> <span data-ttu-id="fd41c-213">換算日の在庫金額を表示するには、[**在庫金額**] レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-213">Use the **Inventory value** report to view inventory values as of the conversion date.</span></span> <span data-ttu-id="fd41c-214">レポートの開始日と終了日の両方は、換算日と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-214">Both the From date and the To date for the report should match the conversion date.</span></span> <span data-ttu-id="fd41c-215">レポートの選択基準は、換算された品目を反映します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-215">The report selection criteria should reflect the converted items.</span></span>
-   <span data-ttu-id="fd41c-216">日付を遡らせた在庫移動を分析します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-216">Analyze back-dated inventory movements.</span></span> <span data-ttu-id="fd41c-217">換算後に入力された、日付を遡らせた在庫移動を表示するには、[**在庫金額**] レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-217">Use the **Inventory value** report to view back-dated inventory movements that were entered after the conversion.</span></span> <span data-ttu-id="fd41c-218">レポートの開始日と終了日は、移行の開始日と換算日のそれぞれの前日と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd41c-218">The "From date and the To date for the report should correspond to the transition start date and the conversion date, minus one day.</span></span> <span data-ttu-id="fd41c-219">レポートの選択基準は、換算された品目を反映します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-219">The report selection criteria should reflect the converted items.</span></span> <span data-ttu-id="fd41c-220">このレポートは、移行期間中に標準原価で行われた在庫移動を表示します。</span><span class="sxs-lookup"><span data-stu-id="fd41c-220">The report shows inventory movements that were made at standard cost during the transition period.</span></span>


<a name="see-also"></a><span data-ttu-id="fd41c-221">参照</span><span class="sxs-lookup"><span data-stu-id="fd41c-221">See also</span></span>
--------

[<span data-ttu-id="fd41c-222">標準原価換算の前提条件</span><span class="sxs-lookup"><span data-stu-id="fd41c-222">Prerequisites for a standard cost conversion</span></span>](prerequisites-standard-cost-conversion.md)



