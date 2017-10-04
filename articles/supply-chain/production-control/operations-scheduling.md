---
title: "工程のスケジューリング"
description: "このトピックでは、工程のスケジューリングに関する情報を提供します。 この工程スケジューリングは、時間経過による生産プロセスの概算を提供する場合に使用します。"
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 198073
ms.assetid: 12c28b11-80aa-4668-b15b-724cb24890bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b9436bcf7a9ebcd19b6b79fdf35280ac586a2333
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="operations-scheduling"></a><span data-ttu-id="80159-104">工程のスケジューリング</span><span class="sxs-lookup"><span data-stu-id="80159-104">Operations scheduling</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="80159-105">このトピックでは、工程のスケジューリングに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="80159-105">This topic provides information about operations scheduling.</span></span> <span data-ttu-id="80159-106">この工程スケジューリングは、時間経過による生産プロセスの概算を提供する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="80159-106">You can use operations scheduling to provide a general estimate of the production process over time.</span></span>

<span data-ttu-id="80159-107">工程レベルおよびジョブ レベルの生産をスケジューリングできます。</span><span class="sxs-lookup"><span data-stu-id="80159-107">You can schedule production at the operation level and the job level.</span></span> <span data-ttu-id="80159-108">ジョブのスケジューリングとは異なり、工程のスケジューリングでは、生産工順の工程がジョブに展開されません。</span><span class="sxs-lookup"><span data-stu-id="80159-108">Unlike job scheduling, operations scheduling doesn't explode the operations for the production route into jobs.</span></span> <span data-ttu-id="80159-109">現在の能力に関する情報など、スケジューリングのより詳細を含めるには、工程のスケジューリングを実行した後にジョブ スケジューリングを実行できます。</span><span class="sxs-lookup"><span data-stu-id="80159-109">If you want to include more detail in the scheduling, such as information about current capacity, you can run job scheduling after you run operations scheduling.</span></span> <span data-ttu-id="80159-110">ジョブのスケジューリングだけも実行できます。</span><span class="sxs-lookup"><span data-stu-id="80159-110">You can also run job scheduling only.</span></span> <span data-ttu-id="80159-111">ジョブのスケジューリングは、通常、近または短期的な時間枠に、作業現場の個々のジョブをスケジュールするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="80159-111">Job scheduling is typically used to schedule individual jobs on the shop floor for an immediate or short-term time frame.</span></span>

## <a name="components-of-operations-scheduling"></a><span data-ttu-id="80159-112">工程のスケジューリングのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="80159-112">Components of operations scheduling</span></span>
<span data-ttu-id="80159-113">工程のスケジューリングの主要なコンポーネントには、スケジューリング方向、リソースの能力、および材料の最適化があります。</span><span class="sxs-lookup"><span data-stu-id="80159-113">The main components of operations scheduling are the scheduling direction, the capacity of resources, and materials optimization.</span></span> <span data-ttu-id="80159-114">工程のスケジューリングを使用して、次の目標を達成できます。</span><span class="sxs-lookup"><span data-stu-id="80159-114">By using operations scheduling, you can achieve the following goals:</span></span>

-   <span data-ttu-id="80159-115">特定の日付から順方向または逆方向にスケジューリングすることによって計画方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="80159-115">Control the planning method by scheduling forward or backward from a given date.</span></span>
-   <span data-ttu-id="80159-116">リソース能力に基づいて生産をスケジューリングすることによってリソースの利用を最適化します。</span><span class="sxs-lookup"><span data-stu-id="80159-116">Optimize the use of resources by scheduling productions based on the capacity of the resources.</span></span> <span data-ttu-id="80159-117">この方法によってさらに、代替リソースをいつ使用するかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="80159-117">This approach also helps identify when alternative resources should be used.</span></span>
-   <span data-ttu-id="80159-118">必要な材料の使用可能性に基づいて生産をスケジューリングすることによって材料の使用を最適化します。</span><span class="sxs-lookup"><span data-stu-id="80159-118">Optimize the use of materials by scheduling productions based on the availability of the required materials.</span></span>
-   <span data-ttu-id="80159-119">参照生産をスケジュールし、同期化します。</span><span class="sxs-lookup"><span data-stu-id="80159-119">Schedule and synchronize reference productions.</span></span> <span data-ttu-id="80159-120">参照生産の日付が、製造オーダーのスケジュールの変更時に、調整されます。</span><span class="sxs-lookup"><span data-stu-id="80159-120">The dates of the reference productions are adjusted when the production order’s schedule is changed.</span></span>

