---
title: "時刻と出勤の登録"
description: "時間登録作業者は、さまざまなタイプの時間登録を入力できます (出勤、退勤、間接活動の登録、および休暇登録時など)。 この記事は、登録とその計算、承認、およびタイムシートの承認プロセスに構造と自動承認を追加するためのワークフローの使用について説明します。"
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorker, JmgCalcApprovePickDialog, JmgGroupApprove, JmgGroupCalc, JmgGroupSigningTable, JmgRegistration, JmgTimeCalcParmeters, WorkflowTableListPageRnr
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53351
ms.assetid: 885b0cdf-53d7-4cb4-92fe-da1b9e32b39f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 83603b1f8d20c18b7f10cd7224d491b558ee1b8b
ms.contentlocale: ja-jp
ms.lasthandoff: 06/29/2017


---

# <a name="time-and-attendance-registration"></a><span data-ttu-id="b285b-104">時刻と出勤の登録</span><span class="sxs-lookup"><span data-stu-id="b285b-104">Time and attendance registration</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b285b-105">時間登録作業者は、さまざまなタイプの時間登録を入力できます (出勤、退勤、間接活動の登録、および休暇登録時など)。</span><span class="sxs-lookup"><span data-stu-id="b285b-105">Time registration workers can enter different types of time registrations, for example, clock in, clock out, register indirect activities, and absence registration.</span></span> <span data-ttu-id="b285b-106">この記事は、登録とその計算、承認、およびタイムシートの承認プロセスに構造と自動承認を追加するためのワークフローの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="b285b-106">This article describes registrations, their calculation, approval, and the use of workflow to add structure and automated approval to the process of approving timesheets.</span></span> 

<a name="registrations"></a><span data-ttu-id="b285b-107">登録</span><span class="sxs-lookup"><span data-stu-id="b285b-107">Registrations</span></span>
-------------

<span data-ttu-id="b285b-108">[時刻と出勤] を使用する会社では、作業者が作業に費やす時刻と出勤を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b285b-108">In companies that use Time and attendance, workers must register the time that they spend at work, as well as their attendance.</span></span> <span data-ttu-id="b285b-109">会社によっては、出勤と退勤の時間登録のみを作業者に義務付けている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b285b-109">Some companies may only require workers to register clocking-in and clocking-out times.</span></span> <span data-ttu-id="b285b-110">別の会社では、作業者は実際に活動を実行する時間消費や、休憩時間を登録する必要のある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b285b-110">In other companies, workers may also be required to register time consumption on the actual activities they perform as well as the breaks they take.</span></span> <span data-ttu-id="b285b-111">[時刻と出勤] の対象ユーザーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b285b-111">The intended users of Time and attendance are:</span></span>
-   <span data-ttu-id="b285b-112">定期的 (毎日、毎週、隔週など) な勤務時間と勤怠の登録が義務付けられている作業者。</span><span class="sxs-lookup"><span data-stu-id="b285b-112">Workers, who are required to register time and attendance at regular intervals, for example daily, weekly or bi-weekly.</span></span>
-   <span data-ttu-id="b285b-113">作業者の登録内容の計算、承認、および移動を行い処理を進める監督者、マネージャ、および給与担当者。</span><span class="sxs-lookup"><span data-stu-id="b285b-113">Supervisors, managers, and payroll officers who calculate, approve, and transfer worker registrations for further processing.</span></span>

| <span data-ttu-id="b285b-114">**メモ**</span><span class="sxs-lookup"><span data-stu-id="b285b-114">**Note**</span></span>                                                                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b285b-115">[時刻と出勤] を [製造実行] とともに実行すると、プロジェクト、プロジェクト活動、間接活動、休暇コード、残業時間、フレックス時間のすべての登録を記録して、双方のモジュールで給与を計算するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b285b-115">If you run Time and attendance together with Manufacturing execution, all registrations on projects, project activities, indirect activities, absence codes, and overtime and flex time will be recorded and are used to calculate payroll in both modules.</span></span> |

