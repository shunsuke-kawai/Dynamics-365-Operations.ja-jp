---
title: "プロジェクトの発注書"
description: "この記事では、プロジェクトの発注書を作成するために使用できるさまざまな方法について説明します。 発注書を作成する方法は、発注書の目的、購入する品目の消費時期、プロジェクトに請求される時期で決まります。"
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: 985a57ae9fb116b1c4514b836b35c5da0f8838fd
ms.contentlocale: ja-jp
ms.lasthandoff: 09/14/2017

---

# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="53eed-104">プロジェクトの発注書</span><span class="sxs-lookup"><span data-stu-id="53eed-104">Purchase orders for a project</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="53eed-105">この記事では、プロジェクトの発注書を作成するために使用できるさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="53eed-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="53eed-106">発注書を作成する方法は、発注書の目的、購入する品目の消費時期、プロジェクトに請求される時期で決まります。</span><span class="sxs-lookup"><span data-stu-id="53eed-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

<span data-ttu-id="53eed-107">Microsoft Dynamics 365 for Finance and Operations,Enterprise エディションでは、プロジェクトの発注書を作成する場合、複数の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="53eed-107">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, you can use multiple methods to create purchase orders for a project.</span></span> <span data-ttu-id="53eed-108">発注書を作成する方法は、発注書の目的、購入する品目の消費時期、プロジェクトに請求される時期で決まります。</span><span class="sxs-lookup"><span data-stu-id="53eed-108">The method that you use depends on the purpose of the purchase order, when the purchased items are consumed, and when the purchased items are charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="53eed-109">発注書を作成する方法</span><span class="sxs-lookup"><span data-stu-id="53eed-109">Methods for creating a purchase order</span></span>

<span data-ttu-id="53eed-110">プロジェクト管理と会計で発注書を作成するには、次の方法のうち 1 つを使用できます。</span><span class="sxs-lookup"><span data-stu-id="53eed-110">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="53eed-111">発注書の目的は、発注書が消費される時点、つまり品目がプロジェクトで請求される時点を決定することです。</span><span class="sxs-lookup"><span data-stu-id="53eed-111">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53eed-112">方式</span><span class="sxs-lookup"><span data-stu-id="53eed-112">Method</span></span></th>
<th><span data-ttu-id="53eed-113">目的</span><span class="sxs-lookup"><span data-stu-id="53eed-113">Purpose</span></span></th>
<th><span data-ttu-id="53eed-114">品目の消費</span><span class="sxs-lookup"><span data-stu-id="53eed-114">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="53eed-115">プロジェクトからの発注書を直接作成します。</span><span class="sxs-lookup"><span data-stu-id="53eed-115">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="53eed-116">プロジェクトでの消費用に外部仕入先から品目を購買するには、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="53eed-116">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="53eed-117">発注書を次の 2 つの方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="53eed-117">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="53eed-118">プロジェクト自体から作成します。</span><span class="sxs-lookup"><span data-stu-id="53eed-118">From the project itself.</span></span> <span data-ttu-id="53eed-119">この場合、プロジェクトはすでに発注書のために定義されています。</span><span class="sxs-lookup"><span data-stu-id="53eed-119">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="53eed-120">プロジェクト発注書に移動することで作成します。</span><span class="sxs-lookup"><span data-stu-id="53eed-120">By navigating to the project purchase order.</span></span> <span data-ttu-id="53eed-121">発注書の作成対象となる仕入先とプロジェクトを両方とも選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53eed-121">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="53eed-122">品目は、仕入先請求書が更新された時点で消費されます。</span><span class="sxs-lookup"><span data-stu-id="53eed-122">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="53eed-123">販売注文から発注書を作成する。</span><span class="sxs-lookup"><span data-stu-id="53eed-123">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="53eed-124">プロジェクトから販売注文を作成する際に品目を購買する場合は、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="53eed-124">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="53eed-125">品目は、販売注文が顧客に請求された時点で消費されます。</span><span class="sxs-lookup"><span data-stu-id="53eed-125">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="53eed-126">在庫品目要求から発注書を作成する。</span><span class="sxs-lookup"><span data-stu-id="53eed-126">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="53eed-127">プロジェクトから在庫品目要求を作成する際に品目を購買する場合は、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="53eed-127">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="53eed-128">品目は、在庫品目要求梱包明細が更新された時点で消費されます。</span><span class="sxs-lookup"><span data-stu-id="53eed-128">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="53eed-129">仕入先請求書または梱包明細を更新するときに、在庫品目要求の梱包明細を更新するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53eed-129">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="53eed-130">詳細については、「[在庫品目要求から発注書の品目を受け取る](tasks/receive-items-purchase-order-item-requirement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53eed-130">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>

