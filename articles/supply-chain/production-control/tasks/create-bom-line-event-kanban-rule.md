--- 
title: "BOM 明細行イベントかんばんルールの作成"
description: "このタスクは、古典的な実稼働環境と混合リーン内の生産 BOM 明細行の供給を確認するイベントかんばんルールを作成するのに必要な設定を対象としています。"
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 452cc5cf6060b71f91ad43e39e756dc23d759448
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-bom-line-event-kanban-rule"></a><span data-ttu-id="e1511-103">BOM 明細行イベントかんばんルールの作成</span><span class="sxs-lookup"><span data-stu-id="e1511-103">Create a BOM line event kanban rule</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e1511-104">このタスクは、古典的な実稼働環境と混合リーン内の生産 BOM 明細行の供給を確認するイベントかんばんルールを作成するのに必要な設定を対象としています。</span><span class="sxs-lookup"><span data-stu-id="e1511-104">This task focuses on the setup needed to create an event kanban rule to ensure supply for production BOM lines in a mixed lean and classic production environment.</span></span> <span data-ttu-id="e1511-105">このタスクの作成に使用するデモ データの会社は USMF です。</span><span class="sxs-lookup"><span data-stu-id="e1511-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="e1511-106">このタスクは、新しい製品または変更された製品の生産を準備している、プロセス エンジニアまたはバリュー ストリーム マネージャーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="e1511-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="e1511-107">新しいかんばんルールの作成</span><span class="sxs-lookup"><span data-stu-id="e1511-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="e1511-108">[生産管理] > [定期処理のタスク] > [かんばん数量計算] > [かんばんルール] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e1511-108">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban rules.</span></span>
2. <span data-ttu-id="e1511-109">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1511-109">Click New.</span></span>
3. <span data-ttu-id="e1511-110">[タイプ] フィールドで、「引き取り」を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1511-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="e1511-111">引き取りタイプが転送かんばんの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1511-111">The Withdrawal type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="e1511-112">[補充方法] フィールドで、「イベント」を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1511-112">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="e1511-113">イベント戦略は、イベントに基づくかんばんの転送を作成するために選択されます。</span><span class="sxs-lookup"><span data-stu-id="e1511-113">The Event strategy is selected to create the transfer of kanbans based on an event.</span></span> <span data-ttu-id="e1511-114">後にタスク ガイドで、製造オーダーの見積が発生します。</span><span class="sxs-lookup"><span data-stu-id="e1511-114">Later in the task guide, we will trigger it by estimating a production order.</span></span>  
5. <span data-ttu-id="e1511-115">[最初の計画活動] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="e1511-115">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="e1511-116">ReplenishSpeakerComponents を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="e1511-116">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="e1511-117">この転送活動は入庫 (出荷) 倉庫と場所 12 にあるので、材料が 12 倉庫の場所 12 に移動されます。</span><span class="sxs-lookup"><span data-stu-id="e1511-117">This transfer activity has receipt (output) warehouse and location 12, which means that material will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="e1511-118">[詳細] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e1511-118">Expand the Details section.</span></span>
7. <span data-ttu-id="e1511-119">[製品] フィールドで、M0001 を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="e1511-119">In the Product field, enter or select M0001.</span></span>
8. <span data-ttu-id="e1511-120">[イベント] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e1511-120">Expand the Events section.</span></span>
9. <span data-ttu-id="e1511-121">[BOM 明細行イベント] フィールドで、「自動」を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1511-121">In the BOM line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="e1511-122">[自動] を設定した [BOM 明細行イベント] フィールドで、製造オーダー BOM 明細行の材料ニーズを満たすためのかんばんが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e1511-122">With the BOM line event field set to Automatic, kanban will be created to fulfill material needs for production order BOM lines.</span></span>  
10. <span data-ttu-id="e1511-123">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e1511-123">Close the page.</span></span>

