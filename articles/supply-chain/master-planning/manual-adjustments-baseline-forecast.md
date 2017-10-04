---
title: "ベースライン予測に対して手動調整を行う"
description: "この記事では、ベースライン予測に手動調整を加えたり、予測の詳細を表示したりする方法を説明します。"
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 218374cdb6b5588648422d97c04fb60f26e47ac7
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="make-manual-adjustments-to-the-baseline-forecast"></a><span data-ttu-id="5265b-103">ベースライン予測に対して手動調整を行う</span><span class="sxs-lookup"><span data-stu-id="5265b-103">Make manual adjustments to the baseline forecast</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5265b-104">この記事では、ベースライン予測に手動調整を加えたり、予測の詳細を表示したりする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5265b-104">This article explains how you can make manual adjustments to a baseline forecast and view details of the forecast.</span></span> 

<span data-ttu-id="5265b-105">手動調整を行う前に、さまざまなページでいくつかの概念を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="5265b-105">Before you make manual adjustments, it's important that you understand a few concepts on various pages.</span></span>

## <a name="grid-on-the-adjusted-demand-forecast-page"></a><span data-ttu-id="5265b-106">[調整された需要予測] ページのグリッド</span><span class="sxs-lookup"><span data-stu-id="5265b-106">Grid on the Adjusted demand forecast page</span></span>
<span data-ttu-id="5265b-107">[**調整された需要予測**] ページには次の構造を持つグリッドが含まれます:</span><span class="sxs-lookup"><span data-stu-id="5265b-107">The **Adjusted demand forecast** page includes a grid that has the following structure:</span></span>

-   <span data-ttu-id="5265b-108">最初の列は予測が生成された品目、品目配賦キー、会社などを示します。</span><span class="sxs-lookup"><span data-stu-id="5265b-108">The first column shows the items, item allocation keys, companies, and so on, that the forecast has been generated for.</span></span> <span data-ttu-id="5265b-109">ページのサブタイトルでは、グリッドに表示される現在の予測分析コードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5265b-109">The subtitle of the page provides a description of the current forecast dimensions that are shown in the grid.</span></span> <span data-ttu-id="5265b-110">たとえば、ページのサブタイトルが [**会社/サイト/品目配賦キー**] で、グリッドの行のヘッダーの 1 つが **USMF / 1 / D\_Alloc** である場合、その行は USMF 会社、サイト 1、および **D\_Alloc** 品目配賦キーの予測を表示します。</span><span class="sxs-lookup"><span data-stu-id="5265b-110">For example, if the subtitle of the page is **Company / Site / Item allocation key**, and one of the row headers in the grid is **USMF / 1 / D\_Alloc**, that row shows the forecast for the USMF company, site 1, and the **D\_Alloc** item allocation key.</span></span>
-   <span data-ttu-id="5265b-111">後続の列は、予測が生成された予測バケットを表します。</span><span class="sxs-lookup"><span data-stu-id="5265b-111">Subsequent columns represent the forecast buckets that the forecast has been generated for.</span></span> <span data-ttu-id="5265b-112">各列のヘッダーは、列を示す予測バケットの最初の日付です。</span><span class="sxs-lookup"><span data-stu-id="5265b-112">Each column header is the first date of the forecast bucket that the column shows.</span></span>
-   <span data-ttu-id="5265b-113">セルの値は、その特定の予測バケットの一つの品目や品目配賦キーの予測などを表します。</span><span class="sxs-lookup"><span data-stu-id="5265b-113">The values in the cells represent the forecast for one item, item allocation key, and so on, for that specific forecast bucket.</span></span>

## <a name="forecast-aggregation-and-deaggregation"></a><span data-ttu-id="5265b-114">予測の集計と非集計</span><span class="sxs-lookup"><span data-stu-id="5265b-114">Forecast aggregation and deaggregation</span></span>
<span data-ttu-id="5265b-115">ページのサブタイトルでは、予測の集計レベルを表示します。</span><span class="sxs-lookup"><span data-stu-id="5265b-115">The subtitle of the page shows the level of forecast aggregation.</span></span> 

<span data-ttu-id="5265b-116">たとえば、ページのサブタイトルが **会社/サイト/配賦キー/品目番号/色/サイズ/コンフィギュレーション/スタイル** の場合は、予測の集計はなく、予測は品目および分析コードのレベルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5265b-116">For example, if the subtitle of the page is **Company / Site / Allocation key / Item number / Color / Size / Configuration / Style**, there is no forecast aggregation, and the forecast is shown at the level of the item and its dimensions.</span></span> <span data-ttu-id="5265b-117">集計を変更するには、アプリケーション メニューから開くことができる [**予測分析コードの変更**] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="5265b-117">To change the aggregation, use the **Change forecast dimensions** page, which you can open from the application menu.</span></span> 

