---
title: "仕入先支払ワークスペース"
description: "このトピックでは、[仕入先支払] モバイル ワークスペースに関する情報を提供します。 [仕入先支払] ワークスペースは、仕入先支払の処理に関連する情報を表示します。"
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: 
ms.assetid: 
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b6c1802a5d53299ac6be8c747146698778a9359c
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="vendor-payments-workspace"></a><span data-ttu-id="b2f57-104">仕入先支払ワークスペース</span><span class="sxs-lookup"><span data-stu-id="b2f57-104">Vendor payments workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b2f57-105">[**仕入先支払**] ワークスペースは、仕入先支払の処理に関連する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="b2f57-105">The **Vendor payments** workspace shows information that is related to the processing of vendor payments.</span></span> <span data-ttu-id="b2f57-106">このワークスペースには、[**自分の作業**] ビューと [**分析**] ページが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2f57-106">This workspace includes a **My work** view and an **Analytics** page.</span></span> <span data-ttu-id="b2f57-107">[**自分の作業**] ビューでは、概要タイル、仕入先トランザクションのグリッド、および関連する仕入先情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="b2f57-107">The **My work** view shows summary tiles, vendor transaction grids, and related vendor information.</span></span> <span data-ttu-id="b2f57-108">[**分析**] ページは、Microsoft Power BI の機能を使用して、仕入先支払に関連付けられているビジュアルを表示します。</span><span class="sxs-lookup"><span data-stu-id="b2f57-108">The **Analytics** page uses the capabilities of Microsoft Power BI to show visuals that are related to vendor payments.</span></span>

## <a name="my-work-view"></a><span data-ttu-id="b2f57-109">自分の作業ビュー</span><span class="sxs-lookup"><span data-stu-id="b2f57-109">My work view</span></span>

### <a name="summary-tiles"></a><span data-ttu-id="b2f57-110">概要タイル</span><span class="sxs-lookup"><span data-stu-id="b2f57-110">Summary tiles</span></span>

<span data-ttu-id="b2f57-111">[**集計**] セクションのタイルは、支払情報の状態の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="b2f57-111">The tiles in the **Summary** section give an overview of the state of your payment information.</span></span> <span data-ttu-id="b2f57-112">まだ転記されていない支払仕訳帳、期日が経過した請求書、すべての仕入先、および保留中の仕入先を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b2f57-112">You can see payment journals that aren't yet posted, invoices that are past due, all vendors, and vendors that are on hold.</span></span> <span data-ttu-id="b2f57-113">[**集計**] セクションから、新しい支払の実行を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b2f57-113">From the **Summary** section, you can create a new pay run.</span></span>

<span data-ttu-id="b2f57-114">[**集計**] セクションの情報は、ユーザーがサインインしている会社に対するものです。</span><span class="sxs-lookup"><span data-stu-id="b2f57-114">The information in the **Summary** section is for the company that you're signed in to.</span></span>

### <a name="vendor-transactions-grids"></a><span data-ttu-id="b2f57-115">仕入先トランザクション グリッド</span><span class="sxs-lookup"><span data-stu-id="b2f57-115">Vendor transactions grids</span></span>

<span data-ttu-id="b2f57-116">[**仕入先トランザクション**] セクションには、期日が経過した請求書、および決済されていない支払の請求書を表示するグリッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2f57-116">The **Vendor transactions** section contains grids that show the invoices that are past due and payments that aren't settled.</span></span> <span data-ttu-id="b2f57-117">[**期日が経過した請求書**] グリッドから、選択した請求書の決済履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b2f57-117">From the **Invoices past due** grid, you can view the settlement history for a selected invoice.</span></span> <span data-ttu-id="b2f57-118">[**未決済の支払**] グリッドから、選択した請求書の決済履歴を表示し、請求書の決済ができます。</span><span class="sxs-lookup"><span data-stu-id="b2f57-118">From the **Payments not settled** grid, you can view the settlement history for a selected invoice and settle an invoice.</span></span>

