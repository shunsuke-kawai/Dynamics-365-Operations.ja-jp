---
title: "調整された予測の承認"
description: "すべての予測データがすぐに承認される必要はありません。 この記事では、予測が承認される期間を指定する方法を説明します。 また、特定の会社と予測モデルの予測を承認する方法も説明します。"
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 399a7a21ec71fe50e280ccb24699cda76d571990
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="authorize-an-adjusted-forecast"></a><span data-ttu-id="f76a0-105">調整された予測の承認</span><span class="sxs-lookup"><span data-stu-id="f76a0-105">Authorize an adjusted forecast</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f76a0-106">すべての予測データがすぐに承認される必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f76a0-106">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="f76a0-107">この記事では、予測が承認される期間を指定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f76a0-107">This article explains how you can specify the period that a forecast is authorized for.</span></span> <span data-ttu-id="f76a0-108">また、特定の会社と予測モデルの予測を承認する方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="f76a0-108">It also explains how you can authorize the forecast for specific companies and forecast models.</span></span>

<span data-ttu-id="f76a0-109">すべての予測データがすぐに承認される必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f76a0-109">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="f76a0-110">予測が承認される期間の開始日と終了日を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f76a0-110">You can specify the start and end dates of the period that the forecast is authorized for.</span></span> <span data-ttu-id="f76a0-111">この機能により、特定のバケットを凍結できます。</span><span class="sxs-lookup"><span data-stu-id="f76a0-111">This functionality lets you freeze specific buckets.</span></span> 

<span data-ttu-id="f76a0-112">指定する開始日と終了日が、予測が生成されたバケットの開始日と終了日に対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f76a0-112">The start and end dates that you specify must correspond to the start and end dates of the bucket that the forecast is generated in.</span></span> <span data-ttu-id="f76a0-113">調整が必要な場合、システムではこの制限が適用され、自動的に日付を調整します。</span><span class="sxs-lookup"><span data-stu-id="f76a0-113">The system enforces this restriction and automatically adjusts the dates, if adjustment is required.</span></span> 

<span data-ttu-id="f76a0-114">[**認証**] ページの [**詳細**] タブで、最後に生成された予測に関する詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f76a0-114">On the **Details** tab of the **Authorization** page, you can view details about the forecast that was most recently generated.</span></span> 

<span data-ttu-id="f76a0-115">会社および予測モデルを選択して、使用する予測を承認できます。</span><span class="sxs-lookup"><span data-stu-id="f76a0-115">You can select the companies and the forecast models to authorize the forecast for use.</span></span> <span data-ttu-id="f76a0-116">既定では、グリッドに需要予測が作成されたすべての会社が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f76a0-116">By default, the grid includes all the companies that forecast demand has been created for.</span></span> <span data-ttu-id="f76a0-117">会社ごとに、現在の予測計画に対応する予測モデルは、パラメーターが事前に入力されているマスタ プランに設定されています。</span><span class="sxs-lookup"><span data-stu-id="f76a0-117">For each company, the forecast model that corresponds to the current forecast plan that is set up in the master planning parameters is prefilled.</span></span> <span data-ttu-id="f76a0-118">ただし、この予測モデルをその会社に属するすべての予測モデルに変更できます。</span><span class="sxs-lookup"><span data-stu-id="f76a0-118">However, you can change this forecast model to any forecast model that belongs to that company.</span></span> <span data-ttu-id="f76a0-119">需要予測データが選択した会社に対して生成されない場合は、インポート時に警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f76a0-119">If no forecast demand data has been generated for a selected company, you receive a warning message at import time.</span></span> 

<span data-ttu-id="f76a0-120">[**ベースライン需要予測に対して行われた手動調整の保存**] チェック ボックスの機能を理解することは非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="f76a0-120">It's very important that you understand how the **Save the manual adjustments made to the baseline demand forecast** check box works.</span></span> <span data-ttu-id="f76a0-121">統計ベースラインの予測に手動調整がある場合、調整された値はこのチェック ボックスがオフの場合でも使用のために承認されます。</span><span class="sxs-lookup"><span data-stu-id="f76a0-121">If you've made manual adjustments to the statistical baseline forecast, the adjusted values are authorized for use, even if this check box is cleared.</span></span> <span data-ttu-id="f76a0-122">ただし、変更は承認後に破棄されます。</span><span class="sxs-lookup"><span data-stu-id="f76a0-122">However, the changes are discarded after the authorization.</span></span> <span data-ttu-id="f76a0-123">したがって、次に予測が生成される時、[**手動調整を需要予測に転送**] が選択されている場合でも、その予測は統計予測のみで手動上書きはありません。</span><span class="sxs-lookup"><span data-stu-id="f76a0-123">Therefore, the next time that a forecast is generated, that forecast is only a statistical forecast and doesn't have any manual overrides, even if **Transfer manual adjustments to the demand forecast** is selected.</span></span> <span data-ttu-id="f76a0-124">したがって、[**ベースライン需要予測に対して行われた手動調整の保存**] チェック ボックスを、すべて手動による変更で維持または破棄するメカニズムと仮定できます。</span><span class="sxs-lookup"><span data-stu-id="f76a0-124">Therefore, you can consider the **Save the manual adjustments made to the baseline demand forecast** check box a mechanism that lets you keep or discard all manual changes.</span></span>

<a name="see-also"></a><span data-ttu-id="f76a0-125">参照</span><span class="sxs-lookup"><span data-stu-id="f76a0-125">See also</span></span>
--------

[<span data-ttu-id="f76a0-126">ベースライン予測の手動調整の実施</span><span class="sxs-lookup"><span data-stu-id="f76a0-126">Making manual adjustments to the baseline forecast</span></span>](manual-adjustments-baseline-forecast.md)

[<span data-ttu-id="f76a0-127">予測精度の監視</span><span class="sxs-lookup"><span data-stu-id="f76a0-127">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)



