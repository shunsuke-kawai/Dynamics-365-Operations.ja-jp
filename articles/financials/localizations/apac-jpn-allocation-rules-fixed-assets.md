---
title: "固定資産配賦ルール"
description: "日本では、固定資産は管理部門に登録され、減価償却量は使用部門間で割り当てられる必要があります。 減価償却金額を割合で複数の財務分析コードに割り当てる配賦ルールを設定できます。 この記事は、固定資産配賦ルールについてよく寄せられる質問に回答します。"
author: RichardLuan
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetAllocationRuleSetup_CN
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 10194
ms.search.region: Japan
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 71bb691b45520e729e339c57e262d7207d41e46d
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="allocation-rules-for-fixed-assets"></a><span data-ttu-id="6e752-105">固定資産配賦ルール</span><span class="sxs-lookup"><span data-stu-id="6e752-105">Allocation rules for fixed assets</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6e752-106">日本では、固定資産は管理部門に登録され、減価償却量は使用部門間で割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e752-106">In Japan, a fixed asset is registered under an administrative department, and the depreciation amount must be allocated among the usage departments.</span></span> <span data-ttu-id="6e752-107">減価償却金額を割合で複数の財務分析コードに割り当てる配賦ルールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6e752-107">You can set up an allocation rule to allocate depreciation amounts to multiple financial dimensions by percentage.</span></span> <span data-ttu-id="6e752-108">この記事は、固定資産配賦ルールについてよく寄せられる質問に回答します。</span><span class="sxs-lookup"><span data-stu-id="6e752-108">This article answers some frequently asked questions about the allocation rules for fixed assets.</span></span>

<span data-ttu-id="6e752-109">自分の法人の分析コードに固定資産の減価償却費を配賦する配賦ルールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6e752-109">You can set up an allocation rule to allocate depreciation costs for a fixed asset to a dimension of your legal entity.</span></span> <span data-ttu-id="6e752-110">固定資産は、部門、コスト センターなどの、複数の分析コードのサービスに投入できます。</span><span class="sxs-lookup"><span data-stu-id="6e752-110">Fixed assets can be put into service for multiple dimensions, such as departments or cost centers.</span></span> <span data-ttu-id="6e752-111">固定資産の減価償却時に、減価償却費は相手勘定に転記されます。</span><span class="sxs-lookup"><span data-stu-id="6e752-111">When you depreciate a fixed asset, the depreciation cost is posted to an offset account.</span></span> <span data-ttu-id="6e752-112">配賦ルールの設定によって、固定資産の減価償却費を法人の複数の分析コード間で分配できます。</span><span class="sxs-lookup"><span data-stu-id="6e752-112">By setting up an allocation rule, you can share the depreciation cost of the fixed asset between multiple dimensions of your legal entity.</span></span>

## <a name="when-depreciation-costs-are-allocated-can-the-dimensions-that-are-based-on-the-allocation-rule-of-the-fixed-asset-model-override-the-default-dimensions-in-the-journal-header"></a><span data-ttu-id="6e752-113">減価償却費を配賦するとき、固定資産モデルの配賦ルールに基づく分析コードが仕訳帳ヘッダーの既定の分析コードを上書きできますか</span><span class="sxs-lookup"><span data-stu-id="6e752-113">When depreciation costs are allocated, can the dimensions that are based on the allocation rule of the fixed asset model override the default dimensions in the journal header?</span></span>
<span data-ttu-id="6e752-114">はい。</span><span class="sxs-lookup"><span data-stu-id="6e752-114">Yes.</span></span> <span data-ttu-id="6e752-115">配賦ルールに指定する分析コードは、仕訳帳ヘッダーに通常表示される既定の分析コードを上書きします。</span><span class="sxs-lookup"><span data-stu-id="6e752-115">The dimensions that you specify in the allocation rule override the default dimensions that are usually displayed in the journal header.</span></span>

