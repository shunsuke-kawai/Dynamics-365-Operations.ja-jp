---
title: "原価配賦合計の方法"
description: "この記事は、原価配賦の合計 (TCA) を使用するためのガイドラインを提供します。 TCA は、バッチ オーダーの主要式品目および式に定義される連産品の間のコストを計算する方法です。"
author: YuyuScheller
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConsistOf, PmfFormulaCoBy
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 83852
ms.assetid: 7c14c3e5-9476-4a79-a210-e77fc91cc7fc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: b070aaeecacdee7af08d8136dc4232449b8f988b
ms.contentlocale: ja-jp
ms.lasthandoff: 07/18/2017

---

# <a name="total-cost-allocation-method"></a><span data-ttu-id="102c3-104">原価配賦合計の方法</span><span class="sxs-lookup"><span data-stu-id="102c3-104">Total cost allocation method</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="102c3-105">この記事は、原価配賦の合計 (TCA) を使用するためのガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="102c3-105">This article provides guidelines for using total cost allocation (TCA).</span></span> <span data-ttu-id="102c3-106">TCA は、バッチ オーダーの主要式品目および式に定義される連産品の間のコストを計算する方法です。</span><span class="sxs-lookup"><span data-stu-id="102c3-106">TCA is a method of calculating the cost between the main formula item for a batch order and the co-products that are defined for the formula.</span></span>

<span data-ttu-id="102c3-107">原価配賦の合計 (TCA) は、バッチ オーダーの主要式品目および式に定義される連産品の間のコストを計算する方法です。</span><span class="sxs-lookup"><span data-stu-id="102c3-107">Total cost allocation (TCA) is a method of calculating the cost between the main formula item for a batch order and the co-products that are defined for the formula.</span></span> <span data-ttu-id="102c3-108">このメソッドは動的になります。</span><span class="sxs-lookup"><span data-stu-id="102c3-108">This method is dynamic.</span></span> <span data-ttu-id="102c3-109">式品目と連産品に対して完了報告された数量間の加重平均としてコストを計算します。</span><span class="sxs-lookup"><span data-stu-id="102c3-109">It calculates the cost as a weighted average between the quantities that are reported as finished for the formula item and the co-products.</span></span> <span data-ttu-id="102c3-110">TCA を使用すると、バッチ オーダーのコスト配賦を確認する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="102c3-110">When TCA is used, you don't have to review cost allocations for every batch order.</span></span> <span data-ttu-id="102c3-111">TCA を使用しない場合、式計算は既存の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="102c3-111">If TCA isn't used, the formula calculation uses existing functionality.</span></span>

## <a name="using-tca-for-coproducts"></a><span data-ttu-id="102c3-112">連産品の TCA の使用</span><span class="sxs-lookup"><span data-stu-id="102c3-112">Using TCA for coproducts</span></span>
<span data-ttu-id="102c3-113">連産品で TCA を使用するためのガイドラインをいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="102c3-113">Here are some of the guidelines for using TCA for co-products:</span></span>

-   <span data-ttu-id="102c3-114">式バージョンの [**原価配賦の合計**] スライダーを [**はい**] に設定すると、連産品に 0 (ゼロ) より大きいコスト価格を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="102c3-114">If you set the **Total Cost Allocation** slider to **Yes** for a formula version, co-products must have a cost price that is more than 0 (zero).</span></span> <span data-ttu-id="102c3-115">値は同じサイトのコスト バージョンから、またはサイト固有でない式の最初のサイトから取得できます。</span><span class="sxs-lookup"><span data-stu-id="102c3-115">The value can be retrieved from the active cost version for the same site, or for the first site for a formula that isn't site-specific.</span></span> <span data-ttu-id="102c3-116">この条件は、式が承認されると検証されます。</span><span class="sxs-lookup"><span data-stu-id="102c3-116">This condition is validated when the formula is approved.</span></span>

    -   <span data-ttu-id="102c3-117">連産品のコスト配賦率を手動で入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="102c3-117">You don’t need to manually enter cost allocation percentages for co-products.</span></span> <span data-ttu-id="102c3-118">代わりに、システムが自動的に連産品の有効なコスト価格の平均としてコスト配賦率を作成します。</span><span class="sxs-lookup"><span data-stu-id="102c3-118">Instead, the system automatically creates the cost allocation percentage as the average of active cost prices of co-products.</span></span> 
    -   <span data-ttu-id="102c3-119">連産品である非標準コスト品目に標準コストを入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="102c3-119">You don’t need to enter standard cost for non-standard cost items that are co-products.</span></span> <span data-ttu-id="102c3-120">システムには、標準コストと予定コストという 2 つのタイプの原価計算バージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="102c3-120">There are two types of costing versions in the system:standard cost and planned cost</span></span> 
    -   <span data-ttu-id="102c3-121">品目が標準コスト評価法で評価されていない場合、予定コスト バージョンの有効なコスト価格を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="102c3-121">If an item isn’t valuated by the standard cost valuation method, we recommend you use an active cost price in the planned cost version.</span></span> <span data-ttu-id="102c3-122">この価格は、コスト見積に、例えば BOM 計算、生産コスト見積、また在庫評価プロセスの予備価格に使用します。</span><span class="sxs-lookup"><span data-stu-id="102c3-122">This price is used for cost estimation, for example, BOM calculation, production cost estimation, and fallback price in the inventory valuation process.</span></span> 