<span data-ttu-id="b2f57-119">集中支払の担当者は、それぞれのグリッドの上部に表示されるフィルターを使用して、会社を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b2f57-119">Centralized payment clerks can use a filter that appears at the top of each grid to select a company.</span></span> <span data-ttu-id="b2f57-120">グリッドはフィルター処理されるので’、集中支払の担当者が表示の権限を持つ、集中支払の組織階層で定義される会社のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="b2f57-120">The grid is then filtered so that it shows only those companies that are defined in the centralized payment organizational hierarchy that the centralized payment clerk has rights to view.</span></span>

<span data-ttu-id="b2f57-121">[**仕入先トランザクション**] セクションの [**トランザクションの検索**] タブで、仕入先トランザクションを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="b2f57-121">The **Find transactions** tab in the **Vendor transactions** section lets you search for a vendor transaction.</span></span>

### <a name="related-information"></a><span data-ttu-id="b2f57-122">関連情報</span><span class="sxs-lookup"><span data-stu-id="b2f57-122">Related information</span></span>

<span data-ttu-id="b2f57-123">ワークスペースの [**関連情報**] セクションでリンクを使用して、[**仕入先エイジング**] レポートおよび [**日付別支払集計**] レポートを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="b2f57-123">You can view the **Vendor aging** report and the **Payment summary by date** report by using the links in the **Related information** section of the workspace.</span></span>

## <a name="analytics-page"></a><span data-ttu-id="b2f57-124">分析ページ</span><span class="sxs-lookup"><span data-stu-id="b2f57-124">Analytics page</span></span>

<span data-ttu-id="b2f57-125">[**分析**] ページは、期日が過ぎている仕入先請求書および期日がまだ先である仕入先請求書などの、重要なメトリックスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b2f57-125">The **Analytics** page provides important metrics, such as vendor invoices that are past due and vendor invoices that are due in the future.</span></span> <span data-ttu-id="b2f57-126">このページには、9 つのレポートのページが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2f57-126">This page contains nine report pages.</span></span> <span data-ttu-id="b2f57-127">1 つのページでは概要を、他の 8 つのページでは買掛金勘定支払メトリックスに関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="b2f57-127">One page provides an overview, and the other eight pages provide details about Accounts payable payment metrics.</span></span>

<span data-ttu-id="b2f57-128">次の表に、各レポートページで使用可能な表示機能を示します。</span><span class="sxs-lookup"><span data-stu-id="b2f57-128">The following table shows the visualizations that are available on each report page.</span></span>