## <a name="create-and-modify-a-new-production-order"></a><span data-ttu-id="e1511-124">新しい製造オーダーを作成および変更します。</span><span class="sxs-lookup"><span data-stu-id="e1511-124">Create and modify a new production order</span></span>
1. <span data-ttu-id="e1511-125">[生産管理] > [製造オーダー] > [すべての製造オーダー] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e1511-125">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="e1511-126">[新しい製造オーダー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1511-126">Click New production order.</span></span>
3. <span data-ttu-id="e1511-127">[品目番号] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="e1511-127">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="e1511-128">「L0001」を選択または入力します。</span><span class="sxs-lookup"><span data-stu-id="e1511-128">Enter or select 'L0001'.</span></span> <span data-ttu-id="e1511-129">ただし、品目 M0001 が品目 L0001 の BOM に含まれるため、品目 L0001 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1511-129">We use item L0001 because item M0001 is included in the BOM for item L0001.</span></span>  
4. <span data-ttu-id="e1511-130">[作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1511-130">Click Create.</span></span>
5. <span data-ttu-id="e1511-131">リストで、L 0001 行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1511-131">In the list, click the link in the row for L0001</span></span>
6. <span data-ttu-id="e1511-132">BOM をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1511-132">Click BOM.</span></span>
7. <span data-ttu-id="e1511-133">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1511-133">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="e1511-134">[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1511-134">Click Edit.</span></span>
9. <span data-ttu-id="e1511-135">[行タイプ]フィールドで、「ペギングされた供給」を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1511-135">In the Line type field, select 'Pegged supply'.</span></span>
    * <span data-ttu-id="e1511-136">ペギングされた供給は、かんばんの供給の作成を発生するために選択されます。</span><span class="sxs-lookup"><span data-stu-id="e1511-136">Pegged supply is selected to trigger the supply creation of a kanban.</span></span>  
10. <span data-ttu-id="e1511-137">[リソース消費]フィールドで、「いいえ」を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1511-137">Select No in the Resource consumption field.</span></span>
    * <span data-ttu-id="e1511-138">リソース消費のチェック ボックスをオフにすると、倉庫を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e1511-138">Clearing the check box of Resource consumption lets us change the warehouse.</span></span>  
11. <span data-ttu-id="e1511-139">[在庫分析コード] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e1511-139">Expand the Inventory dimensions section.</span></span>
12. <span data-ttu-id="e1511-140">[倉庫] フィールドに、「12」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e1511-140">In the Warehouse field, type '12'.</span></span>
    * <span data-ttu-id="e1511-141">倉庫は、引き取り活動の出荷倉庫である 12 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e1511-141">Warehouse is set to 12 because this is the output warehouse for the withdrawal activity.</span></span>  
13. <span data-ttu-id="e1511-142">[場所] フィールドに、「12」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e1511-142">In the Location field, type '12'.</span></span>
    * <span data-ttu-id="e1511-143">場所は、引き取り活動の出荷場所である 12 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e1511-143">Location is set to 12 because this is the output location of the withdrawal activity.</span></span>  
14. <span data-ttu-id="e1511-144">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e1511-144">Close the page.</span></span>
15. <span data-ttu-id="e1511-145">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e1511-145">Close the page.</span></span>

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a><span data-ttu-id="e1511-146">製造オーダーの見積もりを行なって、作成するかんばんを表示します。</span><span class="sxs-lookup"><span data-stu-id="e1511-146">Estimate the production order and view the kanban created</span></span>
1. <span data-ttu-id="e1511-147">[見積] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1511-147">Click Estimate.</span></span>
    * <span data-ttu-id="e1511-148">製造オーダーの見積時には、品目 M0001 を供給する関連のかんばんの作成が発生します。</span><span class="sxs-lookup"><span data-stu-id="e1511-148">Estimating the production order will trigger the creation of the associated kanban to supply item M0001.</span></span>  
2. <span data-ttu-id="e1511-149">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1511-149">Click OK.</span></span>
3. <span data-ttu-id="e1511-150">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e1511-150">Close the page.</span></span>
4. <span data-ttu-id="e1511-151">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e1511-151">Close the page.</span></span>
5. <span data-ttu-id="e1511-152">[製品情報管理] > [リーン生産] > [かんばんルール] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e1511-152">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
6. <span data-ttu-id="e1511-153">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1511-153">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e1511-154">品目 M0001 用に作成したイベントかんばんルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1511-154">Select the event kanban rule created for item M0001.</span></span>  
7. <span data-ttu-id="e1511-155">[かんばん] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e1511-155">Expand the Kanbans section.</span></span>
8. <span data-ttu-id="e1511-156">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="e1511-156">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e1511-157">見積もりを行った製造オーダーの M0001 を供給するために作成されたかんばんを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1511-157">Notice the kanban created to supply M0001 for the estimated production order.</span></span>  
    * <span data-ttu-id="e1511-158">これは最後のステップです!</span><span class="sxs-lookup"><span data-stu-id="e1511-158">This is the last step!</span></span>  

