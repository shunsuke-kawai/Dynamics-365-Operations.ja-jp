---
title: "現物価格とマーキングを使用した LIFO 日付"
description: "後入れ先出し日付 (LIFO 日付) は、LIFO 原則に基づく在庫モデルです。 在庫からの出庫は、在庫トランザクションの日付に基づいて在庫への最後の入庫を対象として決済されます。 払出より前の入庫が存在しない場合、LIFO 日付を使用することで、払出の日付より後に発生する入庫を対象に払出が決済されます。 同じ日付の複数の払出は、最終払出、最後の受入の順に決済される場合があります。"
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 51592
ms.assetid: d9f13274-3268-444f-85c8-b686fd39286d
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 116d2f34c0317f3246b8d9c6569430603e2cd2c6
ms.contentlocale: ja-jp
ms.lasthandoff: 07/18/2017

---

# <a name="lifo-date-with-physical-value-and-marking"></a><span data-ttu-id="8305c-106">現物価格とマーキングを使用した LIFO 日付</span><span class="sxs-lookup"><span data-stu-id="8305c-106">LIFO Date with physical value and marking</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="8305c-107">後入れ先出し日付 (LIFO 日付) は、LIFO 原則に基づく在庫モデルです。</span><span class="sxs-lookup"><span data-stu-id="8305c-107">Last in, First out Date (LIFO Date) is an inventory model based on the LIFO principle.</span></span> <span data-ttu-id="8305c-108">在庫からの出庫は、在庫トランザクションの日付に基づいて在庫への最後の入庫を対象として決済されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-108">Issues from inventory are settled against the last receipts into inventory based on the date of the inventory transaction.</span></span> <span data-ttu-id="8305c-109">払出より前の入庫が存在しない場合、LIFO 日付を使用することで、払出の日付より後に発生する入庫を対象に払出が決済されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-109">By using LIFO Date, if there is no receipt before the issue, the issue is settled against any receipts that occur after the date of the issue.</span></span> <span data-ttu-id="8305c-110">同じ日付の複数の払出は、最終払出、最後の受入の順に決済される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8305c-110">Several issues on the same date may be settled in the order of last issue, last receipt.</span></span> 

<span data-ttu-id="8305c-111">後入れ先出し日付 (LIFO 日付) の在庫モデルを使用すると、払出より前の入庫が存在しない場合、払出の日付より後に発生する入庫を対象に払出が決済されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-111">When you use the Last in, First out Date (LIFO Date) inventory model, if there is no receipt before the issue, the issue is settled against any receipts that occur after the date of the issue.</span></span> <span data-ttu-id="8305c-112">同じ日付の複数の払出は、最終払出、最後の受入の順に決済される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8305c-112">Several issues on the same date can be settled in the order of last issue, last receipt.</span></span> <span data-ttu-id="8305c-113">LIFO 日付を使用する場合、LIFO 日付ルールを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8305c-113">When you use LIFO Date, you don't have to use the LIFO Date rule.</span></span> <span data-ttu-id="8305c-114">代わりに、特定の品目の受入が特定の払出を対象に決済されるように、在庫トランザクションをマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8305c-114">Instead, you can mark inventory transactions so that a specific item receipt is settled against a specific issue.</span></span> 

<span data-ttu-id="8305c-115">LIFO 日付在庫モデルを使用する場合は、在庫原価計算を定期的に行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8305c-115">We recommend a periodic inventory closing when you use the LIFO Date inventory model.</span></span> 

<span data-ttu-id="8305c-116">次の例では、3 つの異なる構成で LIFO 日付を使用した場合の影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="8305c-116">The following examples show the effect of using LIFO Date in three configurations:</span></span>

-   <span data-ttu-id="8305c-117">**現物価格を含める**オプションを指定しない LIFO 日付</span><span class="sxs-lookup"><span data-stu-id="8305c-117">LIFO Date without the **Include physical value** option</span></span>
-   <span data-ttu-id="8305c-118">**現物価格を含める**オプションを指定した LIFO 日付</span><span class="sxs-lookup"><span data-stu-id="8305c-118">LIFO Date with the **Include physical value** option</span></span>
-   <span data-ttu-id="8305c-119">マーキングのある LIFO 日付</span><span class="sxs-lookup"><span data-stu-id="8305c-119">LIFO Date with marking</span></span>