## <a name="time-registrations-workers"></a><span data-ttu-id="b285b-116">時間登録作業者</span><span class="sxs-lookup"><span data-stu-id="b285b-116">Time registrations workers</span></span>
<span data-ttu-id="b285b-117">時間および勤怠を登録するには、作業者は、雇用されている会社の時間登録作業者として設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b285b-117">To be able to register time and absence, workers must be set up as time registration workers in the company they are employed in.</span></span>

<span data-ttu-id="b285b-118">設定後、作業者は、それぞれのタイプの登録を入力できます。</span><span class="sxs-lookup"><span data-stu-id="b285b-118">After setup, the workers can enter different types of registrations.</span></span>

-   <span data-ttu-id="b285b-119">職場に到着または退出するときに、出勤または退勤。</span><span class="sxs-lookup"><span data-stu-id="b285b-119">Clocking in- and out when arriving or leaving work.</span></span>
-   <span data-ttu-id="b285b-120">生産ジョブの時間と品目の消費。</span><span class="sxs-lookup"><span data-stu-id="b285b-120">Time and item consumption on production jobs.</span></span>
-   <span data-ttu-id="b285b-121">機械が作業現場でリソースとして定義されている場合、機械で使用される時間。</span><span class="sxs-lookup"><span data-stu-id="b285b-121">Time used on a machine on the shop floor, if the machine has been defined as a resource.</span></span>

| <span data-ttu-id="b285b-122">**メモ**</span><span class="sxs-lookup"><span data-stu-id="b285b-122">**Note**</span></span>                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b285b-123">作業者が生産ジョブを開始したときに機械のアシスタントとしてその作業者が作業することを選択した場合、その作業者を自動的に作業現場の特定の機械の時間登録に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b285b-123">A worker can be automatically assigned the time registrations that are made on a particular machine on the shop floor, if the worker chooses to work as an assistant to the machine when he or she starts the production job.</span></span> |

-   <span data-ttu-id="b285b-124">プロジェクトおよびプロジェクト活動の時間の登録。</span><span class="sxs-lookup"><span data-stu-id="b285b-124">Time registrations on projects and project activities.</span></span>
-   <span data-ttu-id="b285b-125">個々のプロジェクト手数料仕訳帳、およびプロジェクト品目仕訳帳を使用した、プロジェクト手数料および品目消費の登録。</span><span class="sxs-lookup"><span data-stu-id="b285b-125">Registering project fees and item consumption via the respective project fee journals and project item journals.</span></span>
-   <span data-ttu-id="b285b-126">計画休暇。</span><span class="sxs-lookup"><span data-stu-id="b285b-126">Planned absence.</span></span>
-   <span data-ttu-id="b285b-127">予定より遅れて出勤する場合、または早く退勤する場合の休暇時間。</span><span class="sxs-lookup"><span data-stu-id="b285b-127">Absence when arriving late to work or leaving earlier than planned.</span></span>
-   <span data-ttu-id="b285b-128">手動で登録される、またはシステムによって自動的に計算される休憩。</span><span class="sxs-lookup"><span data-stu-id="b285b-128">Work breaks, either manually registered or automatically calculated by the system.</span></span>
-   <span data-ttu-id="b285b-129">作業者が作業日に従事する可能性のある非生産活動の間接活動。</span><span class="sxs-lookup"><span data-stu-id="b285b-129">Indirect activities, which are non-productive activities a worker might engage in during a workday.</span></span> <span data-ttu-id="b285b-130">これらの活動の例には、会議やワークスペースの掃除が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b285b-130">Examples of these activities include meetings or cleaning their workspace.</span></span>
-   <span data-ttu-id="b285b-131">追加時間、フレックス時間、または残業として登録される時間外の時間。</span><span class="sxs-lookup"><span data-stu-id="b285b-131">Overtime, which can be registered either as extra hours, flextime, or overtime.</span></span>

