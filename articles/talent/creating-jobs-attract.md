---
title: "Attract でジョブ求人の作成、承認、および転記"
description: "このトピックでは、Attract でのジョブ求人の要素について説明します。 ジョブ求人を作成する方法についても説明します。"
author: josaw
manager: AnnBe
ms.date: 10/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-24
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2fc6bf25d303d7d8de8002a923a080b90dcfbeab
ms.openlocfilehash: af945042c150fff1a95cdb046f2a712cb2c2c061
ms.contentlocale: ja-jp
ms.lasthandoff: 10/24/2018

---

# <a name="create-approve-and-post-jobs-in-attract"></a><span data-ttu-id="59cf0-104">Attract でジョブ求人の作成、承認、および転記</span><span class="sxs-lookup"><span data-stu-id="59cf0-104">Create, approve, and post jobs in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="59cf0-105">このトピックでは、Microsoft Dynamics 365 for Talent: Attract でのジョブ求人の要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-105">This topic describes the elements of a job in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="59cf0-106">ジョブ求人を作成する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-106">It also explains how to create a job.</span></span>

## <a name="job-creation"></a><span data-ttu-id="59cf0-107">ジョブ求人の作成</span><span class="sxs-lookup"><span data-stu-id="59cf0-107">Job creation</span></span>

<span data-ttu-id="59cf0-108">管理者、採用担当者、および採用マネージャーがジョブ求人を作成できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-108">Admins, recruiters, and hiring managers can create jobs.</span></span> <span data-ttu-id="59cf0-109">ジョブ求人を作成するときに、プロセスでのロールを選択するよう求められます: 採用マネージャーまたは採用担当者。</span><span class="sxs-lookup"><span data-stu-id="59cf0-109">When you create a job, you're prompted to select your role in the process: hiring manager or recruiter.</span></span> <span data-ttu-id="59cf0-110">ロールを選択した後、プロセス テンプレートを選択するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-110">After you select a role, you're prompted to select a process template.</span></span> <span data-ttu-id="59cf0-111">**スキップ**を選択すると、既定のテンプレートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-111">If you select **Skip**, the default template is used.</span></span> <span data-ttu-id="59cf0-112">プロセス テンプレートの詳細については、[Attract でプロセス テンプレートの作成](./process-templates-attract.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59cf0-112">For more information about process templates, see [Create a process template in Attract](./process-templates-attract.md).</span></span>

<span data-ttu-id="59cf0-113">Attract でのジョブ求人には、職務の詳細、採用チーム、採用プロセス、人材募集、および分析が含まれます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-113">A job in Attract has job details, a hiring team, a hiring process, job postings, and analytics.</span></span>

## <a name="job-details"></a><span data-ttu-id="59cf0-114">職務の詳細</span><span class="sxs-lookup"><span data-stu-id="59cf0-114">Job details</span></span>

<span data-ttu-id="59cf0-115">**職務の詳細**タブには、職務の職責と属性に関する詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="59cf0-115">The **Job details** tab contains details about the job's responsibilities and attributes.</span></span> <span data-ttu-id="59cf0-116">職位、職務明細書、および勤務地のフィールドが必須です。</span><span class="sxs-lookup"><span data-stu-id="59cf0-116">The fields for the job title, job description, and job location are required.</span></span> <span data-ttu-id="59cf0-117">他のフィールドはオプションです。</span><span class="sxs-lookup"><span data-stu-id="59cf0-117">The other fields are optional.</span></span>

<span data-ttu-id="59cf0-118">既定では、**求人数**フィールドが **1** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="59cf0-118">By default, the **Number of openings** field is set to **1**.</span></span> <span data-ttu-id="59cf0-119">ただし、その値は変更できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-119">However, you can change the value.</span></span> <span data-ttu-id="59cf0-120">ジョブのオファーが準備された場合、**空いている求人数**フィールドは減少します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-120">When an offer has been prepared for a job, the value of the **Number of openings available** field is decremented.</span></span>

