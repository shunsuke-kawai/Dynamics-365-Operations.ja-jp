--- 
title: "職位の設定"
description: "職位は組織階層の下位レベルの重要な要素です。"
author: DarinKramer
manager: AnnBe
ms.date: 06/22/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c902f532e189753a375d4b48edd9ef0b6d74020e
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-positions"></a><span data-ttu-id="cffd4-103">職位の設定</span><span class="sxs-lookup"><span data-stu-id="cffd4-103">Set up positions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cffd4-104">職位は組織階層の下位レベルの重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="cffd4-104">Positions are an important element of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="cffd4-105">職位は、職務の個々のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="cffd4-105">A position is an individual instance of a job.</span></span> <span data-ttu-id="cffd4-106">たとえば、「販売マネージャ (東部)」という職位は、「販売マネージャ」という職務に関連付けられている職位の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="cffd4-106">For example, the position, “Sales manager (East),” is one of the positions that is associated with the job, “Sales manager.”</span></span> <span data-ttu-id="cffd4-107">職位は部問内に存在し、一人の作業者だけが関連付けられている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cffd4-107">A position exists in a department and may have only one worker associated with it.</span></span> <span data-ttu-id="cffd4-108">このタスクでは、職位の作成に必要な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-108">In this task we will walk through the steps required to create a position.</span></span> <span data-ttu-id="cffd4-109">この手順は、人事管理の専門家を対象としています。</span><span class="sxs-lookup"><span data-stu-id="cffd4-109">This procedure is intended for Human Resources Specialists.</span></span>

1. <span data-ttu-id="cffd4-110">[要員管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cffd4-110">Click Workforce management.</span></span>
2. <span data-ttu-id="cffd4-111">[空いている職位] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cffd4-111">Click Open positions.</span></span>
3. <span data-ttu-id="cffd4-112">[新規] をクリックすると、ドロップ ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="cffd4-112">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="cffd4-113">[職務] フィールドで値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-113">In the Job field, enter or select a value.</span></span>
    * <span data-ttu-id="cffd4-114">ジョブの説明、肩書き、フルタイム相当の雇用係数は、選択されたジョブから職位に自動的にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="cffd4-114">The Job description, title, and full-time equivalent employment factor are automatically copied from the selected job into the position.</span></span>  
5. <span data-ttu-id="cffd4-115">[ジョブの変更] を解決します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-115">ResolveChanges the Job.</span></span>
6. <span data-ttu-id="cffd4-116">[職位の作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cffd4-116">Click Create position.</span></span>
7. <span data-ttu-id="cffd4-117">[部門] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-117">In the Department field, enter or select a value.</span></span>
8. <span data-ttu-id="cffd4-118">[職位タイプ] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-118">In the Position type field, enter or select a value.</span></span>
9. <span data-ttu-id="cffd4-119">[報酬地域] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-119">In the Compensation region field, enter or select a value.</span></span>
    * <span data-ttu-id="cffd4-120">報酬地域フィールドにより、その職位の従業員に適用される報酬の適格性ルールおよび固定昇給予算が決定します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-120">The Compensation region field determines the compensation eligibility rules and fixed increase budgets that apply to an employee in that position.</span></span>  
10. <span data-ttu-id="cffd4-121">[割り当てに使用可能] フィールドで、日付と時刻を入力します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-121">In the Available for assignment field, enter a date and time.</span></span>
11. <span data-ttu-id="cffd4-122">[職位の期間] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-122">Expand the Position duration section.</span></span>
    * <span data-ttu-id="cffd4-123">職位の期間は、事前に入力された入社日および退職日に基づいて既定で入力されます。</span><span class="sxs-lookup"><span data-stu-id="cffd4-123">Position duration is entered by default based on activation and retirement dates entered earlier</span></span>  
12. <span data-ttu-id="cffd4-124">[報告先職位] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-124">Expand the Reports to position section.</span></span>
    * <span data-ttu-id="cffd4-125">別の職位に報告する職位に作業者を割り当てる場合、2 種類の職位に割り当てられている作業者間の直接の報告関係を作成します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-125">When you assign a worker to a position that reports to another position, you create a direct reporting relationship between the workers who are assigned to the two positions.</span></span>  
13. <span data-ttu-id="cffd4-126">[新規] をクリックすると、ドロップ ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="cffd4-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="cffd4-127">[報告先職位] フィールドで値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-127">In the Reports to field, enter or select a value.</span></span>
15. <span data-ttu-id="cffd4-128">[作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cffd4-128">Click Create.</span></span>
16. <span data-ttu-id="cffd4-129">[作業者割り当て] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-129">Expand the Worker assignment section.</span></span>
17. <span data-ttu-id="cffd4-130">[リレーションシップ] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-130">Expand the Relationships section.</span></span>
    * <span data-ttu-id="cffd4-131">組織でマトリックスの階層または別のカスタム階層を使用すると、職位階層タイプを設定し、設定した各階層の職位への報告リレーションシップを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cffd4-131">If your organization uses a matrix hierarchy or another custom hierarchy, you can set up position hierarchy types and then add reporting relationships to positions for each hierarchy type that you set up.</span></span>  
18. <span data-ttu-id="cffd4-132">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cffd4-132">Click Add.</span></span>
19. <span data-ttu-id="cffd4-133">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="cffd4-133">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="cffd4-134">[階層名] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-134">In the Hierarchy name field, enter or select a value.</span></span>
21. <span data-ttu-id="cffd4-135">[報告先職位] フィールドで値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-135">In the Reports to position field, enter or select a value.</span></span>
22. <span data-ttu-id="cffd4-136">[給与] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-136">Expand the Payroll section.</span></span>
23. <span data-ttu-id="cffd4-137">[支払サイクル] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-137">In the Pay cycle field, enter or select a value.</span></span>
24. <span data-ttu-id="cffd4-138">[支払者] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-138">In the Paid by field, enter or select a value.</span></span>
25. <span data-ttu-id="cffd4-139">[年間基本勤務時間] フィールドで、数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-139">In the Annual regular hours field, enter a number.</span></span>
    * <span data-ttu-id="cffd4-140">これはこの職位の作業者が年ごとに作業すると予測され、定期的に支払われる時間数です。</span><span class="sxs-lookup"><span data-stu-id="cffd4-140">This is the number of regularly paid hours that the worker in this position is expected to work each year.</span></span>  
26. <span data-ttu-id="cffd4-141">[労働組合] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-141">Expand the Labor union section.</span></span>
27. <span data-ttu-id="cffd4-142">[労働組合] セクションを折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="cffd4-142">Collapse the Labor union section.</span></span>
28. <span data-ttu-id="cffd4-143">[財務分析コード] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-143">Expand the Financial dimensions section.</span></span>
29. <span data-ttu-id="cffd4-144">[配送テンプレート] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-144">In the Distribution template field, enter or select a value.</span></span>
30. <span data-ttu-id="cffd4-145">[部門] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cffd4-145">In the Department field, enter or select a value.</span></span>
31. <span data-ttu-id="cffd4-146">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cffd4-146">Click Save.</span></span>