## <a name="adding-clockout-registrations"></a><span data-ttu-id="b285b-132">退勤登録の追加</span><span class="sxs-lookup"><span data-stu-id="b285b-132">Adding clockout registrations</span></span>
<span data-ttu-id="b285b-133">作業者が各自の作業日の終わりに退勤時間の記録を忘れた場合、バッチ ジョブを実行して、漏れている退勤登録を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b285b-133">If a worker forgets to clock-out at the end of their workday, the missing registration can be added by running a batch job.</span></span> <span data-ttu-id="b285b-134">システムは、作業者のプロファイルに従って出勤時間、退勤時間を比較し、プロファイルの終了時刻に合わせて自動的に漏れている退勤登録を挿入します。</span><span class="sxs-lookup"><span data-stu-id="b285b-134">The system will compare the clock-in time and the clock-out time according to the associated profile of the worker, and automatically insert the missing clock-out registration to match the profile’s end time.</span></span> <span data-ttu-id="b285b-135">出勤/退勤登録の両方が、後続の計算、時間登録の承認、給与への転送のために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="b285b-135">Both the clock-in and clock-out registrations are vital for the subsequent calculation and approval of time registrations before they can be transferred to payroll.</span></span>

## <a name="calculating-registrations"></a><span data-ttu-id="b285b-136">登録の計算</span><span class="sxs-lookup"><span data-stu-id="b285b-136">Calculating registrations</span></span>
<span data-ttu-id="b285b-137">登録作業者が、特定のチーム、シフト、作業グループに関連する計算グループに割り当てられているとき。</span><span class="sxs-lookup"><span data-stu-id="b285b-137">When a registration worker is assigned a calculation group that typically relates to a specific team, shift, or work group.</span></span> <span data-ttu-id="b285b-138">チームマネージャーや監修者は、通常、作業者が行った登録を検証し、それぞれの計算グループの計算を毎日実行する責任を負う人物です。</span><span class="sxs-lookup"><span data-stu-id="b285b-138">The team manager or supervisor typically validates the registrations made by the workers, and is therefore also the responsible person to run the calculation for the respective calculation groups on a daily basis.</span></span> <span data-ttu-id="b285b-139">チーム マネージャーや監修者は、計算プロセスの一部として次のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b285b-139">As part of the calculation process the team manager or supervisor is able to:</span></span>
-   <span data-ttu-id="b285b-140">誤った登録の修正。</span><span class="sxs-lookup"><span data-stu-id="b285b-140">Correct erroneous registrations.</span></span> <span data-ttu-id="b285b-141">たとえば、切り替えコードを変更し、生産ジョブのフィードバックを調整します。</span><span class="sxs-lookup"><span data-stu-id="b285b-141">For example, change switch codes and adjust feedback on production jobs.</span></span>
-   <span data-ttu-id="b285b-142">漏れている記録の追加。</span><span class="sxs-lookup"><span data-stu-id="b285b-142">Add missing registrations.</span></span> <span data-ttu-id="b285b-143">たとえば、退勤記録の登録や、休暇トランザクションの作成をします。</span><span class="sxs-lookup"><span data-stu-id="b285b-143">For example, create clock-out registrations and create absence transactions.</span></span>
-   <span data-ttu-id="b285b-144">誤った記録の削除。</span><span class="sxs-lookup"><span data-stu-id="b285b-144">Delete incorrect registrations.</span></span>

