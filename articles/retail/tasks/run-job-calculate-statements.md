--- 
title: "明細書を計算するジョブのコンフィギュレーションおよび実行"
description: "この手順では、選択した店舗または店舗グループの明細書を作成および計算する反復バッチ ジョブを構成し、実行する方法を説明します。"
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
ms.openlocfilehash: 2bae81073fa6561c02d2dac0cd83db6a10ad00c3
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="configure-and-run-a-job-to-calculate-statements"></a><span data-ttu-id="4c315-103">明細書を計算するジョブのコンフィギュレーションおよび実行</span><span class="sxs-lookup"><span data-stu-id="4c315-103">Configure and run a job to calculate statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="4c315-104">この手順では、選択した店舗または店舗グループの明細書を作成および計算する反復バッチ ジョブを構成し、実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="4c315-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="4c315-105">この手順では、デモ データの会社 USRT を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c315-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="4c315-106">[すべてのワークスペース] > [小売店舗の財務] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4c315-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="4c315-107">[明細書の計算] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c315-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="4c315-108">店舗グループのバッチ ジョブを作成する場合は、特定の店舗またはノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c315-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="4c315-109">選択した項目を追加するには、矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c315-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="4c315-110">[バックグラウンドで実行] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c315-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="4c315-111">バッチ処理中の場合は、[はい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c315-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="4c315-112">[再実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c315-112">Click Recurrence.</span></span>
6. <span data-ttu-id="4c315-113">[開始日] フィールドに日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c315-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="4c315-114">[開始時刻] フィールドに時刻を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c315-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="4c315-115">[終了日なし] のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c315-115">Select the No end date option.</span></span>
9. <span data-ttu-id="4c315-116">[PatternUnit] フィールドに「日数」を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c315-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="4c315-117">[間隔] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c315-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="4c315-118">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c315-118">Click OK.</span></span>
12. <span data-ttu-id="4c315-119">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c315-119">Click OK.</span></span>