## <a name="what-happens-if-i-delete-a-dimension-that-is-part-of-an-allocation-rule"></a><span data-ttu-id="6e752-116">配賦ルールの一部の分析コードを削除すると何が起こります。</span><span class="sxs-lookup"><span data-stu-id="6e752-116">What happens if I delete a dimension that is part of an allocation rule?</span></span>
<span data-ttu-id="6e752-117">配賦ルールに割り当てられている財務分析コードを削除すると、償却提案を実行することができないことを示すメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="6e752-117">If you delete a financial dimension that is assigned to an allocation rule, you receive a message that states that the depreciation proposal can't be run.</span></span> <span data-ttu-id="6e752-118">配賦ルールの別の財務分析コードを選択し、償却提案を再度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e752-118">You must select another financial dimension for the allocation rule and run the depreciation proposal again.</span></span>

## <a name="how-does-rounding-the-currency-up-or-down-affect-the-allocation-rule"></a><span data-ttu-id="6e752-119">通貨の端数の切り上げまたは切り下げはどのように配賦ルールに影響しますか</span><span class="sxs-lookup"><span data-stu-id="6e752-119">How does rounding the currency up or down affect the allocation rule?</span></span>
<span data-ttu-id="6e752-120">配賦ルールを固定資産に適用すると、法人の分析コードに配賦される減価償却費は合計額か、または分割した額になります。</span><span class="sxs-lookup"><span data-stu-id="6e752-120">After an allocation rule is applied to a fixed asset, the deprecation cost that is allocated to a legal entity dimension can be a whole amount or a fractional amount.</span></span> <span data-ttu-id="6e752-121">通貨の丸めルールを適用した場合、配賦ルールに従って、結果として配賦される減価償却費は減価償却費よりも大きくなるか小さくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e752-121">If you've set up rounding rules for your currency, the resulting allocated depreciation costs can be more than or less than the depreciation cost, in accordance with the allocation rule.</span></span> <span data-ttu-id="6e752-122">通貨の丸め方が配賦ルールに影響を及ぼす例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="6e752-122">Here are some examples that show how currency rounding can affect the allocation rule.</span></span>

### <a name="rounded-up-currency"></a><span data-ttu-id="6e752-123">通貨の切り上げ</span><span class="sxs-lookup"><span data-stu-id="6e752-123">Rounded-up currency</span></span>

<span data-ttu-id="6e752-124">この例では、固定資産の減価償却費の金額が 170 通貨単位です。</span><span class="sxs-lookup"><span data-stu-id="6e752-124">For this example, the depreciation cost amount of a fixed asset is 170 currency units.</span></span> <span data-ttu-id="6e752-125">自分の法人の 100 種類の分析コードごとに減価償却費の 1% を割り当てる配賦ルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="6e752-125">You've set up an allocation rule to allocate 1 percent of the depreciation cost to each of the 100 dimensions of your legal entity.</span></span> <span data-ttu-id="6e752-126">2 つの通貨単位間の中間値よりも大きい小数の通貨単位は、もっとも近い通貨単位に切り上げることを指示する丸めルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="6e752-126">You've also set up a rounding rule that indicates that fractional currency units that are more than halfway between two whole currency units are rounded up to the nearest whole currency unit.</span></span> <span data-ttu-id="6e752-127">このシナリオでの分析コードごとの減価償却費の計算方法をここに示します。</span><span class="sxs-lookup"><span data-stu-id="6e752-127">Here is how the depreciation cost per dimension is calculated in this scenario:</span></span>

-   <span data-ttu-id="6e752-128">分析コードごとの元の減価償却費 = 1.70 通貨単位</span><span class="sxs-lookup"><span data-stu-id="6e752-128">Original depreciation cost per dimension = 1.70 currency units</span></span>
-   <span data-ttu-id="6e752-129">切り上げた分析コードごとの減価償却費 = 2.00 通貨単位</span><span class="sxs-lookup"><span data-stu-id="6e752-129">Rounded-up depreciation cost per dimension = 2.00 currency units</span></span>
-   <span data-ttu-id="6e752-130">固定資産の合計の切り上げた減価償却費 = 2.00 × 100 = 200 通貨単位</span><span class="sxs-lookup"><span data-stu-id="6e752-130">Total rounded-up depreciation cost of the fixed asset = 2.00 × 100 = 200 currency units</span></span>