<span data-ttu-id="b285b-145">登録された時間は、登録を計算する前に作業者の時間プロファイルと比較されるため、標準作業時間プロファイルからの例外があるすべての作業者の作業時間プロファイルは上書きしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b285b-145">Because the registered time must match the worker’s time profile prior to calculating the registrations, you must override the work time profile for any worker who has an exception to his standard work time profile.</span></span> <span data-ttu-id="b285b-146">この場合、作業者のプロファイルが日勤で、作業者が時間外手当のない夜勤で作業することに合意しているとき、チームマネージャーまたは監修者は既定の作業者プロファイルを上書きして、時間外ではなく夜勤の標準レートで作業時間を計算するようにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b285b-146">In the case, where the worker profile is day shift, and the worker has agreed to work a night shift with no overtime pay, the team manager or supervisor must override the default worker profile in order to calculate the working time at the standard night rate and not as overtime.</span></span> <span data-ttu-id="b285b-147">計算時に休暇登録が見つからない場合、エラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="b285b-147">The calculation will also display an error if an absence registration is missing.</span></span> <span data-ttu-id="b285b-148">先に追加しておかないと、計算を完了させることができません。</span><span class="sxs-lookup"><span data-stu-id="b285b-148">It must be added before the calculation can be completed.</span></span>

## <a name="approving-registrations"></a><span data-ttu-id="b285b-149">登録の承認</span><span class="sxs-lookup"><span data-stu-id="b285b-149">Approving registrations</span></span>
<span data-ttu-id="b285b-150">計算グループを時間登録作業者に割り当てるのと同様に、承認グループも割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b285b-150">Just as you assign a calculation group to a time registration worker, you must assign an approval group as well.</span></span> <span data-ttu-id="b285b-151">一般に、グループは、特定のチーム、シフト、または作業グループです。</span><span class="sxs-lookup"><span data-stu-id="b285b-151">Typically the group will be specific to a team, shift, or work group.</span></span> <span data-ttu-id="b285b-152">休暇時間登録が正しく計算されると、承認する必要があります。これは、計算中にエラーがなかった場合を指します。その後、支払項目が生成され、給与システムに転送されます。</span><span class="sxs-lookup"><span data-stu-id="b285b-152">You must approve the time registrations that were calculated correctly – this means doing a calculation without errors – before pay items can be generated that afterward can be transferred to a payroll system.</span></span> <span data-ttu-id="b285b-153">給与管理者は通常、登録を承認します。承認前に次を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="b285b-153">The payroll administrator will typically do the approval of registrations, and prior to the approval he is able to:</span></span>
-   <span data-ttu-id="b285b-154">各従業員の支払契約を上書きします。</span><span class="sxs-lookup"><span data-stu-id="b285b-154">Override pay agreements for individual workers.</span></span>
-   <span data-ttu-id="b285b-155">他割増時間を追加します。</span><span class="sxs-lookup"><span data-stu-id="b285b-155">Add manual premiums.</span></span>
-   <span data-ttu-id="b285b-156">休暇登録に関する追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b285b-156">Enter additional information about absence registrations.</span></span>

| <span data-ttu-id="b285b-157">**メモ**</span><span class="sxs-lookup"><span data-stu-id="b285b-157">**Note**</span></span>                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b285b-158">特定の作業者に対し残業が計算されている場合、その日の特定のジョブに残業を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b285b-158">If overtime has been calculated for specific workers, the overtime can be allocated to specific jobs during the day.</span></span> <span data-ttu-id="b285b-159">これは、ジョブの原価が作業者の支払に基づいて計算される場合に重要です。</span><span class="sxs-lookup"><span data-stu-id="b285b-159">This is relevant if job cost is calculated based on worker pay.</span></span> |

## <a name="approving-registrations-using-workflow"></a><span data-ttu-id="b285b-160">ワークフローを使用した登録の承認</span><span class="sxs-lookup"><span data-stu-id="b285b-160">Approving registrations using workflow</span></span>
<span data-ttu-id="b285b-161">ワークフローの承認プロセスを設定して、ワークフロー ルールに従って自動的に登録を承認することができます。手動で処理する必要のある誤差のみが残ります。</span><span class="sxs-lookup"><span data-stu-id="b285b-161">You can set up a workflow approval process that automatically approves registrations which comply with workflow rules, leaving only deviations to be handled manually.</span></span> <span data-ttu-id="b285b-162">ワークフローの承認が有効になっている場合、チームマネージャーまたは監修者は承認のために計算済登録を送信します。</span><span class="sxs-lookup"><span data-stu-id="b285b-162">If workflow approval is activated, the team manager or supervisor submits the calculated registrations for approval.</span></span> <span data-ttu-id="b285b-163">ワークフロー プロセスによって適切な承認とタスクが作成され、ワークフローで指定されるユーザーとロールに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b285b-163">The workflow process will generate the appropriate approvals and tasks, and then assign them to the right users and roles as identified in the workflow.</span></span> <span data-ttu-id="b285b-164">時刻と出勤には 2 つのワークフローの承認があります。</span><span class="sxs-lookup"><span data-stu-id="b285b-164">There are two workflow approvals for time and attendance.</span></span>