## <a name="lifo-date-without-the-include-physical-value-option"></a><span data-ttu-id="8305c-120">[現物価格を含める] オプションを指定しない LIFO 日付</span><span class="sxs-lookup"><span data-stu-id="8305c-120">LIFO Date without the Include physical value option</span></span>
<span data-ttu-id="8305c-121">この例では、品目モデル グループが現物価格を含むようにマークされていません。</span><span class="sxs-lookup"><span data-stu-id="8305c-121">In this example, the item model group isn't marked to include physical value.</span></span> <span data-ttu-id="8305c-122">次の図は、これらのトランザクションについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-122">The illustration that follows shows these transactions:</span></span>

-   <span data-ttu-id="8305c-123">1a。</span><span class="sxs-lookup"><span data-stu-id="8305c-123">1a.</span></span> <span data-ttu-id="8305c-124">原価がそれぞれ USD 10.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-124">Inventory physical receipt for a quantity of 1 at a cost of USD 10.00 each.</span></span>
-   <span data-ttu-id="8305c-125">1b.</span><span class="sxs-lookup"><span data-stu-id="8305c-125">1b.</span></span> <span data-ttu-id="8305c-126">原価がそれぞれ USD 10.00 の数量 1 に対する在庫財務入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-126">Inventory financial receipt for a quantity of 1 at a cost of USD 10.00 each.</span></span>
-   <span data-ttu-id="8305c-127">2a.</span><span class="sxs-lookup"><span data-stu-id="8305c-127">2a.</span></span> <span data-ttu-id="8305c-128">原価がそれぞれ USD 20.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-128">Inventory physical receipt for a quantity of 1 at a cost of USD 20.00 each.</span></span>
-   <span data-ttu-id="8305c-129">2b.</span><span class="sxs-lookup"><span data-stu-id="8305c-129">2b.</span></span> <span data-ttu-id="8305c-130">原価がそれぞれ USD 20.00 の数量 1 に対する在庫財務入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-130">Inventory financial receipt for a quantity of 1 at a cost of USD 20.00 each.</span></span>
-   <span data-ttu-id="8305c-131">3a.</span><span class="sxs-lookup"><span data-stu-id="8305c-131">3a.</span></span> <span data-ttu-id="8305c-132">原価がそれぞれ USD 25.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-132">Inventory physical receipt for a quantity of 1 at a cost of USD 25.00 each.</span></span>
-   <span data-ttu-id="8305c-133">4a。</span><span class="sxs-lookup"><span data-stu-id="8305c-133">4a.</span></span> <span data-ttu-id="8305c-134">原価価格がそれぞれ USD 15.00 の数量が 1 に対する在庫現物払出 (財務更新済トランザクションの移動平均)</span><span class="sxs-lookup"><span data-stu-id="8305c-134">Inventory physical issue for a quantity of 1 at a cost price of USD 15.00 (running average of financially updated transactions).</span></span>
-   <span data-ttu-id="8305c-135">4b。</span><span class="sxs-lookup"><span data-stu-id="8305c-135">4b.</span></span> <span data-ttu-id="8305c-136">原価価格がそれぞれ USD 15.00 の数量が 1 に対する在庫財務払出 (財務更新済トランザクションの移動平均)</span><span class="sxs-lookup"><span data-stu-id="8305c-136">Inventory financial issue for a quantity of 1 at a cost price of USD 15.00 (running average of financially updated transactions).</span></span>
-   <span data-ttu-id="8305c-137">5a。</span><span class="sxs-lookup"><span data-stu-id="8305c-137">5a.</span></span> <span data-ttu-id="8305c-138">原価がそれぞれ USD 30.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-138">Inventory physical receipt for a quantity of 1 at a cost of USD 30.00 each.</span></span>
-   <span data-ttu-id="8305c-139">5b。</span><span class="sxs-lookup"><span data-stu-id="8305c-139">5b.</span></span> <span data-ttu-id="8305c-140">原価がそれぞれ USD 30.00 の数量 1 に対する在庫財務入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-140">Inventory financial receipt for a quantity of 1 at a cost of USD 30.00 each.</span></span>
-   6. <span data-ttu-id="8305c-141">在庫決算が行われました。</span><span class="sxs-lookup"><span data-stu-id="8305c-141">Inventory close is performed.</span></span> <span data-ttu-id="8305c-142">LIFO 日付法に基づいて、最後の財務更新済払出が最後の財務更新済入庫に対して日付によって決済されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-142">Based on the LIFO Date method, the last financially updated issue will be settled against the last financially updated receipt by date.</span></span> <span data-ttu-id="8305c-143">USD 5.00 の調整が払出トランザクションに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-143">An adjustment of USD 5.00 will be made on the issue transaction.</span></span> <span data-ttu-id="8305c-144">これらのトランザクションは相互に決済されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-144">These transactions will be settled against each other.</span></span>

