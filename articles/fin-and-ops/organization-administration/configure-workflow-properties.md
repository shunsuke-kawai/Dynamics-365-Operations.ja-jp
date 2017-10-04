---
title: "ワークフローのプロパティをコンフィギュレーション"
description: "このトピックでは、ワークフローの各種プロパティをコンフィギュレーションする方法について説明します。"
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 6cad67d4108a81de545a1e633dc4e12a31af683b
ms.contentlocale: ja-jp
ms.lasthandoff: 07/18/2017

---

# <a name="configure-the-properties-of-a-workflow"></a><span data-ttu-id="98c04-103">ワークフローのプロパティをコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="98c04-103">Configure the properties of a workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="98c04-104">このトピックでは、ワークフローの各種プロパティをコンフィギュレーションする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98c04-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="98c04-105">ワークフローのプロパティをコンフィギュレーションするには、ワークフロー エディターでワークフローを開きます。</span><span class="sxs-lookup"><span data-stu-id="98c04-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="98c04-106">ワークフロー エディターのキャンバスをクリックし、[**プロパティ**] をクリックして、[**プロパティ**] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="98c04-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="98c04-107">ワークフローの各種プロパティをコンフィギュレーションするには、次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="98c04-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="98c04-108">ワークフローに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="98c04-108">Name the workflow</span></span>
<span data-ttu-id="98c04-109">次の手順でワークフローの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c04-109">Follow these steps to enter a name for the workflow.</span></span>