| <span data-ttu-id="b285b-165">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="b285b-165">Workflow</span></span>                                  | <span data-ttu-id="b285b-166">目的</span><span class="sxs-lookup"><span data-stu-id="b285b-166">Purpose</span></span>                                                                                                   | <span data-ttu-id="b285b-167">登録タイプ</span><span class="sxs-lookup"><span data-stu-id="b285b-167">Registration type</span></span>                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b285b-168">時刻と出勤の合計日数</span><span class="sxs-lookup"><span data-stu-id="b285b-168">Time and attendance days total</span></span>            | <span data-ttu-id="b285b-169">このワークフローは、たとえば、1 日の期待作業時間数に対して登録を検証します。</span><span class="sxs-lookup"><span data-stu-id="b285b-169">The workflow validates registrations against, for example, the expected number of work hours for the day.</span></span> |                                                                                                                                                                                                                                                       |
| <span data-ttu-id="b285b-170">時刻と出勤の仕訳帳登録。</span><span class="sxs-lookup"><span data-stu-id="b285b-170">Time and attendance journal registration.</span></span> | <span data-ttu-id="b285b-171">このワークフローは、登録日の各登録タイプを検証します。</span><span class="sxs-lookup"><span data-stu-id="b285b-171">The workflow validates each registration type for the date of the registration.</span></span>                           | <span data-ttu-id="b285b-172">時刻と出勤 • 出勤 • 退勤 • 休暇 • 休憩 • 切り替えコード • プロジェクト • プロジェクト活動 • 間接活動 生産ジョブ • 作業前待ち時間 • 段取り • プロセス • 重複 • 移動 • 作業後待ち時間 • アシスタント開始 • アシスタント停止</span><span class="sxs-lookup"><span data-stu-id="b285b-172">Time and attendance • Clock-in • Clock-out • Absence • Break • Switch code • Project • Project activity • Indirect activity Production jobs • Queue before • Setup • Process • Overlap • Transport • Queue after • Start assistance • Stop assistance</span></span> |

 

## <a name="transferring-approved-registrations"></a><span data-ttu-id="b285b-173">承認された登録の転送</span><span class="sxs-lookup"><span data-stu-id="b285b-173">Transferring approved registrations</span></span>
<span data-ttu-id="b285b-174">登録の承認後に、定期的な給与ジョブに転送できます。</span><span class="sxs-lookup"><span data-stu-id="b285b-174">After approval of the registrations you can transfer them to a periodic payroll job.</span></span> <span data-ttu-id="b285b-175">移動された登録は、たとえば、製造オーダーやプロジェクトなどに関連する活動またはジョブに転記されます。</span><span class="sxs-lookup"><span data-stu-id="b285b-175">A transferred registration is posted to an activity or job that it relates to, for example, a production order or a project.</span></span> <span data-ttu-id="b285b-176">給与トランザクションは、登録に基づいて作業者ごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="b285b-176">Payroll transactions are generated for each worker based on the registrations.</span></span>  