<span data-ttu-id="5265b-118">予測を変更するには、使用可能なセルのいずれかをクリックし、調整された予測の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5265b-118">To modify the forecast, click in any of the cells that are available, and type the adjusted forecast value.</span></span> <span data-ttu-id="5265b-119">編集されたセルは、需要予測外部サービスが作成された予測ではなく、手動で調整されている予測であることを示すためにすぐに太字になります。</span><span class="sxs-lookup"><span data-stu-id="5265b-119">The edited cell immediately becomes bold to indicate that the forecast that it shows isn't the forecast that the demand forecasting service created, but has been manually adjusted.</span></span> 

<span data-ttu-id="5265b-120">より多くの集計データを表示するページを作成する集計を変更する場合、[**需要予測の明細行**] ページを使用して、集計予測を構成する個々の予測明細行を表示します。</span><span class="sxs-lookup"><span data-stu-id="5265b-120">If you change the aggregation to make the page show more aggregated data, you can use the **Demand forecast lines** page to see the individual forecast lines that make up the aggregated forecast.</span></span> 

<span data-ttu-id="5265b-121">たとえば、品目レベルで予測が生成されているが、プロモーションまたは別の類似したイベントのためにこの品目の需要がすべてのサイトで増すことに気づきます。</span><span class="sxs-lookup"><span data-stu-id="5265b-121">For example, you've generated the forecast at the item level, but you know that the demand for this item will increase across all sites because of a promotion or another similar event.</span></span> <span data-ttu-id="5265b-122">この場合、[**予測分析コードの変更**] ページで、**会社/品目配賦キー/品目**に集約を設定できます。</span><span class="sxs-lookup"><span data-stu-id="5265b-122">In this case, you can set the aggregation to **Company / Item allocation key / Item** on the **Change forecast dimensions** page.</span></span> <span data-ttu-id="5265b-123">[**調整された需要予測**] グリッド内のすべてのサイトで品目のグローバル予測を調整できます。</span><span class="sxs-lookup"><span data-stu-id="5265b-123">You can adjust the global forecast for the item across all sites in the **Adjusted demand forecast** grid.</span></span> <span data-ttu-id="5265b-124">すべてのサイトに変更の影響を表示するには、[**需要予測の明細行**] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="5265b-124">To see the effect of your change across all sites, open the **Demand forecast lines** page.</span></span> <span data-ttu-id="5265b-125">このページでは、各サイトの品目に対する 1 つの明細行、調整された予測数量、および当初予測数量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5265b-125">On this page, you will see one line for the item for each site, the adjusted forecast quantity, and the original forecast quantity.</span></span> 

<span data-ttu-id="5265b-126">予測数量の調整が集計レベルで行われる場合、システムでは加重配賦を使用して、変更が集計を作成する明細行に配分されます。</span><span class="sxs-lookup"><span data-stu-id="5265b-126">When the adjustment of the forecasted quantity is made at an aggregated level, the system uses weighted allocation to distribute the change among the lines that create the aggregation.</span></span> 

<span data-ttu-id="5265b-127">また、非集計グリッドの [**合計数量**] 値または [**数量**] セルのいずれかを変更することで、[**需要予測の明細行**] ページで手動調整を加えることもできます。</span><span class="sxs-lookup"><span data-stu-id="5265b-127">You can also make manual adjustments on the **Demand forecast lines** page, by modifying either the **Total quantity** value or the **Quantity** cells in the de-aggregation grid.</span></span>

## <a name="viewing-details-of-the-forecast"></a><span data-ttu-id="5265b-128">予測の詳細を表示</span><span class="sxs-lookup"><span data-stu-id="5265b-128">Viewing details of the forecast</span></span>
<span data-ttu-id="5265b-129">[**需要予測の詳細**] ページを開いて、予測に関する詳細情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5265b-129">You can open the **Demand forecast details** page to view more information about the forecast.</span></span> 

<span data-ttu-id="5265b-130">[**需要予測の詳細**] ページでは、グラフィックおよび表の形式で次の情報を表示します:</span><span class="sxs-lookup"><span data-stu-id="5265b-130">The **Demand forecast details** page shows the following information in graphical and tabular formats:</span></span>

