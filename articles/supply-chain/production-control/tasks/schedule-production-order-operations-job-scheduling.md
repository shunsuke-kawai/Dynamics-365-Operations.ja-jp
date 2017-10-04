--- 
title: "工程とジョブのスケジューリングによる製造オーダーのスケジュール"
description: "この手順では、工程のスケジューリングとジョブのスケジューリングで製造オーダーのスケジューリングを行うことに焦点を当てています。"
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d4aac437876862e9f776264fc81f246c820bdf45
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="029f1-103">工程とジョブのスケジューリングによる製造オーダーのスケジュール</span><span class="sxs-lookup"><span data-stu-id="029f1-103">Schedule a production order with operations and job scheduling</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="029f1-104">この手順では、工程のスケジューリングとジョブのスケジューリングで製造オーダーのスケジューリングを行うことに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="029f1-104">This procedure focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="029f1-105">ジョブは、ジョブのスケジューリングで作成されますが、工程のスケジューリングでは作成されません。</span><span class="sxs-lookup"><span data-stu-id="029f1-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="029f1-106">このタスクの作成に使用するデモ データの会社は USMF です。</span><span class="sxs-lookup"><span data-stu-id="029f1-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="029f1-107">この手順は、個別の製造環境で作業をしている生産マネージャ、生産計画担当者、または作業現場の監督を対象としています。</span><span class="sxs-lookup"><span data-stu-id="029f1-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="029f1-108">製造オーダーの作成</span><span class="sxs-lookup"><span data-stu-id="029f1-108">Create a production order</span></span>
1. <span data-ttu-id="029f1-109">[生産管理] > [製造オーダー] > [すべての製造オーダー] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="029f1-109">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="029f1-110">[新しい製造オーダー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-110">Click New production order.</span></span>
3. <span data-ttu-id="029f1-111">[品目番号] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="029f1-111">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="029f1-112">品目番号 D0001 を選択します。</span><span class="sxs-lookup"><span data-stu-id="029f1-112">Select Item number D0001.</span></span>  
4. <span data-ttu-id="029f1-113">[作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-113">Click Create.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="029f1-114">製造オーダの工程のスケジュール</span><span class="sxs-lookup"><span data-stu-id="029f1-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="029f1-115">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="029f1-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="029f1-116">作成した製造オーダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="029f1-116">Select the production order that you have just created.</span></span> <span data-ttu-id="029f1-117">一覧の先頭に表示されます。</span><span class="sxs-lookup"><span data-stu-id="029f1-117">It should be at the top of the list.</span></span>      
2. <span data-ttu-id="029f1-118">[アクション ペイン] で、[スケジュール] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-118">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="029f1-119">工程スケジュールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-119">Click Schedule operations.</span></span>
4. <span data-ttu-id="029f1-120">[スケジューリング指示] フィールドで、[スケジューリングの日付からフォワード] を選択します。</span><span class="sxs-lookup"><span data-stu-id="029f1-120">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
5. <span data-ttu-id="029f1-121">[スケジューリングの日付] フィールドに日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="029f1-121">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="029f1-122">将来期日、たとえば、今日とさらに 1 週間を選択します。</span><span class="sxs-lookup"><span data-stu-id="029f1-122">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="029f1-123">選択されたスケジューリング指示で、製造オーダーは、この日付を起点としてスケジューリングされます。</span><span class="sxs-lookup"><span data-stu-id="029f1-123">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="029f1-124">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-124">Click OK.</span></span>
7. <span data-ttu-id="029f1-125">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="029f1-125">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="029f1-126">ステータスが "スケジュール済" に変わることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="029f1-126">Note that the status is changed to Scheduled.</span></span>  
8. <span data-ttu-id="029f1-127">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-127">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="029f1-128">[すべてのジョブ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-128">Click All jobs.</span></span>
    * <span data-ttu-id="029f1-129">ジョブは、工程のスケジューリングで作成されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="029f1-129">Note that no jobs are created with operations scheduling.</span></span>  
10. <span data-ttu-id="029f1-130">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="029f1-130">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="029f1-131">製造オーダのジョブのスケジュール</span><span class="sxs-lookup"><span data-stu-id="029f1-131">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="029f1-132">[アクション ペイン] で、[スケジュール] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-132">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="029f1-133">[ジョブのスケジュール設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-133">Click Schedule jobs.</span></span>
3. <span data-ttu-id="029f1-134">[スケジューリング指示] フィールドで、[スケジューリングの日付からフォワード] を選択します。</span><span class="sxs-lookup"><span data-stu-id="029f1-134">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
4. <span data-ttu-id="029f1-135">[スケジューリングの日付] フィールドに日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="029f1-135">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="029f1-136">将来の日付、たとえば、今日とさらに 1 週間を選択します。</span><span class="sxs-lookup"><span data-stu-id="029f1-136">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="029f1-137">選択されたスケジューリング指示で、製造オーダーは、この日付を起点としてスケジューリングされます。</span><span class="sxs-lookup"><span data-stu-id="029f1-137">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="029f1-138">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-138">Click OK.</span></span>
6. <span data-ttu-id="029f1-139">アクション ウィンドウで、[製造オーダー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-139">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="029f1-140">[すべてのジョブ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029f1-140">Click All jobs.</span></span>
    * <span data-ttu-id="029f1-141">有効な工順に基づいて、ジョブ スケジューリングで5 つのジョブが作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="029f1-141">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  