## <a name="reversing-transferred-registrations"></a><span data-ttu-id="b285b-177">転送した登録の取消</span><span class="sxs-lookup"><span data-stu-id="b285b-177">Reversing transferred registrations</span></span>
<span data-ttu-id="b285b-178">登録を取り消すタスク、つまりロールバックするタスクは、給与期間の支払への振替が実行されるまでであれば実行できます。</span><span class="sxs-lookup"><span data-stu-id="b285b-178">The task of reversing transactions – rolling them back – can be done until the time when the payroll period’s pay transfer is run.</span></span> <span data-ttu-id="b285b-179">つまり、そのときは、給与データが外部ファイルに転送済です。</span><span class="sxs-lookup"><span data-stu-id="b285b-179">This means that payroll data has been transferred to an external file.</span></span> <span data-ttu-id="b285b-180">取消時には、すべての登録が元に戻され、製造オーダーやプロジェクトに転記されたトランザクションは相殺されて中立化されます。</span><span class="sxs-lookup"><span data-stu-id="b285b-180">When reversed, all registrations are withdrawn, and any transactions posted on production orders or projects are offset and neutralized.</span></span>

| <span data-ttu-id="b285b-181">**メモ**</span><span class="sxs-lookup"><span data-stu-id="b285b-181">**Note**</span></span>                                                 |
|----------------------------------------------------------|
| <span data-ttu-id="b285b-182">外部ファイルは、給与システムにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="b285b-182">The external file can be imported into a payroll system.</span></span> |

## <a name="registrations-in-electronic-timecards"></a><span data-ttu-id="b285b-183">電子タイムカードの登録</span><span class="sxs-lookup"><span data-stu-id="b285b-183">Registrations in electronic timecards</span></span>
<span data-ttu-id="b285b-184">生産ジョブなど即時のフィードバックを必要としない職務でも、プロジェクト活動の作業を行っている作業者は、電子タイムカードを使用する利点があります。</span><span class="sxs-lookup"><span data-stu-id="b285b-184">Workers with job tasks that do not require immediate feedback, as is the case with production jobs, but who work on project activities, can benefit from using the electronic timecard.</span></span> <span data-ttu-id="b285b-185">電子タイムカードは、いつでも記録を登録でき、毎日、毎週、または作業者がオフィスから退出してまた戻るなどの業務スケジュールにおいて最善の方法で記録できる柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="b285b-185">Electronic timecards offer the flexibility to enter registrations any time and in the best way for your business schedule – daily, weekly, or when a worker is in the office again after being away.</span></span> <span data-ttu-id="b285b-186">電子タイムカードを使用する、このような作業者を定義するには、作業者の詳細で [タイムカードを使用] を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b285b-186">To use electronic timecards or these workers, you must specify, Use timecard, in the worker details.</span></span> <span data-ttu-id="b285b-187">電子タイムカードにより、作業者は次のことが登録できます。</span><span class="sxs-lookup"><span data-stu-id="b285b-187">Electronic timecards enable the worker to register:</span></span>

-   <span data-ttu-id="b285b-188">日</span><span class="sxs-lookup"><span data-stu-id="b285b-188">Date</span></span>
-   <span data-ttu-id="b285b-189">登録タイプ</span><span class="sxs-lookup"><span data-stu-id="b285b-189">Registration type</span></span>
-   <span data-ttu-id="b285b-190">プロジェクト、間接活動、製造オーダーなどのジョブ参照</span><span class="sxs-lookup"><span data-stu-id="b285b-190">Job reference, such as project, indirect activity, or production order</span></span>
-   <span data-ttu-id="b285b-191">ジョブ ID</span><span class="sxs-lookup"><span data-stu-id="b285b-191">Job identification</span></span>
-   <span data-ttu-id="b285b-192">時間消費量</span><span class="sxs-lookup"><span data-stu-id="b285b-192">Time consumption</span></span>
-   <span data-ttu-id="b285b-193">プロジェクト手数料</span><span class="sxs-lookup"><span data-stu-id="b285b-193">Project fees</span></span>
-   <span data-ttu-id="b285b-194">プロジェクト品目</span><span class="sxs-lookup"><span data-stu-id="b285b-194">Project items</span></span>