<span data-ttu-id="8305c-145">新しい移動平均原価価格は、USD 15.00 での財務更新済トランザクションの平均を反映しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-145">The new running average cost price reflects the average of the financially updated transactions at USD 15.00.</span></span> 

<span data-ttu-id="8305c-146">次の図は、**現物価格を含める**オプションを使用しない場合の LIFO 日付在庫モデルの影響について説明しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-146">The following illustration shows the effects of the LIFO Date inventory model when the **Include physical value** option isn't used.</span></span> <span data-ttu-id="8305c-147">![[現物価格を含める] がオンの場合の LIFO 日付](./media/lifodatewithoutincludephysicalvalue.gif)</span><span class="sxs-lookup"><span data-stu-id="8305c-147">![LIFO Date with Include Physical Value](./media/lifodatewithoutincludephysicalvalue.gif)</span></span> 

<span data-ttu-id="8305c-148">**図の説明**</span><span class="sxs-lookup"><span data-stu-id="8305c-148">**Key to the diagram**</span></span>

-   <span data-ttu-id="8305c-149">在庫トランザクションは、縦の矢印で表されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-149">Inventory transactions are represented by vertical arrows.</span></span>
-   <span data-ttu-id="8305c-150">在庫への入庫は、タイムラインの上の縦の矢印で表されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-150">Receipts into inventory are represented by vertical arrows above the timeline.</span></span>
-   <span data-ttu-id="8305c-151">在庫からの払出は、タイムラインの下の縦の矢印で表されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-151">Issues out of inventory are represented by vertical arrows below the timeline.</span></span>
-   <span data-ttu-id="8305c-152">各縦矢印の上 (または下) には、在庫トランザクションの値が Quantity@Unitprice の形式で指定されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-152">Above (or below) each vertical arrow, the value of the inventory transaction is specified in the format Quantity@Unitprice.</span></span>
-   <span data-ttu-id="8305c-153">かっこで囲まれた在庫トランザクションの値は、在庫トランザクションが在庫に現物転記されることを示します。</span><span class="sxs-lookup"><span data-stu-id="8305c-153">An inventory transaction value that is enclosed in parentheses indicates that the inventory transaction is physically posted into inventory.</span></span>
-   <span data-ttu-id="8305c-154">かっこで囲まれていない在庫トランザクションの値は、在庫トランザクションが在庫に財務転記されることを示します。</span><span class="sxs-lookup"><span data-stu-id="8305c-154">An inventory transaction value that isn't enclosed in parentheses indicates that the inventory transaction is financially posted into inventory.</span></span>
-   <span data-ttu-id="8305c-155">個々の新しい入庫トランザクションまたは払出トランザクションは、新しいラベルで示されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-155">Each new receipt or issue transaction is designated by a new label.</span></span>
-   <span data-ttu-id="8305c-156">各縦矢印には、*1a* のような連続した ID のラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="8305c-156">Each vertical arrow is labeled with a sequential identifier, such as *1a*.</span></span> <span data-ttu-id="8305c-157">ID は、タイムラインでの在庫トランザクション転記の順序を示しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-157">The identifiers indicate the order of inventory transaction postings in the timeline.</span></span>
-   <span data-ttu-id="8305c-158">在庫原価計算は、赤い縦の点線と*在庫原価計算*のラベルで示されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-158">Inventory closings are represented by a red vertical dashed line and the label *Inventory Close*.</span></span>
-   <span data-ttu-id="8305c-159">在庫原価計算によって実行される決済は、入庫から払出へと斜めに向かう赤い点線矢印で表されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-159">Settlements that are performed by inventory close are represented by red diagonal dashed arrows that go from a receipt to an issue.</span></span>