-   <span data-ttu-id="5265b-131">予測の予想の基になる履歴需要。</span><span class="sxs-lookup"><span data-stu-id="5265b-131">The historical demand that the forecast predictions are based on.</span></span>
-   <span data-ttu-id="5265b-132">マスタ プランで使用される現在の予測。</span><span class="sxs-lookup"><span data-stu-id="5265b-132">The current forecast that is used by Master planning.</span></span>
-   <span data-ttu-id="5265b-133">手動で調整されている新しい需要予測の値および金額。</span><span class="sxs-lookup"><span data-stu-id="5265b-133">The new demand forecast values and the amounts they have been manually adjusted by.</span></span>
-   <span data-ttu-id="5265b-134">予測された値の信頼区間。</span><span class="sxs-lookup"><span data-stu-id="5265b-134">The confidence interval for the forecasted values.</span></span>
-   <span data-ttu-id="5265b-135">予測を生成するのに使用された予測モデル。</span><span class="sxs-lookup"><span data-stu-id="5265b-135">The forecast model that was used to generate the forecast.</span></span> <span data-ttu-id="5265b-136">集計データを表示している場合、集計されたすべてのタイム シリーズに使用されたすべての方法の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5265b-136">If you're viewing aggregated data, you will see the list of all the methods that were used for all the aggregated time series.</span></span>
-   <span data-ttu-id="5265b-137">内部モデル精度 (MAPE)。</span><span class="sxs-lookup"><span data-stu-id="5265b-137">The internal model accuracy (MAPE).</span></span> <span data-ttu-id="5265b-138">予測精度に関する詳細については、[予測精度の監視](monitor-forecast-accuracy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5265b-138">For more information about forecast accuracy, see [Monitoring forecast accuracy](monitor-forecast-accuracy.md).</span></span>

<span data-ttu-id="5265b-139">**メモ :**</span><span class="sxs-lookup"><span data-stu-id="5265b-139">**Notes:**</span></span>

-   <span data-ttu-id="5265b-140">このページの [**予測**] セクションに表示される信頼区間は、信頼区間の上限と信頼区間の下限の差を表します。</span><span class="sxs-lookup"><span data-stu-id="5265b-140">The confidence interval that appears in the **Forecast** section of the page represents the difference between the confidence interval upper limit and the confidence interval lower limit.</span></span> <span data-ttu-id="5265b-141">上限と下限の値を確認するには、[**履歴需要と予測のグラフィック表示**] セクションでグラフをポイントします。</span><span class="sxs-lookup"><span data-stu-id="5265b-141">To see the values for the upper and lower limits, hover over the chart in the **Historical demand and forecast graphically** section.</span></span>
-   <span data-ttu-id="5265b-142">Finance and Operations 需要予測 Microsoft Azure Machine Learning サービスを使用する際は、生成される予測に必要な信頼レベルの割合を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5265b-142">If you use the Finance and Operations Demand forecasting Microsoft Azure Machine Learning service, you can specify the confidence level percentage that the forecast that is generated should have.</span></span> <span data-ttu-id="5265b-143">信頼区間は、需要予測の商品見積として機能する値の範囲で構成されます。</span><span class="sxs-lookup"><span data-stu-id="5265b-143">A confidence interval consists of a range of values that act as good estimates for the demand forecast.</span></span> <span data-ttu-id="5265b-144">95% の信頼レベルは、需要予測が信頼区間の範囲外になるリスクが 5% あることを示します。</span><span class="sxs-lookup"><span data-stu-id="5265b-144">A 95-percent confidence level percentage indicates that there is a 5-percent risk that the demand forecast falls outside the confidence interval range.</span></span>

<span data-ttu-id="5265b-145">また、[**予測**] セクションの [**予測**] 行の値を変更することによって、[**需要予測の詳細**] ページで予測に手動調整を加えることもできます。</span><span class="sxs-lookup"><span data-stu-id="5265b-145">You can also make manual adjustments to the forecast on the **Demand forecast details** page, by modifying the values in the **Forecast** row in the **Forecast** section.</span></span>

<a name="see-also"></a><span data-ttu-id="5265b-146">参照</span><span class="sxs-lookup"><span data-stu-id="5265b-146">See also</span></span>
--------

[<span data-ttu-id="5265b-147">予測精度の監視</span><span class="sxs-lookup"><span data-stu-id="5265b-147">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)

[<span data-ttu-id="5265b-148">統計ベースライン予測の生成</span><span class="sxs-lookup"><span data-stu-id="5265b-148">Generating a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)



