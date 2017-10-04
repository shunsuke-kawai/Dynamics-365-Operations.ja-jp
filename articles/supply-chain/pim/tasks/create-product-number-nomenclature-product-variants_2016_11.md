--- 
title: "コンフィギュレーションされている製品バリアントの製品番号の作成"
description: "この手順では、コンフィギュレーション済製品バリアントにおける製品番号の分類を設定する方法、およびそれをコンフィギュレーション可能な製品マスターに関連付ける方法を示します。"
author: BibiSp
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e70a5f28635e75a69811085637f7e7431c0f1d40
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-product-number-for-configured-product-variants"></a><span data-ttu-id="18344-103">コンフィギュレーションされている製品バリアントの製品番号の作成</span><span class="sxs-lookup"><span data-stu-id="18344-103">Create a product number for configured product variants</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="18344-104">この手順では、コンフィギュレーション済製品バリアントにおける製品番号の分類を設定する方法、およびそれをコンフィギュレーション可能な製品マスターに関連付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="18344-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="18344-105">この手順では、製品コンフィギュレーション モデル コンポーネントのコンフィギュレーションに関する用語をどのように作成するかを示します。</span><span class="sxs-lookup"><span data-stu-id="18344-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="18344-106">この手順の作成に使用するデモ データの会社は USMF です。</span><span class="sxs-lookup"><span data-stu-id="18344-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="18344-107">新しい製品番号の分類は、「D0004」製品マスターに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="18344-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="18344-108">このタスクは、通常、製品デザイナーが行います。</span><span class="sxs-lookup"><span data-stu-id="18344-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="18344-109">[製品番号の分類] を作成します。</span><span class="sxs-lookup"><span data-stu-id="18344-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="18344-110">[製品バリアント モデルの定義] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="18344-111">[製品の分類] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="18344-112">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-112">Click New.</span></span>
4. <span data-ttu-id="18344-113">[名前] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="18344-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="18344-114">[説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="18344-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="18344-115">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-115">Click Add.</span></span>
7. <span data-ttu-id="18344-116">[製品マスター番号] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-116">Click Product master number.</span></span>
8. <span data-ttu-id="18344-117">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-117">Click Add.</span></span>
9. <span data-ttu-id="18344-118">[テキスト定数] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-118">Click Text constant.</span></span>
10. <span data-ttu-id="18344-119">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="18344-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="18344-120">[テキスト] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="18344-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="18344-121">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-121">Click Add.</span></span>
13. <span data-ttu-id="18344-122">[コンフィギュレーション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-122">Click Configuration.</span></span>
14. <span data-ttu-id="18344-123">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="18344-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="18344-124">製品番号の分類を製品マスターに割り当てる</span><span class="sxs-lookup"><span data-stu-id="18344-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="18344-125">[製品マスター] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-125">Click Product masters.</span></span>
2. <span data-ttu-id="18344-126">クイック フィルターを使用して、レコードを見つけます。</span><span class="sxs-lookup"><span data-stu-id="18344-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="18344-127">たとえば、「D」という値を含む [製品番号] フィールドをフィルターします。</span><span class="sxs-lookup"><span data-stu-id="18344-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="18344-128">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="18344-129">[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-129">Click Edit.</span></span>
5. <span data-ttu-id="18344-130">[分類の使用] フィールドで、[はい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18344-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="18344-131">[製品バリアント番号の分類] フィールドに、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="18344-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="18344-132">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="18344-132">Close the page.</span></span>
8. <span data-ttu-id="18344-133">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="18344-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="18344-134">製品コンフィギュレーション モデル コンポーネントの分類の作成</span><span class="sxs-lookup"><span data-stu-id="18344-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="18344-135">[製品コンフィギュレーション モデル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="18344-136">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="18344-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="18344-137">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="18344-138">[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-138">Click Edit.</span></span>
5. <span data-ttu-id="18344-139">[コンフィギュレーションの分類の使用] フィールドで、[はい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18344-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="18344-140">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-140">Click Add.</span></span>
7. <span data-ttu-id="18344-141">[属性値] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-141">Click Attribute value.</span></span>
8. <span data-ttu-id="18344-142">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="18344-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="18344-143">[属性] フィールドに、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="18344-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="18344-144">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-144">Click Add.</span></span>
11. <span data-ttu-id="18344-145">[テキスト定数] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-145">Click Text constant.</span></span>
12. <span data-ttu-id="18344-146">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="18344-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="18344-147">[テキスト] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="18344-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="18344-148">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-148">Click Add.</span></span>
15. <span data-ttu-id="18344-149">[属性値] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-149">Click Attribute value.</span></span>
16. <span data-ttu-id="18344-150">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="18344-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="18344-151">[属性] フィールドに、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="18344-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="18344-152">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-152">Click Add.</span></span>
19. <span data-ttu-id="18344-153">[テキスト定数] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-153">Click Text constant.</span></span>
20. <span data-ttu-id="18344-154">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="18344-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="18344-155">[テキスト] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="18344-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="18344-156">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-156">Click Add.</span></span>
23. <span data-ttu-id="18344-157">[属性値] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-157">Click Attribute value.</span></span>
24. <span data-ttu-id="18344-158">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="18344-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="18344-159">[属性] フィールドに、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="18344-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="18344-160">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-160">Click Add.</span></span>
27. <span data-ttu-id="18344-161">[テキスト定数] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-161">Click Text constant.</span></span>
28. <span data-ttu-id="18344-162">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="18344-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="18344-163">[テキスト] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="18344-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="18344-164">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-164">Click Add.</span></span>
31. <span data-ttu-id="18344-165">[属性値] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-165">Click Attribute value.</span></span>
32. <span data-ttu-id="18344-166">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="18344-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="18344-167">[属性] フィールドに、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="18344-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="18344-168">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-168">Click Add.</span></span>
35. <span data-ttu-id="18344-169">[テキスト定数] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-169">Click Text constant.</span></span>
36. <span data-ttu-id="18344-170">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="18344-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="18344-171">[テキスト] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="18344-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="18344-172">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-172">Click Add.</span></span>
39. <span data-ttu-id="18344-173">[番号順序値] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18344-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="18344-174">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="18344-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="18344-175">[番号順序] フィールドに、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="18344-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="18344-176">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="18344-176">Close the page.</span></span>
43. <span data-ttu-id="18344-177">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="18344-177">Close the page.</span></span>
44. <span data-ttu-id="18344-178">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="18344-178">Close the page.</span></span>

