--- 
title: "バッチ ジョブの作成"
description: "バッチ ジョブは、自動処理のために Application Object Server (AOS) インスタンスに送信されるタスクのグループです。"
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 31c8e2ba87ef8c17a3147e1159104585258d4164
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-batch-job"></a><span data-ttu-id="52c18-103">バッチ ジョブの作成</span><span class="sxs-lookup"><span data-stu-id="52c18-103">Create a batch job</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="52c18-104">バッチ ジョブは、自動処理のために Application Object Server (AOS) インスタンスに送信されるタスクのグループです。</span><span class="sxs-lookup"><span data-stu-id="52c18-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="52c18-105">バッチ ジョブは、ジョブを作成したユーザーのセキュリティ資格情報を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="52c18-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="52c18-106">バッチ ジョブを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="52c18-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="52c18-107">この手順の作成に使用するデモ データの会社は USMF です。</span><span class="sxs-lookup"><span data-stu-id="52c18-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="52c18-108">バッチ ジョブの作成</span><span class="sxs-lookup"><span data-stu-id="52c18-108">Create the batch job</span></span>
1. <span data-ttu-id="52c18-109">[システム管理] > [照会] > [バッチ ジョブ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52c18-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="52c18-110">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52c18-110">Click New.</span></span>
3. <span data-ttu-id="52c18-111">[ジョブの説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="52c18-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="52c18-112">[開始予定日時] フィールドで、日時を入力します。</span><span class="sxs-lookup"><span data-stu-id="52c18-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="52c18-113">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52c18-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="52c18-114">再実行の作成</span><span class="sxs-lookup"><span data-stu-id="52c18-114">Create a recurrence</span></span>
1. <span data-ttu-id="52c18-115">アクション ウィンドウで、[バッチ ジョブ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52c18-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="52c18-116">[再実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52c18-116">Click Recurrence.</span></span>
    * <span data-ttu-id="52c18-117">これらのオプションを使用して再実行の範囲とパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="52c18-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="52c18-118">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52c18-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="52c18-119">警告の追加</span><span class="sxs-lookup"><span data-stu-id="52c18-119">Add alerts</span></span>
1. <span data-ttu-id="52c18-120">アクション ウィンドウで、[バッチ ジョブ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52c18-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="52c18-121">[警告] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52c18-121">Click Alerts.</span></span>
    * <span data-ttu-id="52c18-122">バッチ ジョブの終了時、エラー発生時、またはキャンセル時に警告メッセージを表示するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="52c18-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="52c18-123">そして、警告をポップアップ メッセージとして表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="52c18-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="52c18-124">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52c18-124">Click OK.</span></span>