## <a name="lifo-date-with-the-include-physical-value-option"></a><span data-ttu-id="8305c-160">[現物価格を含める] オプションを使用した LIFO 日付</span><span class="sxs-lookup"><span data-stu-id="8305c-160">LIFO Date with the Include physical value option</span></span>
<span data-ttu-id="8305c-161">**品目モデル グループ** ページで、品目の**現物価格を含める**チェック ボックスをオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8305c-161">You can select the **Include physical value** check box for an item on the **Item model groups** page.</span></span> <span data-ttu-id="8305c-162">この場合、システムは現物入庫トランザクションと財務入庫トランザクションの両方を使用して移動平均原価価格を計算します。</span><span class="sxs-lookup"><span data-stu-id="8305c-162">In this case, the system uses both physical and financial receipt transactions to calculate the running average cost price.</span></span> <span data-ttu-id="8305c-163">該当する場合は、現物更新済払出トランザクションに対する調整も行われます。</span><span class="sxs-lookup"><span data-stu-id="8305c-163">Where applicable, the system also makes adjustments to the physically updated issue transaction.</span></span> <span data-ttu-id="8305c-164">**現物価格を含める**チェック ボックスがオフの場合、LIFO 日付在庫モデルを使用した在庫原価計算では、財務更新済のトランザクションに対してのみ決済が行われます。</span><span class="sxs-lookup"><span data-stu-id="8305c-164">When the **Include physical value** check box is cleared, inventory close that uses the LIFO Date inventory model makes settlements only to transactions that are financially updated.</span></span> 

<span data-ttu-id="8305c-165">この例では、品目モデル グループが現物価格を含むようにマークされています。</span><span class="sxs-lookup"><span data-stu-id="8305c-165">In this example, the item model group is marked to include physical value.</span></span> 

<span data-ttu-id="8305c-166">次の図は、これらのトランザクションについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-166">The illustration that follows shows these transactions:</span></span>

-   <span data-ttu-id="8305c-167">1a。</span><span class="sxs-lookup"><span data-stu-id="8305c-167">1a.</span></span> <span data-ttu-id="8305c-168">原価がそれぞれ USD 10.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-168">Inventory physical receipt for a quantity of 1 at a cost of USD 10.00 each.</span></span>
-   <span data-ttu-id="8305c-169">1b.</span><span class="sxs-lookup"><span data-stu-id="8305c-169">1b.</span></span> <span data-ttu-id="8305c-170">原価がそれぞれ USD 10.00 の数量 1 に対する在庫財務入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-170">Inventory financial receipt for a quantity of 1 at a cost of USD 10.00 each.</span></span>
-   <span data-ttu-id="8305c-171">2a.</span><span class="sxs-lookup"><span data-stu-id="8305c-171">2a.</span></span> <span data-ttu-id="8305c-172">原価がそれぞれ USD 20.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-172">Inventory physical receipt for a quantity of 1 at a cost of USD 20.00 each.</span></span>
-   <span data-ttu-id="8305c-173">2b.</span><span class="sxs-lookup"><span data-stu-id="8305c-173">2b.</span></span> <span data-ttu-id="8305c-174">原価がそれぞれ USD 20.00 の数量 1 に対する在庫財務入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-174">Inventory financial receipt for a quantity of 1 at a cost of USD 20.00 each.</span></span>
-   <span data-ttu-id="8305c-175">3a.</span><span class="sxs-lookup"><span data-stu-id="8305c-175">3a.</span></span> <span data-ttu-id="8305c-176">原価がそれぞれ USD 25.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-176">Inventory physical receipt for a quantity of 1 at a cost of USD 25.00 each.</span></span>
-   <span data-ttu-id="8305c-177">4a。</span><span class="sxs-lookup"><span data-stu-id="8305c-177">4a.</span></span> <span data-ttu-id="8305c-178">原価価格がそれぞれ USD 18.33 の数量 1 に対する在庫現物払出 (財務更新済トランザクションの移動平均)</span><span class="sxs-lookup"><span data-stu-id="8305c-178">Inventory physical issue for a quantity of 1 at a cost price of USD 18.33 each (running average of financially updated transactions).</span></span>
-   <span data-ttu-id="8305c-179">4b。</span><span class="sxs-lookup"><span data-stu-id="8305c-179">4b.</span></span> <span data-ttu-id="8305c-180">原価価格がそれぞれ USD 18.33 の数量 1 に対する在庫財務払出 (財務更新済トランザクションの移動平均)</span><span class="sxs-lookup"><span data-stu-id="8305c-180">Inventory financial issue for a quantity of 1 at a cost price USD 18.33 each (running average of financially updated transactions).</span></span>
-   <span data-ttu-id="8305c-181">5a。</span><span class="sxs-lookup"><span data-stu-id="8305c-181">5a.</span></span> <span data-ttu-id="8305c-182">原価がそれぞれ USD 30.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-182">Inventory physical receipt for a quantity of 1 at a cost of USD 30.00 each.</span></span>
-   <span data-ttu-id="8305c-183">5b。</span><span class="sxs-lookup"><span data-stu-id="8305c-183">5b.</span></span> <span data-ttu-id="8305c-184">原価がそれぞれ USD 30.00 の数量 1 に対する在庫財務入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-184">Inventory financial receipt for a quantity of 1 at a cost of USD 30.00 each.</span></span>
-   6. <span data-ttu-id="8305c-185">在庫決算が行われました。</span><span class="sxs-lookup"><span data-stu-id="8305c-185">Inventory close is performed.</span></span> <span data-ttu-id="8305c-186">LIFO 日付法に基づき、日付によって、最後の更新済払出が最後の更新済入庫に対して調整または決済されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-186">Based on the LIFO Date method, the last updated issue will be adjusted or settled against the last updated receipt by date.</span></span> <span data-ttu-id="8305c-187">財務入庫トランザクションが現物更新済トランザクションに対して調整されるので、これらのトランザクションは相互には決済されません。</span><span class="sxs-lookup"><span data-stu-id="8305c-187">These transactions will not be settled by each other, because the financial receipt transaction is adjusted to a physical update transaction.</span></span> <span data-ttu-id="8305c-188">代わりに、USD 6.67 の調整だけが払出トランザクションに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="8305c-188">Instead, only an adjustment of USD 6.67 will be made on the issue transaction.</span></span>