<span data-ttu-id="80159-121">工程のスケジューリングを実行する前に、製造オーダーのコストを見積る必要があります。</span><span class="sxs-lookup"><span data-stu-id="80159-121">You must estimate the cost of a production order before you can run operations scheduling.</span></span> <span data-ttu-id="80159-122">見積を実行していない場合は、工程のスケジューリングが開始される前に、自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="80159-122">If you haven't run an estimate, it's automatically run before operations scheduling is started.</span></span> <span data-ttu-id="80159-123">工程スケジュールでは、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="80159-123">An operations schedule specifies the following information:</span></span>

-   <span data-ttu-id="80159-124">生産に対して計画された製品</span><span class="sxs-lookup"><span data-stu-id="80159-124">The product that is planned for production</span></span>
-   <span data-ttu-id="80159-125">製品のコンフィギュレーション。</span><span class="sxs-lookup"><span data-stu-id="80159-125">The configuration of the product</span></span>
-   <span data-ttu-id="80159-126">生産に関連する数量</span><span class="sxs-lookup"><span data-stu-id="80159-126">The quantities that are involved in the production</span></span>
-   <span data-ttu-id="80159-127">生産の開始日および終了日</span><span class="sxs-lookup"><span data-stu-id="80159-127">The dates when the production will start and end</span></span>
-   <span data-ttu-id="80159-128">生産活動を実行するリソースの確保済能力</span><span class="sxs-lookup"><span data-stu-id="80159-128">The capacity reservations for the resources that perform the production activities</span></span>

<span data-ttu-id="80159-129">段取り時間、処理時間、実行時間は生産の工程に対して設定されています。</span><span class="sxs-lookup"><span data-stu-id="80159-129">The setup time, process time, and run time are set for operations in the production.</span></span> <span data-ttu-id="80159-130">工程のスケジューリングを実行した後、製造オーダーのステータスは [**スケジュール済**] であり、すべての工程は、生産工順で指定された順序でスケジューリングされます。</span><span class="sxs-lookup"><span data-stu-id="80159-130">After you run operations scheduling, the status of the production order is **Scheduled**, and all operations are scheduled in the order that is specified by the production route.</span></span> <span data-ttu-id="80159-131">ただし、工程の期間のみが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="80159-131">However, only the duration of the operation is considered.</span></span> <span data-ttu-id="80159-132">開始時刻と終了時刻は、スケジュールされません。</span><span class="sxs-lookup"><span data-stu-id="80159-132">Start times and end times aren't scheduled.</span></span>

## <a name="scheduling-direction-and-date"></a><span data-ttu-id="80159-133">スケジューリング指示と日付</span><span class="sxs-lookup"><span data-stu-id="80159-133">Scheduling direction and date</span></span>
<span data-ttu-id="80159-134">スケジューリング指示は、スケジューリング プロセスの基本となる要素です。</span><span class="sxs-lookup"><span data-stu-id="80159-134">The scheduling direction is fundamental to the scheduling process.</span></span> <span data-ttu-id="80159-135">生産は、タイミングとスケジューリング要件に応じて、任意の日付から順方向 (将来) または逆方向 (過去) にスケジューリングできます。</span><span class="sxs-lookup"><span data-stu-id="80159-135">Production can be scheduled forward or backward from any date, depending on timing and scheduling requirements.</span></span>

-   <span data-ttu-id="80159-136">で**スケジューリングの日付から順方向** – できるだけ早く開始する生産をスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="80159-136">**Forward from the scheduling date** – You can schedule production to start as early as possible.</span></span> <span data-ttu-id="80159-137">生産の開始日としては、今日、明日、または将来の特定の日付を指定できます。</span><span class="sxs-lookup"><span data-stu-id="80159-137">Production can be started today, tomorrow, or on any date in the future.</span></span> <span data-ttu-id="80159-138">生産が最も早い終了日にスケジュール設定されます。</span><span class="sxs-lookup"><span data-stu-id="80159-138">The production is scheduled forward in time to the earliest possible end date.</span></span>
-   <span data-ttu-id="80159-139">**スケジューリングの日付から逆方向** – できるだけ遅く開始する生産をスケジュール設定できます。</span><span class="sxs-lookup"><span data-stu-id="80159-139">**Backward from the scheduling date** – You can schedule production to start as late as possible.</span></span> <span data-ttu-id="80159-140">逆方向のスケジューリングは、生産の完了期限の日付に基づいています。</span><span class="sxs-lookup"><span data-stu-id="80159-140">Backward scheduling is based on the date when the production must be completed.</span></span> <span data-ttu-id="80159-141">スケジュールは、この日付から、生産が開始され、なお期限どおりに完了可能な一番遅い日付へ逆方向にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="80159-141">The schedule counts backward from that date to the latest possible date that the production can be started and still be completed on time.</span></span>