1.  <span data-ttu-id="98c04-110">左ウィンドウで [**基本設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-110">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="98c04-111">[**名前**] フィールドに、ワークフローの固有の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c04-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="98c04-112">たとえば、事業を行っている国または地域ごとに購買要求ワークフローを作成する場合には、購買要求ワークフローの名前を「**購買要求 (デンマーク)**」、または「**購買要求 (スペイン)**」のようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="98c04-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="98c04-113">ワークフローの所有者の指定</span><span class="sxs-lookup"><span data-stu-id="98c04-113">Specify the workflow owner</span></span>
<span data-ttu-id="98c04-114">ワークフローの所有者とは、そのワークフローの管理と保守を行う人のことです。</span><span class="sxs-lookup"><span data-stu-id="98c04-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="98c04-115">次の手順でワークフローの所有者を指定します。</span><span class="sxs-lookup"><span data-stu-id="98c04-115">Follow these steps to specify the workflow owner.</span></span>

1.  <span data-ttu-id="98c04-116">左ウィンドウで [**基本設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-116">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="98c04-117">[**所有者**] 一覧で、ワークフローの管理を行う人の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="98c04-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="98c04-118">電子メール テンプレートの選択</span><span class="sxs-lookup"><span data-stu-id="98c04-118">Select an email template</span></span>
<span data-ttu-id="98c04-119">このワークフローに関する通知メッセージを生成するのに使用する電子メール テンプレートを選択するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="98c04-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1.  <span data-ttu-id="98c04-120">左ウィンドウで [**基本設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-120">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="98c04-121">[**ワークフロー通知の電子メール テンプレート**] 一覧で、テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="98c04-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="98c04-122">ユーザーに対する指示の入力</span><span class="sxs-lookup"><span data-stu-id="98c04-122">Enter instructions for users</span></span>
<span data-ttu-id="98c04-123">処理と承認を求めてドキュメントを送信するユーザーに指示を入力できます。</span><span class="sxs-lookup"><span data-stu-id="98c04-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="98c04-124">これらのユーザーは、[*作成者*] とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="98c04-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="98c04-125">たとえば、購買要求ワークフローを作成しており、指示を入力するとします。</span><span class="sxs-lookup"><span data-stu-id="98c04-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="98c04-126">これらの指示は、[**購買要求**] ページで、購買要求を入力するユーザーに対して表示できます。</span><span class="sxs-lookup"><span data-stu-id="98c04-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="98c04-127">指示を表示するには、作成者がワークフロー メッセージ バーのアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="98c04-128">次の手順に従って、ユーザーに対する指示を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c04-128">Follow these steps to enter instructions for users.</span></span>

1.  <span data-ttu-id="98c04-129">左ウィンドウで [**基本設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-129">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="98c04-130">[**送信指示**] フィールドで、指示を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c04-130">In the **Submission instructions** field, enter the instructions.</span></span>
3.  <span data-ttu-id="98c04-131">指示を個人向けのものにするには、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="98c04-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="98c04-132">プレースホルダーは、指示行がユーザーに表示されるときに、適切なデータに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="98c04-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="98c04-133">プレースホルダーを挿入するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="98c04-133">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="98c04-134">[**送信指示**] フィールドをクリックして、プレースホルダを表示する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="98c04-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="98c04-135">[**プレースホルダーの挿入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-135">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="98c04-136">表示されるリストで、挿入するプレースホルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="98c04-136">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="98c04-137">[**挿入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-137">Click **Insert**.</span></span>

4.  <span data-ttu-id="98c04-138">指示行の翻訳を追加するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="98c04-138">To add translations of the instructions, follow these steps:</span></span>
    1.  <span data-ttu-id="98c04-139">[**翻訳**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-139">Click **Translations**.</span></span>
    2.  <span data-ttu-id="98c04-140">表示されるページで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-140">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="98c04-141">表示される一覧で、テキストを入力する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="98c04-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4.  <span data-ttu-id="98c04-142">[**翻訳テキスト**] フィールドで、テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="98c04-142">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="98c04-143">テキストをカスタマイズするには、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="98c04-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="98c04-144">プレースホルダーを入力する方法については、ステップ 3 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c04-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6.  <span data-ttu-id="98c04-145">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used"></a><span data-ttu-id="98c04-146">このワークフローが使用される条件の指定</span><span class="sxs-lookup"><span data-stu-id="98c04-146">Specify when this workflow is used</span></span>
<span data-ttu-id="98c04-147">同じタイプに基づく複数のワークフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="98c04-147">You can create multiple workflows that are based on the same type.</span></span> <span data-ttu-id="98c04-148">たとえば、事業を行っている国や地域ごとの購買要求ワークフロー ("購買要求 (デンマーク)" および "購買要求 (スペイン)" など) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="98c04-148">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain.</span></span> <span data-ttu-id="98c04-149">同じタイプに基づくワークフローが複数ある場合は、各ワークフローが使用される条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98c04-149">When you have multiple workflows that are based on the same type, you must specify when each workflow is used.</span></span> <span data-ttu-id="98c04-150">前の例では、次のような条件を指定することになります。</span><span class="sxs-lookup"><span data-stu-id="98c04-150">For the preceding example, you specify the following conditions:</span></span>

-   <span data-ttu-id="98c04-151">購買要求 (デンマーク) は、国/地域 = DK の場合に使用する</span><span class="sxs-lookup"><span data-stu-id="98c04-151">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
-   <span data-ttu-id="98c04-152">購買要求 (スペイン) は、国/地域 = ES の場合に使用する</span><span class="sxs-lookup"><span data-stu-id="98c04-152">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="98c04-153">次の手順を実行して、コンフィギュレーション内のワークフローをいつ使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="98c04-153">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1.  <span data-ttu-id="98c04-154">左ウィンドウで、[**有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-154">In the left pane, click **Activation**.</span></span>
2.  <span data-ttu-id="98c04-155">[**このワークフローを実行する条件を設定する**] のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="98c04-155">Select the **Set the conditions for running this workflow** check box.</span></span>
3.  <span data-ttu-id="98c04-156">[**条件の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-156">Click **Add condition**.</span></span>
4.  <span data-ttu-id="98c04-157">条件を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c04-157">Enter a condition.</span></span>
5.  <span data-ttu-id="98c04-158">必要に応じて、追加条件を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c04-158">Enter any additional conditions that are required.</span></span>
6.  <span data-ttu-id="98c04-159">入力した条件が正しく設定されていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c04-159">To verify that the conditions that you entered are set correctly, follow these steps:</span></span>
    1.  <span data-ttu-id="98c04-160">[**テスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-160">Click **Test**.</span></span>
    2.  <span data-ttu-id="98c04-161">[**ワークフロー条件のテスト**] ページで、[**条件の検証**] 領域で、レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="98c04-161">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3.  <span data-ttu-id="98c04-162">[**テスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-162">Click **Test**.</span></span> <span data-ttu-id="98c04-163">システムによってレコードが評価され、指定した条件を満たすかどうかが判定されます。</span><span class="sxs-lookup"><span data-stu-id="98c04-163">The system evaluates the record to determine whether it meets the conditions that you specified.</span></span> <span data-ttu-id="98c04-164">たとえば、スペイン向けの購買要求ワークフローを作成している場合、ページの [**条件の検証**] 領域に、購買要求の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="98c04-164">For example, if you're creating a purchase requisition workflow for Spain, the **Validate condition** area of the page shows a list of purchase requisitions.</span></span> <span data-ttu-id="98c04-165">[**テスト**] をクリックすると、選択した購買要求が評価され、国/地域 = ES (スペイン) であるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="98c04-165">When you click **Test**, the system evaluates the selected purchase requisition to determine whether the country/region is ES.</span></span>
    4.  <span data-ttu-id="98c04-166">[**OK**]、または [**キャンセル**] をクリックして、[**プロパティ**] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="98c04-166">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="98c04-167">いつ通知を送信するかを指定する</span><span class="sxs-lookup"><span data-stu-id="98c04-167">Specify when notifications are sent</span></span>
<span data-ttu-id="98c04-168">処理のためにドキュメントが送信されると、ワークフロー インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="98c04-168">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="98c04-169">このワークフローに基づくワークフロー インスタンスが開始、完了、打ち切り、またはエラーによって停止されたときに、ユーザーに通知を送信できます。</span><span class="sxs-lookup"><span data-stu-id="98c04-169">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="98c04-170">いつ通知を送信するかを指定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="98c04-170">Follow these steps to specify when notifications are sent.</span></span>

1.  <span data-ttu-id="98c04-171">左ウィンドウで、[**通知**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-171">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="98c04-172">通知をトリガーする各イベントのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="98c04-172">Select the check box for each event that should trigger notifications:</span></span>
    -   <span data-ttu-id="98c04-173">[**開始済**] – ワークフロー インスタンスが開始されたときに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="98c04-173">**Started** – Send notifications when a workflow instance is started.</span></span>
    -   <span data-ttu-id="98c04-174">[**停止済**] – ワークフロー インスタンスがエラーで停止したときに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="98c04-174">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    -   <span data-ttu-id="98c04-175">[**完了**] – ワークフロー インスタンスが完了したときに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="98c04-175">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    -   <span data-ttu-id="98c04-176">[**修復不可能**] – ワークフロー インスタンスが、修復不可能なエラーで停止したときに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="98c04-176">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    -   <span data-ttu-id="98c04-177">[**終了**] – ワークフロー インスタンスが打ち切られたときに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="98c04-177">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3.  <span data-ttu-id="98c04-178">ステップ 2 で選択したイベントの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="98c04-178">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="98c04-179">[**通知テキスト**] タブで、通知のテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="98c04-179">On the **Notification text** tab, enter the text of the notification.</span></span>
5.  <span data-ttu-id="98c04-180">テキストをカスタマイズするには、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="98c04-180">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="98c04-181">プレースホルダーは、テキストがユーザーに表示されるときに、適切なデータに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="98c04-181">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="98c04-182">プレースホルダーを挿入するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="98c04-182">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="98c04-183">フィールド内でクリックして、プレースホルダーを表示する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="98c04-183">Click in the field to specify where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="98c04-184">[**プレースホルダーの挿入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-184">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="98c04-185">表示されるリストで、挿入するプレースホルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="98c04-185">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="98c04-186">[**挿入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-186">Click **Insert**.</span></span>

6.  <span data-ttu-id="98c04-187">テキストの翻訳を追加するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="98c04-187">To add translations of the text, follow these steps:</span></span>
    1.  <span data-ttu-id="98c04-188">[**翻訳**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-188">Click **Translations**.</span></span>
    2.  <span data-ttu-id="98c04-189">表示されるページで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-189">On the page that appears, Click **Add**.</span></span>
    3.  <span data-ttu-id="98c04-190">表示される一覧で、テキストを入力する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="98c04-190">In the list that appears, select the language that you will enter the text in.</span></span>
    4.  <span data-ttu-id="98c04-191">[**翻訳テキスト**] フィールドで、テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="98c04-191">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="98c04-192">テキストをカスタマイズするには、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="98c04-192">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="98c04-193">プレースホルダーを入力する方法の指示については、ステップ 5 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c04-193">For instructions about how to enter a placeholder, see step 5.</span></span>
    6.  <span data-ttu-id="98c04-194">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-194">Click **Close**.</span></span>

7.  <span data-ttu-id="98c04-195">[**受信者**] タブで、次のオプションを使用して、通知の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="98c04-195">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="98c04-196">オプション</span><span class="sxs-lookup"><span data-stu-id="98c04-196">Option</span></span></th>
    <th><span data-ttu-id="98c04-197">通知はこれらのユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="98c04-197">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="98c04-198">通知を送信するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="98c04-198">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="98c04-199">参加者</span><span class="sxs-lookup"><span data-stu-id="98c04-199">Participant</span></span></td>
    <td><span data-ttu-id="98c04-200">特定のグループまたはロールに割り当てられたユーザー</span><span class="sxs-lookup"><span data-stu-id="98c04-200">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="98c04-201">[<strong>受信者</strong>] タブで [<strong>参加者</strong>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-201">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="98c04-202">[<strong>参加者のタイプ</strong>] 一覧の、[<strong>ロール ベース</strong>] タブで、通知の送信先のグループまたはロールのタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="98c04-202">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="98c04-203">[<strong>参加者</strong>] の一覧で、通知の送信先のグループまたはロールのタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="98c04-203">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="98c04-204">ワークフロー ユーザー</span><span class="sxs-lookup"><span data-stu-id="98c04-204">Workflow user</span></span></td>
    <td><span data-ttu-id="98c04-205">このワークフローの参加者であるユーザー</span><span class="sxs-lookup"><span data-stu-id="98c04-205">Users who are participants in this workflow</span></span></td>
    <td><ol>
    <li><span data-ttu-id="98c04-206">[<strong>受信者</strong>] タブの、[<strong>ワークフロー ユーザー</strong>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-206">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="98c04-207">[<strong>ワークフロー ユーザー</strong> の一覧の、[<strong>ワークフロー ユーザー</strong>] タブで、このワークフローの参加者を選択します。</span><span class="sxs-lookup"><span data-stu-id="98c04-207">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="98c04-208">ユーザー</span><span class="sxs-lookup"><span data-stu-id="98c04-208">User</span></span></td>
    <td><span data-ttu-id="98c04-209">特定の Finance and Operations ユーザー</span><span class="sxs-lookup"><span data-stu-id="98c04-209">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="98c04-210">[<strong>受信者</strong>] タブの、[<strong>ユーザー</strong>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-210">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="98c04-211">[<strong>ユーザー</strong>] タブの [<strong>利用可能なユーザー</strong>] 一覧には、すべての Dynamics 365 for Finance and Operations ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="98c04-211">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="98c04-212">通知の送信先のユーザーを選択して、それらのユーザーを [<strong>選択されたユーザー</strong>] リストに移動します。</span><span class="sxs-lookup"><span data-stu-id="98c04-212">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  <span data-ttu-id="98c04-213">ステップ 2 で選択したイベントごとに、ステップ 3～7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="98c04-213">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="98c04-214">ワークフローに加えた変更に関するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="98c04-214">Enter comments about the changes that you made to the workflow</span></span>
<span data-ttu-id="98c04-215">このワークフローに加えた変更に関するコメントを入力するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="98c04-215">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1.  <span data-ttu-id="98c04-216">左ウィンドウで、[**メモ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c04-216">In the left pane, click **Notes**.</span></span>
2.  <span data-ttu-id="98c04-217">[**ワークフローに関するコメントの入力**] フィールドにコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="98c04-217">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3.  <span data-ttu-id="98c04-218">入力したコメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="98c04-218">Review your comments.</span></span> <span data-ttu-id="98c04-219">追加したコメントは変更できません。</span><span class="sxs-lookup"><span data-stu-id="98c04-219">After you add comments, you can't modify them.</span></span>
4.  <span data-ttu-id="98c04-220">[**追加**] をクリックして、[**コメントの履歴**] 領域にコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="98c04-220">Click **Add** to add your comments to the **Comment history** area.</span></span>