<span data-ttu-id="8305c-189">新しい移動平均原価価格は、USD 20.00 での財務更新済トランザクションの平均を反映しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-189">The new running average cost price reflects the average of the financially updated transactions at USD 20.00.</span></span> 

<span data-ttu-id="8305c-190">次の図は、**現物価格を含める**オプションを使用した LIFO 在庫モデルの影響について説明しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-190">The following illustration shows the effects of the LIFO inventory model when the **Include physical value** option is used.</span></span> <span data-ttu-id="8305c-191">![[現物価格を含める] がオンの場合の LIFO 日付](./media/lifodatewithincludephysicalvalue.gif)</span><span class="sxs-lookup"><span data-stu-id="8305c-191">![LIFO Date with Include Physical Value](./media/lifodatewithincludephysicalvalue.gif)</span></span> 

<span data-ttu-id="8305c-192">**図の説明**</span><span class="sxs-lookup"><span data-stu-id="8305c-192">**Key to the diagram**</span></span>

-   <span data-ttu-id="8305c-193">在庫トランザクションは、縦の矢印で表されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-193">Inventory transactions are represented by vertical arrows.</span></span>
-   <span data-ttu-id="8305c-194">在庫への入庫は、タイムラインの上の縦の矢印で表されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-194">Receipts into inventory are represented by vertical arrows above the timeline.</span></span>
-   <span data-ttu-id="8305c-195">在庫からの払出は、タイムラインの下の縦の矢印で表されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-195">Issues out of inventory are represented by vertical arrows below the timeline.</span></span>
-   <span data-ttu-id="8305c-196">各縦矢印の上 (または下) には、在庫トランザクションの値が Quantity@Unitprice の形式で指定されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-196">Above (or below) each vertical arrow, the value of the inventory transaction is specified in the format Quantity@Unitprice.</span></span>
-   <span data-ttu-id="8305c-197">かっこで囲まれた在庫トランザクションの値は、在庫トランザクションが在庫に現物転記されることを示します。</span><span class="sxs-lookup"><span data-stu-id="8305c-197">An inventory transaction value that is enclosed in parentheses indicates that the inventory transaction is physically posted into inventory.</span></span>
-   <span data-ttu-id="8305c-198">かっこで囲まれていない在庫トランザクションの値は、在庫トランザクションが在庫に財務転記されることを示します。</span><span class="sxs-lookup"><span data-stu-id="8305c-198">An inventory transaction value that isn't enclosed in parentheses indicates that the inventory transaction is financially posted into inventory.</span></span>
-   <span data-ttu-id="8305c-199">個々の新しい入庫トランザクションまたは払出トランザクションは、新しいラベルで示されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-199">Each new receipt or issue transaction is designated by a new label.</span></span>
-   <span data-ttu-id="8305c-200">各縦矢印には、*1a* のような連続した ID のラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="8305c-200">Each vertical arrow is labeled with a sequential identifier, such as *1a*.</span></span> <span data-ttu-id="8305c-201">ID は、タイムラインでの在庫トランザクション転記の順序を示しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-201">The identifiers indicate the order of inventory transaction postings in the timeline.</span></span>
-   <span data-ttu-id="8305c-202">在庫原価計算は、赤い縦の点線と*在庫原価計算*のラベルで示されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-202">Inventory closings are represented by a red vertical dashed line and the label *Inventory Close*.</span></span>
-   <span data-ttu-id="8305c-203">在庫原価計算によって実行される決済は、入庫から払出へと斜めに向かう赤い点線矢印で表されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-203">Settlements that are performed by inventory close are represented by red diagonal dashed arrows that go from a receipt to an issue.</span></span>

