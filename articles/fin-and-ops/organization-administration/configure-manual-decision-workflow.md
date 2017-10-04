---
title: "ワークフローでの手動決定のコンフィギュレーション"
description: "このトピックでは、手動決定のプロパティをコンフィギュレーションする方法について説明します。"
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
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 078d7d5e822a5ffa74131838b249563201b54c7f
ms.contentlocale: ja-jp
ms.lasthandoff: 07/18/2017

---

# <a name="configure-a-manual-decision-in-a-workflow"></a><span data-ttu-id="e4c95-103">ワークフローでの手動決定のコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="e4c95-103">Configure a manual decision in a workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e4c95-104">このトピックでは、手動決定のプロパティをコンフィギュレーションする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-104">This topic explains how to configure the properties of a manual decision.</span></span>

<span data-ttu-id="e4c95-105">ワークフロー エディターで手動決定をコンフィギュレーションするには、手動決定を右クリックし、[**プロパティ**] をクリックして、[**プロパティ**] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-105">To configure a manual decision in the workflow editor, right-click the manual decision, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="e4c95-106">その後、手動決定のプロパティをコンフィギュレーションするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-106">Then use the following procedures to configure the properties of the manual decision.</span></span>

## <a name="name-the-decision"></a><span data-ttu-id="e4c95-107">判断名の設定</span><span class="sxs-lookup"><span data-stu-id="e4c95-107">Name the decision</span></span>
<span data-ttu-id="e4c95-108">手動決定の名前を入力するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-108">Follow these steps to enter a name for the manual decision.</span></span>

