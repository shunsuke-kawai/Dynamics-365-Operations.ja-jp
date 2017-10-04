--- 
title: "かんばんプロセス ジョブの実行"
description: "この手順は、かんばんプロセス ジョブの実行を対象としています。"
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 752eab976f740606154d416678ba2381641697df
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="execute-kanban-process-jobs"></a><span data-ttu-id="6dc37-103">かんばんプロセス ジョブの実行</span><span class="sxs-lookup"><span data-stu-id="6dc37-103">Execute kanban process jobs</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6dc37-104">この手順は、かんばんプロセス ジョブの実行を対象としています。</span><span class="sxs-lookup"><span data-stu-id="6dc37-104">This procedure focuses on executing kanban process jobs.</span></span> <span data-ttu-id="6dc37-105">最初のジョブでは、予定数量が完了されずエラーはありません。</span><span class="sxs-lookup"><span data-stu-id="6dc37-105">The first job is completed with the expected quantity and has no errors.</span></span> <span data-ttu-id="6dc37-106">2 番目のジョブはエラーで完了されます。</span><span class="sxs-lookup"><span data-stu-id="6dc37-106">The second job is completed with errors.</span></span> <span data-ttu-id="6dc37-107">この手順の作成に使用するデモ データの会社は USMF です。</span><span class="sxs-lookup"><span data-stu-id="6dc37-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="6dc37-108">この手順は、機械オペレーターを対象としています。</span><span class="sxs-lookup"><span data-stu-id="6dc37-108">This procedure is intended for the machine operator.</span></span>


## <a name="select-a-kanban-job"></a><span data-ttu-id="6dc37-109">かんばん作業を選択</span><span class="sxs-lookup"><span data-stu-id="6dc37-109">Select a kanban job</span></span>
1. <span data-ttu-id="6dc37-110">[生産管理] > [かんばん] > [プロセス ジョブのかんばんボード] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6dc37-110">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="6dc37-111">[作業セル] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="6dc37-111">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="6dc37-112">リソース グループ 1250 を含む行をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dc37-112">Click the row with resource group 1250.</span></span> <span data-ttu-id="6dc37-113">これによって、作業セル 1250 のジョブのみを表示するジョブ リストをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="6dc37-113">This filters the Jobs list to display only the jobs for work cell 1250.</span></span>
    * <span data-ttu-id="6dc37-114">計画済みのジョブ ステータスがある行をマークします。</span><span class="sxs-lookup"><span data-stu-id="6dc37-114">Mark the row that has the Planned job status.</span></span>  

## <a name="complete-a-job-with-expected-quantity"></a><span data-ttu-id="6dc37-115">予定数量のジョブを完了します。</span><span class="sxs-lookup"><span data-stu-id="6dc37-115">Complete a job with expected quantity</span></span>
1. <span data-ttu-id="6dc37-116">[詳細] セクションを展開または折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="6dc37-116">Expand or collapse the Details section.</span></span>
    * <span data-ttu-id="6dc37-117">このセクションでは、カード番号、品目番号、注文済の数量、および活動名に関する重要な情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="6dc37-117">This section displays important information about card number, item number, quantity ordered, and activity name.</span></span>  
2. <span data-ttu-id="6dc37-118">[生産指示] セクションを展開または折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="6dc37-118">Expand or collapse the Production instructions section.</span></span>
    * <span data-ttu-id="6dc37-119">このセクションでは、活動の生産指示を表示します。</span><span class="sxs-lookup"><span data-stu-id="6dc37-119">This section displays production instructions for the activity.</span></span> <span data-ttu-id="6dc37-120">その手順は、テキスト、写真、図面、またはその他のドキュメントのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="6dc37-120">The instructions can be text, pictures, drawings, and other documents.</span></span>  
3. <span data-ttu-id="6dc37-121">[開始] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dc37-121">Click Start.</span></span>
    * <span data-ttu-id="6dc37-122">完了していないジョブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6dc37-122">Select a job that is not completed.</span></span> <span data-ttu-id="6dc37-123">ジョブ ステータスを表示している [ジョブ ステータス] フィールドでステータスのアイコンを使用します。</span><span class="sxs-lookup"><span data-stu-id="6dc37-123">Use status icons in the Job status field to view job status.</span></span>      
4. <span data-ttu-id="6dc37-124">[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dc37-124">Click Complete.</span></span>
    * <span data-ttu-id="6dc37-125">ジョブは、期待品質で完了しています。</span><span class="sxs-lookup"><span data-stu-id="6dc37-125">The job is completed with the expected quality.</span></span>  

## <a name="complete-a-job-with-errors"></a><span data-ttu-id="6dc37-126">エラーのジョブを完了します。</span><span class="sxs-lookup"><span data-stu-id="6dc37-126">Complete a job with errors</span></span>
1. <span data-ttu-id="6dc37-127">[開始] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dc37-127">Click Start.</span></span>
    * <span data-ttu-id="6dc37-128">ジョブが完了すると、リストの次のジョブが自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="6dc37-128">When a job is completed, the next job on the list is selected automatically.</span></span> <span data-ttu-id="6dc37-129">[開始] をクリックする前にジョブを選択する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6dc37-129">This is why you don't need to select a job before you click Start.</span></span>  
2. <span data-ttu-id="6dc37-130">[アクション ペイン] 上で、[製造] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dc37-130">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="6dc37-131">[完了] (詳細) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dc37-131">Click Complete (details).</span></span>
4. <span data-ttu-id="6dc37-132">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="6dc37-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="6dc37-133">[エラー数量] フィールドに番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="6dc37-133">In the Error quantity field, enter a number.</span></span>
6. <span data-ttu-id="6dc37-134">[適正数量] フィールドに番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="6dc37-134">In the Good quantity field, enter a number.</span></span>
7. <span data-ttu-id="6dc37-135">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dc37-135">Click OK.</span></span>