## <a name="lifo-date-with-marking"></a><span data-ttu-id="8305c-204">マーキングを使用した LIFO 日付</span><span class="sxs-lookup"><span data-stu-id="8305c-204">LIFO Date with marking</span></span>
<span data-ttu-id="8305c-205">マーキングの処理を使用することで、払出トランザクションを入庫トランザクションにリンクまたはマークできます。</span><span class="sxs-lookup"><span data-stu-id="8305c-205">Marking is a process that lets you link, or mark, an issue transaction to a receipt transaction.</span></span> <span data-ttu-id="8305c-206">マーキングは、トランザクションが転記される前でも後でも可能です。</span><span class="sxs-lookup"><span data-stu-id="8305c-206">Marking can occur either before or after a transaction is posted.</span></span> <span data-ttu-id="8305c-207">トランザクションを転記するとき、または在庫原価計算を実行するときに、在庫の原価を正確にする必要がある場合は、マーキングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8305c-207">You can use marking when you want to be sure of the exact cost of inventory when the transaction is posted or the inventory close is performed.</span></span> 

<span data-ttu-id="8305c-208">たとえば、顧客サービス部門が重要な顧客から急ぎの注文を受けたとします。</span><span class="sxs-lookup"><span data-stu-id="8305c-208">For example, the Customer Service department accepted a rush order from an important customer.</span></span> <span data-ttu-id="8305c-209">急ぎの注文なので、顧客の要求に対応するには、その品目に対する支払を高くする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8305c-209">Because this order is a rush order, you will have to pay more for this item in order to fulfill your customer’s request.</span></span> <span data-ttu-id="8305c-210">この販売注文請求書の利ざや、つまり、売却済商品の原価 (COGS) に在庫品目の原価が確実に反映されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8305c-210">You must make sure that the cost of this inventory item is reflected in the margin, or cost of goods sold (COGS), for this sales order invoice.</span></span> 

<span data-ttu-id="8305c-211">発注書を転記するとき、在庫は USD 120.00 の原価で入庫されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-211">When the purchase order is posted, the inventory is received at a cost of USD 120.00.</span></span> <span data-ttu-id="8305c-212">梱包明細または請求書を転記する前に販売注文文書を発注書に対してマークすると、COGS は、品目の現在の移動平均原価ではなく USD 120.00 になります。</span><span class="sxs-lookup"><span data-stu-id="8305c-212">If this sales order document is marked to the purchase order before the packing slip or invoice is posted, the COGS will be USD 120.00, not the current running average cost for the item.</span></span> <span data-ttu-id="8305c-213">マーキングが発生する前に販売注文梱包明細または請求書が転記されると、COGS は移動平均原価価格で転記されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-213">If the sales order packing slip or invoice is posted before the marking occurs, the COGS will be posted at the running average cost price.</span></span> 

<span data-ttu-id="8305c-214">在庫原価計算を実行する前でも、これら 2 つのトランザクションは相互にマークできます。</span><span class="sxs-lookup"><span data-stu-id="8305c-214">Before inventory close is performed, these two transactions can still be marked to each other.</span></span> 

<span data-ttu-id="8305c-215">たとえば、受入トランザクションは払出トランザクションにマークされています。</span><span class="sxs-lookup"><span data-stu-id="8305c-215">For example, a receipt transaction is marked for an issue transaction.</span></span> <span data-ttu-id="8305c-216">その場合、品目の品目モデル グループに対して定義されている評価方法は無視され、システムがこれらのトランザクションを相互に決済します。</span><span class="sxs-lookup"><span data-stu-id="8305c-216">In this case, the valuation method that is defined in the item’s item model group is disregarded, and the system settles these transactions against each other.</span></span> 

<span data-ttu-id="8305c-217">トランザクションが転記される前に払出トランザクションを入庫にマークするには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="8305c-217">You can mark an issue transaction to a receipt before the transaction is posted.</span></span> <span data-ttu-id="8305c-218">**販売注文の詳細**ページの販売注文明細行から、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8305c-218">You can do this from a sales order line on the **Sales order details** page.</span></span> <span data-ttu-id="8305c-219">**マーキング** ページで未処理入庫トランザクションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8305c-219">You can view the open receipt transactions on the **Marking** page.</span></span> 