1.  <span data-ttu-id="e4c95-109">左ウィンドウで [**基本設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="e4c95-110">[**名前**] フィールドに、手動決定の一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-110">In the **Name** field, enter a unique name for the manual decision.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="e4c95-111">件名行と指示を入力する</span><span class="sxs-lookup"><span data-stu-id="e4c95-111">Enter a subject line and instructions</span></span>
<span data-ttu-id="e4c95-112">この手動決定に割り当てられるユーザーに対して件名行と指示を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4c95-112">You must provide a subject line and instructions to users who are assigned to the manual decision.</span></span> <span data-ttu-id="e4c95-113">たとえば、購買要求の決定をコンフィギュレーションする場合には、その決定に割り当てられるユーザーに対して、[**購買要求**] ページの件名行と指示が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-113">For example, if you're configuring a decision for purchase requisitions, the user who is assigned to the decision sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="e4c95-114">件名行はページのメッセージ バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="e4c95-115">ユーザーは、その後、メッセージ バーのアイコンをクリックして、指示を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="e4c95-116">次に手順に従って、件名行と指示を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-116">Follow these steps to enter a subject line and instructions.</span></span>

1.  <span data-ttu-id="e4c95-117">左ウィンドウで [**基本設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-117">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="e4c95-118">[**作業項目の件名**] フィールドの [**指示**] タブで、件名行を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-118">On the **Instructions** tab, in the **Work item subject** field, enter the subject line.</span></span>
3.  <span data-ttu-id="e4c95-119">件名行をカスタマイズするには、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="e4c95-120">プレースホルダーは、件名行がユーザーに表示されるときに、適切なデータに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="e4c95-121">次の手順に従って、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-121">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="e4c95-122">テキスト ボックス内で、プレースホルダを表示する場所をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-122">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="e4c95-123">[**プレースホルダーの挿入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-123">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="e4c95-124">表示されるリストで、挿入するプレースホルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-124">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="e4c95-125">[**挿入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-125">Click **Insert**.</span></span>

4.  <span data-ttu-id="e4c95-126">件名行の翻訳を追加するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-126">To add translations of the subject line, follow these steps:</span></span>
    1.  <span data-ttu-id="e4c95-127">[**翻訳**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-127">Click **Translations**.</span></span>
    2.  <span data-ttu-id="e4c95-128">表示されるページで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-128">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="e4c95-129">表示される一覧で、テキストを入力する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="e4c95-130">[**翻訳テキスト**] フィールドで、テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-130">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="e4c95-131">テキストをカスタマイズする場合は、ステップ 3 の説明に従い、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6.  <span data-ttu-id="e4c95-132">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-132">Click **Close**.</span></span>

5.  <span data-ttu-id="e4c95-133">[**作業項目の指示**] フィールドで、指示を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-133">In the **Work item instructions** field, enter the instructions.</span></span>
6.  <span data-ttu-id="e4c95-134">指示を個人向けのものにするには、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="e4c95-135">プレースホルダーは、指示行がユーザーに表示されるときに、適切なデータに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="e4c95-136">次の手順に従って、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-136">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="e4c95-137">テキスト ボックス内で、プレースホルダを表示する場所をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-137">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="e4c95-138">[**プレースホルダーの挿入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-138">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="e4c95-139">表示されるリストで、挿入するプレースホルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-139">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="e4c95-140">[**挿入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-140">Click **Insert**.</span></span>

7.  <span data-ttu-id="e4c95-141">指示行の翻訳を追加するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-141">To add translations of the instructions, follow these steps:</span></span>
    1.  <span data-ttu-id="e4c95-142">[**翻訳**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-142">Click **Translations**.</span></span>
    2.  <span data-ttu-id="e4c95-143">表示されるページで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-143">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="e4c95-144">表示される一覧で、テキストを入力する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="e4c95-145">[**翻訳テキスト**] フィールドで、テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-145">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="e4c95-146">テキストをカスタマイズする場合は、ステップ 6 の説明に従い、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6.  <span data-ttu-id="e4c95-147">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-147">Click **Close**.</span></span>

## <a name="specify-the-possible-outcomes-of-a-decision"></a><span data-ttu-id="e4c95-148">決定の可能な結果を指定する</span><span class="sxs-lookup"><span data-stu-id="e4c95-148">Specify the possible outcomes of a decision</span></span>
<span data-ttu-id="e4c95-149">通常、ドキュメントが意思決定者に割り当てられると、その意志決定者に質問が行われます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-149">Typically, when a document is assigned to a decision maker, the decision maker is asked a question.</span></span> <span data-ttu-id="e4c95-150">この質問に対する回答は、通常 [**はい**] または [**いいえ**] または [**True**] または [**False**] です。</span><span class="sxs-lookup"><span data-stu-id="e4c95-150">The answer to this question is usually **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="e4c95-151">手動決定の結果の候補を指定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-151">Follow these steps to specify the possible outcomes of the manual decision.</span></span>

1.  <span data-ttu-id="e4c95-152">左ウィンドウで [**基本設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-152">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="e4c95-153">[**結果 1**] フィールドの [**結果**] タブに、結果の名前またはオプションを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-153">On the **Outcomes** tab, in the **Outcome 1** field, enter the name of the outcome, or the option.</span></span>
3.  <span data-ttu-id="e4c95-154">結果の翻訳を追加するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-154">To add translations of the outcome, follow these steps:</span></span>
    1.  <span data-ttu-id="e4c95-155">[**翻訳**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-155">Click **Translations**.</span></span>
    2.  <span data-ttu-id="e4c95-156">表示されるページで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-156">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="e4c95-157">表示される一覧で、テキストを入力する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-157">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="e4c95-158">[**翻訳テキスト**] フィールドで、テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-158">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="e4c95-159">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-159">Click **Close**.</span></span>

4.  <span data-ttu-id="e4c95-160">[**結果 2**] フィールドに、結果の名前またはオプションを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-160">In the **Outcome 2** field, enter the name of the outcome, or the option.</span></span>
5.  <span data-ttu-id="e4c95-161">結果の翻訳を追加するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-161">To add translations of the outcome, follow these steps:</span></span>
    1.  <span data-ttu-id="e4c95-162">[**翻訳**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-162">Click **Translations**.</span></span>
    2.  <span data-ttu-id="e4c95-163">表示されるページで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-163">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="e4c95-164">表示される一覧で、テキストを入力する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-164">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="e4c95-165">[**翻訳テキスト**] フィールドで、テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-165">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="e4c95-166">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-166">Click **Close**.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="e4c95-167">いつ通知を送信するかを指定する</span><span class="sxs-lookup"><span data-stu-id="e4c95-167">Specify when notifications are sent</span></span>
<span data-ttu-id="e4c95-168">決定の実行、委任、またはエスカレーションが行われたときに、ユーザーに通知を送信できます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-168">You can send notifications to people when a decision has been made, delegated, or escalated.</span></span> <span data-ttu-id="e4c95-169">通知の送信条件と、通知の送信先のユーザーを指定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-169">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1.  <span data-ttu-id="e4c95-170">左ウィンドウで、[**通知**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-170">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="e4c95-171">通知を送信するイベントの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-171">Select the check box next to the events that notifications should be sent for:</span></span>
    -   <span data-ttu-id="e4c95-172">**\[選択 1\]** – 割り当てられたユーザーは **\[選択 1\]** を選択しました。</span><span class="sxs-lookup"><span data-stu-id="e4c95-172">**\[Choice 1\]** – The assigned user has selected **\[Choice 1\]**.</span></span>
    -   <span data-ttu-id="e4c95-173">**\[選択 2\]** – 割り当てられたユーザーは **\[選択 2\]** を選択しました。</span><span class="sxs-lookup"><span data-stu-id="e4c95-173">**\[Choice 2\]** – The assigned user has selected **\[Choice 2\]**.</span></span>
    -   <span data-ttu-id="e4c95-174">[**委任**] – 割り当てられたユーザーは別のユーザーに決定を割り当てました。</span><span class="sxs-lookup"><span data-stu-id="e4c95-174">**Delegate** – The assigned user has assigned the decision to another user.</span></span>
    -   <span data-ttu-id="e4c95-175">[**エスカレート**] – 割り当てられたユーザーは割り当てられた時間内に決定を行いませんでした。</span><span class="sxs-lookup"><span data-stu-id="e4c95-175">**Escalate** – The assigned user hasn't made the decision in the allotted time.</span></span>

3.  <span data-ttu-id="e4c95-176">ステップ 2 で選択したイベントの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-176">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="e4c95-177">[**通知テキスト**] タブのテキスト ボックス内で、通知のテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-177">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5.  <span data-ttu-id="e4c95-178">通知を個人向けのものにするには、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-178">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="e4c95-179">プレースホルダーは、通知がユーザーに表示されるときに、適切なデータに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-179">Placeholders are replaced with appropriate data when the notification is show to users.</span></span> <span data-ttu-id="e4c95-180">次の手順に従って、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-180">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="e4c95-181">テキスト ボックス内で、プレースホルダを表示する場所をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-181">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="e4c95-182">[**プレースホルダーの挿入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-182">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="e4c95-183">表示されるリストで、挿入するプレースホルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-183">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="e4c95-184">[**挿入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-184">Click **Insert**.</span></span>

6.  <span data-ttu-id="e4c95-185">通知の翻訳を追加するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-185">To add translations of the notification, follow these steps:</span></span>
    1.  <span data-ttu-id="e4c95-186">[**翻訳**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-186">Click **Translations**.</span></span>
    2.  <span data-ttu-id="e4c95-187">表示されるページで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-187">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="e4c95-188">表示される一覧で、テキストを入力する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-188">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="e4c95-189">[**翻訳テキスト**] フィールドで、テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-189">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="e4c95-190">テキストをカスタマイズする場合は、ステップ 5 の説明に従い、プレースホルダーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-190">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6.  <span data-ttu-id="e4c95-191">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-191">Click **Close**.</span></span>

7.  <span data-ttu-id="e4c95-192">[**受信者**] タブで、通知の送信先ユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-192">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="e4c95-193">次の表のいずれかのオプションを選択し、オプションの追加ステップを実行してから、ステップ 8 に進みます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-193">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="e4c95-194">オプション</span><span class="sxs-lookup"><span data-stu-id="e4c95-194">Option</span></span></th>
    <th><span data-ttu-id="e4c95-195">通知の受信者</span><span class="sxs-lookup"><span data-stu-id="e4c95-195">Notification recipients</span></span></th>
    <th><span data-ttu-id="e4c95-196">追加手順</span><span class="sxs-lookup"><span data-stu-id="e4c95-196">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="e4c95-197">参加者</span><span class="sxs-lookup"><span data-stu-id="e4c95-197">Participant</span></span></td>
    <td><span data-ttu-id="e4c95-198">特定のグループまたはロールに割り当てられたユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-198">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="e4c95-199">[<strong>参加者のタイプ</strong>] 一覧の [<strong>ロール ベース</strong>] タブの、[<strong>参加者</strong>] を選択したのち、通知の送信先のグループまたはロールのタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-199">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="e4c95-200">[<strong>参加者</strong>] の一覧で、通知の送信先のグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-200">In the <strong>Participant</strong> list, select the group or to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="e4c95-201">ワークフロー ユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-201">Workflow user</span></span></td>
    <td><span data-ttu-id="e4c95-202">現在のワークフロー内のユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-202">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="e4c95-203">[<strong>ワークフロー ユーザー</strong>] 一覧の、[<strong>ワークフロー ユーザー</strong>] タブの、[<strong>ワークフロー ユーザー</strong>] を選択したのち、ワークフローに参加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-203">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="e4c95-204">ユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-204">User</span></span></td>
    <td><span data-ttu-id="e4c95-205">特定の Microsoft Dynamics 365 for Finance and Operations ユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-205">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="e4c95-206">[<strong>ユーザー</strong>] を選択したのち、[<strong>ユーザー</strong>] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-206">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="e4c95-207">[<strong>利用可能なユーザー</strong>] 一覧には、すべての Finance and Operations ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-207">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="e4c95-208">通知の送信先のユーザーを選択して、それらのユーザーを [<strong>選択されたユーザー</strong>] リストに移動します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-208">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  <span data-ttu-id="e4c95-209">ステップ 2 で選択したイベントごとに、ステップ 3～7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-209">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="assign-a-decision"></a><span data-ttu-id="e4c95-210">決定の割り当て</span><span class="sxs-lookup"><span data-stu-id="e4c95-210">Assign a decision</span></span>
<span data-ttu-id="e4c95-211">手動決定の割り当て先のユーザーを指定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-211">Follow these steps to specify who a manual decision should be assigned to.</span></span>

1.  <span data-ttu-id="e4c95-212">左ウィンドウで、[**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-212">In the left pane, click **Assignment**.</span></span>
2.  <span data-ttu-id="e4c95-213">[**割り当てタイプ**] タブで、次の表のいずれかのオプションを選択し、オプションの追加手順を実行してから、手順 3 に進みます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-213">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="e4c95-214">オプション</span><span class="sxs-lookup"><span data-stu-id="e4c95-214">Option</span></span></th>
    <th><span data-ttu-id="e4c95-215">決定の割り当て先のユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-215">Users that the decision is assigned to</span></span></th>
    <th><span data-ttu-id="e4c95-216">追加手順</span><span class="sxs-lookup"><span data-stu-id="e4c95-216">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="e4c95-217">参加者</span><span class="sxs-lookup"><span data-stu-id="e4c95-217">Participant</span></span></td>
    <td><span data-ttu-id="e4c95-218">特定のグループまたはロールに割り当てられたユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-218">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="e4c95-219">[<strong>参加者のタイプ</strong>] 一覧の [<strong>ロール ベース</strong>] タブの、[<strong>参加者</strong>] を選択した後、決定の割り当て先のグループまたはロールのタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-219">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the decision to.</span></span></li>
    <li><span data-ttu-id="e4c95-220">[<strong>参加者</strong>] の一覧で、決定の割り当て先のグループまたはロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-220">In the <strong>Participant</strong> list, select the group or role to assign the decision to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="e4c95-221">階層</span><span class="sxs-lookup"><span data-stu-id="e4c95-221">Hierarchy</span></span></td>
    <td><span data-ttu-id="e4c95-222">特定の組織階層内のユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-222">Users in a specific organizational hierarchy</span></span></td>
    <td><ol>
    <li><span data-ttu-id="e4c95-223">[<strong>階層タイプ</strong>] 一覧の [<strong>階層選択</strong>] タブの、[<strong>階層</strong>] を選択したのち、決定の割り当て先の階層タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-223">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the decision to.</span></span></li>
    <li><span data-ttu-id="e4c95-224">システムは、一定範囲のユーザー名を階層から取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4c95-224">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="e4c95-225">これらの名前は、決定を割り当てることができるユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-225">These names represent users that the decision can be assigned to.</span></span> <span data-ttu-id="e4c95-226">システムで取得するユーザー名の範囲について、その開始点と終了点を指定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-226">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="e4c95-227">開始点を指定するには、[<strong>開始</strong>] 一覧から人物を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-227">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="e4c95-228">終了点を指定するには、[<strong>条件の追加</strong>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-228">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="e4c95-229">次に、階層のどこで名前の取得を止めるかを示す条件を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-229">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="e4c95-230">[<strong>階層オプション</strong>] で、決定を割り当てる範囲内のユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-230">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="e4c95-231">[<strong>取得したすべてのユーザーに割り当てる</strong>] – 決定は範囲内のすべてのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-231"><strong>Assign to all users retrieved</strong> – The decision is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="e4c95-232">[<strong>取得した最後のユーザーのみに割り当てる</strong>] – 決定は、範囲内の最後のユーザーのみに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-232"><strong>Assign only to last user retrieved</strong> – The decision is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="e4c95-233">[<strong>次の条件のユーザーを除外します</strong>] – 決定は、特定の条件に該当する範囲内のどのユーザーにも割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="e4c95-233"><strong>Exclude users with the following condition</strong> – The decision isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="e4c95-234">条件を指定するには、[<strong>条件の追加</strong>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-234">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="e4c95-235">ワークフロー ユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-235">Workflow user</span></span></td>
    <td><span data-ttu-id="e4c95-236">現在のワークフロー内のユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-236">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="e4c95-237">[<strong>ワークフロー ユーザー</strong>] 一覧の、[<strong>ワークフロー ユーザー</strong>] タブの、[<strong>ワークフロー ユーザー</strong>] を選択したのち、ワークフローに参加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-237">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="e4c95-238">ユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-238">User</span></span></td>
    <td><span data-ttu-id="e4c95-239">特定の Finance and Operations ユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-239">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="e4c95-240">[<strong>ユーザー</strong>] を選択したのち、[<strong>ユーザー</strong>] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-240">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="e4c95-241">[<strong>利用可能なユーザー</strong>] 一覧には、すべての Finance and Operations ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-241">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="e4c95-242">決定を割り当てるユーザーを選択し、そのユーザーを [<strong>選択されたユーザー</strong>] リストに移動します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-242">Select the users to assign the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="e4c95-243">キュー</span><span class="sxs-lookup"><span data-stu-id="e4c95-243">Queue</span></span></td>
    <td><span data-ttu-id="e4c95-244">作業項目キュー</span><span class="sxs-lookup"><span data-stu-id="e4c95-244">A work item queue</span></span></td>
    <td><ol>
    <li><span data-ttu-id="e4c95-245">[<strong>キュー</strong>] を選択した後、[<strong>キュー ベース</strong>] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-245">After you select <strong>Queue</strong>, click the <strong>Queue based</strong> tab.</span></span></li>
    <li><span data-ttu-id="e4c95-246">決定を特定のキューに割り当てるには、次の手順に従います。:</span><span class="sxs-lookup"><span data-stu-id="e4c95-246">To assign the decision to a specific queue, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="e4c95-247">[<strong>キュー タイプ</strong>] 一覧で、[<strong>作業項目キュー</strong>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-247">In the <strong>Queue type</strong> list, select <strong>Work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="e4c95-248">[<strong>キュー名</strong>] の一覧でキューを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-248">In the <strong>Queue name</strong> list, select the queue.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="e4c95-249">決定を割り当てるキューを特定の条件で決める場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-249">If a specific condition should determine which queue the decision is assigned to, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="e4c95-250">[<strong>キュー タイプ</strong>] 一覧で、[<strong>条件付き作業項目キュー</strong>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-250">In the <strong>Queue type</strong> list, select <strong>Conditional work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="e4c95-251">[<strong>キュー名</strong>] の一覧で、[<strong>条件付きキュー</strong>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-251">In the <strong>Queue name</strong> list, select <strong>Conditional queue</strong>.</span></span></li>
    </ol></li>
    </ol><span data-ttu-id="e4c95-252">
    <strong>注:</strong> このオプションは、ケース管理などのいくつかのワークフローのみで使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-252">
    <strong>Note:</strong> This option is used for only a few workflows, such as Case management.</span></span></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="e4c95-253">[**期限**] タブの、[**期間**] フィールドで、ユーザーが決定をしなければならない期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-253">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="e4c95-254">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-254">Select one of the following options:</span></span>
    -   <span data-ttu-id="e4c95-255">[**時間数**] – ユーザーが決定を行わなければならない期限を時間数で入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-255">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="e4c95-256">続いて、組織で使用しているカレンダーを選択し、組織の週間労働時間に関する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-256">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="e4c95-257">[**日数**] – ユーザーが決定を行わなければならない期限を日数で入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-257">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="e4c95-258">続いて、組織で使用しているカレンダーを選択し、組織の週間労働時間に関する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-258">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="e4c95-259">[**週数**] – ユーザーが決定を行わなければならない期限を週数で入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-259">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    -   <span data-ttu-id="e4c95-260">[**月**] – ユーザーが決定を行わなければならない期限を曜日および週で選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-260">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="e4c95-261">たとえば、当月の第 3 週の金曜日までに決定を行うよう設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-261">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="e4c95-262">[**月**] – ユーザーが決定を行わなければならない期限を曜日、週、および月で選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-262">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="e4c95-263">たとえば、12 月の第 3 週の金曜日までに決定を行うよう設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-263">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

    <span data-ttu-id="e4c95-264">割り当てられている時間内にユーザーが決定を行わなかった場合、その決定は期限超過になります。</span><span class="sxs-lookup"><span data-stu-id="e4c95-264">If the user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="e4c95-265">期限超過の決定は、このページの [**エスカレーション**] 領域で選択したオプションに基づいて、エスカレートされます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-265">A decision that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-a-decision-is-overdue"></a><span data-ttu-id="e4c95-266">決定が期限超過の場合の処置を指定する</span><span class="sxs-lookup"><span data-stu-id="e4c95-266">Specify what happens when a decision is overdue</span></span>
<span data-ttu-id="e4c95-267">割り当てられている時間内にユーザーが決定を行わなかった場合、その決定は期限超過になります。</span><span class="sxs-lookup"><span data-stu-id="e4c95-267">If a user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="e4c95-268">期限超過した決定は、別のユーザーにエスカレートする (自動的に割り当てる) ことができます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-268">A decision that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="e4c95-269">期限超過した決定をエスカレートするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-269">Follow these steps to escalate the decision if it's overdue.</span></span>

1.  <span data-ttu-id="e4c95-270">左ウィンドウで、[**エスカレーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-270">In the left pane, click **Escalation**.</span></span>
2.  <span data-ttu-id="e4c95-271">[**エスカレーション パスを使用**] チェック ボックスをオンにし、エスカレーション パスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-271">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="e4c95-272">決定は、エスカレーション パスにリストされるユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-272">The system automatically assigns the decision to the users who are listed in the escalation path.</span></span> <span data-ttu-id="e4c95-273">たとえば、次の表に、エスカレーション パスを示します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-273">For example, the following table represents an escalation path.</span></span>
    | <span data-ttu-id="e4c95-274">順番</span><span class="sxs-lookup"><span data-stu-id="e4c95-274">Sequence</span></span> | <span data-ttu-id="e4c95-275">エスカレーション パス</span><span class="sxs-lookup"><span data-stu-id="e4c95-275">Escalation path</span></span>            |
    |----------|----------------------------|
    | <span data-ttu-id="e4c95-276">1</span><span class="sxs-lookup"><span data-stu-id="e4c95-276">1</span></span>        | <span data-ttu-id="e4c95-277">割り当て先: 奈緒美</span><span class="sxs-lookup"><span data-stu-id="e4c95-277">Assign to: Donna</span></span>           |
    | <span data-ttu-id="e4c95-278">2</span><span class="sxs-lookup"><span data-stu-id="e4c95-278">2</span></span>        | <span data-ttu-id="e4c95-279">割り当て先: 悦子</span><span class="sxs-lookup"><span data-stu-id="e4c95-279">Assign to: Erin</span></span>            |
    | <span data-ttu-id="e4c95-280">3</span><span class="sxs-lookup"><span data-stu-id="e4c95-280">3</span></span>        | <span data-ttu-id="e4c95-281">最終アクション: \[選択 1\]</span><span class="sxs-lookup"><span data-stu-id="e4c95-281">Final action: \[Choice 1\]</span></span> |

    <span data-ttu-id="e4c95-282">この例では、奈緒美に、期限超過の決定が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-282">In this example, the system assigns the overdue decision to Donna.</span></span> <span data-ttu-id="e4c95-283">割り当てられた時間内に奈緒美が決定を行わない場合は、悦子に決定が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-283">If Donna doesn't make the decision in the allotted time, the system assigns the decision to Erin.</span></span> <span data-ttu-id="e4c95-284">割り当てられた時間内に悦子が決定を行わない場合は、**\[選択 1\]** が決定として選択されます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-284">If Erin doesn't make the decision in the allotted time, the system selects **\[Choice 1\]** as the decision.</span></span>
3.  <span data-ttu-id="e4c95-285">エスカレーション パスにユーザーを追加するには、[**エスカレーションの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-285">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="e4c95-286">次の表のいずれかのオプションを選択し、そのオプションの追加ステップを実行してから、ステップ 4 に進みます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-286">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="e4c95-287">オプション</span><span class="sxs-lookup"><span data-stu-id="e4c95-287">Option</span></span></th>
    <th><span data-ttu-id="e4c95-288">決定のエスカレート先のユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-288">Users that the decision is escalated to</span></span></th>
    <th><span data-ttu-id="e4c95-289">追加手順</span><span class="sxs-lookup"><span data-stu-id="e4c95-289">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="e4c95-290">階層</span><span class="sxs-lookup"><span data-stu-id="e4c95-290">Hierarchy</span></span></td>
    <td><span data-ttu-id="e4c95-291">特定の組織階層内のユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-291">Users in a specific organizational hierarchy</span></span></td>
    <td><ol>
    <li><span data-ttu-id="e4c95-292">[<strong>階層タイプ</strong>] 一覧の [<strong>階層選択</strong>] タブの、[<strong>階層</strong>] を選択したのち、決定をエスカレートする先の階層グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-292">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the decision to.</span></span></li>
    <li><span data-ttu-id="e4c95-293">システムは、一定範囲のユーザー名を階層から取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4c95-293">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="e4c95-294">これらの名前は、決定のエスカレート先にすることできるユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-294">These names represent users that the decision can be escalated to.</span></span> <span data-ttu-id="e4c95-295">システムで取得するユーザー名の範囲について、その開始点と終了点を指定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-295">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="e4c95-296">開始点を指定するには、[<strong>開始</strong>] 一覧から人物を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-296">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="e4c95-297">終了点を指定するには、[<strong>条件の追加</strong>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-297">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="e4c95-298">次に、階層のどこで名前の取得を止めるかを示す条件を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-298">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="e4c95-299">[<strong>階層オプション</strong>] で、決定をエスカレートできる範囲内のユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-299">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="e4c95-300">[<strong>取得したすべてのユーザーに割り当てる</strong>] – 決定は範囲内のすべてのユーザーにエスカレートされます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-300"><strong>Assign to all users retrieved</strong> – The decision is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="e4c95-301">[<strong>取得した最後のユーザーのみに割り当てる</strong>] – 決定は、範囲内の最後のユーザーのみにエスカレートされます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-301"><strong>Assign only to last user retrieved</strong> – The decision is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="e4c95-302">[<strong>次の条件のユーザーを除外します</strong>] – 決定は、特定の条件に該当する範囲内のどのユーザーにもエスカレートされません。</span><span class="sxs-lookup"><span data-stu-id="e4c95-302"><strong>Exclude users with the following condition:</strong> – The decision isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="e4c95-303">条件を指定するには、[<strong>条件の追加</strong>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-303">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="e4c95-304">ワークフロー ユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-304">Workflow user</span></span></td>
    <td><span data-ttu-id="e4c95-305">現在のワークフロー内のユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-305">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="e4c95-306">[<strong>ワークフロー ユーザー</strong>] 一覧の、[<strong>ワークフロー ユーザー</strong>] タブの、[<strong>ワークフロー ユーザー</strong>] を選択したのち、ワークフローに参加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-306">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="e4c95-307">ユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-307">User</span></span></td>
    <td><span data-ttu-id="e4c95-308">特定の Finance and Operations ユーザー</span><span class="sxs-lookup"><span data-stu-id="e4c95-308">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="e4c95-309">[<strong>ユーザー</strong>] を選択したのち、[<strong>ユーザー</strong>] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-309">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="e4c95-310">[<strong>利用可能なユーザー</strong>] 一覧には、すべての Finance and Operations ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-310">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="e4c95-311">決定をエスカレートするユーザーを選択し、そのユーザーを [<strong>選択されたユーザー</strong>] リストに移動します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-311">Select the users to escalate the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

4.  <span data-ttu-id="e4c95-312">[**期限**] タブの、[**期間**] フィールドで、ユーザーが決定をしなければならない期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-312">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="e4c95-313">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-313">Select one of the following options:</span></span>
    -   <span data-ttu-id="e4c95-314">[**時間数**] – ユーザーが決定を行わなければならない期限を時間数で入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-314">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="e4c95-315">続いて、組織で使用しているカレンダーを選択し、組織の週間労働時間に関する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-315">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="e4c95-316">[**日数**] – ユーザーが決定を行わなければならない期限を日数で入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-316">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="e4c95-317">続いて、組織で使用しているカレンダーを選択し、組織の週間労働時間に関する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-317">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="e4c95-318">[**週数**] – ユーザーが決定を行わなければならない期限を週数で入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-318">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    -   <span data-ttu-id="e4c95-319">[**月**] – ユーザーが決定を行わなければならない期限を曜日および週で選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-319">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="e4c95-320">たとえば、当月の第 3 週の金曜日までに決定を行うよう設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-320">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="e4c95-321">[**月**] – ユーザーが決定を行わなければならない期限を曜日、週、および月で選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-321">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="e4c95-322">たとえば、12 月の第 3 週の金曜日までに決定を行うよう設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-322">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

5.  <span data-ttu-id="e4c95-323">エスカレーション パスに追加するユーザーごとに、ステップ 3～4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-323">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="e4c95-324">ユーザーの順序は、変更できます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-324">You can change the order of the users.</span></span>
6.  <span data-ttu-id="e4c95-325">エスカレーション パスに含まれるユーザーが、割り当てられた時間内に決定を行わない場合、システムによって決定が行われます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-325">If the users in the escalation path don't make the decision in the allotted time, the system makes the decision.</span></span> <span data-ttu-id="e4c95-326">システムによるオプションを指定するには、[**アクション**] 行を選択し、[**アクションの終了**] タブでオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-326">To specify the option that the system selects, select the **Action** row, and then, on the **End action** tab, select an option.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="e4c95-327">期限の設定</span><span class="sxs-lookup"><span data-stu-id="e4c95-327">Set a time limit</span></span>
<span data-ttu-id="e4c95-328">特定の時間内に決定を行わなければならないようにするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c95-328">Follow these steps if the decision must be made in a specific time.</span></span> <span data-ttu-id="e4c95-329">**注:** この手順で選択するオプションは、このページの [**割り当て**]、および [**エスカレーション**] 領域で選択されたオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-329">**Note:** The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1.  <span data-ttu-id="e4c95-330">左ウィンドウで [**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-330">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="e4c95-331">[**ワークフロー要素の期限の設定**] を選択し、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e4c95-331">Select the **Set a time limit for the workflow element** check box.</span></span>
3.  <span data-ttu-id="e4c95-332">[**期間**] フィールドで、決定を行う必要がある期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-332">In the **Duration** field, specify when the decision must be made.</span></span> <span data-ttu-id="e4c95-333">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-333">Select one of the following options:</span></span>
    -   <span data-ttu-id="e4c95-334">[**時間数**] – 時間数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-334">**Hours** – Enter the number of hours.</span></span> <span data-ttu-id="e4c95-335">続いて、組織で使用しているカレンダーを選択し、組織の週間労働時間に関する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-335">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="e4c95-336">[**日数**] – 日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-336">**Days** – Enter the number of days.</span></span> <span data-ttu-id="e4c95-337">続いて、組織で使用しているカレンダーを選択し、組織の週間労働時間に関する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-337">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="e4c95-338">[**週数**] – 週数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-338">**Weeks** – Enter the number of weeks.</span></span>
    -   <span data-ttu-id="e4c95-339">[**月**] – 決定の実行期限を曜日、週で選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-339">**Months** – Select the day and week that the decision must be made by.</span></span> <span data-ttu-id="e4c95-340">たとえば、当月の第 3 週の金曜日までに決定を実行する必要があるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-340">For example, you might want the decision to be made by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="e4c95-341">[**年**] – 決定の実行期限を曜日、週、月で選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-341">**Years** – Select the day, week, and month that the decision must be made by.</span></span> <span data-ttu-id="e4c95-342">たとえば、12 月の第 3 週の金曜日までに決定を実行する必要があるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-342">For example, you might want the decision to be made by Friday of the third week of December.</span></span>

4.  <span data-ttu-id="e4c95-343">時間制限を超過した場合は、システムによって決定が行われます。</span><span class="sxs-lookup"><span data-stu-id="e4c95-343">If the time limit is exceeded, the system makes the decision.</span></span> <span data-ttu-id="e4c95-344">[**アクション**] の一覧から、システムで選択するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c95-344">In the **Action** list, select the option that the system should select.</span></span>




