--- 
title: "連続スケジュールの定義"
description: "このトピックでは、連続プログラム (それ以外の場合は、繰り返し注文とも呼ばれます) の設定について説明します。"
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4f99b3b71e46aae1e510cc24efe2f99f1a258fa1
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="define-continuity-schedules"></a><span data-ttu-id="e49e0-103">連続スケジュールの定義</span><span class="sxs-lookup"><span data-stu-id="e49e0-103">Define continuity schedules</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="e49e0-104">このトピックでは、連続プログラム (それ以外の場合は、繰り返し注文とも呼ばれます) の設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-104">This topic walks through setting up a continuity program (otherwise known as reoccurring orders).</span></span> <span data-ttu-id="e49e0-105">このトピックでは、デモ データの会社 USRT を使用します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-105">This topic uses company USRT in the demo data.</span></span>


## <a name="create-continuity-program"></a><span data-ttu-id="e49e0-106">連続プログラムの作成</span><span class="sxs-lookup"><span data-stu-id="e49e0-106">Create continuity program</span></span>
1. <span data-ttu-id="e49e0-107">[小売りとコマース] > [連続] > [連続 プログラム] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-107">Go to Retail and commerce > Continuity > Continuity programs.</span></span>
2. <span data-ttu-id="e49e0-108">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e49e0-108">Click New.</span></span>
3. <span data-ttu-id="e49e0-109">スケジュール ID フィールドで、[連続スケジュール ID] と入力します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-109">In the Schedule ID field, type the continuity schedule ID.</span></span>
4. <span data-ttu-id="e49e0-110">[注文の開始] フィールドで、「最初のイベント」を選択します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-110">In the Order start field, select 'First event'.</span></span>
    * <span data-ttu-id="e49e0-111">顧客が連続プログラムの新しい注文を配置する場合は、どの製品を出荷するかについて 2 つのオプションがあります: 1。</span><span class="sxs-lookup"><span data-stu-id="e49e0-111">If a customer places a new order for the continuity program, there are two options for which product will be shipped:  1.</span></span> <span data-ttu-id="e49e0-112">最初のイベント: 連続プログラムで最初の製品を出荷します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-112">First event: the first product in the continuity program will be shipped.</span></span>  <span data-ttu-id="e49e0-113">2.</span><span class="sxs-lookup"><span data-stu-id="e49e0-113">2.</span></span> <span data-ttu-id="e49e0-114">現在のイベント: 現在の製品が出荷されます。</span><span class="sxs-lookup"><span data-stu-id="e49e0-114">Current event: the current product will be shipped.</span></span> <span data-ttu-id="e49e0-115">例えば、</span><span class="sxs-lookup"><span data-stu-id="e49e0-115">For example.</span></span> <span data-ttu-id="e49e0-116">3 か月間のプログラムで、顧客はプログラムの 3 番目を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e49e0-116">three months into the program, the customer will receive the third in the program.</span></span>  
5. <span data-ttu-id="e49e0-117">注文の開始日を確認するには、[はい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-117">Select 'Yes' to prompt for the order start date.</span></span>
6. <span data-ttu-id="e49e0-118">[明細行の追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e49e0-118">Click Add line.</span></span>
7. <span data-ttu-id="e49e0-119">[品目番号] フィールドで、最初の品目番号 (0013) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-119">In the Item number field, type the item number for the first product ('0013').</span></span>
8. <span data-ttu-id="e49e0-120">[CP] と入力します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-120">Type 'CP'.</span></span>
9. <span data-ttu-id="e49e0-121">最初の製品が注文できる日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-121">Enter the date when the first product will be available for order.</span></span>
10. <span data-ttu-id="e49e0-122">[行の追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e49e0-122">Click Add line.</span></span>
11. <span data-ttu-id="e49e0-123">[品目番号] フィールドで「0014」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-123">In the Item number field, type '0014'.</span></span>
12. <span data-ttu-id="e49e0-124">日付間隔コードフィールドで、値をオフにすると、フィールドは空になります。</span><span class="sxs-lookup"><span data-stu-id="e49e0-124">In the Date interval code field, clear the value so the field is empty.</span></span>
    * <span data-ttu-id="e49e0-125">この手順で、日付範囲をオフにします。</span><span class="sxs-lookup"><span data-stu-id="e49e0-125">For this procedure, clear the date interval.</span></span> <span data-ttu-id="e49e0-126">最初の品目の増分日付として開始日付を設定します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-126">You'll set the date as incremental from the start date of the first item.</span></span>  
13. <span data-ttu-id="e49e0-127">ここでは、製品を出荷する間隔を入力します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-127">Here you'll enter the interval at which the products are shipped.</span></span> <span data-ttu-id="e49e0-128">タイプ「30」。</span><span class="sxs-lookup"><span data-stu-id="e49e0-128">Type '30'.</span></span>
    * <span data-ttu-id="e49e0-129">月ごとのプログラムの場合、間隔は 30 日と入力します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-129">For a monthly program, you'll enter 30 days for the interval.</span></span>  
14. <span data-ttu-id="e49e0-130">[明細行の追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e49e0-130">Click Add line.</span></span>
15. <span data-ttu-id="e49e0-131">[品目番号] フィールドで「0015」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-131">In the Item number field, type '0015'.</span></span>
16. <span data-ttu-id="e49e0-132">[終了] と入力します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-132">Type 'End'.</span></span>
17. <span data-ttu-id="e49e0-133">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e49e0-133">Click Save.</span></span>

## <a name="assign-to-continuity-item"></a><span data-ttu-id="e49e0-134">連続品目に割り当てます</span><span class="sxs-lookup"><span data-stu-id="e49e0-134">Assign to continuity item</span></span>
1. <span data-ttu-id="e49e0-135">[製品情報管理] > [製品] > [リリースされた製品] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-135">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="e49e0-136">品目「0016」を選択します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-136">Select item '0016'.</span></span>
    * <span data-ttu-id="e49e0-137">この手順では、品目番号 0016 を選択します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-137">For this procedure, you'll select item number 0016.</span></span> <span data-ttu-id="e49e0-138">通常、コール センターの販売注文時に適用される、追加の連続ビジネス ロジックがあるリリースされた製品を作成しています。</span><span class="sxs-lookup"><span data-stu-id="e49e0-138">Normally, you'll have created a released product that has additional continuity business logic applied when it's placed on a sales order in call center.</span></span>  
3. <span data-ttu-id="e49e0-139">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e49e0-139">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="e49e0-140">[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e49e0-140">Click Edit.</span></span>
5. <span data-ttu-id="e49e0-141">[販売] セクションを展開または折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="e49e0-141">Expand or collapse the Sell section.</span></span>
6. <span data-ttu-id="e49e0-142">ここでは、この品目が示す連続プログラムを入力します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-142">Here you'll enter the continuity program that this item represents.</span></span> <span data-ttu-id="e49e0-143">前に作成したスケジュール ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="e49e0-143">Type the Schedule ID you created earlier.</span></span>
    * <span data-ttu-id="e49e0-144">この品目がコールセンターで販売される場合、追加のビジネス ロジックは、選択した連続プログラムから適用されます。</span><span class="sxs-lookup"><span data-stu-id="e49e0-144">When this item is sold in a call center, additional business logic is applied from the selected continuity program.</span></span>  
7. <span data-ttu-id="e49e0-145">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e49e0-145">Click Save.</span></span>

