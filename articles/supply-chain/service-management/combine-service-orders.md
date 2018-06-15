---
title: "サービス注文の組み合わせ"
description: "サービス注文を組み合わせることができます。"
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
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
ms.openlocfilehash: 8bc28d03d36d184e4bf41de2c50dac15e6d7813c
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="combine-service-orders"></a><span data-ttu-id="9ebe6-103">サービス注文の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="9ebe6-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="9ebe6-104">**サービス合意**フォームでサービス注文明細行を自動的に作成する場合、次のいずれかのオプションを選択してそれらをグループ化する方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="9ebe6-105">**サービス契約別**</span><span class="sxs-lookup"><span data-stu-id="9ebe6-105">**By service agreement**</span></span>

  - <span data-ttu-id="9ebe6-106">**サービス作業別**</span><span class="sxs-lookup"><span data-stu-id="9ebe6-106">**By service task**</span></span>

  - <span data-ttu-id="9ebe6-107">**従業員別**</span><span class="sxs-lookup"><span data-stu-id="9ebe6-107">**By employee**</span></span>

  - <span data-ttu-id="9ebe6-108">**サービス対象別**</span><span class="sxs-lookup"><span data-stu-id="9ebe6-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="9ebe6-109">例</span><span class="sxs-lookup"><span data-stu-id="9ebe6-109">Example</span></span>

<span data-ttu-id="9ebe6-110">開始日が 2007 年 3 月 31 日のサービス合意を作成します。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="9ebe6-111">**サービス注文の組み合わせ**フィールドで、**サービス対象別**を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="9ebe6-112">その後、次のサービス合意項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-112">You then create the following service agreement lines:</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ebe6-113">契約明細行番号</span><span class="sxs-lookup"><span data-stu-id="9ebe6-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="9ebe6-114">トランザクション タイプ</span><span class="sxs-lookup"><span data-stu-id="9ebe6-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="9ebe6-115">説明</span><span class="sxs-lookup"><span data-stu-id="9ebe6-115">Description</span></span></p></th>
<th><p><span data-ttu-id="9ebe6-116">間隔</span><span class="sxs-lookup"><span data-stu-id="9ebe6-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="9ebe6-117">サービス対象</span><span class="sxs-lookup"><span data-stu-id="9ebe6-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="9ebe6-118">入社日</span><span class="sxs-lookup"><span data-stu-id="9ebe6-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ebe6-119">1</span><span class="sxs-lookup"><span data-stu-id="9ebe6-119">1</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-120"><strong>時</strong></span><span class="sxs-lookup"><span data-stu-id="9ebe6-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="9ebe6-121">SAL1</span><span class="sxs-lookup"><span data-stu-id="9ebe6-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-122">毎週</span><span class="sxs-lookup"><span data-stu-id="9ebe6-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-123">X-1</span><span class="sxs-lookup"><span data-stu-id="9ebe6-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-124">2007 - 04 - 01</span><span class="sxs-lookup"><span data-stu-id="9ebe6-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ebe6-125">2</span><span class="sxs-lookup"><span data-stu-id="9ebe6-125">2</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-126"><strong>時</strong></span><span class="sxs-lookup"><span data-stu-id="9ebe6-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="9ebe6-127">SAL2</span><span class="sxs-lookup"><span data-stu-id="9ebe6-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-128">隔週</span><span class="sxs-lookup"><span data-stu-id="9ebe6-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-129">X-2</span><span class="sxs-lookup"><span data-stu-id="9ebe6-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-130">2007 - 04 - 01</span><span class="sxs-lookup"><span data-stu-id="9ebe6-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ebe6-131">3</span><span class="sxs-lookup"><span data-stu-id="9ebe6-131">3</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-132"><strong>時</strong></span><span class="sxs-lookup"><span data-stu-id="9ebe6-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="9ebe6-133">SAL3</span><span class="sxs-lookup"><span data-stu-id="9ebe6-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-134">毎週</span><span class="sxs-lookup"><span data-stu-id="9ebe6-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-135">X-2</span><span class="sxs-lookup"><span data-stu-id="9ebe6-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="9ebe6-136">2007 - 04 - 01</span><span class="sxs-lookup"><span data-stu-id="9ebe6-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9ebe6-137">どのサービス合意項目でも時間枠は指定しません。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="9ebe6-138">したがって、サービス注文明細行は、該当する算出日から移動しません。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="9ebe6-139">次に、**サービス注文の作成**フォームで 2007 年 4 月 1 日から 2007 年 4 月 30 日までのサービス注文明細行を生成します。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="9ebe6-140">合計で 10 件のサービス注文が作成されます。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="9ebe6-141">選択した組み合わせの設定が**サービス対象別**であるため、作成されるすべてのサービス注文の明細行が、1 つの特定のサービス対象を含むサービス注文明細行のみになります。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="9ebe6-142">サービス合意から生成され、同じサービス日付と対象を含むサービス注文明細行が、同じサービス注文に組み合わせられます。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="9ebe6-143">この例では、<STRONG>サービス管理パラメーター</STRONG>フォームで指定されたカレンダーに休業日がないものとします。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="9ebe6-144">サービス注文明細行をさらにサービス注文にグループ化する場合は、サービス合意項目に対して指定する時間枠に基づきます。</span><span class="sxs-lookup"><span data-stu-id="9ebe6-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ebe6-145">参照</span><span class="sxs-lookup"><span data-stu-id="9ebe6-145">See also</span></span>

[<span data-ttu-id="9ebe6-146">サービス注文の自動作成</span><span class="sxs-lookup"><span data-stu-id="9ebe6-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  


