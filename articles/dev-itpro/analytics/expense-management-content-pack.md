---
title: 経費管理 Power BI コンテンツ
description: このトピックでは、経費管理 Power BI コンテンツ パックの内容について説明します。
author: RyanSand
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: TrvExpenseWorkspace, ExpenseWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: a07d9ed7e4c57c2444d1c2a017109509c153aad4
ms.sourcegitcommit: 4e104ad3fc4a160a06f0d031974d60abcbb62829
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "851187"
---
# <a name="expense-management-power-bi-content"></a><span data-ttu-id="b0efd-103">経費管理 Power BI コンテンツ</span><span class="sxs-lookup"><span data-stu-id="b0efd-103">Expense management Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0efd-104">このトピックでは、経費管理 Power BI コンテンツの内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0efd-104">This topic describes what is included in the Expense management Power BI content.</span></span> 

## <a name="overview"></a><span data-ttu-id="b0efd-105">概要</span><span class="sxs-lookup"><span data-stu-id="b0efd-105">Overview</span></span>
<span data-ttu-id="b0efd-106">バージョン 8.1 以降では、2 つの Power BI コンテンツ パックを経費管理で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0efd-106">Two Power BI content packs are available for use with Expense management in version 8.1 and later.</span></span> 
- <span data-ttu-id="b0efd-107">経費精算書を送信する従業員用に設計された個人用ダッシュボードがあります。</span><span class="sxs-lookup"><span data-stu-id="b0efd-107">There is a personal dashboard designed for employees who submit expense reports.</span></span> 

  <span data-ttu-id="b0efd-108">ダッシュボードは、未送信および送信済の金額、履歴、および経費トランザクションの履歴分析に関する重要な情報を個人に提供するように調整されています。</span><span class="sxs-lookup"><span data-stu-id="b0efd-108">The dashboard is tailored to provide key information to individuals about unsubmitted and submitted amounts, as well as history and insights into expense transaction history.</span></span> <span data-ttu-id="b0efd-109">個人用ダッシュボードは、ユーザーにとって最も重要な情報を含む単一ページです。</span><span class="sxs-lookup"><span data-stu-id="b0efd-109">The personal dashboard is a single page containing the most important information for the user.</span></span>

- <span data-ttu-id="b0efd-110">買掛金勘定の担当者およびマネージャー用に設計された、管理者ダッシュボードがあります。</span><span class="sxs-lookup"><span data-stu-id="b0efd-110">There is an admin dashboard designed for accounts payable clerks and managers.</span></span> <span data-ttu-id="b0efd-111">ダッシュボードは、従業員経費全体の追跡および報告のために調整されています。</span><span class="sxs-lookup"><span data-stu-id="b0efd-111">The dashboard is tailored toward tracking and reporting on overall employee expenses.</span></span> <span data-ttu-id="b0efd-112">未送信の経費、マイレージおよび経費報告の平均金額などの主要経費指標が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0efd-112">It provides key expense metrics, such as unsubmitted expenses, mileage, and average expense report amounts.</span></span> <span data-ttu-id="b0efd-113">トランザクション データを使用し、すべての会社の経費管理の集計ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="b0efd-113">It uses transactional data and provides aggregate views of expense management across all companies.</span></span> <span data-ttu-id="b0efd-114">また、財務分析コードのデータを追加するオプションを使用して、従業員ごとの内訳も表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0efd-114">It also provides a breakdown per employee, with the option to add financial dimension data.</span></span> <span data-ttu-id="b0efd-115">管理者経費分析の内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b0efd-115">The Admin expense analytics content contains:</span></span> 
  - <span data-ttu-id="b0efd-116">経費金額に関する主要な指標とドラフト、処理中の経費、および完了した経費報告に関する分析を含む概要ページ。</span><span class="sxs-lookup"><span data-stu-id="b0efd-116">An overview page with key metrics about expense amounts and insights into draft, in process, and completed expense reports.</span></span> 
  - <span data-ttu-id="b0efd-117">時間、原価タイプ、統計グループ別に従業員に関する個々の詳細を確認するための従業員統計ページ。</span><span class="sxs-lookup"><span data-stu-id="b0efd-117">An employee statistics page to review individual details about an employee by time, cost type, and statistics group.</span></span> 
  - <span data-ttu-id="b0efd-118">経時的に複数の従業員を比較するための従業員比較ページ。</span><span class="sxs-lookup"><span data-stu-id="b0efd-118">An employee comparison page to compare multiple employees over time.</span></span> 