## <a name="resource-scheduling"></a><span data-ttu-id="80159-142">リソース スケジューリング</span><span class="sxs-lookup"><span data-stu-id="80159-142">Resource scheduling</span></span>
<span data-ttu-id="80159-143">工程スケジュールを実行すると、生産工順内の各工程が、工程に指定されたリソースに対してスケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="80159-143">When you run an operations schedule, each operation in the production route is scheduled for the resource that is specified for the operation.</span></span> <span data-ttu-id="80159-144">また、各工程の期間が生産工順で指定されます。</span><span class="sxs-lookup"><span data-stu-id="80159-144">Additionally, the duration of each operation is specified on the production route.</span></span> <span data-ttu-id="80159-145">リソース グループが工程で指定される場合、スケジューリングではグループの能力が確保されます。</span><span class="sxs-lookup"><span data-stu-id="80159-145">If a resource group is specified for an operation, the scheduling reserves capacity on the group.</span></span> <span data-ttu-id="80159-146">ただし、ジョブのスケジューリングとは異なり、工程のスケジューリングは、グループ内に特定のリソースを選択しません。</span><span class="sxs-lookup"><span data-stu-id="80159-146">However, unlike job scheduling, operations scheduling doesn't select the specific resources in the group.</span></span> <span data-ttu-id="80159-147">有限能力で作業している場合、スケジュールは、生産を完了するのに必要なリソースの利用可能性によって異なります。</span><span class="sxs-lookup"><span data-stu-id="80159-147">If you're working with finite capacity, the schedule depends on the availability of the resources that are required in order to complete production.</span></span> <span data-ttu-id="80159-148">工程のスケジューリングは、生産工順で指定されている工程の順序に基づいています。</span><span class="sxs-lookup"><span data-stu-id="80159-148">Operations scheduling follows the sequence of operations that is specified on the production route.</span></span> <span data-ttu-id="80159-149">スケジューリングでは、生産工順で定義された工程時間に基づいてリソース グループの能力が確保されます。</span><span class="sxs-lookup"><span data-stu-id="80159-149">The scheduling reserves capacity on the resource groups, based on the operation times that are defined on the production route.</span></span> <span data-ttu-id="80159-150">関連するリソースの利用可能な能力の合計で、リソース グループの能力が決定されます。</span><span class="sxs-lookup"><span data-stu-id="80159-150">The sum of available capacity on the resources that are involved determines the capacity for the resource group.</span></span> <span data-ttu-id="80159-151">リソースに対して既に存在する確保済能力は使用できない能力と見なされます。</span><span class="sxs-lookup"><span data-stu-id="80159-151">Capacity reservations that already exist for the resources are considered unavailable capacity.</span></span> <span data-ttu-id="80159-152">利用可能な能力が生産に不十分である場合、製造オーダーが遅延したり、さらに停止したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80159-152">If there isn't enough available capacity for the production, the production orders can be delayed or even stopped.</span></span> <span data-ttu-id="80159-153">他にも生産に関連するリソースから予期するで効率性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="80159-153">You can also specify the efficiency that you expect from the resources that are involved in the production.</span></span> <span data-ttu-id="80159-154">リソースに割合として効率性を指定します。</span><span class="sxs-lookup"><span data-stu-id="80159-154">You specify the efficiency as a percentage on the resource.</span></span> <span data-ttu-id="80159-155">効率性の割合で、リソースのスループットが調整されます。</span><span class="sxs-lookup"><span data-stu-id="80159-155">The efficiency percentage adjusts the throughput of the resource.</span></span> <span data-ttu-id="80159-156">たとえばこの調整は、リソースに対して予約される時間に影響します。</span><span class="sxs-lookup"><span data-stu-id="80159-156">This adjustment affects the time that is reserved for the resource.</span></span> <span data-ttu-id="80159-157">リソースを使用する工程のリード タイムも、それに応じて調整されます。</span><span class="sxs-lookup"><span data-stu-id="80159-157">The lead times for the operations that use the resource are also adjusted accordingly.</span></span>

