---
title: アプリケーション ビジネス イベント
description: このトピックでは、アプリケーション ビジネス イベントを一覧します。
author: Sunil-Garg
manager: AnnBe
ms.date: 01/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: Platform update 24
ms.dyn365.ops.version: 2019-02-28
ms.openlocfilehash: b9ba448adc202b02e63ed9e3040d802bac4bb1cc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "368972"
---
# <a name="application-business-events"></a><span data-ttu-id="b6a5d-103">アプリケーション ビジネス イベント</span><span class="sxs-lookup"><span data-stu-id="b6a5d-103">Application business events</span></span>

[!include[banner](../includes/banner.md)]
[!include[preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="b6a5d-104">このトピックでは、アプリケーション ビジネス イベントを一覧します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-104">This topic lists application business events.</span></span>

<a name="procure-to-pay"></a><span data-ttu-id="b6a5d-105">仕入れから支払</span><span class="sxs-lookup"><span data-stu-id="b6a5d-105">Procure to pay</span></span>
--------------

| <span data-ttu-id="b6a5d-106">ビジネス イベント</span><span class="sxs-lookup"><span data-stu-id="b6a5d-106">Business event</span></span>                  | <span data-ttu-id="b6a5d-107">説明</span><span class="sxs-lookup"><span data-stu-id="b6a5d-107">Description</span></span>                                                                                                                                | <span data-ttu-id="b6a5d-108">モジュール</span><span class="sxs-lookup"><span data-stu-id="b6a5d-108">Module</span></span>           |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|------------------|
| <span data-ttu-id="b6a5d-109">仕入先請求書が一致しました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-109">Vendor invoice matched</span></span>          | <span data-ttu-id="b6a5d-110">これは、仕入れから支払プロセスの一部として仕入先請求書のために請求書照合検証が完了するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-110">This is triggered when invoice matching validation is completed for a vendor invoice as part of the Procure to pay process.</span></span> | <span data-ttu-id="b6a5d-111">買掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-111">Accounts payable</span></span> |
| <span data-ttu-id="b6a5d-112">仕入先請求書が転記されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-112">Vendor invoice posted</span></span>           | <span data-ttu-id="b6a5d-113">調達から支払いまでのプロセスの一環として、ユーザーが仕入先請求書を転記する場合、このビジネス イベントがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-113">This business event is triggered when a user posts a vendor invoice as part of the Procure to Pay process.</span></span> | <span data-ttu-id="b6a5d-114">買掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-114">Accounts payable</span></span> |
| <span data-ttu-id="b6a5d-115">仕入先支払が転記されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-115">Vendor payment posted</span></span>           | <span data-ttu-id="b6a5d-116">これはユーザーが仕入れから支払プロセスの一部として仕入先支払を転記するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-116">This is triggered when a user posts a vendor payment as part of the Procure to pay process.</span></span>                                 | <span data-ttu-id="b6a5d-117">買掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-117">Accounts payable</span></span> |
| <span data-ttu-id="b6a5d-118">仕入帳仕訳帳が転記されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-118">Invoice register journal posted</span></span> | <span data-ttu-id="b6a5d-119">これはユーザーが仕入れから支払プロセスの一部として仕入帳仕訳を転記するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-119">This is triggered when a user posts an invoice register journal as part of the Procure to pay process.</span></span>                      | <span data-ttu-id="b6a5d-120">買掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-120">Accounts payable</span></span> |
| <span data-ttu-id="b6a5d-121">請求仕訳帳が転記されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-121">Invoice journal posted</span></span>          | <span data-ttu-id="b6a5d-122">これはユーザーが仕入れから支払プロセスの一部として請求仕訳帳を転記するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-122">This is triggered when a user posts an invoice journal as part of the Procure to pay process.</span></span>                               | <span data-ttu-id="b6a5d-123">買掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-123">Accounts payable</span></span> |
| <span data-ttu-id="b6a5d-124">請求書承認仕訳帳が転帰されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-124">Invoice approval journal posted</span></span> | <span data-ttu-id="b6a5d-125">これはユーザーが仕入れから支払プロセスの一部として請求書承認仕訳帳を転記するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-125">This is triggered when a user posts an invoice approval journal as part of the Procure to pay process.</span></span>                      | <span data-ttu-id="b6a5d-126">買掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-126">Accounts payable</span></span> | 
|<span data-ttu-id="b6a5d-127">発注書が確認されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-127">Purchase order confirmed</span></span> |<span data-ttu-id="b6a5d-128">これは発注書が仕入先によって確認されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-128">This is triggered when a purchase order is confirmed by a vendor.</span></span> <span data-ttu-id="b6a5d-129">次のいずれかのアクションがイベントを発生させます: ユーザーが発注書のユーザー インターフェイスで手動で発注書を確認する、発注書の確認がバッチで実行されるとき、または確認が会社間シナリオでプログラムで実行されるとき。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-129">One of the following actions triggers the event: the user manually confirms a purchase order in the user interface for purchase orders, when the purchase order confirmation is executed in a batch, or when the confirmation is executed programmatically in intercompany scenarios.</span></span> <span data-ttu-id="b6a5d-130">仕入先コラボレーションが使用されるシナリオ、および仕入先コラボレーションのポリシーが発注書の自動確認にセットされるシナリオでは、 **仕入先コラボレーション** ポータルの **発注書の確認** ページで **承認** ボタンがクリックされるときにトリガーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-130">In scenarios where vendor collaboration is used, and the vendor collaboration policy is set to auto-confirm a purchase order, the trigger occurs when the **Accept** button is clicked on the **Purchase order confirmation**  page in the **Vendor collaboration** portal.</span></span>|<span data-ttu-id="b6a5d-131">調達</span><span class="sxs-lookup"><span data-stu-id="b6a5d-131">Procurement and sourcing</span></span>|
|<span data-ttu-id="b6a5d-132">発注書が受領されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-132">Purchase order received</span></span> |<span data-ttu-id="b6a5d-133">これは、商品やサービスが 1 つまたは複数の発注書に対して入庫済として登録されるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-133">This is triggered when goods or services are registered as received against one or more purchase orders.</span></span> <span data-ttu-id="b6a5d-134">次のいずれかのアクションがイベントを発生させます: 製品受領書が 1 または複数の発注書に対して発注書および製品受領書のユーザー インターフェイスで手動で生成される、製品受領書がバッチで生成されるとき、または製品受領書が会社間シナリオでプログラムで生成されるとき。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-134">One of the following actions triggers the event: a product receipt is generated for one or more purchase orders manually in the user interface for purchase orders and product receipts, when product receipts are generated in a batch, or when product receipts are generated programmatically in intercompany scenarios.</span></span>|<span data-ttu-id="b6a5d-135">調達</span><span class="sxs-lookup"><span data-stu-id="b6a5d-135">Procurement and sourcing</span></span>||

<a name="quote-to-cash"></a><span data-ttu-id="b6a5d-136">現金に対する見積</span><span class="sxs-lookup"><span data-stu-id="b6a5d-136">Quote to cash</span></span>
-------------

| <span data-ttu-id="b6a5d-137">ビジネス イベント</span><span class="sxs-lookup"><span data-stu-id="b6a5d-137">Business event</span></span>                             | <span data-ttu-id="b6a5d-138">説明</span><span class="sxs-lookup"><span data-stu-id="b6a5d-138">Description</span></span>                                                                                                                       | <span data-ttu-id="b6a5d-139">モジュール</span><span class="sxs-lookup"><span data-stu-id="b6a5d-139">Module</span></span>                 |
|--------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|------------------------|
| <span data-ttu-id="b6a5d-140">販売注文から請求書が作成されます</span><span class="sxs-lookup"><span data-stu-id="b6a5d-140">Invoice is created from a sales order</span></span>      | <span data-ttu-id="b6a5d-141">これはユーザーが見積から入金プロセスの一部として販売注文請求書を転記するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-141">This is triggered when a user posts a sales order invoice as part of the Quote to Cash process.</span></span>                    | <span data-ttu-id="b6a5d-142">売掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-142">Accounts receivable</span></span>    |
| <span data-ttu-id="b6a5d-143">自由書式の請求書が転記されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-143">Free text invoice posted</span></span>                   | <span data-ttu-id="b6a5d-144">これはユーザーが見積から入金プロセスの一部として自由書式の請求書を転記するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-144">This is triggered when a user posts a free text invoice as part of the Quote to Cash process.</span></span>                      | <span data-ttu-id="b6a5d-145">売掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-145">Accounts receivable</span></span>    |
| <span data-ttu-id="b6a5d-146">支払が転記されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-146">Payment posted</span></span>                             | <span data-ttu-id="b6a5d-147">これはユーザーが見積から入金プロセスの一部として支払を転記するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-147">This is triggered when a user posts a payment as part of the Quote to Cash process.</span></span>                                | <span data-ttu-id="b6a5d-148">売掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-148">Accounts receivable</span></span>    |
| <span data-ttu-id="b6a5d-149">トランザクションが損金処理されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-149">Transaction is written off</span></span>                 | <span data-ttu-id="b6a5d-150">これはユーザーが見積から入金プロセスの一部として顧客取引を記述するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-150">This is triggered when a user writes off a customer transaction as part of the Quote to Cash process.</span></span>              | <span data-ttu-id="b6a5d-151">売掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-151">Accounts receivable</span></span>    |
| <span data-ttu-id="b6a5d-152">トランザクションの回収状態が変更されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-152">Collection status of a transaction changed</span></span> | <span data-ttu-id="b6a5d-153">これはユーザーが見積から入金プロセスの一部として回収状態を更新するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-153">This is triggered when a user updates the collection status of a transaction as part of the Quote to Cash process.</span></span> | <span data-ttu-id="b6a5d-154">売掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-154">Accounts receivable</span></span>    |
| <span data-ttu-id="b6a5d-155">利子計算書が転記されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-155">Interest note posted</span></span>                       | <span data-ttu-id="b6a5d-156">これはユーザーが見積から入金プロセスの一部として利子計算書を転記するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-156">This is triggered when a user posts an interest note as part of the Quote to Cash process.</span></span>                         | <span data-ttu-id="b6a5d-157">売掛金管理</span><span class="sxs-lookup"><span data-stu-id="b6a5d-157">Accounts receivable</span></span>    |
| <span data-ttu-id="b6a5d-158">督促状が作成されました</span><span class="sxs-lookup"><span data-stu-id="b6a5d-158">Collection letter created</span></span>                  | <span data-ttu-id="b6a5d-159">これはユーザーが見積から入金プロセスの一部として督促状を作成するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b6a5d-159">This is triggered when a user creates a collection letter for a customer as part of the Quote to Cash process.</span></span>     | <span data-ttu-id="b6a5d-160">貸方転記および取立</span><span class="sxs-lookup"><span data-stu-id="b6a5d-160">Credit and collections</span></span> |
