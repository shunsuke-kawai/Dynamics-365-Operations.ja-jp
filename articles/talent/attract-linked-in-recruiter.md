---
title: "LinkedIn Recruiter によるソーシング"
description: "このトピックでは、ジョブおよびジョブ候補の推奨事項を取得する機械学習の使用に関する情報を提供します。"
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2fc6bf25d303d7d8de8002a923a080b90dcfbeab
ms.openlocfilehash: 106103e2c3d8f3d89aac5140174e5794da22536f
ms.contentlocale: ja-jp
ms.lasthandoff: 10/24/2018

---

# <a name="sourcing-with-linkedin-recruiter"></a><span data-ttu-id="cc701-103">LinkedIn Recruiter によるソーシング</span><span class="sxs-lookup"><span data-stu-id="cc701-103">Sourcing with LinkedIn Recruiter</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="cc701-104">LinkedIn は世界最大の人材データベースで、多くの場合、採用担当者が検索、やり取りおよび採用担当者による入力を検討するジョブの候補者ソースを使用するプライマリ システムです。</span><span class="sxs-lookup"><span data-stu-id="cc701-104">LinkedIn is the world’s largest talent database and often the primary system that recruiters use to find, communicate with, and source candidates for the jobs that recruiters are looking to fill.</span></span> <span data-ttu-id="cc701-105">Dynamics 365 for Talent と LinkedIn Recruiter の統合: Attract は、ユーザー用に採用および 2 つのシステム間で同期するデータの保存ができます。</span><span class="sxs-lookup"><span data-stu-id="cc701-105">LinkedIn Recruiter integration with Dynamics 365 for Talent: Attract makes it easier for users to hire, and to keep the data in sync between the two systems.</span></span>

> [!NOTE]
> <span data-ttu-id="cc701-106">Attract と統合する LinkedIn Recruiter を使えるようにするには、包括採用アドオンおよび LinkedIn Recruiter 席が必要です。</span><span class="sxs-lookup"><span data-stu-id="cc701-106">You need the Comprehensive hiring add-on and LinkedIn Recruiter seats to be able to use LinkedIn Recruiter integration with Attract.</span></span>

## <a name="set-up-linkedin-recruiter-with-attract"></a><span data-ttu-id="cc701-107">Attract と LinkedIn Recruiter を設定</span><span class="sxs-lookup"><span data-stu-id="cc701-107">Set up LinkedIn Recruiter with Attract</span></span> 

<span data-ttu-id="cc701-108">LinkedIn Recruiter 能力を使用するには、Attract インスタンスで契約レベルまたは会社レベルのアクセスをコンフィギュレーションする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc701-108">Before you can use the LinkedIn Recruiter capabilities, you must configure contract-level or company-level access with your Attract instance.</span></span> <span data-ttu-id="cc701-109">コンフィギュレーション プロセスを完了するには、LinkedIn Recruiter 契約の管理者であるユーザーを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc701-109">To complete the configuration process, you must work with the user who is an Admin on your LinkedIn Recruiter contract.</span></span> <span data-ttu-id="cc701-110">Attract で LinkedIn Recruiter をコンフィギュレーションするには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc701-110">Complete the following steps to configure LinkedIn Recruiter with Attract.</span></span>

1.  <span data-ttu-id="cc701-111">管理者として Attract にサインインし、**管理者設定**へ移動します。</span><span class="sxs-lookup"><span data-stu-id="cc701-111">Sign in to Attract as an Admin and go to **Admin Settings**.</span></span>

2.  <span data-ttu-id="cc701-112">左ウィンドウで **LinkedIn 統合**タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc701-112">On the left pane, click the **LinkedIn Integration** tab.</span></span>