<span data-ttu-id="59cf0-121">職位管理が管理センターで有効になった場合、**職位の更新**ルックアップが使用できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-121">If position management has been turned on in the Admin Center, the **Update positions** lookup is available.</span></span> <span data-ttu-id="59cf0-122">このルックアップは Common Data Service for Apps の JobPosition エンティティを読み込み、職務に対して選択可能な職位の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-122">This lookup reads the JobPosition entity in Common Data Service for Apps and returns a list of positions that can be selected for the job.</span></span> <span data-ttu-id="59cf0-123">選択する求人数が職位の求人数を超える場合、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-123">If the number of positions that you select exceeds the number of open positions, you receive a warning.</span></span> <span data-ttu-id="59cf0-124">職位が複数の職務に使用される場合にも、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-124">You also receive a warning if a position is used on multiple jobs.</span></span>

> [!NOTE]
> <span data-ttu-id="59cf0-125">職位管理は、 包括採用アドオンで使用できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-125">Position management is available with the Comprehensive Hiring Add-on.</span></span>

<span data-ttu-id="59cf0-126">採用プロセスのオファー アクティビティでの設定に応じて、職位数は 1 つのオファーに対して 2 回使用できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-126">Depending on the settings in the Offer activity of the hiring process, a position number can be used twice in an offer.</span></span> <span data-ttu-id="59cf0-127">詳細については、[採用プロセス](./activities-attract.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59cf0-127">For more information, see [Hiring process](./activities-attract.md).</span></span>

<span data-ttu-id="59cf0-128">Attract には、既定の一連の**スキル**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-128">Attract includes a default set of **Skills**.</span></span> <span data-ttu-id="59cf0-129">これらのスキルは、入力する際の提案として表示されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-129">These skills appear as suggestions as you type.</span></span> <span data-ttu-id="59cf0-130">フィールドに新しいスキル テキストを入力し、Enter キーを押して、スキルをさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-130">You can add more skills by entering the new skill text in the field and then pressing Enter.</span></span>

<span data-ttu-id="59cf0-131">Attract には、既定の一連の**職務権限**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-131">Attract includes a default set of **Job functions**.</span></span> <span data-ttu-id="59cf0-132">フィールドに新しい職務権限を入力し、Enter キーを押して、3 つまでさらに職務権限を追加できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-132">You can add up to three more job functions by entering the new job function in the field and then pressing Enter.</span></span>

<span data-ttu-id="59cf0-133">Attract には、既定の一連の**会社の業種**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-133">Attract includes a default set of **Company industry**.</span></span> <span data-ttu-id="59cf0-134">フィールドに新しい会社の業種を入力し、Enter キーを押して、3 つまでさらに会社の業種を追加できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-134">You can add up to three more company industries by entering the new company industry in the field and then pressing Enter.</span></span>

## <a name="hiring-team"></a><span data-ttu-id="59cf0-135">採用チーム</span><span class="sxs-lookup"><span data-stu-id="59cf0-135">Hiring team</span></span>