-   <span data-ttu-id="102c3-123">式バージョンの [**原価配賦の合計**] スライダーを [**はい**] に設定し、次の条件に当てはまる場合、コスト配賦方法は [**TCA**] を使用し、コスト配賦率は不変です。</span><span class="sxs-lookup"><span data-stu-id="102c3-123">If you set the **Total Cost Allocation** slider to **Yes** for the formula version and the following conditions are true, the method of cost allocation is **TCA**, and the percentage of cost allocation is unchanged:</span></span>
    -   <span data-ttu-id="102c3-124">連産品を追加済み。</span><span class="sxs-lookup"><span data-stu-id="102c3-124">You added co-products.</span></span>
    -   <span data-ttu-id="102c3-125">連産品に異なるコスト配賦方法を使用済み。</span><span class="sxs-lookup"><span data-stu-id="102c3-125">You used a different method of cost allocation for the co-products.</span></span>
-   <span data-ttu-id="102c3-126">式バージョンの [**原価配賦の合計**] スライダーを [**いいえ**] に設定し、次の条件に当てはまる場合、コスト配賦方法は [**手動**] に変更され、コスト配賦率は不変です。</span><span class="sxs-lookup"><span data-stu-id="102c3-126">If you set the **Total Cost Allocation** slider to **No** for the formula version and the following conditions are true, the method of cost allocation is changed to **Manual**, and the percentage of cost allocation is unchanged:</span></span>
    -   <span data-ttu-id="102c3-127">連産品を追加済み。</span><span class="sxs-lookup"><span data-stu-id="102c3-127">You added co-products.</span></span>
    -   <span data-ttu-id="102c3-128">コスト配賦率が 0 (ゼロ) を超えます。</span><span class="sxs-lookup"><span data-stu-id="102c3-128">The percentage of cost allocation is more than 0 (zero).</span></span>