<span data-ttu-id="cc701-113">[![LinkedIn Recruiter 統合を開始する Attract 管理者ビュー](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span><span class="sxs-lookup"><span data-stu-id="cc701-113">[![Attract Admin view to start LinkedIn Recruiter integration](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span></span>

3.  <span data-ttu-id="cc701-114">**接続**をクリックして設定を開始すると、LinkedIn サインイン手順のガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc701-114">Click **Connect** to start the setup and be guided through the LinkedIn sign-in process.</span></span>

4.  <span data-ttu-id="cc701-115">複数の LinkedIn 契約に関する席数を使用する場合は、Attract システムにする契約を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc701-115">If you have seats on multiple LinkedIn contracts, select the contract that you would like to connect to the Attract system.</span></span> <span data-ttu-id="cc701-116">1 つの LinkedIn 契約のみの場合、この手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cc701-116">If you have a seat on only one LinkedIn contract, this step will not be needed.</span></span>

5.  <span data-ttu-id="cc701-117">LinkedIn ウィジェットでは、表示されている統合一覧で管理者の設定を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="cc701-117">The LinkedIn widget will now load in your Admin settings with the list of integrations shown.</span></span> <span data-ttu-id="cc701-118">**Recruiter System 接続**で、**要求**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc701-118">Under **Recruiter System connect**, click **Request**.</span></span>

<span data-ttu-id="cc701-119">[![要求 LinkedIn Recruiter 統合への Attract 管理者ビュー](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span><span class="sxs-lookup"><span data-stu-id="cc701-119">[![Attract Admin view to Request LinkedIn Recruiter integration](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span></span>

6.  <span data-ttu-id="cc701-120">統合が Attract から要求されると、**パートナー準備完了**と表示され、**採用管理者設定**から有効にする準備が可能です。</span><span class="sxs-lookup"><span data-stu-id="cc701-120">After the integration is requested from Attract, it will show as **Partner ready** and is ready to be turned on from **Recruiter Admin settings**.</span></span> <span data-ttu-id="cc701-121">このページで**通知パートナー**が表示されたら、しばらく待ち、**通知パートナー**をクリックしてページを最新の情報に更新します。</span><span class="sxs-lookup"><span data-stu-id="cc701-121">If you see **Notify partner** on this page, wait a few seconds, click **Notify partner**, and then refresh the page.</span></span> <span data-ttu-id="cc701-122">**パートナー準備完了**と表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc701-122">It should now show as **Partner ready**.</span></span>

<span data-ttu-id="cc701-123">[![完了した要求の Attract 側を示す Attract 管理者ビュー](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span><span class="sxs-lookup"><span data-stu-id="cc701-123">[![Attract Admin view to indicate Attract side of requests have been completed](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span></span>

<span data-ttu-id="cc701-124">次の手順を完了するには、LinkedIn Recruiter 契約に関する管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="cc701-124">To complete the next step, you need to have an Admin privilege on your LinkedIn Recruiter Contract.</span></span>

7.  <span data-ttu-id="cc701-125">管理者アカウントを使用して LinkedIn にサインインし、右上の LinkedIn Recruiter に移動します。</span><span class="sxs-lookup"><span data-stu-id="cc701-125">Sign in to LinkedIn using the Admin account and go to LinkedIn Recruiter on the top right.</span></span> 

8. <span data-ttu-id="cc701-126">画面上部にある**詳細**メニューで、**管理者設定**をクリックしてから **ATS** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc701-126">On the **More** menu at the top of the screen, click **Admin Settings**, and then click the **ATS** Tab.</span></span>

<span data-ttu-id="cc701-127">Attract システムでは、使用可能なオプションがいくつか表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc701-127">The Attract system will be listed with a couple of options that can be turned on.</span></span>

9. <span data-ttu-id="cc701-128">**In-ATS インジケータ**と **In-ATS プロファイル ウィジェット**に 1 クリック エキスポートのみ有効にする場合、**会社レベルのアクセスを**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc701-128">If you want to enable only 1-Click export for the **In-ATS indicator** and the **In-ATS Profile Widget**, select **Company-level access**.</span></span> <span data-ttu-id="cc701-129">InMail 履歴、メモの履歴および InMail スタブ プロファイル アクセスをプラスした会社レベル アクセスの機能を有効にする場合は、**契約レベル アクセス**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc701-129">If you want to enable all of Company-level access features plus InMail history, Notes history, and the InMail stub profile access, select **Contract-level access**.</span></span>

10. <span data-ttu-id="cc701-130">LinkedIn Recrioter の**管理者 ATS** 設定から必要なアクセス レベルをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cc701-130">Turn on the desired access level from your LinkedIn Recruiter **Admin-ATS** settings.</span></span>

<span data-ttu-id="cc701-131">[![LinkedIn Recruiter 管理者ビューから Attract 統合にオン](./media/EnableRSC.png)](./media/EnableRSC.png)</span><span class="sxs-lookup"><span data-stu-id="cc701-131">[![Turn on Attract integration from LinkedIn Recruiter Admin view](./media/EnableRSC.png)](./media/EnableRSC.png)</span></span>

12. <span data-ttu-id="cc701-132">AttractAdmin として Attract 管理者設定に戻り**LinkedIn 統合**タブを選択します。選択されたアクセス レベルをオンにし、**有効**と表示された Linkedln ウィジェットの積荷を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cc701-132">Go back to Attract Admin Settings as an AttractAdmin and select the **LinkedIn integration** tab. You should now see the LinkedIn widget load showing **Enabled** with the selected access level turned on.</span></span>

<span data-ttu-id="cc701-133">[![LinkedIn Recruiter 統合完了](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span><span class="sxs-lookup"><span data-stu-id="cc701-133">[![LinkedIn Recruiter integration complete](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span></span>

## <a name="using-linkedin-recruiter-capabilities"></a><span data-ttu-id="cc701-134">LinkedIn Recruiter 能力を使用</span><span class="sxs-lookup"><span data-stu-id="cc701-134">Using LinkedIn Recruiter capabilities</span></span>

<span data-ttu-id="cc701-135">Attract 管理者が LinkedIn Recruiter 能力を有効にした後、採用マネージャーおよび採用担当者はアクセス可能です。</span><span class="sxs-lookup"><span data-stu-id="cc701-135">After LinkedIn Recruiter capabilities has been enabled by the Attract Admin it is available for hiring managers and recruiters to access.</span></span> <span data-ttu-id="cc701-136">これらの能力を使用するには、**ユーザー設定**で LinkedIn アカウントに接続します。</span><span class="sxs-lookup"><span data-stu-id="cc701-136">To use these capabilities, connect your LinkedIn account under **User Settings**.</span></span> <span data-ttu-id="cc701-137">管理者とユーザーの両方の設定を接続した後、いくつかの能力が使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="cc701-137">Several capabilities will be available after both the Admin and User settings have been connected.</span></span>

### <a name="in-ats-profile-widget"></a><span data-ttu-id="cc701-138">In-ATS プロファイル ウィジェット</span><span class="sxs-lookup"><span data-stu-id="cc701-138">In-ATS profile widget</span></span>

<span data-ttu-id="cc701-139">応募者の LinkedIn プロファイルを Attract で表示できます。</span><span class="sxs-lookup"><span data-stu-id="cc701-139">You can view the candidate’s LinkedIn profile in Attract.</span></span> <span data-ttu-id="cc701-140">ATS 情報がユーザーの LinkedIn 情報と一致すると、Linkedln ウイジェット では候補者のプロファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc701-140">The LinkedIn widget will display the candidate profile when the ATS information matches the LinkedIn information of its users.</span></span>

<span data-ttu-id="cc701-141">プロファイルを表示するには、ジョブまたは人材プールのいずれかより候補者のプロファイルへ移動します。</span><span class="sxs-lookup"><span data-stu-id="cc701-141">To view a profile, go the candidate profile either from a job or talent pool.</span></span> <span data-ttu-id="cc701-142">候補者のプロファイルにて **LinkedIn** タブを選択し、プロファイル ウィジェットを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="cc701-142">In the candidate profile, select the **LinkedIn** tab and the profile widget will load.</span></span> <span data-ttu-id="cc701-143">プロファイル ウィジェットを使用して、正しい一致であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="cc701-143">Using the profile widget, indicate if this is the correct match.</span></span> <span data-ttu-id="cc701-144">一致しない場合は、正しい担当者を検索します。</span><span class="sxs-lookup"><span data-stu-id="cc701-144">If it is not, find the correct person.</span></span> <span data-ttu-id="cc701-145">候補者をこのページから LinkedIn Recruiter プロジェクトに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc701-145">You can also save the candidate to your LinkedIn Recruiter projects from this page.</span></span>

### <a name="1-click-export"></a><span data-ttu-id="cc701-146">1 クリック エクスポート</span><span class="sxs-lookup"><span data-stu-id="cc701-146">1-click export</span></span> 

<span data-ttu-id="cc701-147">LinkedIn の候補者を調達する間、候補者を現在開いているジョブに 1 クリック エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="cc701-147">While sourcing candidates in LinkedIn, you can 1-click export the candidate to the jobs that you currently have open.</span></span> <span data-ttu-id="cc701-148">1 クリック エクスポートの以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc701-148">Complete the following steps for a 1-click export.</span></span> <span data-ttu-id="cc701-149">これらの手順を完了する前に、ジョブの採用マネージャーまたは採用担当者のロールが割り当てられており、そのジョブで**見込顧客**ステージが表示されているか確認します。</span><span class="sxs-lookup"><span data-stu-id="cc701-149">Before you complete these steps, verify that you are a assigned the role of Hiring manager or Recruiter for the job and that the job has a **Prospect** stage.</span></span>

1.  <span data-ttu-id="cc701-150">ジョブを作成し、適切なロールを割り当てた後、ジョブをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="cc701-150">Create the job, assign the appropriate roles, and activate the job.</span></span>

2.  <span data-ttu-id="cc701-151">ジョブがアクティブである場合は、LinkedIn Recruiter に移動します。</span><span class="sxs-lookup"><span data-stu-id="cc701-151">When the job is activated, navigate to LinkedIn Recruiter.</span></span>

3.  <span data-ttu-id="cc701-152">探している候補者を検索して、プロファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="cc701-152">Find the candidate that you are looking for and go to their profile.</span></span>

4.  <span data-ttu-id="cc701-153">連絡先カードのジョブ検索ボックスを使用して、タイトルまたは Attract で有効のジョブ ID を使いジョブを検索します。</span><span class="sxs-lookup"><span data-stu-id="cc701-153">Using the job search box in the contact card, find the job using the title or the Job ID that was activated in Attract.</span></span> <span data-ttu-id="cc701-154">ジョブが見つからない場合は、**変更 ATS** をクリックして正しい Attract インスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="cc701-154">If you don’t find the job, click **Change ATS** to find the correct Attract instance.</span></span>

5. <span data-ttu-id="cc701-155">ジョブを選択して、**エクスポート**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc701-155">After the job is selected, click **Export**.</span></span> <span data-ttu-id="cc701-156">Attract は候補者をフェッチします。</span><span class="sxs-lookup"><span data-stu-id="cc701-156">The candidate is now fetched by Attract.</span></span>

6.  <span data-ttu-id="cc701-157">Attract に移動して、それぞれのジョブをオープンします。</span><span class="sxs-lookup"><span data-stu-id="cc701-157">Go to Attract and open the respective job.</span></span> <span data-ttu-id="cc701-158">ジョブの**見込顧客**ステージで、エクスポートした候補者を検索します。</span><span class="sxs-lookup"><span data-stu-id="cc701-158">You will find the candidate that you just exported in the **Prospect** stage of the job.</span></span>

### <a name="in-ats-indicator"></a><span data-ttu-id="cc701-159">In-ATS インジケーター</span><span class="sxs-lookup"><span data-stu-id="cc701-159">In-ATS indicator</span></span> 

<span data-ttu-id="cc701-160">LinkedIn Recruiter を使用すると、候補者が組織内の他のジョブに適用するかどうかの追跡が可能で、ジョブ アプリケーションの異なるステージであることの確認および LinkedIn Recruiter の Attract からフィードバックとコメントの表示が可能です。</span><span class="sxs-lookup"><span data-stu-id="cc701-160">Using LinkedIn recruiter, you can track whether a candidate has applied to other jobs in your organization, look at where they are in different stages of job applications, and view the feedback and comments from Attract in LinkedIn Recruiter.</span></span>

1.  <span data-ttu-id="cc701-161">LinkedIn Recruiter を開き、探している候補者プロファイルを特定します。</span><span class="sxs-lookup"><span data-stu-id="cc701-161">Open LinkedIn Recruiter and locate the candidate profile that you are looking for.</span></span>

2.  <span data-ttu-id="cc701-162">下にスクロールして、候補者プロファイルで **In-ATS** セクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="cc701-162">Scroll down to view the **In-ATS** section on the candidate’s profile.</span></span>

3.  <span data-ttu-id="cc701-163">このウィジェットを使用して、LinkedIn Recruiter ビュー内から Attract に存在する候補者の関連情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="cc701-163">You can use this widget to view all of the information about the candidate that’s present in Attract from within the LinkedIn Recruiter view.</span></span>

4.  <span data-ttu-id="cc701-164">**Jobs & Statuses** タブを選択して、ジョブの一部、最新のステータス、および各ジョブに移動する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc701-164">Select the **Jobs & Statuses** tab to see jobs they are part of, the latest status, and how they have been moving against each job.</span></span>

5.  <span data-ttu-id="cc701-165">**面接フィードバック**タブを選択し、面接者が Attract で送信したフィードバックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc701-165">Select the **Interview Feedback** tab to see feedback that the interviewers have submitted in Attract.</span></span>

6.  <span data-ttu-id="cc701-166">**メモ**タブを選択し、Attract で申請者にキャプチャされたメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc701-166">Select the **Notes** tab to see notes that have been captured for this applicant in Attract.</span></span>

### <a name="inmail-history"></a><span data-ttu-id="cc701-167">InMail 履歴</span><span class="sxs-lookup"><span data-stu-id="cc701-167">InMail history</span></span>

<span data-ttu-id="cc701-168">LinkedIn InMail 履歴は、LinkedIn Recruiter と契約レベルのアクセスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc701-168">The LinkedIn InMail history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="cc701-169">有効な場合は、候補者とともに全体の InMail 履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cc701-169">When it is enabled, you can view your entire InMail history with the candidate.</span></span> <span data-ttu-id="cc701-170">また、組織の誰が候補者と InMail を交換できたのかも確認できますが、両間でメッセージを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc701-170">You can also see who else from your organization has exchanged InMail with the candidate, however you can't view the messages between them.</span></span>

<span data-ttu-id="cc701-171">InMail 履歴を表示するには、応募者のプロファイルから **LinkedIn** タブに移動し、履歴を表示するページの下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="cc701-171">To view InMail history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="cc701-172">候補者が要求に答え、LinkedIn でプロファイルの共有を選択する場合にのみ、InMail 履歴を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="cc701-172">You can view the InMail history only if the candidate has responded to your request and chosen to share their profile with you in LinkedIn.</span></span> <span data-ttu-id="cc701-173">InMail からのメッセージは、数時間ごとに Attract と同期します。</span><span class="sxs-lookup"><span data-stu-id="cc701-173">The messages from InMail sync with Attract every couple of hours.</span></span>

### <a name="notes-history"></a><span data-ttu-id="cc701-174">メモの履歴</span><span class="sxs-lookup"><span data-stu-id="cc701-174">Notes history</span></span> 

<span data-ttu-id="cc701-175">LinkedIn メモの履歴は、LinkedIn Recruiter と契約レベルのアクセスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc701-175">The LinkedIn notes history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="cc701-176">有効にすると、組織とな異なる採用担当者によってキャプチャされた候補者に関するメモを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cc701-176">When it is enabled, you can view the notes that have been captured about the candidate by different recruiters from your organization.</span></span>

<span data-ttu-id="cc701-177">メモの履歴を表示するには、応募者のプロファイルから **LinkedIn** タブに移動し、履歴を表示するページの下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="cc701-177">To view Notes history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="cc701-178">LinkedIn Recruiter からの応募者に関するすべてのメモを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="cc701-178">You can view all the notes about the candidate from LinkedIn Recruiter.</span></span>

### <a name="inmail-stub-profile"></a><span data-ttu-id="cc701-179">InMail スタブ プロファイル</span><span class="sxs-lookup"><span data-stu-id="cc701-179">InMail stub profile</span></span>

<span data-ttu-id="cc701-180">InMail スタブ プロファイルは、LinkedIn Recruiter と契約レベルのアクセスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc701-180">The InMail stub profile is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="cc701-181">候補者が組織内のユーザーとその LinkedIn プロファイルの共有に同意する場合は、Attract 候補者を追跡でき、新しい候補者のレコードが各候補者へ作成されます。</span><span class="sxs-lookup"><span data-stu-id="cc701-181">If candidates agree to share their LinkedIn profiles with any user in your organization, you can track the candidates in Attract and a new candidate record will be created for each candidate.</span></span>

<span data-ttu-id="cc701-182">候補者の一覧を表示するには、**人材プール**に移動し、システムで作成された LinkedIn 人材プールを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc701-182">To view the list of candidates, go to **Talent pools** to see a system-created LinkedIn talent pool.</span></span> <span data-ttu-id="cc701-183">この人材プールには、LinkedIn から受信した候補者リストと スタブ プロファイルが含まれています。リストには候補者の名前と姓が表示されています。</span><span class="sxs-lookup"><span data-stu-id="cc701-183">This talent pool contains the list candidates and their stub profiles as received from LinkedIn, showing the candidate's first name and last name.</span></span> <span data-ttu-id="cc701-184">候補者が自身の電子メール アドレスを共有すると選択した場合、電子メール IDが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc701-184">The candidate’s email ID will be displayed if the candidate had chosen to share their email address.</span></span>