| <span data-ttu-id="b2f57-129">レポート ページ</span><span class="sxs-lookup"><span data-stu-id="b2f57-129">Report page</span></span> | <span data-ttu-id="b2f57-130">視覚化</span><span class="sxs-lookup"><span data-stu-id="b2f57-130">Visualization</span></span> |
|-------------|---------------|
| <span data-ttu-id="b2f57-131">仕入先支払の概要</span><span class="sxs-lookup"><span data-stu-id="b2f57-131">Vendor payments overview</span></span> | <ul><li><span data-ttu-id="b2f57-132">期日が経過した請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-132">Invoices past due</span></span></li><li><span data-ttu-id="b2f57-133">今日が期限の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-133">Invoices due today</span></span></li><li><span data-ttu-id="b2f57-134">失効した割引に対して取得される割引</span><span class="sxs-lookup"><span data-stu-id="b2f57-134">Discounts taken to discounts lost</span></span></li><li><span data-ttu-id="b2f57-135">現金割引日付による、期日がまだ先の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-135">Invoices due in future by cash discount date</span></span></li><li><span data-ttu-id="b2f57-136">期日別の、期日がまだ先の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-136">Invoices due in future by due date</span></span></li><li><span data-ttu-id="b2f57-137">期限厳守で支払われた請求書に対して、遅く支払われた請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-137">Invoices paid late to invoices paid on time</span></span></li><li><span data-ttu-id="b2f57-138">支払のワークフローの割り当て</span><span class="sxs-lookup"><span data-stu-id="b2f57-138">Payment workflow assignment</span></span></li><li><span data-ttu-id="b2f57-139">顧客残高への仕入先</span><span class="sxs-lookup"><span data-stu-id="b2f57-139">Vendor to customer balance</span></span></li><li><span data-ttu-id="b2f57-140">支払保留の未処理請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-140">Open invoices with payment hold</span></span></li></ul> |
| <span data-ttu-id="b2f57-141">期日が経過した請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-141">Invoices past due</span></span> | <ul><li><span data-ttu-id="b2f57-142">期日が経過した請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-142">Invoices past due</span></span></li><li><span data-ttu-id="b2f57-143">期日が経過した請求書の詳細</span><span class="sxs-lookup"><span data-stu-id="b2f57-143">Invoices past due details</span></span></li><li><span data-ttu-id="b2f57-144">未処理請求書の合計</span><span class="sxs-lookup"><span data-stu-id="b2f57-144">Total open invoices</span></span></li><li><span data-ttu-id="b2f57-145">仕入先グループごとの、期日が経過した請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-145">Invoices past due per vendor group</span></span></li><li><span data-ttu-id="b2f57-146">会社ごとの期日が経過した請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-146">Invoices past due per company</span></span></li></ul> |
| <span data-ttu-id="b2f57-147">今日が期日の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-147">Invoices due today</span></span> | <ul><li><span data-ttu-id="b2f57-148">今日が期日の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-148">Invoices due today</span></span></li><li><span data-ttu-id="b2f57-149">今日が期日の請求書の詳細</span><span class="sxs-lookup"><span data-stu-id="b2f57-149">Invoices due today details</span></span></li><li><span data-ttu-id="b2f57-150">会社ごとの今日が期日の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-150">Invoices due today per company</span></span></li><li><span data-ttu-id="b2f57-151">仕入先グループごとの、今日が期日の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-151">Invoices due today per vendor group</span></span></li></ul> |
| <span data-ttu-id="b2f57-152">失効した割引に対して取得される割引</span><span class="sxs-lookup"><span data-stu-id="b2f57-152">Discounts taken to discounts lost</span></span> | <ul><li><span data-ttu-id="b2f57-153">失効した割引に対して取得される割引</span><span class="sxs-lookup"><span data-stu-id="b2f57-153">Discounts taken to discount lost</span></span></li><li><span data-ttu-id="b2f57-154">失効した割引詳細に対して取得される割引</span><span class="sxs-lookup"><span data-stu-id="b2f57-154">Discounts taken to discount lost details</span></span></li><li><span data-ttu-id="b2f57-155">会社ごとに失効した割引に対して取得される割引</span><span class="sxs-lookup"><span data-stu-id="b2f57-155">Discounts taken to discount lost per company</span></span></li><li><span data-ttu-id="b2f57-156">仕入先グループごとに失効した割引に対して取得される割引</span><span class="sxs-lookup"><span data-stu-id="b2f57-156">Discounts taken to discount lost per vendor group</span></span></li></ul> |
| <span data-ttu-id="b2f57-157">未来が期日の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-157">Invoices due in future</span></span> | <ul><li><span data-ttu-id="b2f57-158">未来が期日の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-158">Invoices due in future</span></span></li><li><span data-ttu-id="b2f57-159">未来が期日の請求書の詳細</span><span class="sxs-lookup"><span data-stu-id="b2f57-159">Invoices due in future details</span></span></li><li><span data-ttu-id="b2f57-160">会社ごとの、未来が期日の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-160">Invoices due in future per company</span></span></li><li><span data-ttu-id="b2f57-161">仕入先グループごとの、未来が期日の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-161">Invoices due in future per vendor group</span></span></li><li><span data-ttu-id="b2f57-162">現金割引日付による、期日がまだ先の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-162">Invoices due in future by cash discount date</span></span></li><li><span data-ttu-id="b2f57-163">期日別の、期日がまだ先の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-163">Invoices due in future by due date</span></span></li></ul> |
| <span data-ttu-id="b2f57-164">遅く支払われた請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-164">Invoices paid late</span></span> | <ul><li><span data-ttu-id="b2f57-165">期日後に支払われた請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-165">Invoices paid after due date</span></span></li><li><span data-ttu-id="b2f57-166">期日後に支払われた請求書の詳細</span><span class="sxs-lookup"><span data-stu-id="b2f57-166">Invoices paid after due date details</span></span></li><li><span data-ttu-id="b2f57-167">会社ごとの、期日後に支払われた請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-167">Invoices paid after due date per company</span></span></li><li><span data-ttu-id="b2f57-168">仕入先グループごとの、期日後に支払われた請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-168">Invoices paid after due date per vendor group</span></span></li><li><span data-ttu-id="b2f57-169">期限厳守で支払われた請求書と遅く支払われた請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-169">Invoices paid late versus invoices paid on time</span></span></li></ul> |
| <span data-ttu-id="b2f57-170">支払ワークフロー</span><span class="sxs-lookup"><span data-stu-id="b2f57-170">Payment workflow</span></span> | <ul><li><span data-ttu-id="b2f57-171">仕入先支払ワークフロー インスタンス</span><span class="sxs-lookup"><span data-stu-id="b2f57-171">Vendor payment workflow instances</span></span></li><li><span data-ttu-id="b2f57-172">承認者ごとの仕入先支払ワークフロー インスタンス</span><span class="sxs-lookup"><span data-stu-id="b2f57-172">Vendor payment workflow instances per approver</span></span></li><li><span data-ttu-id="b2f57-173">会社ごとの仕入先支払ワークフロー インスタンス</span><span class="sxs-lookup"><span data-stu-id="b2f57-173">Vendor payment workflow instances per company</span></span></li><li><span data-ttu-id="b2f57-174">承認者によるワークフローでの平均日数</span><span class="sxs-lookup"><span data-stu-id="b2f57-174">Average days in workflow by approver</span></span></li></ul> |
| <span data-ttu-id="b2f57-175">顧客残高への仕入先</span><span class="sxs-lookup"><span data-stu-id="b2f57-175">Vendor to customer balance</span></span> | <ul><li><span data-ttu-id="b2f57-176">顧客残高への仕入先</span><span class="sxs-lookup"><span data-stu-id="b2f57-176">Vendor to customer balance</span></span></li><li><span data-ttu-id="b2f57-177">会社ごとの顧客残高への仕入先</span><span class="sxs-lookup"><span data-stu-id="b2f57-177">Vendor to customer balance per company</span></span></li><li><span data-ttu-id="b2f57-178">顧客残高への仕入先の詳細</span><span class="sxs-lookup"><span data-stu-id="b2f57-178">Vendor to customer balance details</span></span></li></ul> |
| <span data-ttu-id="b2f57-179">支払保留の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-179">Invoices with payment hold</span></span> | <ul><li><span data-ttu-id="b2f57-180">支払保留の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-180">Invoices with payment hold</span></span></li><li><span data-ttu-id="b2f57-181">支払保留の請求書の詳細</span><span class="sxs-lookup"><span data-stu-id="b2f57-181">Invoices with payment hold details</span></span></li><li><span data-ttu-id="b2f57-182">会社ごとの支払保留の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-182">Invoices with payment hold per company</span></span></li><li><span data-ttu-id="b2f57-183">仕入先グループごとの支払保留の請求書</span><span class="sxs-lookup"><span data-stu-id="b2f57-183">Invoices with payment hold per vendor group</span></span></li></ul> |
