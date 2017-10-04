--- 
title: "製造オーダーの開始"
description: "この手順では、作業現場での製造オーダーの開始方法を説明します。"
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 33558053d33d9fe4a2ecb3576da569b2c441db80
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="start-a-production-order"></a><span data-ttu-id="15f28-103">製造オーダーの開始</span><span class="sxs-lookup"><span data-stu-id="15f28-103">Start a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="15f28-104">この手順では、作業現場での製造オーダーの開始方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="15f28-104">This procedure shows how to start a production order on the shop floor.</span></span> <span data-ttu-id="15f28-105">時間および材料の消費は、このプロセスでレポートされます。</span><span class="sxs-lookup"><span data-stu-id="15f28-105">Time and material consumption are reported in this process.</span></span> <span data-ttu-id="15f28-106">この手順の作成に使用するデモ データの会社は USMF です。</span><span class="sxs-lookup"><span data-stu-id="15f28-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="15f28-107">これは、製造オーダーのライフ サイクルを説明する 7 個の手順の 5 番目です。</span><span class="sxs-lookup"><span data-stu-id="15f28-107">This is the fifth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="start-a-production-order"></a><span data-ttu-id="15f28-108">製造オーダーの開始</span><span class="sxs-lookup"><span data-stu-id="15f28-108">Start a production order</span></span>
1. <span data-ttu-id="15f28-109">[生産管理] > [製造オーダー] > [すべての製造オーダー] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="15f28-109">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="15f28-110">ステータスが [リリース済] の製造オーダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="15f28-110">Select a production order that has the Released status.</span></span>  
2. <span data-ttu-id="15f28-111">アクション ウィンドウで、[製造オーダー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-111">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="15f28-112">[開始] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-112">Click Start.</span></span>
    * <span data-ttu-id="15f28-113">このページで、製造オーダーの開始を確認できます。</span><span class="sxs-lookup"><span data-stu-id="15f28-113">On this page, you can confirm the start of the production order.</span></span>  
4. <span data-ttu-id="15f28-114">[一般] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-114">Click the General tab.</span></span>
5. <span data-ttu-id="15f28-115">[開始行程</span><span class="sxs-lookup"><span data-stu-id="15f28-115">In the From Oper.</span></span> <span data-ttu-id="15f28-116">一連番号</span><span class="sxs-lookup"><span data-stu-id="15f28-116">No.</span></span> <span data-ttu-id="15f28-117">フィールドで、「10」を入力します。</span><span class="sxs-lookup"><span data-stu-id="15f28-117">field, enter '10'.</span></span>
6. <span data-ttu-id="15f28-118">[自動工順消費] フィールドで、「常に」を選択します。</span><span class="sxs-lookup"><span data-stu-id="15f28-118">In the Automatic route consumption field, select 'Always'.</span></span>
7. <span data-ttu-id="15f28-119">[工順カード転記] チェック ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-119">Click the Post route card now checkbox.</span></span>
8. <span data-ttu-id="15f28-120">[自動 BOM 消費] フィールドで、「常に」を選択します。</span><span class="sxs-lookup"><span data-stu-id="15f28-120">In the Automatic BOM consumption field, select 'Always'.</span></span>
9. <span data-ttu-id="15f28-121">[ピッキング リスト転記] チェックボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-121">Click the Post picking list now checkbox.</span></span>
10. <span data-ttu-id="15f28-122">[ピッキング リストの印刷] チェックボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-122">Click the Print picking list checkbox.</span></span>
11. <span data-ttu-id="15f28-123">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-123">Click OK.</span></span>
    * <span data-ttu-id="15f28-124">これは、製造オーダーに使用される材料を示す印刷されたピッキング リストです。</span><span class="sxs-lookup"><span data-stu-id="15f28-124">This is the printed picking list that shows the materials used for the production order.</span></span>  
12. <span data-ttu-id="15f28-125">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="15f28-125">Close the page.</span></span>

## <a name="validate-the-picking-list"></a><span data-ttu-id="15f28-126">ピッキング リストの検証</span><span class="sxs-lookup"><span data-stu-id="15f28-126">Validate the picking list</span></span>
1. <span data-ttu-id="15f28-127">アクション ウィンドウで、[表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-127">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="15f28-128">[ピッキング リスト] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-128">Click Picking list.</span></span>
3. <span data-ttu-id="15f28-129">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="15f28-129">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="15f28-130">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-130">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="15f28-131">[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-131">Click Edit.</span></span>
6. <span data-ttu-id="15f28-132">[消費] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="15f28-132">In the Consumption field, enter a number.</span></span>
7. <span data-ttu-id="15f28-133">[転記] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-133">Click Post.</span></span>
8. <span data-ttu-id="15f28-134">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-134">Click OK.</span></span>
    * <span data-ttu-id="15f28-135">ピッキング リスト仕訳帳には、製造オーダーによって消費される材料が転記されます。</span><span class="sxs-lookup"><span data-stu-id="15f28-135">In the picking list journal, the materials consumed by the production order are posted.</span></span> <span data-ttu-id="15f28-136">見積数量と実際の消費量に差がある場合は、仕訳帳を転記する前に調整することができます。</span><span class="sxs-lookup"><span data-stu-id="15f28-136">Before posting the journal, you can make adjustments if there is a difference between the estimated quantity and the actual consumed quantity.</span></span>  
9. <span data-ttu-id="15f28-137">[グリッド パネル] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-137">Click the GridPanel tab.</span></span>
10. <span data-ttu-id="15f28-138">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="15f28-138">Close the page.</span></span>

## <a name="verify-the-route-card-journal"></a><span data-ttu-id="15f28-139">工順カード仕訳帳の確認</span><span class="sxs-lookup"><span data-stu-id="15f28-139">Verify the route card journal</span></span>
1. <span data-ttu-id="15f28-140">アクション ウィンドウで、[表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-140">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="15f28-141">[工順カード] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-141">Click Route card.</span></span>
3. <span data-ttu-id="15f28-142">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="15f28-142">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="15f28-143">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="15f28-144">[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-144">Click Edit.</span></span>
6. <span data-ttu-id="15f28-145">[時間] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="15f28-145">In the Hours field, enter a number.</span></span>
7. <span data-ttu-id="15f28-146">[転記] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-146">Click Post.</span></span>
8. <span data-ttu-id="15f28-147">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15f28-147">Click OK.</span></span>
    * <span data-ttu-id="15f28-148">[工順カード仕訳帳] では、個々の工程にかかった時間が記録されます。</span><span class="sxs-lookup"><span data-stu-id="15f28-148">In the Route card journal, the time spent on the individual operations is recorded.</span></span> <span data-ttu-id="15f28-149">良品および不良品の数量をレポートできます。</span><span class="sxs-lookup"><span data-stu-id="15f28-149">Good and error quantity can also be reported.</span></span>  