<span data-ttu-id="8305c-220">トランザクションが転記された後に払出トランザクションを入庫にマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8305c-220">You can also mark an issue transaction to a receipt after the transaction is posted.</span></span> <span data-ttu-id="8305c-221">転記済在庫調整仕訳帳からの在庫品目の未処理入庫トランザクションについて、払出トランザクションに一致またはマークできます。</span><span class="sxs-lookup"><span data-stu-id="8305c-221">You can match or mark an issue transaction for an open receipt transaction for an inventoried item from a posted inventory adjustment journal.</span></span> 

<span data-ttu-id="8305c-222">次の図は、これらのトランザクションについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-222">The illustration that follows shows these transactions:</span></span>

-   <span data-ttu-id="8305c-223">1a。</span><span class="sxs-lookup"><span data-stu-id="8305c-223">1a.</span></span> <span data-ttu-id="8305c-224">原価がそれぞれ USD 10.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-224">Inventory physical receipt for a quantity of 1 at a cost of USD 10.00 each.</span></span>
-   <span data-ttu-id="8305c-225">1b.</span><span class="sxs-lookup"><span data-stu-id="8305c-225">1b.</span></span> <span data-ttu-id="8305c-226">原価がそれぞれ USD 10.00 の数量 1 に対する在庫財務入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-226">Inventory financial receipt for a quantity of 1 at a cost of USD 10.00 each.</span></span>
-   <span data-ttu-id="8305c-227">2a.</span><span class="sxs-lookup"><span data-stu-id="8305c-227">2a.</span></span> <span data-ttu-id="8305c-228">原価がそれぞれ USD 20.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-228">Inventory physical receipt for a quantity of 1 at a cost of USD 20.00 each.</span></span>
-   <span data-ttu-id="8305c-229">2b.</span><span class="sxs-lookup"><span data-stu-id="8305c-229">2b.</span></span> <span data-ttu-id="8305c-230">原価がそれぞれ USD 20.00 の数量 1 に対する在庫財務入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-230">Inventory financial receipt for a quantity of 1 at a cost of USD 20.00 each.</span></span>
-   <span data-ttu-id="8305c-231">3a.</span><span class="sxs-lookup"><span data-stu-id="8305c-231">3a.</span></span> <span data-ttu-id="8305c-232">原価がそれぞれ USD 25.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-232">Inventory physical receipt for a quantity of 1 at a cost of USD 25.00 each.</span></span>
-   <span data-ttu-id="8305c-233">4a.</span><span class="sxs-lookup"><span data-stu-id="8305c-233">4a.</span></span> <span data-ttu-id="8305c-234">原価がそれぞれ USD 30.00 の数量 1 に対する在庫現物入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-234">Inventory physical receipt for a quantity of 1 at a cost of USD 30.00 each.</span></span>
-   <span data-ttu-id="8305c-235">4b.</span><span class="sxs-lookup"><span data-stu-id="8305c-235">4b.</span></span> <span data-ttu-id="8305c-236">原価がそれぞれ USD 30.00 の数量 1 に対する在庫財務入庫</span><span class="sxs-lookup"><span data-stu-id="8305c-236">Inventory financial receipt for a quantity of 1 at a cost of USD 30.00 each.</span></span>
-   <span data-ttu-id="8305c-237">5a。</span><span class="sxs-lookup"><span data-stu-id="8305c-237">5a.</span></span> <span data-ttu-id="8305c-238">原価価格がそれぞれ USD 21.25 の数量が 1 に対する在庫現物払出 (財務および現物更新済トランザクションの移動平均)</span><span class="sxs-lookup"><span data-stu-id="8305c-238">Inventory physical issue for a quantity of 1 at a cost price of USD 21.25 each (running average of financial and physical updated transactions).</span></span>
-   <span data-ttu-id="8305c-239">5b。</span><span class="sxs-lookup"><span data-stu-id="8305c-239">5b.</span></span> <span data-ttu-id="8305c-240">トランザクションが転記される前に、数量 1 に対する在庫財務払出を、在庫入庫 2b にマークします。</span><span class="sxs-lookup"><span data-stu-id="8305c-240">Inventory financial issue for a quantity of 1 is marked to inventory receipt 2b before the transaction is posted.</span></span> <span data-ttu-id="8305c-241">このトランザクションは、原価価格がそれぞれ USD 20.00 で転記されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-241">This transaction is posted with a cost price of USD 20.00 each.</span></span>
-   <span data-ttu-id="8305c-242">6a。</span><span class="sxs-lookup"><span data-stu-id="8305c-242">6a.</span></span> <span data-ttu-id="8305c-243">原価価格がそれぞれ USD 21.25 の数量 1 に対する在庫現物払出</span><span class="sxs-lookup"><span data-stu-id="8305c-243">Inventory physical issue for a quantity of 1 at a cost price of USD 21.25 each.</span></span>
-   7. <span data-ttu-id="8305c-244">在庫決算が行われました。</span><span class="sxs-lookup"><span data-stu-id="8305c-244">Inventory close is performed.</span></span> <span data-ttu-id="8305c-245">財務更新済の 先入れ先出し (FIFO) トランザクションが既存の入庫にマークされているため、これらのトランザクションは相互に決済され、調整は行われません。</span><span class="sxs-lookup"><span data-stu-id="8305c-245">Because the financially updated First in, First out (FIFO) transaction is marked to an existing receipt, these transactions are settled to each other, and no adjustment is made.</span></span>