### <a name="rounded-down-currency"></a><span data-ttu-id="6e752-131">切り下げた通貨</span><span class="sxs-lookup"><span data-stu-id="6e752-131">Rounded-down currency</span></span>

<span data-ttu-id="6e752-132">この例では、固定資産の減価償却費の金額が 120 通貨単位です。</span><span class="sxs-lookup"><span data-stu-id="6e752-132">For this example, the depreciation cost amount of a fixed asset is 120 currency units.</span></span> <span data-ttu-id="6e752-133">自分の法人の 100 種類の分析コードごとに減価償却費の 1% を割り当てる配賦ルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="6e752-133">You've set up an allocation rule to allocate 1 percent of the depreciation cost to each of the 100 dimensions of your legal entity.</span></span> <span data-ttu-id="6e752-134">2 つの通貨単位間の中間値よりも小さい小数の通貨単位は、もっとも近い通貨単位に切り下げることを指示する丸めルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="6e752-134">You've also set up a rounding rule that indicates that fractional currency units that are less than halfway between two whole currency units are rounded down to the nearest whole currency unit.</span></span> <span data-ttu-id="6e752-135">このシナリオでの分析コードごとの減価償却費の計算方法をここに示します。</span><span class="sxs-lookup"><span data-stu-id="6e752-135">Here is how the depreciation cost per dimension is calculated in this scenario:</span></span>

-   <span data-ttu-id="6e752-136">分析コードごとの元の減価償却費 = 1.20 通貨単位</span><span class="sxs-lookup"><span data-stu-id="6e752-136">Original depreciation cost per dimension = 1.20 currency units</span></span>
-   <span data-ttu-id="6e752-137">切り下げた分析コードごとの減価償却費 = 1.00 通貨単位</span><span class="sxs-lookup"><span data-stu-id="6e752-137">Rounded-down depreciation cost per dimension = 1.00 currency units</span></span>
-   <span data-ttu-id="6e752-138">固定資産の合計の切り下げた減価償却費 = 1.00 × 100 = 100 通貨単位</span><span class="sxs-lookup"><span data-stu-id="6e752-138">Total rounded-down depreciation cost of the fixed asset = 1.00 × 100 = 100 currency units</span></span>

<span data-ttu-id="6e752-139">各分析コードに割り当てる合計の切り下げた減価償却費が丸める額よりも小さい場合、この配賦ルールは減価償却に適用しません。</span><span class="sxs-lookup"><span data-stu-id="6e752-139">If the total rounded-down depreciation cost that must be allocated across each dimension is less than the rounding amount, the allocation rule isn't applied to the depreciation.</span></span> <span data-ttu-id="6e752-140">代わりに、減価償却額は主勘定に転記されるか、**固定資産転記プロファイル**  ページで設定する転記プロファイルを使用して相殺されます。</span><span class="sxs-lookup"><span data-stu-id="6e752-140">Instead, the depreciation amount is either posted to the main account or offset by using the posting profile rules that you set up on the **Fixed asset posting profiles** page.</span></span> <span data-ttu-id="6e752-141">これらおよび同様のシナリオを回避するために、固定資産減価償却の丸めルールを**通貨**ページで手動で調整できます。</span><span class="sxs-lookup"><span data-stu-id="6e752-141">To avoid these and similar scenarios, you can manually adjust the rounding rule for fixed asset depreciation on the **Currencies** page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6e752-142">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="6e752-142">Additional resources</span></span>
- [<span data-ttu-id="6e752-143">資産グループへの共有資産とのれんの帳簿価額の配賦</span><span class="sxs-lookup"><span data-stu-id="6e752-143">Allocate carrying amount of shared asset and goodwill to cash generating units</span></span>](./tasks/allocate-carrying-amount.md)



