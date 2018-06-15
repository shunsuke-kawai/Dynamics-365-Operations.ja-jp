---
title: "返品品目の廃棄方法の指定"
description: "返品品目の廃棄方法を指定します。"
author: YuyuScheller
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d25a53ac58b0ab44605af253f174ba2ec7b74174
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="specify-how-to-dispose-of-returned-items"></a><span data-ttu-id="8b703-103">返品品目の廃棄方法の指定</span><span class="sxs-lookup"><span data-stu-id="8b703-103">Specify how to dispose of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="8b703-104">返品注文を処理する場合、製品が返品されている理由を識別する返品理由コードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b703-104">When you handle a return order, you must specify a reason return code to identify why the product is being returned.</span></span> <span data-ttu-id="8b703-105">返品製品自体に何が実行されたかを特定する廃棄コード、および処分アクションも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b703-105">You must also specify a disposition code and a disposition action to determine what should be done with the returned product itself.</span></span>

<span data-ttu-id="8b703-106">廃棄コードは、返品注文の作成、品目到着の登録または品目到着の梱包明細の更新、および検査指示の終了時に適用できます。</span><span class="sxs-lookup"><span data-stu-id="8b703-106">A disposition code can be applied when you create the return order, register item arrival or packing-slip update an item arrival, and end a quarantine order.</span></span>

