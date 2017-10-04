---
title: "仕入先請求仕訳帳および請求書承認仕訳帳の既定の相手勘定"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c2b62eafc71b5d1ad4eaaf252efd1dcbb97b86f3
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a><span data-ttu-id="e38bc-102">仕入先請求仕訳帳および請求書承認仕訳帳の既定の相手勘定</span><span class="sxs-lookup"><span data-stu-id="e38bc-102">Default offset accounts for vendor invoice journals and invoice approval journals</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="e38bc-103">既定の相手勘定は、次の仕入先請求仕訳帳のページで使用されます:</span><span class="sxs-lookup"><span data-stu-id="e38bc-103">Default offset accounts are used on the following vendor invoice journal pages:</span></span>

-   <span data-ttu-id="e38bc-104">請求仕訳帳</span><span class="sxs-lookup"><span data-stu-id="e38bc-104">Invoice journal</span></span>
-   <span data-ttu-id="e38bc-105">請求書承認仕訳帳</span><span class="sxs-lookup"><span data-stu-id="e38bc-105">Invoice approval journal</span></span>

<span data-ttu-id="e38bc-106">次の表を使用して、請求仕訳の既定の勘定を割り当てる場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="e38bc-106">Use the following table to help decide where you should assign default accounts for invoice journals.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e38bc-107">既定の勘定を設定する</span><span class="sxs-lookup"><span data-stu-id="e38bc-107">Set up default accounts here</span></span></th>
<th><span data-ttu-id="e38bc-108">既定の勘定が提供される場所</span><span class="sxs-lookup"><span data-stu-id="e38bc-108">Where default accounts are provided</span></span></th>
<th><span data-ttu-id="e38bc-109">このオプションが処理に与える影響</span><span class="sxs-lookup"><span data-stu-id="e38bc-109">How this option affects processing</span></span></th>
<th><span data-ttu-id="e38bc-110">このオプションを使用する状況</span><span class="sxs-lookup"><span data-stu-id="e38bc-110">When you should use this option</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e38bc-111"><strong>仕入先グループ</strong> – <strong>仕入先グループ</strong>ページから開くことができる<strong>既定の勘定の設定</strong>ページで、仕入先グループの既定の相手勘定を設定します 。</span><span class="sxs-lookup"><span data-stu-id="e38bc-111"><strong>Vendor group</strong> – Set up default offset accounts for vendor groups on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendor groups</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="e38bc-112">仕入先</span><span class="sxs-lookup"><span data-stu-id="e38bc-112">Vendor account</span></span></li>
<li><span data-ttu-id="e38bc-113">既定の勘定が仕入先勘定に対して指定されていない場合の仕入先グループ内の仕入先勘定の仕訳エントリ</span><span class="sxs-lookup"><span data-stu-id="e38bc-113">Journal entries for vendor accounts in the vendor group, if default accounts aren’t specified for vendor accounts</span></span></li>
</ul></td>
<td><span data-ttu-id="e38bc-114">仕入先グループの既定の相手勘定は、<strong>既定の勘定の設定</strong>ページに仕入先の既定の相手勘定として表示されます。</span><span class="sxs-lookup"><span data-stu-id="e38bc-114">The default offset accounts for vendor groups are shown as default offset accounts for vendors on the <strong>Default account setup</strong> page.</span></span> <span data-ttu-id="e38bc-115"><strong>すべての仕入先</strong>リスト ページから、このページを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="e38bc-115">You can open this page from the <strong>All vendors</strong> list page.</span></span></td>
<td><span data-ttu-id="e38bc-116">同じ仕入先グループから繰り返し同種の物品に対して支払を行っている場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e38bc-116">Use this option if you typically pay for the same types of things from the same vendor groups over time.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e38bc-117"><strong>仕入先</strong> – <strong>仕入先</strong>ページから開くことができる<strong>既定の勘定の設定</strong>ページで、仕入先の既定の勘定を設定します 。</span><span class="sxs-lookup"><span data-stu-id="e38bc-117"><strong>Vendor account</strong> – Set up default accounts for vendor accounts on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendors</strong> page.</span></span></td>
<td><span data-ttu-id="e38bc-118">仕入先勘定の仕訳入力</span><span class="sxs-lookup"><span data-stu-id="e38bc-118">Journal entries for the vendor account</span></span></td>
<td><span data-ttu-id="e38bc-119">仕入先勘定の既定の相手勘定は、仕入先勘定の仕訳入力の既定の相手勘定として表示されます。</span><span class="sxs-lookup"><span data-stu-id="e38bc-119">The default offset accounts for vendor accounts are shown as default offset accounts for journal entries for the vendor account.</span></span></td>
<td><span data-ttu-id="e38bc-120">同じ仕入先から繰り返し同種の物品に対して支払を行っている場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e38bc-120">Use this option if you typically pay for the same types of things from the same vendors over time.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e38bc-121"><strong>仕訳帳名</strong> – は、<strong>仕訳帳名</strong>ページの仕訳帳の既定の相手勘定を設定します。</span><span class="sxs-lookup"><span data-stu-id="e38bc-121"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="e38bc-122"><strong>固定相手勘定</strong>オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e38bc-122">Select the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="e38bc-123">仕訳帳名の仕訳帳タイプが<strong>仕入帳</strong>または<strong>承認</strong>の場合は、仕訳帳名で既定の相手勘定を指定することができないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e38bc-123">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="e38bc-124">仕訳帳名を使用する仕訳帳のヘッダー</span><span class="sxs-lookup"><span data-stu-id="e38bc-124">Journal header that uses the journal name</span></span></li>
<li><span data-ttu-id="e38bc-125">仕訳帳名を使用する仕訳帳の仕訳入力</span><span class="sxs-lookup"><span data-stu-id="e38bc-125">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="e38bc-126"><strong>仕訳帳名</strong>ページの<strong>固定相手勘定</strong>オプションがオンの場合、仕訳帳名の相手勘定は、仕入先または仕入先グループの既定の相手勘定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="e38bc-126">If the <strong>Fixed offset account</strong> option on the <strong>Journal names</strong> page is selected, the offset account for the journal name overrides the default offset account for the vendor or vendor group.</span></span></td>
<td><span data-ttu-id="e38bc-127">このオプションを使用すると、特定の勘定に請求する特定の原価および経費の仕訳帳を、仕入先や仕入先グループの所属先に関わらず、設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e38bc-127">Use this option to set up journals for specific costs and expenses that are charged to specific accounts, regardless of the vendor or the vendor group that the vendor belongs to.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e38bc-128"><strong>仕訳帳名</strong> – は、<strong>仕訳帳名</strong>ページの仕訳帳の既定の相手勘定を設定します。</span><span class="sxs-lookup"><span data-stu-id="e38bc-128"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="e38bc-129"><strong>固定相手勘定</strong>オプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e38bc-129">Clear the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="e38bc-130">仕訳帳名の仕訳帳タイプが<strong>仕入帳</strong>または<strong>承認</strong>の場合は、仕訳帳名で既定の相手勘定を指定することができないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e38bc-130">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="e38bc-131">仕訳帳ヘッダー</span><span class="sxs-lookup"><span data-stu-id="e38bc-131">Journal header</span></span></li>
<li><span data-ttu-id="e38bc-132">仕訳帳名を使用する仕訳帳の仕訳入力</span><span class="sxs-lookup"><span data-stu-id="e38bc-132">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="e38bc-133">これらの既定のエントリは、仕訳帳ヘッダーのページで使用され、仕訳帳ヘッダー ページの相手勘定は仕訳帳伝票ページで既定のエントリとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="e38bc-133">These default entries are used on journal header pages, and the offset account on the journal header page is used as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="e38bc-134"><strong>仕訳帳名</strong>ページの既定の勘定は、既定の勘定が仕入先勘定に設定されていない場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="e38bc-134">Default accounts from the <strong>Journal names </strong>page are used only if default accounts aren’t set up for the vendor account.</span></span></td>
<td><span data-ttu-id="e38bc-135">このオプションを使用して、既定の仕入先相手勘定が割り当てられていないときに使用する既定の勘定を設定します。</span><span class="sxs-lookup"><span data-stu-id="e38bc-135">Use this option to set up default accounts that are used when a default vendor offset account isn't assigned.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e38bc-136"><strong>仕訳帳ヘッダー</strong> – 仕訳帳の既定の相手勘定を設定して、仕訳伝票ページの既定のエントリとして使用します。</span><span class="sxs-lookup"><span data-stu-id="e38bc-136"><strong>Journal header</strong> – Set up a default offset account for a journal as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="e38bc-137">仕訳帳名の仕訳帳タイプが<strong>仕入帳</strong>または<strong>承認</strong>の場合は、仕訳帳ヘッダーで既定の相手勘定を指定することができないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e38bc-137">Note that you can't specify default offset accounts on the journal header if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><span data-ttu-id="e38bc-138">仕訳帳の仕訳入力</span><span class="sxs-lookup"><span data-stu-id="e38bc-138">Journal entries in the journal</span></span></td>
<td><span data-ttu-id="e38bc-139">仕訳帳の既定の相手勘定は、仕訳伝票ページの既定のエントリとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="e38bc-139">The default offset account for a journal is used as the default entry on the journal voucher pages.</span></span></td>
<td><span data-ttu-id="e38bc-140">仕訳帳のほとんどのエントリに同じ相手勘定が存在する場合は、このオプションを使用するとデータ入力が速くなります。</span><span class="sxs-lookup"><span data-stu-id="e38bc-140">Use this option to help speed up data entry if most entries in a journal have the same offset account.</span></span></td>
</tr>
</tbody>
</table>





