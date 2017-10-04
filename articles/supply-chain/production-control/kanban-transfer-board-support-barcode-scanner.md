---
title: "バーコード スキャナー用かんばん転送ボードのサポート"
description: "かんばん転送ボードは、かんばん作業を選択、開始、完了、および空にするためのウィジェット バーコード スキャナーのスキャナー入力をサポートします。"
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1dc40de2b77be5c5c2399fd55c3c3bd15a9f24ec
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="efc40-103">バーコード スキャナー用かんばん転送ボードのサポート</span><span class="sxs-lookup"><span data-stu-id="efc40-103">Kanban transfer board support for barcode scanners</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="efc40-104">かんばん転送ボードは、かんばん作業を選択、開始、完了、および空にするためのウィジェット バーコード スキャナーのスキャナー入力をサポートします。</span><span class="sxs-lookup"><span data-stu-id="efc40-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="efc40-105">登録モード</span><span class="sxs-lookup"><span data-stu-id="efc40-105">Registration modes</span></span>
------------------

<span data-ttu-id="efc40-106">**スキャナーの登録**クイック タブで登録モードを選択すると、登録モードを選択できます。これは、[かんばんカード番号] フィールドでかんばんカード番号をスキャンまたは手動入力するときのアクションを制御します。</span><span class="sxs-lookup"><span data-stu-id="efc40-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>
| <span data-ttu-id="efc40-107">登録モードの設定</span><span class="sxs-lookup"><span data-stu-id="efc40-107">Set registration mode</span></span> | <span data-ttu-id="efc40-108">説明</span><span class="sxs-lookup"><span data-stu-id="efc40-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="efc40-109">開始日</span><span class="sxs-lookup"><span data-stu-id="efc40-109">Start</span></span>                 | <span data-ttu-id="efc40-110">かんばん転送ジョブを進行中として登録します。</span><span class="sxs-lookup"><span data-stu-id="efc40-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="efc40-111">完了</span><span class="sxs-lookup"><span data-stu-id="efc40-111">Complete</span></span>              | <span data-ttu-id="efc40-112">かんばん転送ジョブを完了として登録します。</span><span class="sxs-lookup"><span data-stu-id="efc40-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="efc40-113">空</span><span class="sxs-lookup"><span data-stu-id="efc40-113">Empty</span></span>                 | <span data-ttu-id="efc40-114">かんばんカードで参照される材料取り扱い単位を空として登録します。</span><span class="sxs-lookup"><span data-stu-id="efc40-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="efc40-115">選択</span><span class="sxs-lookup"><span data-stu-id="efc40-115">Select</span></span>                | <span data-ttu-id="efc40-116">かんばんカード番号を登録すると、自動的にかんばんリストに参照されるジョブが選択されます。</span><span class="sxs-lookup"><span data-stu-id="efc40-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="efc40-117">[選択] の登録モード</span><span class="sxs-lookup"><span data-stu-id="efc40-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="efc40-118">ジョブを選択するのにバーコードを使用する場合、かんばんボードの表示モードを変更します。</span><span class="sxs-lookup"><span data-stu-id="efc40-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="efc40-119">このモードでは、次の要件が適用されます:</span><span class="sxs-lookup"><span data-stu-id="efc40-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="efc40-120">スキャンしたかんばん作業のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="efc40-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="efc40-121">選択したジョブの詳細は、**詳細**クイック タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="efc40-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="efc40-122">**メッセージ** クイック タブでは、選択したジョブに対してのみメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="efc40-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="efc40-123">[アクション ウィンドウ] で使用できる機能を使用してジョブのステータスを変更できます。</span><span class="sxs-lookup"><span data-stu-id="efc40-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="efc40-124">今回、かんばん転送ボードは 1 つのジョブのみを継続して表示します。</span><span class="sxs-lookup"><span data-stu-id="efc40-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="efc40-125">ジョブのリストの情報を手動で更新するには、アクション ペインの [**更新**] (Shift+F5) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc40-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="efc40-126">情報を更新すると、ジョブのフィルターの完全な結果が再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="efc40-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="efc40-127">ジョブ状態と実行可能なアクション</span><span class="sxs-lookup"><span data-stu-id="efc40-127">Job status and possible actions</span></span>
<span data-ttu-id="efc40-128">選択したジョブのステータスおよびイベントのかんばんにペギングされたジョブのステータスによって、このジョブをさらに処理するかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="efc40-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="efc40-129">次の表に、これらのステータスやタスクに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efc40-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="efc40-130">ジョブに使用できるステータス、またはジョブによって参照される材料取り扱い単位のステータス。</span><span class="sxs-lookup"><span data-stu-id="efc40-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="efc40-131">ジョブに対して実行できる各タスク。</span><span class="sxs-lookup"><span data-stu-id="efc40-131">Each task that you can perform for the job.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efc40-132">ジョブ タイプ</span><span class="sxs-lookup"><span data-stu-id="efc40-132">Job type</span></span></th>
<th><span data-ttu-id="efc40-133">ジョブ ステータスまたは材料取り扱い単位ステータス</span><span class="sxs-lookup"><span data-stu-id="efc40-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="efc40-134">ピッキング リストの更新</span><span class="sxs-lookup"><span data-stu-id="efc40-134">Update picking list</span></span></th>
<th><span data-ttu-id="efc40-135">開始日</span><span class="sxs-lookup"><span data-stu-id="efc40-135">Start</span></span></th>
<th><span data-ttu-id="efc40-136">登録の更新</span><span class="sxs-lookup"><span data-stu-id="efc40-136">Update registration</span></span></th>
<th><span data-ttu-id="efc40-137">完了</span><span class="sxs-lookup"><span data-stu-id="efc40-137">Complete</span></span></th>
<th><span data-ttu-id="efc40-138">空</span><span class="sxs-lookup"><span data-stu-id="efc40-138">Empty</span></span></th>
<th><span data-ttu-id="efc40-139">イベントのかんばんを作成</span><span class="sxs-lookup"><span data-stu-id="efc40-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="efc40-140">移動</span><span class="sxs-lookup"><span data-stu-id="efc40-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="efc40-141">未定</span><span class="sxs-lookup"><span data-stu-id="efc40-141">Not planned</span></span></li>
<li><span data-ttu-id="efc40-142">ペギングにしたジョブがない、またはペギングにしたジョブが [完了]</span><span class="sxs-lookup"><span data-stu-id="efc40-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="efc40-143">有</span><span class="sxs-lookup"><span data-stu-id="efc40-143">Yes</span></span></td>
<td><span data-ttu-id="efc40-144">有</span><span class="sxs-lookup"><span data-stu-id="efc40-144">Yes</span></span></td>
<td><span data-ttu-id="efc40-145">有</span><span class="sxs-lookup"><span data-stu-id="efc40-145">Yes</span></span></td>
<td><span data-ttu-id="efc40-146">有</span><span class="sxs-lookup"><span data-stu-id="efc40-146">Yes</span></span></td>
<td><span data-ttu-id="efc40-147">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-147">No</span></span></td>
<td><span data-ttu-id="efc40-148">有</span><span class="sxs-lookup"><span data-stu-id="efc40-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="efc40-149">移動</span><span class="sxs-lookup"><span data-stu-id="efc40-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="efc40-150">未定</span><span class="sxs-lookup"><span data-stu-id="efc40-150">Not planned</span></span></li>
<li><span data-ttu-id="efc40-151">ペギングにされたジョブが [完了] ではない</span><span class="sxs-lookup"><span data-stu-id="efc40-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="efc40-152">有</span><span class="sxs-lookup"><span data-stu-id="efc40-152">Yes</span></span></td>
<td><span data-ttu-id="efc40-153">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-153">No</span></span></td>
<td><span data-ttu-id="efc40-154">有</span><span class="sxs-lookup"><span data-stu-id="efc40-154">Yes</span></span></td>
<td><span data-ttu-id="efc40-155">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-155">No</span></span></td>
<td><span data-ttu-id="efc40-156">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-156">No</span></span></td>
<td><span data-ttu-id="efc40-157">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="efc40-158">移動</span><span class="sxs-lookup"><span data-stu-id="efc40-158">Transfer</span></span></td>
<td><span data-ttu-id="efc40-159">処理中</span><span class="sxs-lookup"><span data-stu-id="efc40-159">In progress</span></span></td>
<td><span data-ttu-id="efc40-160">有</span><span class="sxs-lookup"><span data-stu-id="efc40-160">Yes</span></span></td>
<td><span data-ttu-id="efc40-161">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-161">No</span></span></td>
<td><span data-ttu-id="efc40-162">有</span><span class="sxs-lookup"><span data-stu-id="efc40-162">Yes</span></span></td>
<td><span data-ttu-id="efc40-163">有</span><span class="sxs-lookup"><span data-stu-id="efc40-163">Yes</span></span></td>
<td><span data-ttu-id="efc40-164">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-164">No</span></span></td>
<td><span data-ttu-id="efc40-165">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="efc40-166">移動</span><span class="sxs-lookup"><span data-stu-id="efc40-166">Transfer</span></span></td>
<td><span data-ttu-id="efc40-167">完了</span><span class="sxs-lookup"><span data-stu-id="efc40-167">Completed</span></span></td>
<td><span data-ttu-id="efc40-168">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-168">No</span></span></td>
<td><span data-ttu-id="efc40-169">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-169">No</span></span></td>
<td><span data-ttu-id="efc40-170">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-170">No</span></span></td>
<td><span data-ttu-id="efc40-171">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-171">No</span></span></td>
<td><span data-ttu-id="efc40-172">有</span><span class="sxs-lookup"><span data-stu-id="efc40-172">Yes</span></span></td>
<td><span data-ttu-id="efc40-173">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="efc40-174">転送または処理中</span><span class="sxs-lookup"><span data-stu-id="efc40-174">Transfer or process</span></span></td>
<td><span data-ttu-id="efc40-175">空</span><span class="sxs-lookup"><span data-stu-id="efc40-175">Empty</span></span></td>
<td><span data-ttu-id="efc40-176">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-176">No</span></span></td>
<td><span data-ttu-id="efc40-177">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-177">No</span></span></td>
<td><span data-ttu-id="efc40-178">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-178">No</span></span></td>
<td><span data-ttu-id="efc40-179">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-179">No</span></span></td>
<td><span data-ttu-id="efc40-180">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-180">No</span></span></td>
<td><span data-ttu-id="efc40-181">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="efc40-182">転送または処理中</span><span class="sxs-lookup"><span data-stu-id="efc40-182">Transfer or process</span></span></td>
<td><span data-ttu-id="efc40-183">かんばんカードがない</span><span class="sxs-lookup"><span data-stu-id="efc40-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="efc40-184">いいえ</span><span class="sxs-lookup"><span data-stu-id="efc40-184">No</span></span></td>
<td><span data-ttu-id="efc40-185">いいえ</span><span class="sxs-lookup"><span data-stu-id="efc40-185">No</span></span></td>
<td><span data-ttu-id="efc40-186">いいえ</span><span class="sxs-lookup"><span data-stu-id="efc40-186">No</span></span></td>
<td><span data-ttu-id="efc40-187">いいえ</span><span class="sxs-lookup"><span data-stu-id="efc40-187">No</span></span></td>
<td><span data-ttu-id="efc40-188">いいえ</span><span class="sxs-lookup"><span data-stu-id="efc40-188">No</span></span></td>
<td><span data-ttu-id="efc40-189">いいえ</span><span class="sxs-lookup"><span data-stu-id="efc40-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="efc40-190">転送または処理中</span><span class="sxs-lookup"><span data-stu-id="efc40-190">Transfer or process</span></span></td>
<td><span data-ttu-id="efc40-191">かんばんカードはあるが、かんばんに割り当てられていない</span><span class="sxs-lookup"><span data-stu-id="efc40-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="efc40-192">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-192">No</span></span></td>
<td><span data-ttu-id="efc40-193">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-193">No</span></span></td>
<td><span data-ttu-id="efc40-194">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-194">No</span></span></td>
<td><span data-ttu-id="efc40-195">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-195">No</span></span></td>
<td><span data-ttu-id="efc40-196">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-196">No</span></span></td>
<td><span data-ttu-id="efc40-197">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="efc40-198">処理</span><span class="sxs-lookup"><span data-stu-id="efc40-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="efc40-199">未定</span><span class="sxs-lookup"><span data-stu-id="efc40-199">Not planned</span></span></li>
<li><span data-ttu-id="efc40-200">準備済</span><span class="sxs-lookup"><span data-stu-id="efc40-200">Prepared</span></span></li>
<li><span data-ttu-id="efc40-201">処理中</span><span class="sxs-lookup"><span data-stu-id="efc40-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="efc40-202">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-202">No</span></span></td>
<td><span data-ttu-id="efc40-203">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-203">No</span></span></td>
<td><span data-ttu-id="efc40-204">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-204">No</span></span></td>
<td><span data-ttu-id="efc40-205">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-205">No</span></span></td>
<td><span data-ttu-id="efc40-206">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-206">No</span></span></td>
<td><span data-ttu-id="efc40-207">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="efc40-208">処理</span><span class="sxs-lookup"><span data-stu-id="efc40-208">Process</span></span></td>
<td><span data-ttu-id="efc40-209">完了</span><span class="sxs-lookup"><span data-stu-id="efc40-209">Completed</span></span></td>
<td><span data-ttu-id="efc40-210">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-210">No</span></span></td>
<td><span data-ttu-id="efc40-211">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-211">No</span></span></td>
<td><span data-ttu-id="efc40-212">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-212">No</span></span></td>
<td><span data-ttu-id="efc40-213">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-213">No</span></span></td>
<td><span data-ttu-id="efc40-214">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-214">No</span></span></td>
<td><span data-ttu-id="efc40-215">第        条</span><span class="sxs-lookup"><span data-stu-id="efc40-215">No</span></span></td>
</tr>
</tbody>
</table>