<span data-ttu-id="8b703-107">業務プロセスをサポートするため、任意の必要な廃棄コードを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8b703-107">You can define any disposition codes that you need in order to support the business processes.</span></span> <span data-ttu-id="8b703-108">次の表に、返品品目の廃棄を割り当てるために一般的に使用されるコードを示します。</span><span class="sxs-lookup"><span data-stu-id="8b703-108">The following table provides a set of typically used codes to assign return-item disposition.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8b703-109">廃棄タイプ</span><span class="sxs-lookup"><span data-stu-id="8b703-109">Disposition type</span></span></p></th>
<th><p><span data-ttu-id="8b703-110">一般的なコード</span><span class="sxs-lookup"><span data-stu-id="8b703-110">Common code</span></span></p></th>
<th><p><span data-ttu-id="8b703-111">説明</span><span class="sxs-lookup"><span data-stu-id="8b703-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b703-112">処分</span><span class="sxs-lookup"><span data-stu-id="8b703-112">Disposal</span></span></p></td>
<td><p><span data-ttu-id="8b703-113">SC</span><span class="sxs-lookup"><span data-stu-id="8b703-113">SC</span></span></p></td>
<td><p><span data-ttu-id="8b703-114">解体/廃棄</span><span class="sxs-lookup"><span data-stu-id="8b703-114">Scrap/Destroy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b703-115">処分</span><span class="sxs-lookup"><span data-stu-id="8b703-115">Disposal</span></span></p></td>
<td><p><span data-ttu-id="8b703-116">DC</span><span class="sxs-lookup"><span data-stu-id="8b703-116">DC</span></span></p></td>
<td><p><span data-ttu-id="8b703-117">慈善活動に寄贈</span><span class="sxs-lookup"><span data-stu-id="8b703-117">Donate to Charity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b703-118">処分</span><span class="sxs-lookup"><span data-stu-id="8b703-118">Disposal</span></span></p></td>
<td><p><span data-ttu-id="8b703-119">TD</span><span class="sxs-lookup"><span data-stu-id="8b703-119">TD</span></span></p></td>
<td><p><span data-ttu-id="8b703-120">サード パーティによる廃棄</span><span class="sxs-lookup"><span data-stu-id="8b703-120">Third-Party Disposal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b703-121">処分</span><span class="sxs-lookup"><span data-stu-id="8b703-121">Disposal</span></span></p></td>
<td><p><span data-ttu-id="8b703-122">SL</span><span class="sxs-lookup"><span data-stu-id="8b703-122">SL</span></span></p></td>
<td><p><span data-ttu-id="8b703-123">回収</span><span class="sxs-lookup"><span data-stu-id="8b703-123">Salvage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b703-124">処分</span><span class="sxs-lookup"><span data-stu-id="8b703-124">Disposal</span></span></p></td>
<td><p><span data-ttu-id="8b703-125">TS</span><span class="sxs-lookup"><span data-stu-id="8b703-125">TS</span></span></p></td>
<td><p><span data-ttu-id="8b703-126">サード パーティへの売却 (二次市場)</span><span class="sxs-lookup"><span data-stu-id="8b703-126">Third-Party Sale (Secondary Markets)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b703-127">修復/変更</span><span class="sxs-lookup"><span data-stu-id="8b703-127">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="8b703-128">RW</span><span class="sxs-lookup"><span data-stu-id="8b703-128">RW</span></span></p></td>
<td><p><span data-ttu-id="8b703-129">再加工</span><span class="sxs-lookup"><span data-stu-id="8b703-129">Rework</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b703-130">修復/変更</span><span class="sxs-lookup"><span data-stu-id="8b703-130">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="8b703-131">RF</span><span class="sxs-lookup"><span data-stu-id="8b703-131">RF</span></span></p></td>
<td><p><span data-ttu-id="8b703-132">再製品化/修繕</span><span class="sxs-lookup"><span data-stu-id="8b703-132">Remanufacture/Refurbish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b703-133">修復/変更</span><span class="sxs-lookup"><span data-stu-id="8b703-133">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="8b703-134">MD</span><span class="sxs-lookup"><span data-stu-id="8b703-134">MD</span></span></p></td>
<td><p><span data-ttu-id="8b703-135">変更</span><span class="sxs-lookup"><span data-stu-id="8b703-135">Modify</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b703-136">修復/変更</span><span class="sxs-lookup"><span data-stu-id="8b703-136">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="8b703-137">RP</span><span class="sxs-lookup"><span data-stu-id="8b703-137">RP</span></span></p></td>
<td><p><span data-ttu-id="8b703-138">修復</span><span class="sxs-lookup"><span data-stu-id="8b703-138">Repair</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b703-139">修復/変更</span><span class="sxs-lookup"><span data-stu-id="8b703-139">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="8b703-140">RV</span><span class="sxs-lookup"><span data-stu-id="8b703-140">RV</span></span></p></td>
<td><p><span data-ttu-id="8b703-141">仕入先に返品</span><span class="sxs-lookup"><span data-stu-id="8b703-141">Return to Vendor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b703-142">その他</span><span class="sxs-lookup"><span data-stu-id="8b703-142">Other</span></span></p></td>
<td><p><span data-ttu-id="8b703-143">AI</span><span class="sxs-lookup"><span data-stu-id="8b703-143">AI</span></span></p></td>
<td><p><span data-ttu-id="8b703-144">現状のまま使用</span><span class="sxs-lookup"><span data-stu-id="8b703-144">Use as is</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b703-145">その他</span><span class="sxs-lookup"><span data-stu-id="8b703-145">Other</span></span></p></td>
<td><p><span data-ttu-id="8b703-146">RS</span><span class="sxs-lookup"><span data-stu-id="8b703-146">RS</span></span></p></td>
<td><p><span data-ttu-id="8b703-147">再販売</span><span class="sxs-lookup"><span data-stu-id="8b703-147">Resale</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b703-148">その他</span><span class="sxs-lookup"><span data-stu-id="8b703-148">Other</span></span></p></td>
<td><p><span data-ttu-id="8b703-149">前</span><span class="sxs-lookup"><span data-stu-id="8b703-149">EX</span></span></p></td>
<td><p><span data-ttu-id="8b703-150">交換</span><span class="sxs-lookup"><span data-stu-id="8b703-150">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b703-151">その他</span><span class="sxs-lookup"><span data-stu-id="8b703-151">Other</span></span></p></td>
<td><p><span data-ttu-id="8b703-152">Ms.</span><span class="sxs-lookup"><span data-stu-id="8b703-152">MS</span></span></p></td>
<td><p><span data-ttu-id="8b703-153">雑費</span><span class="sxs-lookup"><span data-stu-id="8b703-153">Miscellaneous</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b703-154">定義した各廃棄コードごとに、処分アクションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b703-154">For each disposition code that you define, you must select a disposition action.</span></span> <span data-ttu-id="8b703-155">処分アクションにより、廃棄コードの物理的および財務的意味が決まります。</span><span class="sxs-lookup"><span data-stu-id="8b703-155">The disposition action determines the physical and financial implications of the disposition codes.</span></span> <span data-ttu-id="8b703-156">たとえば、交換品目を顧客に送る必要がある場合、処分アクションにより、返品品目の物理的な処理や返品品目の財務上の影響などが決まります。</span><span class="sxs-lookup"><span data-stu-id="8b703-156">For example, the disposition action determines the physical handling of the returned item, the financial effect of the returned item, and if a replacement item must be sent to the customer.</span></span> <span data-ttu-id="8b703-157">業務のニーズに応じて廃棄コードの数を任意に定義できますが、6 種類の定義済の処分アクションのみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="8b703-157">You can define an unlimited number of disposition codes according to your business needs, but there are only six predefined disposition actions that you can select from.</span></span> <span data-ttu-id="8b703-158">次の表に、処分アクションとその定義を示します。</span><span class="sxs-lookup"><span data-stu-id="8b703-158">The following table provides the disposition actions and their definitions.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8b703-159">処分アクション</span><span class="sxs-lookup"><span data-stu-id="8b703-159">Disposition action</span></span></p></th>
<th><p><span data-ttu-id="8b703-160">説明</span><span class="sxs-lookup"><span data-stu-id="8b703-160">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b703-161"><strong>クレジット</strong></span><span class="sxs-lookup"><span data-stu-id="8b703-161"><strong>Credit</strong></span></span></p></td>
<td><p><span data-ttu-id="8b703-162">品目を在庫に返品し、顧客に対して貸方転記します。</span><span class="sxs-lookup"><span data-stu-id="8b703-162">Return the item to inventory and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b703-163"><strong>貸方のみ</strong></span><span class="sxs-lookup"><span data-stu-id="8b703-163"><strong>Credit only</strong></span></span></p></td>
<td><p><span data-ttu-id="8b703-164">品目の返品を要求または期待せずに、顧客に対して貸方転記します。</span><span class="sxs-lookup"><span data-stu-id="8b703-164">Credit the customer without requiring or expecting the item to be returned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b703-165"><strong>仕損</strong></span><span class="sxs-lookup"><span data-stu-id="8b703-165"><strong>Scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="8b703-166">品目を処分して、顧客に対して貸方転記します。</span><span class="sxs-lookup"><span data-stu-id="8b703-166">Scrap the item and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b703-167"><strong>置換と貸方転記</strong></span><span class="sxs-lookup"><span data-stu-id="8b703-167"><strong>Replace and credit</strong></span></span></p></td>
<td><p><span data-ttu-id="8b703-168">品目を在庫に戻して、交換注文を作成し、顧客に対して貸方転記します。</span><span class="sxs-lookup"><span data-stu-id="8b703-168">Return the item to inventory, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b703-169"><strong>置換と仕損</strong></span><span class="sxs-lookup"><span data-stu-id="8b703-169"><strong>Replace and scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="8b703-170">品目の処分し、交換注文を作成し、顧客に対して貸方転記します。</span><span class="sxs-lookup"><span data-stu-id="8b703-170">Scrap the item, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b703-171"><strong>顧客に戻る</strong></span><span class="sxs-lookup"><span data-stu-id="8b703-171"><strong>Return to customer</strong></span></span></p></td>
<td><p><span data-ttu-id="8b703-172">品目の返品を拒否して、顧客に返送します。</span><span class="sxs-lookup"><span data-stu-id="8b703-172">Reject the returned item and return it to the customer.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a><span data-ttu-id="8b703-173">検査指示の廃棄コードの選択</span><span class="sxs-lookup"><span data-stu-id="8b703-173">Select a disposition code for a quarantine order</span></span>

1.  <span data-ttu-id="8b703-174">**在庫管理** \> **定期処理** \> **品質管理** \> **検査指示**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b703-174">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="8b703-175">既存の検査指示に対して、**概要**タブの**廃棄コード**フィールドからアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8b703-175">For an existing quarantine order, select an action from the **Disposition code** field on the **Overview** tab.</span></span>



## <a name="see-also"></a><span data-ttu-id="8b703-176">参照</span><span class="sxs-lookup"><span data-stu-id="8b703-176">See also</span></span>

<span data-ttu-id="8b703-177">[検査指示 (フォーム)](https://technet.microsoft.com/en-us/library/aa554073(v=ax.60))</span><span class="sxs-lookup"><span data-stu-id="8b703-177">[Quarantine order (form)](https://technet.microsoft.com/en-us/library/aa554073(v=ax.60))</span></span>

<span data-ttu-id="8b703-178">[廃棄コード (フォーム)](https://technet.microsoft.com/en-us/library/hh597113\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="8b703-178">[Disposition codes (form)](https://technet.microsoft.com/en-us/library/hh597113\(v=ax.60\))</span></span>

  