<span data-ttu-id="b0efd-119">金額はすべて会社通貨で表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0efd-119">All the amounts are shown in the company currency.</span></span> <span data-ttu-id="b0efd-120">すべての会社のデータが表示されますが、必要に応じて会社のフィルターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b0efd-120">Data for all companies are shown, but if needed you can add a company filter.</span></span> 

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="b0efd-121">Power BI コンテンツへのアクセス</span><span class="sxs-lookup"><span data-stu-id="b0efd-121">Accessing the Power BI content</span></span>
<span data-ttu-id="b0efd-122">Expense Admin Dashboard.pbix および Expense Personal Dashboard.pbix Power BI コンテンツは、Microsoft Dynamics Lifecycle Services (LCS) の共有資産ライブラリにあります。</span><span class="sxs-lookup"><span data-stu-id="b0efd-122">You can find the Expense Admin Dashboard.pbix and Expense Personal Dashboard.pbix Power BI content in the Shared assets library in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="b0efd-123">コンテンツのダウンロード方法および組織で実装する方法の詳細については、[Microsoft およびパートナーからの LCS での Power BI コンテンツ](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0efd-123">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).</span></span>
<span data-ttu-id="b0efd-124">コンテンツは、経費管理ワークスペースから埋め込み Power Bi コンテンツとして入手できます。</span><span class="sxs-lookup"><span data-stu-id="b0efd-124">The content is available from the Expense Management workspace as embedded Power Bi content.</span></span> <span data-ttu-id="b0efd-125">経費の所有者は、誰でも自分の経費にアクセスすることができますが、すべてのユーザーの経費データに関しては、買掛金担当者と管理者のみが管理者コンテンツにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0efd-125">Any expense owner can access personal expenses for themselves, while only Accounts Payable clerks and managers have access to the Admin content to view all user's expense data.</span></span>

## <a name="refreshing-the-power-bi-content"></a><span data-ttu-id="b0efd-126">Power BI コンテンツの更新</span><span class="sxs-lookup"><span data-stu-id="b0efd-126">Refreshing the Power BI content</span></span>
<span data-ttu-id="b0efd-127">経費管理 Power BI コンテンツは、TrvBiExpenseMeasurement メジャーおよび BudgetActivityMeasure をエンティティ格納から更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0efd-127">The Expense management Power BI content requires the TrvBiExpenseMeasurement measure and the BudgetActivityMeasure to be refreshed from the Entity Store.</span></span> 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="b0efd-128">Power BI コンテンツに含まれるメトリックス</span><span class="sxs-lookup"><span data-stu-id="b0efd-128">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="b0efd-129">コンテンツには、レポートのページ一式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b0efd-129">The content includes a set of report pages.</span></span> <span data-ttu-id="b0efd-130">各ページは、グラフ、タイル、テーブルとして視覚化される一連のメトリックスで構成されています。</span><span class="sxs-lookup"><span data-stu-id="b0efd-130">Each page consists of a set of metrics that are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="b0efd-131">次の表は、Power BI コンテンツの視覚化の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="b0efd-131">The following table provides an overview of the visualizations in the Power BI content.</span></span>

<span data-ttu-id="b0efd-132">**個人経費分析**</span><span class="sxs-lookup"><span data-stu-id="b0efd-132">**Personal expenses analytics**</span></span>

| <span data-ttu-id="b0efd-133">レポート ページ</span><span class="sxs-lookup"><span data-stu-id="b0efd-133">Report page</span></span> | <span data-ttu-id="b0efd-134">視覚化</span><span class="sxs-lookup"><span data-stu-id="b0efd-134">Visualization</span></span>                             |
|-------------|-------------------------------------------|
| <span data-ttu-id="b0efd-135">自分の経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-135">My expenses</span></span> | <span data-ttu-id="b0efd-136">マイレージの量</span><span class="sxs-lookup"><span data-stu-id="b0efd-136">Amount of mileage</span></span>                         |
|             | <span data-ttu-id="b0efd-137">処理中の経費精算書</span><span class="sxs-lookup"><span data-stu-id="b0efd-137">In process expense reports</span></span>                |
|             | <span data-ttu-id="b0efd-138">一連番号</span><span class="sxs-lookup"><span data-stu-id="b0efd-138">No.</span></span> <span data-ttu-id="b0efd-139">未送信経費の</span><span class="sxs-lookup"><span data-stu-id="b0efd-139">of Unsubmitted expenses</span></span>               |
|             | <span data-ttu-id="b0efd-140">支払対象の個人経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-140">Personal expenses to be paid</span></span>              |
|             | <span data-ttu-id="b0efd-141">未送信金額</span><span class="sxs-lookup"><span data-stu-id="b0efd-141">Amount unsubmitted</span></span>                        |
|             | <span data-ttu-id="b0efd-142">送信済金額</span><span class="sxs-lookup"><span data-stu-id="b0efd-142">Amount submitted</span></span>                          |
|             | <span data-ttu-id="b0efd-143">払い戻し処理中の金額</span><span class="sxs-lookup"><span data-stu-id="b0efd-143">Amount awaiting reimbursement</span></span>             |
|             | <span data-ttu-id="b0efd-144">金額とステータスを含む経費精算書</span><span class="sxs-lookup"><span data-stu-id="b0efd-144">Expense reports with amounts and status</span></span>   |
|             | <span data-ttu-id="b0efd-145">送信されたが未承認の経費清算書</span><span class="sxs-lookup"><span data-stu-id="b0efd-145">Submitted but unapproved expense reports</span></span>  |
|             | <span data-ttu-id="b0efd-146">原価タイプ別経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-146">Expenses by cost type</span></span>                     |
|             | <span data-ttu-id="b0efd-147">商社別経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-147">Expenses by merchant</span></span>                      |
|             | <span data-ttu-id="b0efd-148">処理済経費別経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-148">Expenses by processed expenses</span></span>            |
|             | <span data-ttu-id="b0efd-149">プロジェクト別経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-149">Expenses by project</span></span>                       |
|             | <span data-ttu-id="b0efd-150">時間経過に伴うトランザクション合計金額</span><span class="sxs-lookup"><span data-stu-id="b0efd-150">Total transaction amount over time</span></span>        |

<span data-ttu-id="b0efd-151">**管理者経費分析**</span><span class="sxs-lookup"><span data-stu-id="b0efd-151">**Admin expenses analytics**</span></span>

| <span data-ttu-id="b0efd-152">レポート ページ</span><span class="sxs-lookup"><span data-stu-id="b0efd-152">Report page</span></span>         | <span data-ttu-id="b0efd-153">視覚化</span><span class="sxs-lookup"><span data-stu-id="b0efd-153">Visualization</span></span>                           |           
|---------------------|-----------------------------------------|
| <span data-ttu-id="b0efd-154">経費の概要</span><span class="sxs-lookup"><span data-stu-id="b0efd-154">Expense Overview</span></span>    | <span data-ttu-id="b0efd-155">ドラフト経費金額</span><span class="sxs-lookup"><span data-stu-id="b0efd-155">Draft expenses amount</span></span>                   |
|                     | <span data-ttu-id="b0efd-156">ドラフト経費の行の数</span><span class="sxs-lookup"><span data-stu-id="b0efd-156">Number of draft expense lines</span></span>           |
|                     | <span data-ttu-id="b0efd-157">ドラフト経費行</span><span class="sxs-lookup"><span data-stu-id="b0efd-157">Draft expense lines</span></span>                     |
|                     | <span data-ttu-id="b0efd-158">経費精算書のポリシー違反</span><span class="sxs-lookup"><span data-stu-id="b0efd-158">Expense report policy violations</span></span>        |
|                     | <span data-ttu-id="b0efd-159">未払い金額</span><span class="sxs-lookup"><span data-stu-id="b0efd-159">Amount outstanding</span></span>                      |
|                     | <span data-ttu-id="b0efd-160">送信されたが未承認の経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-160">Submitted but unapproved expenses</span></span>       |
|                     | <span data-ttu-id="b0efd-161">承認済経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-161">Approved expenses</span></span>                       |
|                     | <span data-ttu-id="b0efd-162">経費合計金額</span><span class="sxs-lookup"><span data-stu-id="b0efd-162">Total expense amount</span></span>                    |
|                     | <span data-ttu-id="b0efd-163">経費精算書の概要</span><span class="sxs-lookup"><span data-stu-id="b0efd-163">Expense report summaries</span></span>                |
|                     | <span data-ttu-id="b0efd-164">原価タイプ別経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-164">Expenses by cost type</span></span>                   |
|                     | <span data-ttu-id="b0efd-165">商社別経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-165">Expenses by merchant</span></span>                    |
|                     | <span data-ttu-id="b0efd-166">従業員別経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-166">Expenses by employees</span></span>                   |
|                     | <span data-ttu-id="b0efd-167">プロジェクト対経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-167">Expenses vs project</span></span>                     |
| <span data-ttu-id="b0efd-168">従業員比較</span><span class="sxs-lookup"><span data-stu-id="b0efd-168">Employee Comparison</span></span> | <span data-ttu-id="b0efd-169">経費金額</span><span class="sxs-lookup"><span data-stu-id="b0efd-169">Expense amounts</span></span>                         |
|                     | <span data-ttu-id="b0efd-170">時間経過に伴う従業員ごとの経費金額</span><span class="sxs-lookup"><span data-stu-id="b0efd-170">Expense amounts over time by employee</span></span>   |
| <span data-ttu-id="b0efd-171">従業員統計</span><span class="sxs-lookup"><span data-stu-id="b0efd-171">Employee Statistics</span></span> | <span data-ttu-id="b0efd-172">原価タイプ別経費清算書</span><span class="sxs-lookup"><span data-stu-id="b0efd-172">Expense reports by cost type</span></span>            |
|                     | <span data-ttu-id="b0efd-173">個人経費</span><span class="sxs-lookup"><span data-stu-id="b0efd-173">Personal expenses</span></span>                       |
|                     | <span data-ttu-id="b0efd-174">統計グループ別経費精算書</span><span class="sxs-lookup"><span data-stu-id="b0efd-174">Expense reports by statistics group</span></span>     |