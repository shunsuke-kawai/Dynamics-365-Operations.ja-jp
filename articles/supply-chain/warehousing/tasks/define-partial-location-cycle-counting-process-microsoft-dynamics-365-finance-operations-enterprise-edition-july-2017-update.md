--- 
title: "部分的な場所の循環棚卸プロセスの定義"
description: "循環棚卸作業を使用して棚卸作業を作成する場合は、その場所において手持在庫の代わりに、特定の製品および製品バリアントのみがカウントされるよう要求することによって、実際の棚卸操作を指示できます。"
author: YuyuScheller
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 030f0f75d64c97f1109f36c9fd38283c2d1fa7b0
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="define-partial-location-cycle-counting-process"></a><span data-ttu-id="493ec-103">部分的な場所の循環棚卸プロセスの定義</span><span class="sxs-lookup"><span data-stu-id="493ec-103">Define partial location cycle counting process</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="493ec-104">循環棚卸作業を使用して棚卸作業を作成する場合は、その場所において手持在庫の代わりに、特定の製品および製品バリアントのみがカウントされるよう要求することによって、実際の棚卸操作を指示できます。</span><span class="sxs-lookup"><span data-stu-id="493ec-104">When you use cycle count plans to create counting work, you can guide the actual counting operations by requesting that only specific products and product variants be counted instead of all on-hand inventory at the location.</span></span> <span data-ttu-id="493ec-105">特定の製品をフィルター処理することで、倉庫マネージャーはレビュー間接費を削減し、統合ミスを回避し、時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="493ec-105">By filtering on specific products, the warehouse manager can reduce review overhead, help prevent consolidation mistakes, and save time.</span></span> <span data-ttu-id="493ec-106">通常、倉庫マネージャが設定タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="493ec-106">Typically, a warehouse manager performs the setup tasks.</span></span> <span data-ttu-id="493ec-107">USMF デモ データ会社または独自のデータを使用して、この手順を踏むことができます。</span><span class="sxs-lookup"><span data-stu-id="493ec-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="create-a-cycle-counting-work-template"></a><span data-ttu-id="493ec-108">循環棚卸作業テンプレートを作成します</span><span class="sxs-lookup"><span data-stu-id="493ec-108">Create a cycle counting work template</span></span>
1. <span data-ttu-id="493ec-109">[倉庫管理] > [設定] > [作業] > [作業テンプレート] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="493ec-109">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="493ec-110">[ワーク オーダー タイプ] フィールドで、[循環棚卸] を選択します。</span><span class="sxs-lookup"><span data-stu-id="493ec-110">In the Work order type field, select 'Cycle counting'.</span></span>
3. <span data-ttu-id="493ec-111">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-111">Click New.</span></span>
4. <span data-ttu-id="493ec-112">[順序番号] フィールドに番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="493ec-112">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="493ec-113">並べ替え順序は、最小番号から最大番号です。</span><span class="sxs-lookup"><span data-stu-id="493ec-113">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="493ec-114">値は 0 (ゼロ) より大きい値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="493ec-114">The value must be more than 0 (zero).</span></span>  
5. <span data-ttu-id="493ec-115">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="493ec-115">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="493ec-116">[作業テンプレート] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="493ec-116">In the Work template field, type a value.</span></span>
7. <span data-ttu-id="493ec-117">[作業テンプレートの説明] フィールドで、値を入力します。</span><span class="sxs-lookup"><span data-stu-id="493ec-117">In the Work template description field, type a value.</span></span>
8. <span data-ttu-id="493ec-118">[作業プール ID] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="493ec-118">In the Work pool ID field, enter or select a value.</span></span>
9. <span data-ttu-id="493ec-119">[作業の優先順位] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="493ec-119">In the Work priority field, enter a number.</span></span>
10. <span data-ttu-id="493ec-120">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-120">Click Save.</span></span>
11. <span data-ttu-id="493ec-121">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-121">Click New.</span></span>
12. <span data-ttu-id="493ec-122">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="493ec-122">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="493ec-123">[作業タイプ] フィールドで [棚卸] を選択します。</span><span class="sxs-lookup"><span data-stu-id="493ec-123">In the Work type field, select 'Counting'.</span></span>
14. <span data-ttu-id="493ec-124">[作業クラス ID] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="493ec-124">In the Work class ID field, enter or select a value.</span></span>
15. <span data-ttu-id="493ec-125">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-125">Click Save.</span></span>
16. <span data-ttu-id="493ec-126">[作業明細行内訳] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-126">Click Work line breaks.</span></span>
17. <span data-ttu-id="493ec-127">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-127">Click New.</span></span>
18. <span data-ttu-id="493ec-128">[順序番号] フィールドに番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="493ec-128">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="493ec-129">並べ替え順序は、最小番号から最大番号です。</span><span class="sxs-lookup"><span data-stu-id="493ec-129">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="493ec-130">値は 0 (ゼロ) より大きい値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="493ec-130">The value must be more than 0 (zero).</span></span>  
19. <span data-ttu-id="493ec-131">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-131">Click Save.</span></span>
20. <span data-ttu-id="493ec-132">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="493ec-132">Close the page.</span></span>
21. <span data-ttu-id="493ec-133">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="493ec-133">Close the page.</span></span>

## <a name="create-a-cycle-counting-plan"></a><span data-ttu-id="493ec-134">循環棚卸計画を作成します</span><span class="sxs-lookup"><span data-stu-id="493ec-134">Create a cycle counting plan</span></span>
1. <span data-ttu-id="493ec-135">[倉庫管理] > [設定] > [循環棚卸] > [循環棚卸計画] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="493ec-135">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="493ec-136">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-136">Click New.</span></span>
3. <span data-ttu-id="493ec-137">[循環棚卸計画 ID] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="493ec-137">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="493ec-138">[説明] フィールドで値を入力します。</span><span class="sxs-lookup"><span data-stu-id="493ec-138">In the Description field, type a value.</span></span>
5. <span data-ttu-id="493ec-139">[循環棚卸の最大数] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="493ec-139">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="493ec-140">[作業テンプレート] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="493ec-140">In the Work template field, enter or select a value.</span></span>
7. <span data-ttu-id="493ec-141">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-141">Click New.</span></span>
8. <span data-ttu-id="493ec-142">[順序番号] フィールドに番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="493ec-142">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="493ec-143">並べ替え順序は、最小番号から最大番号です。</span><span class="sxs-lookup"><span data-stu-id="493ec-143">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="493ec-144">値は 0 (ゼロ) より大きい値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="493ec-144">The value must be more than 0 (zero).</span></span>  
9. <span data-ttu-id="493ec-145">[説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="493ec-145">In the Description field, type a value.</span></span>
10. <span data-ttu-id="493ec-146">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-146">Click Save.</span></span>
11. <span data-ttu-id="493ec-147">[製品クエリの定義] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-147">Click Define product query.</span></span>
12. <span data-ttu-id="493ec-148">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="493ec-148">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="493ec-149">[基準] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="493ec-149">In the Criteria field, enter or select a value.</span></span>
14. <span data-ttu-id="493ec-150">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="493ec-150">Click OK.</span></span>
15. <span data-ttu-id="493ec-151">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="493ec-151">Close the page.</span></span>

