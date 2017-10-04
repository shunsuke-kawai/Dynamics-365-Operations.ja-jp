--- 
title: "引き取りかんばんルールの作成"
description: "この手順は、リーン環境で材料を転送する引き取りかんばんルールを作成するために必要な設定を表示します。"
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
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
ms.openlocfilehash: 02c7133d2e02b27fb428874deeda21e2bab28fb6
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-withdrawal-kanban-rule"></a><span data-ttu-id="8bc92-103">引き取りかんばんルールの作成</span><span class="sxs-lookup"><span data-stu-id="8bc92-103">Create a withdrawal kanban rule</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8bc92-104">この手順は、リーン環境で材料を転送する引き取りかんばんルールを作成するために必要な設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-104">This procedure shows the setup that is needed to create a withdrawal kanban rule for transferring material in a lean environment.</span></span> <span data-ttu-id="8bc92-105">この手順の作成に使用するデモ データの会社は USMF です。</span><span class="sxs-lookup"><span data-stu-id="8bc92-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8bc92-106">この手順は、新しい材料または変更された材料の補充を準備している、プロセス エンジニアまたはバリュー ストリーム マネージャーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="8bc92-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare replenishment of new or modified material.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="8bc92-107">新しいかんばんルールの作成</span><span class="sxs-lookup"><span data-stu-id="8bc92-107">Create new kanban rule</span></span>
1. <span data-ttu-id="8bc92-108">[かんばんルール] に移動します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="8bc92-109">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bc92-109">Click New.</span></span>
3. <span data-ttu-id="8bc92-110">[タイプ] フィールドで、「引き取り」を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="8bc92-111">引き取りタイプは、材料や商品を転送するためのかんばんルールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bc92-111">The Withdrawal type is used for kanban rules to transfer material or goods.</span></span>  
4. <span data-ttu-id="8bc92-112">[最初の計画活動] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="8bc92-113">ReplenishSpeakerComponents を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-113">Select ReplenishSpeakerComponents.</span></span>   <span data-ttu-id="8bc92-114">この活動は倉庫 11、場所 11 から倉庫 12、および場所 12 へコンポーネントを移動するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="8bc92-114">This activity is set up to move components from warehouse 11, location 11 to warehouse 12, and location 12.</span></span>  
5. <span data-ttu-id="8bc92-115">[製品] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-115">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="8bc92-116">M0007 を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-116">Select M0007.</span></span>  
6. <span data-ttu-id="8bc92-117">[リード タイム] フィールドで、数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-117">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="8bc92-118">たとえば、60 です。</span><span class="sxs-lookup"><span data-stu-id="8bc92-118">For example, 60.</span></span>  
7. <span data-ttu-id="8bc92-119">[計量単位] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-119">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="8bc92-120">たとえば、分単位です。</span><span class="sxs-lookup"><span data-stu-id="8bc92-120">For example, Minutes.</span></span>  

## <a name="set-quantities-for-kanban"></a><span data-ttu-id="8bc92-121">かんばんの数量を設定します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-121">Set quantities for kanban</span></span>
1. <span data-ttu-id="8bc92-122">既定の数量を「5」に設定します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-122">Set Default quantity to '5'.</span></span>
    * <span data-ttu-id="8bc92-123">これは、かんばんごとに転送される数量です。</span><span class="sxs-lookup"><span data-stu-id="8bc92-123">This is the quantity that will be transferred for each kanban.</span></span>  
2. <span data-ttu-id="8bc92-124">[固定かんばん数量] フィールドで、「2」を入力します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-124">In the Fixed kanban quantity field, enter '2'.</span></span>
    * <span data-ttu-id="8bc92-125">これは有効にするかんばんの量です。</span><span class="sxs-lookup"><span data-stu-id="8bc92-125">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="8bc92-126">この場合、2 つのかんばんが、それぞれ 5 つずつ転送します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-126">In this case, 2 kanbans transferring 5 each.</span></span>  
3. <span data-ttu-id="8bc92-127">[下限値に対する警告] フィールドで、「1」を入力します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-127">In the Alert boundary minimum field, enter '1'.</span></span>
    * <span data-ttu-id="8bc92-128">出荷先にあるべきすべてのかんばんの最小数量を追跡するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bc92-128">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="8bc92-129">たとえば、これはかんばんの数量の概要に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bc92-129">For example, this is used on the kanban quantity overview.</span></span>  
4. <span data-ttu-id="8bc92-130">[上限値に対する警告] フィールドで、「2」を入力します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-130">In the Alert boundary maximum field, enter '2'.</span></span>
    * <span data-ttu-id="8bc92-131">出荷先にあるべきすべてのかんばんの最大数量を追跡するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bc92-131">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="8bc92-132">たとえば、これはかんばんの数量の概要に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bc92-132">For example, this is used on the kanban quantity overview.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="8bc92-133">かんばんの作成</span><span class="sxs-lookup"><span data-stu-id="8bc92-133">Create kanbans</span></span>
1. <span data-ttu-id="8bc92-134">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bc92-134">Click Save.</span></span>
    * <span data-ttu-id="8bc92-135">かんばんルールは、かんばんを作成する前に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc92-135">The kanban rule needs to be saved before kanbans can be created.</span></span>  
2. <span data-ttu-id="8bc92-136">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bc92-136">Click Add.</span></span>
    * <span data-ttu-id="8bc92-137">提示された「新しいかんばんの数」が 2 であるために、有効なかんばんはないことに注意してください。これは「固定かんばん数量」と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="8bc92-137">Note that there are no active kanbans because the suggested 'Number of new kanbans' is 2, which is equal to the 'Fixed kanban quantity'.</span></span>  
3. <span data-ttu-id="8bc92-138">[作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bc92-138">Click Create.</span></span>
    * <span data-ttu-id="8bc92-139">これは、2 つのかんばんを作成します。</span><span class="sxs-lookup"><span data-stu-id="8bc92-139">This will create two kanbans.</span></span>  
    * <span data-ttu-id="8bc92-140">この引き取りかんばんルールのために、それぞれ 5 つずつに対し 2 つのかんばんが作成されたことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8bc92-140">Note that 2 kanbans, for 5 each, was created for this withdrawal kanban rule.</span></span>  <span data-ttu-id="8bc92-141">これは、この手順の最後のステップです。</span><span class="sxs-lookup"><span data-stu-id="8bc92-141">This is the last step in this procedure.</span></span>  