-   <span data-ttu-id="102c3-129">正常に式計算を実行する前に、コスト配賦率を見積もる必要があります。</span><span class="sxs-lookup"><span data-stu-id="102c3-129">Before you can successfully perform a formula calculation, you must estimate the percentages of cost allocation.</span></span> <span data-ttu-id="102c3-130">手動で、または [**連産品**] ページの [**見積原価**] オプションを使用してこのステップを完了できます。</span><span class="sxs-lookup"><span data-stu-id="102c3-130">You can complete this step either manually or by using the **Estimate cost** option on the **Co-products** page.</span></span> <span data-ttu-id="102c3-131">**メモ:** [**見積原価**] オプションは [**原価配賦の合計**] スライダーが式バージョンで [**はい**] に設定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="102c3-131">**Note:** The **Estimate cost** option is available only when the **Total Cost Allocation** slider is set to **Yes** for the formula version.</span></span> <span data-ttu-id="102c3-132">完了済として報告されたバッチ オーダーの数量が式に表示される数量と一致する場合、予測配賦を表示できます。</span><span class="sxs-lookup"><span data-stu-id="102c3-132">You can view the expected allocation if the batch order quantities that are reported as finished match quantities that appear on the formula.</span></span>
-   <span data-ttu-id="102c3-133">バッチ オーダーが手動で作成されるか、または計画バッチ オーダーが確定されると、式バージョンの [**原価配賦の合計**] スライダーの値がバッチ オーダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="102c3-133">When a batch order is created manually or a planned batch order is firmed, the value of the **Total Cost Allocation** slider for the formula version is copied to the batch order.</span></span> <span data-ttu-id="102c3-134">ただし、バッチ オーダー上でこの設定は変更できます。</span><span class="sxs-lookup"><span data-stu-id="102c3-134">However, you can change this setting on the batch order.</span></span> <span data-ttu-id="102c3-135">[**原価配賦の合計**] スライダーが式バージョンで [**いいえ**] に設定され、バッチ オーダーで [**はい**] に変更した場合、[**手動**] に設定されていた各行のコスト配賦方法が [**TCA**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="102c3-135">If the **Total Cost Allocation** slider is set to **No** for the formula version and then changed to **Yes** for the batch order, the method of cost allocation for each line that was set to **Manual** is changed to **TCA**.</span></span> <span data-ttu-id="102c3-136">[**なし**] のコスト配賦は不変です。</span><span class="sxs-lookup"><span data-stu-id="102c3-136">A cost allocation of **None** is unchanged.</span></span> <span data-ttu-id="102c3-137">[**原価配賦の合計**] スライダーが式バージョンで [**はい**] に設定され、バッチ オーダーで [**いいえ**] に変更した場合、[**製造**] タイプの各連産品のコスト配賦方法が [**手動**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="102c3-137">If the **Total Cost Allocation** slider is set to **Yes** for the formula version and then changed to **No** for the batch order, the method of cost allocation for each co-product of the **Production** type is changed to **Manual**.</span></span> <span data-ttu-id="102c3-138">コスト配賦率のすべての見積が不変です。</span><span class="sxs-lookup"><span data-stu-id="102c3-138">Any estimated percentage of cost allocation is unchanged.</span></span>
-   <span data-ttu-id="102c3-139">[**連産品原価配賦**] ページに計算済コスト配賦率が表示されます。</span><span class="sxs-lookup"><span data-stu-id="102c3-139">The **Co-product cost allocation** page shows the calculated cost allocation percentage.</span></span> <span data-ttu-id="102c3-140">[**バッチ オーダー**] ページから、このページを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="102c3-140">You can open this page from the **Batch order** page.</span></span> <span data-ttu-id="102c3-141">この情報は、バッチ オーダーで予定済みまたは開始済みの数量と異なると報告された製品および数量に便利です。</span><span class="sxs-lookup"><span data-stu-id="102c3-141">This information is useful when the products and quantities that are reported differ from the scheduled or started quantities on the batch order.</span></span> <span data-ttu-id="102c3-142">コストが完了すると、TCA からの新しい配賦割合は [**連産品原価配賦**] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="102c3-142">When the cost is complete, these new percentage allocations from TCA are shown on the **Co-product cost allocation** page.</span></span>

## <a name="calculating-the-burden-for-byproducts"></a><span data-ttu-id="102c3-143">副産物の負担の計算</span><span class="sxs-lookup"><span data-stu-id="102c3-143">Calculating the burden for byproducts</span></span>
<span data-ttu-id="102c3-144">[**連産品**] ページの [**副産物原価配賦**] フィールドは副産物でのみ使用される列挙子のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="102c3-144">The **By-product cost allocation** field on the **Co-products** page is an enumerator field that is used only for by-products.</span></span> <span data-ttu-id="102c3-145">連産品の場合、このフィールドの値は常に [**なし**] です。</span><span class="sxs-lookup"><span data-stu-id="102c3-145">For co-products, the value of this field is always **None**.</span></span> <span data-ttu-id="102c3-146">副産物明細行の場合、このフィールドにより副産物明細行のコスト量が製品の合計コストにどのように追加されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="102c3-146">For by-product lines, this field determines how the cost amount for the by-product line is added to the total cost of the production.</span></span> <span data-ttu-id="102c3-147">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="102c3-147">The following options are available:</span></span>

-   <span data-ttu-id="102c3-148">[**なし**] ─ この副産物明細行の生産の合計コストにはどの量も追加されません。</span><span class="sxs-lookup"><span data-stu-id="102c3-148">**None** ─ No amount is added to the total cost of the production for this by-product line.</span></span>
-   <span data-ttu-id="102c3-149">[**パーセンテージ**] ─ コスト量は生産で消費される原材料に対する合計コストの割合として計算されます。</span><span class="sxs-lookup"><span data-stu-id="102c3-149">**Percent** ─ The cost amount is calculated as a percentage of the total cost of raw materials that are consumed in the production.</span></span> <span data-ttu-id="102c3-150">計算に使用するパーセンテージは、フィールドで入力されます。</span><span class="sxs-lookup"><span data-stu-id="102c3-150">The percentage that is used for the calculation is entered in the field.</span></span>
-   <span data-ttu-id="102c3-151">[**生産数**] ─ コスト量は製造オーダーの標準的なバッチ サイズあたりの量として計算されます。</span><span class="sxs-lookup"><span data-stu-id="102c3-151">**Per series** ─ The cost amount is calculated as an amount per standard batch size of the production order.</span></span> <span data-ttu-id="102c3-152">この量は、生産の完了報告された数量には依存しません。</span><span class="sxs-lookup"><span data-stu-id="102c3-152">This amount is independent of the reported quantity in the production.</span></span> <span data-ttu-id="102c3-153">計算に使用する量はフィールドに入力されます。</span><span class="sxs-lookup"><span data-stu-id="102c3-153">The amount that is used for the calculation is entered in the field.</span></span>
-   <span data-ttu-id="102c3-154">[**数量あたり**] ─ コスト量は、生産の式品目の報告された数量あたりの量として計算されます。</span><span class="sxs-lookup"><span data-stu-id="102c3-154">**Per quantity** ─ The cost amount is calculated as an amount per reported quantity of the formula item in the production.</span></span> <span data-ttu-id="102c3-155">計算に使用する量はフィールドに入力されます。</span><span class="sxs-lookup"><span data-stu-id="102c3-155">The amount that is used for the calculation is entered in the field.</span></span>