<span data-ttu-id="59cf0-136">**採用チーム**タブには、ジョブ求人に関与する個人の一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-136">The **Hiring team** tab contains the list of individuals who will be involved in the job.</span></span> <span data-ttu-id="59cf0-137">ユーザーが採用チームに追加される場合、採用チームでのロールが割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="59cf0-137">When users are added to a hiring team, they must be assigned a role on the hiring team.</span></span> <span data-ttu-id="59cf0-138">ロールは、ユーザーのアクセス先および受信する通知のデータを決定します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-138">The role determines the data that the users have access to and the notifications that they receive.</span></span> <span data-ttu-id="59cf0-139">選択できるロールは、**採用担当者**、**採用マネージャー**、**代理人**、および**面接者**です。</span><span class="sxs-lookup"><span data-stu-id="59cf0-139">The roles that can be selected are **Recruiter**, **Hiring manager**, **Delegate**, and **Interviewer**.</span></span> <span data-ttu-id="59cf0-140">ロール権限の詳細については、"ロール管理" ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59cf0-140">For more information about role privileges, see the "Role management" document.</span></span> <span data-ttu-id="59cf0-141">採用担当者および採用マネージャーは、代わりに 1 名以上の複数の代理人を指名できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-141">Recruiters and hiring managers can appoint one or more delegates to work on their behalf.</span></span> <span data-ttu-id="59cf0-142">代理人の詳細については、[Attract でのセキュリティおよびロールの管理](./security-attract.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59cf0-142">For more information about delegates, see [Security and role management in Attract](./security-attract.md).</span></span>

<span data-ttu-id="59cf0-143">ジョブ求人が有効になった後、採用チームを更新できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-143">The hiring team can be updated after the job is activated.</span></span>

## <a name="process"></a><span data-ttu-id="59cf0-144">プロセス</span><span class="sxs-lookup"><span data-stu-id="59cf0-144">Process</span></span>

<span data-ttu-id="59cf0-145">採用プロセスに関する既定の情報は、ジョブ求人が作成されたときに選択されたプロセス テンプレートに基づきます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-145">Default information about the hiring process is based on the process template that was selected when the job was created.</span></span> <span data-ttu-id="59cf0-146">その時点で特定のテンプレートが選択されなかった場合には、既定のテンプレートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-146">If a specific template wasn't selected at that time, the default template is used.</span></span> <span data-ttu-id="59cf0-147">採用プロセスを定義する場合、候補者、応募、およびオファー ステージ以外のさまざまなステージを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-147">When you define the hiring process, you can add or remove various stages, except the Prospect, Application, and Offer stages.</span></span> <span data-ttu-id="59cf0-148">候補者のステージを削除できませんが、無効にはできます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-148">Although the Prospect stage can't be removed, it can be turned off.</span></span> <span data-ttu-id="59cf0-149">各ステージ内では、1 つまたは複数の事前に定義された活動を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-149">Within each stage, you can add or remove one or more predefined activities.</span></span>

<span data-ttu-id="59cf0-150">採用プロセスに追加できる活動に関する詳細については、[Attract での採用プロセス活動](./activities-attract.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59cf0-150">For more information about activities that can be added to the hiring process, see [Hiring process activities in Attract](./activities-attract.md).</span></span>

> [!NOTE]
> <span data-ttu-id="59cf0-151">ジョブ求人が有効になった後は、採用のプロセスを更新できません。</span><span class="sxs-lookup"><span data-stu-id="59cf0-151">The process hiring can't be updated after a job is activated.</span></span>

## <a name="postings"></a><span data-ttu-id="59cf0-152">転記</span><span class="sxs-lookup"><span data-stu-id="59cf0-152">Postings</span></span>

<span data-ttu-id="59cf0-153">ジョブ求人が有効になった後に、転記できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-153">After a job is activated, it can be posted.</span></span> <span data-ttu-id="59cf0-154">採用担当者と管理者だけが、ジョブ求人を転記できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-154">Only recruiters and admins can post jobs.</span></span> <span data-ttu-id="59cf0-155">ジョブ求人は、Talent Careers (Microsoft Dynamics 365 for Talent キャリア サイト) または LinkedIn のいずれかに転記できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-155">The job can be posted to either Talent Careers (a Microsoft Dynamics 365 for Talent career site) or LinkedIn.</span></span> <span data-ttu-id="59cf0-156">Attract チームは、継続的にジョブ ボード アグリゲータと提携していきます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-156">The Attract team continually works to partner with job board aggregators.</span></span> <span data-ttu-id="59cf0-157">したがって、このリストは時間の経過に伴い展開されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-157">Therefore, this list will expand over time.</span></span>

<span data-ttu-id="59cf0-158">ジョブ求人の転記の詳細については、[Attractでキャリア サイト機能](./career-site.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59cf0-158">For more information about job postings, see [Career site functionality in Attract](./career-site.md).</span></span>

> [!NOTE]
> <span data-ttu-id="59cf0-159">ジョブ求人の転記機能は、Attract の包括採用アドオンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-159">The job posting functionality is available only with the Comprehensive Hiring Add-on for Attract.</span></span>

## <a name="activate"></a><span data-ttu-id="59cf0-160">有効化する</span><span class="sxs-lookup"><span data-stu-id="59cf0-160">Activate</span></span>

<span data-ttu-id="59cf0-161">ジョブ求人が有効になった後、転記でき、候補者および申請者を追加できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-161">After a job is activated, it can be posted, and prospects and applicants can be added to it.</span></span> <span data-ttu-id="59cf0-162">ジョブ求人に候補者を追加するオプションは、採用プロセスの候補者活動で設定されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-162">The option to add prospects to a job is set in the Prospect activity in the hiring process.</span></span>

> [!NOTE]
> <span data-ttu-id="59cf0-163">ジョブ求人が有効になった後は、採用のプロセスを更新できません。</span><span class="sxs-lookup"><span data-stu-id="59cf0-163">The process hiring can't be updated after a job is activated.</span></span>

## <a name="prospects-and-applicants"></a><span data-ttu-id="59cf0-164">候補者および申請者</span><span class="sxs-lookup"><span data-stu-id="59cf0-164">Prospects and applicants</span></span>

<span data-ttu-id="59cf0-165">ジョブ求人に候補者を追加するオプションは、採用プロセスの [候補者活動](./activities-attract.md#prospect-activity) で設定されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-165">The option to add prospects to a job is set in the [Prospect activity](./activities-attract.md#prospect-activity) in the hiring process.</span></span> <span data-ttu-id="59cf0-166">ジョブ求人を有効にする前に、このオプションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59cf0-166">This option should be set before you activate the job.</span></span> <span data-ttu-id="59cf0-167">ジョブ求人が有効になった後、候補者および申請者を追加できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-167">After a job is activated, prospects and applicants can be added to it.</span></span>

## <a name="approvals"></a><span data-ttu-id="59cf0-168">承認</span><span class="sxs-lookup"><span data-stu-id="59cf0-168">Approvals</span></span>

<span data-ttu-id="59cf0-169">Attract のジョブ求人は、承認用に申請できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-169">Attract jobs can be submitted for approval.</span></span> <span data-ttu-id="59cf0-170">すべてのジョブ求人に、承認が必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="59cf0-170">Not all jobs require approval.</span></span> <span data-ttu-id="59cf0-171">要件は、テンプレート レベルで設定されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-171">The requirement is set at the template level.</span></span> <span data-ttu-id="59cf0-172">既定では、テンプレートで承認が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="59cf0-172">By default, approvals are turned off on the template.</span></span> <span data-ttu-id="59cf0-173">承認を設定するには、プロセス テンプレートに移動し、**承認**フィールドを既定値に設定します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-173">To set up approvals, go to a process template, and set the **Approval** field to Default.</span></span> <span data-ttu-id="59cf0-174">それから、ジョブ求人を作成するときにそのテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-174">Then select that template when you create the job.</span></span>

<span data-ttu-id="59cf0-175">ジョブ求人を保存した後、承認用に申請できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-175">After a job is saved, it can be submitted for approval.</span></span> <span data-ttu-id="59cf0-176">次の表では、承認を使用するドキュメントのステータスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-176">The following table lists the statuses of a document that uses approvals.</span></span>

| <span data-ttu-id="59cf0-177">ステータス</span><span class="sxs-lookup"><span data-stu-id="59cf0-177">Status</span></span>   | <span data-ttu-id="59cf0-178">行政単位 (区画)</span><span class="sxs-lookup"><span data-stu-id="59cf0-178">State</span></span>                                                               |
|----------|---------------------------------------------------------------------|
| <span data-ttu-id="59cf0-179">ドラフト</span><span class="sxs-lookup"><span data-stu-id="59cf0-179">Draft</span></span>    | <span data-ttu-id="59cf0-180">ジョブ求人が保存されたが、まだワークフローに送信されていません。</span><span class="sxs-lookup"><span data-stu-id="59cf0-180">The job has been saved, but it hasn't been submitted to a workflow.</span></span> |
| <span data-ttu-id="59cf0-181">保留中</span><span class="sxs-lookup"><span data-stu-id="59cf0-181">Pending</span></span>  | <span data-ttu-id="59cf0-182">ジョブ求人を承認者に送信しました。</span><span class="sxs-lookup"><span data-stu-id="59cf0-182">The job has been submitted to approvers.</span></span>                            |
| <span data-ttu-id="59cf0-183">承認済</span><span class="sxs-lookup"><span data-stu-id="59cf0-183">Approved</span></span> | <span data-ttu-id="59cf0-184">ジョブ求人が承認されたが、まだ有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="59cf0-184">The job has been approved, but it hasn't been activated.</span></span>            |
| <span data-ttu-id="59cf0-185">拒否済</span><span class="sxs-lookup"><span data-stu-id="59cf0-185">Rejected</span></span> | <span data-ttu-id="59cf0-186">ジョブ求人が拒否されると、有効化はできません。</span><span class="sxs-lookup"><span data-stu-id="59cf0-186">The job has been rejected, and it can't be activated.</span></span>               |
| <span data-ttu-id="59cf0-187">使用可能</span><span class="sxs-lookup"><span data-stu-id="59cf0-187">Active</span></span>   | <span data-ttu-id="59cf0-188">ジョブ求人が承認され、有効化されました。</span><span class="sxs-lookup"><span data-stu-id="59cf0-188">The job has been approved and activated.</span></span>                            |

<span data-ttu-id="59cf0-189">ジョブ求人の一覧で、ジョブ ステータスでフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-189">In the job list, you can filter on the job statuses.</span></span>

<span data-ttu-id="59cf0-190">承認は、会社内の任意の Microsoft Azure Active Directory (Azure AD) ユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-190">Approvals can be sent to any Microsoft Azure Active Directory (Azure AD) user in the company.</span></span> <span data-ttu-id="59cf0-191">承認は、承認者として一覧表示されているすべての人に同時に送信されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-191">The approvals are sent in parallel to all the people who are listed as approvers.</span></span> <span data-ttu-id="59cf0-192">ジョブ求人が承認された後に、有効になります。</span><span class="sxs-lookup"><span data-stu-id="59cf0-192">After a job is approved, it can be activated.</span></span>

<span data-ttu-id="59cf0-193">承認者として一覧表示されている人は、Attract で承認する項目があるという通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="59cf0-193">The people who are listed as approvers will receive a notification in Attract to inform them that they have an item to approve.</span></span> <span data-ttu-id="59cf0-194">承認項目は、ダッシュボードの**自分に割り当て済み**セクションにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-194">An approval item will also appear in the **Assigned to you** section on the dashboard.</span></span> <span data-ttu-id="59cf0-195">誰かがジョブ求人を受け入れまたは承認した後に、採用チームが通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="59cf0-195">After someone accepts or approves a job, the hiring team will receive a notification.</span></span> <span data-ttu-id="59cf0-196">最後に、採用チームはジョブ求人が承認されたときに通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="59cf0-196">Finally, the hiring team will receive a notification when the job is approved.</span></span>

## <a name="create-a-job"></a><span data-ttu-id="59cf0-197">職務の作成</span><span class="sxs-lookup"><span data-stu-id="59cf0-197">Create a job</span></span>

<span data-ttu-id="59cf0-198">職務を作成するには、これらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="59cf0-198">Follow these steps to create a job.</span></span>

1. <span data-ttu-id="59cf0-199">**職務**に移動します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-199">Go to **Jobs**.</span></span>
2. <span data-ttu-id="59cf0-200">**新規** を選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-200">Select **New**.</span></span>
3. <span data-ttu-id="59cf0-201">**職位**フィールドに、職位を入力します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-201">In the **Job title** field, enter the job title.</span></span> <span data-ttu-id="59cf0-202">**ロール**フィールドに、ロールを入力します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-202">In the **Role** field, enter your role.</span></span>
4. <span data-ttu-id="59cf0-203">**テンプレート** フィールドで、テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-203">In the **Template** field, select a template.</span></span> <span data-ttu-id="59cf0-204">または、**スキップ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-204">Alternatively, select **Skip**.</span></span> <span data-ttu-id="59cf0-205">**スキップ**を選択した場合、既定のテンプレートとしてマークされているテンプレートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-205">If you select **Skip**, the template that is marked as the default template is used.</span></span>

    <span data-ttu-id="59cf0-206">ドキュメントが承認プロセスを経由する必要がある場合、**承認プロセス**フィールドを**既定値**に設定しているテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-206">If the document should go through an approval process, select a template where the **Approval process** field is set to **Default**.</span></span>

5. <span data-ttu-id="59cf0-207">**詳細**タブで、職務の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-207">On the **Details** tab, enter the details of the job.</span></span> <span data-ttu-id="59cf0-208">**肩書き**、**職務明細書**、および**勤務地**フィールドが必須です。</span><span class="sxs-lookup"><span data-stu-id="59cf0-208">The **Title**, **Job description**, and **Location** fields are required.</span></span>
6. <span data-ttu-id="59cf0-209">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-209">Select **Save**.</span></span>
7. <span data-ttu-id="59cf0-210">**採用チーム**タブで、採用マネージャー、採用担当者、または面接者を追加します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-210">On the **Hiring team** tab, add a hiring manager, recruiter, or interviewer.</span></span>
8. <span data-ttu-id="59cf0-211">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-211">Select **Save**.</span></span>
9. <span data-ttu-id="59cf0-212">**プロセス**タブで、必要なステージを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-212">On the **Process** tab, add or remove stages as you require:</span></span>

    - <span data-ttu-id="59cf0-213">ステージを追加するには、**+ 新規ステージ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-213">To add a stage, select **+ New Stage**.</span></span>
    - <span data-ttu-id="59cf0-214">ステージを削除するには、ポインターをステージに移動して削除し、表示されるごみ箱ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-214">To remove a stage, hover the pointer over the stage to remove, and then select the trash can button that appears.</span></span>

        > [!NOTE]
        > <span data-ttu-id="59cf0-215">候補者、申請、およびオファー ステージを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="59cf0-215">The Prospect, Application, and Offer stages can't be removed.</span></span>

10. <span data-ttu-id="59cf0-216">必要に応じて、活動を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-216">Add or remove activities as you require:</span></span>

    - <span data-ttu-id="59cf0-217">活動を追加するには、右の一覧から適切なステージにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="59cf0-217">To add an activity, drag it from the list on the right to the appropriate stage.</span></span> <span data-ttu-id="59cf0-218">または、活動をダブルクリックし、それを追加するステージを選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-218">Alternatively, double-click the activity, and then select the stage to add it to.</span></span>
    - <span data-ttu-id="59cf0-219">活動を削除するには、活動を展開し、活動ヘッダーのごみ箱ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-219">To remove an activity, expand the activity, and then select the trash can button on the activity header.</span></span>

11. <span data-ttu-id="59cf0-220">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-220">Select **Save**.</span></span>
12. <span data-ttu-id="59cf0-221">承認プロセスを使用する選択をした場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="59cf0-221">If you selected to use an approval process, follow these steps:</span></span>

    1. <span data-ttu-id="59cf0-222">**+ 承認者の追加**を選択し、Azure AD アカウントを持つユーザーを入力します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-222">Select **+ Add approver**, and then enter a user who has an Azure AD account.</span></span> <span data-ttu-id="59cf0-223">複数の承認者を追加できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-223">You can add multiple approvers.</span></span>
    2. <span data-ttu-id="59cf0-224">**承認者に送信**を選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-224">Select **Send to approvers**.</span></span>

    <span data-ttu-id="59cf0-225">職務の**ジョブ ステータス**フィールドを**保留中**に設定します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-225">The **Job status** field of the job is set to **Pending**.</span></span> <span data-ttu-id="59cf0-226">**ジョブ ステータス**フィールドの値が**承認済**に変更した後、ジョブ求人を有効化できます。</span><span class="sxs-lookup"><span data-stu-id="59cf0-226">After the value of the **Job status** field changes to **Approved**, the job can be activated.</span></span>

13. <span data-ttu-id="59cf0-227">ジョブ求人を有効にするには、**有効化**を選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-227">To activate the job, select **Activate**.</span></span>
14. <span data-ttu-id="59cf0-228">ジョブ求人を転記するには、**転記**に移動し、Talent Careers サイトまたは LinkedIn で**今すぐ転記**を選択します。</span><span class="sxs-lookup"><span data-stu-id="59cf0-228">To post the job, go to **Postings**, and then select **Post Now** under the Talent Careers site or LinkedIn.</span></span>