## <a name="operations-scheduling-and-master-planning"></a><span data-ttu-id="80159-158">工程のスケジューリングおよびマスタ プラン</span><span class="sxs-lookup"><span data-stu-id="80159-158">Operations scheduling and master planning</span></span>
<span data-ttu-id="80159-159">工程のスケジュールでは、マスタ プランが活用され、必要な材料の計算を決定します。</span><span class="sxs-lookup"><span data-stu-id="80159-159">The operations schedule also drives master planning and determines calculations for material requirements.</span></span> <span data-ttu-id="80159-160">工程のスケジューリングでは次の情報を考慮します。</span><span class="sxs-lookup"><span data-stu-id="80159-160">Operations scheduling considers the following information:</span></span>

-   <span data-ttu-id="80159-161">**受注残の生産** – 計画済、リリース済、開始済の製品</span><span class="sxs-lookup"><span data-stu-id="80159-161">**Backlogged productions** – Products that are planned, released, or started</span></span>
-   <span data-ttu-id="80159-162">**使用可能な材料** – 在庫、副生産、外注業者、および仕入先</span><span class="sxs-lookup"><span data-stu-id="80159-162">**Material availability** – Inventory, subproductions, suppliers, and vendors</span></span>
-   <span data-ttu-id="80159-163">**能力の利用可能性** – 生産に必要なリソース</span><span class="sxs-lookup"><span data-stu-id="80159-163">**Capacity availability** – Resources that are required for production</span></span>

## <a name="cancellations"></a><span data-ttu-id="80159-164">取消</span><span class="sxs-lookup"><span data-stu-id="80159-164">Cancellations</span></span>
<span data-ttu-id="80159-165">工程のスケジューリングを実行すると、特定部分の工順をキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="80159-165">When you run operations scheduling, you can cancel specific parts of the routing.</span></span> <span data-ttu-id="80159-166">これらの機能には、待ち時間、段取り時間、プロセス時間、重複時間および配送時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="80159-166">These parts include the queue time, setup time, process time, overlap time, and transport times.</span></span>

## <a name="finite-materials"></a><span data-ttu-id="80159-167">有限原材料</span><span class="sxs-lookup"><span data-stu-id="80159-167">Finite materials</span></span>
<span data-ttu-id="80159-168">有限原材料を使用する場合、スケジューリングはさらに、生産に必要な材料の利用可能性によって異なります。</span><span class="sxs-lookup"><span data-stu-id="80159-168">If you're working with finite materials, scheduling also depends on the availability of the materials that are required for production.</span></span> <span data-ttu-id="80159-169">生産に利用可能なコンポーネントが十分ではない場合、生産が遅れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80159-169">If there aren't enough available components for the production, production can be delayed.</span></span> <span data-ttu-id="80159-170">生産に利用する必要のある材料を指定して、材料の使用に基づいてスケジューリングできます。</span><span class="sxs-lookup"><span data-stu-id="80159-170">You can base scheduling on the use of materials by specifying the materials that must be available for production.</span></span> <span data-ttu-id="80159-171">リソースの能力と材料の利用可能性に基づいて最適化すると、生産は、これらの制限に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="80159-171">When you optimize on both resource capacity and the availability of materials, production is calculated according to these restrictions.</span></span> <span data-ttu-id="80159-172">製造オーダーは、能力と材料が同時に、必要量利用可能になるまで、スケジューリングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="80159-172">A production order can't be scheduled to start until capacity and materials are available at the same time and in the required quantities.</span></span>

<a name="see-also"></a><span data-ttu-id="80159-173">参照</span><span class="sxs-lookup"><span data-stu-id="80159-173">See also</span></span>
--------

[<span data-ttu-id="80159-174">工程のスケジューリング オプション</span><span class="sxs-lookup"><span data-stu-id="80159-174">Operation scheduling options</span></span>](operation-scheduling-options.md)