<span data-ttu-id="8305c-246">新しい移動平均原価価格は、USD 27.50 での財務および現物更新済トランザクションの平均を反映しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-246">The new running average cost price reflects the average of the financially and physically updated transactions at USD 27.50.</span></span> 

<span data-ttu-id="8305c-247">次の図は、払出と入庫の間でマーキングを使用するときの LIFO 在庫モデルの影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-247">The following illustration shows the effects of the LIFO inventory model when marking between issues and receipts is used.</span></span> ![[マーキング] が有効な場合の LIFO 日付](./media/lifodatewithmarking.gif) 

<span data-ttu-id="8305c-249">**図の説明**</span><span class="sxs-lookup"><span data-stu-id="8305c-249">**Key to the diagram**</span></span>

-   <span data-ttu-id="8305c-250">在庫トランザクションは、縦の矢印で表されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-250">Inventory transactions are represented by vertical arrows.</span></span>
-   <span data-ttu-id="8305c-251">在庫への入庫は、タイムラインの上の縦の矢印で表されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-251">Receipts into inventory are represented by vertical arrows above the timeline.</span></span>
-   <span data-ttu-id="8305c-252">在庫からの払出は、タイムラインの下の縦の矢印で表されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-252">Issues out of inventory are represented by vertical arrows below the timeline.</span></span>
-   <span data-ttu-id="8305c-253">各縦矢印の上 (または下) には、在庫トランザクションの値が Quantity@Unitprice の形式で指定されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-253">Above (or below) each vertical arrow, the value of the inventory transaction is specified in the format Quantity@Unitprice.</span></span>
-   <span data-ttu-id="8305c-254">かっこで囲まれた在庫トランザクションの値は、在庫トランザクションが在庫に現物転記されることを示します。</span><span class="sxs-lookup"><span data-stu-id="8305c-254">An inventory transaction value that is enclosed in parentheses indicates that the inventory transaction is physically posted into inventory.</span></span>
-   <span data-ttu-id="8305c-255">かっこで囲まれていない在庫トランザクションの値は、在庫トランザクションが在庫に財務転記されることを示します。</span><span class="sxs-lookup"><span data-stu-id="8305c-255">An inventory transaction value that isn't enclosed in parentheses indicates that the inventory transaction is financially posted into inventory.</span></span>
-   <span data-ttu-id="8305c-256">個々の新しい入庫トランザクションまたは払出トランザクションは、新しいラベルで示されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-256">Each new receipt or issue transaction is designated by a new label.</span></span>
-   <span data-ttu-id="8305c-257">各縦矢印には、*1a* のような連続した ID のラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="8305c-257">Each vertical arrow is labeled with a sequential identifier, such as *1a*.</span></span> <span data-ttu-id="8305c-258">ID は、タイムラインでの在庫トランザクション転記の順序を示しています。</span><span class="sxs-lookup"><span data-stu-id="8305c-258">The identifiers indicate the order of inventory transaction postings in the timeline.</span></span>
-   <span data-ttu-id="8305c-259">在庫原価計算は、赤い縦の点線と*在庫原価計算*のラベルで示されています。</span><span class="sxs-lookup"><span data-stu-id="8305c-259">Inventory closings are represented by a red vertical dashed line and the label *Inventory Close*.</span></span>
-   <span data-ttu-id="8305c-260">在庫原価計算によって実行される決済は、入庫から払出へと斜めに向かう赤い点線矢印で表されます。</span><span class="sxs-lookup"><span data-stu-id="8305c-260">Settlements that are performed by inventory close are represented by red diagonal dashed arrows that go from a receipt to an issue.</span></span>




