---
title: "ワークフローの作成"
description: "このトピックでは、ワークフローの作成方法を説明します。"
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, UnifiedOperations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 4d57e47fe7f38a43ecfdfbdd701d7e6a7d7800d6
ms.contentlocale: ja-jp
ms.lasthandoff: 07/18/2017

---

# <a name="create-a-workflow"></a><span data-ttu-id="d1aa5-103">ワークフローの作成</span><span class="sxs-lookup"><span data-stu-id="d1aa5-103">Create a workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d1aa5-104">このトピックでは、ワークフローの作成方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-104">This topics explains how to create a workflow.</span></span>

<a name="open-the-workflow-editor"></a><span data-ttu-id="d1aa5-105">ワークフロー エディターを開く</span><span class="sxs-lookup"><span data-stu-id="d1aa5-105">Open the workflow editor</span></span>
------------------------

<span data-ttu-id="d1aa5-106">使用している Microsoft Dynamics 365 for Finance and Operations モジュールで、作成できるワークフローのタイプが決まります。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-106">The Microsoft Dynamics 365 for Finance and Operations module that you're working in determines the types of workflow that you can create.</span></span> <span data-ttu-id="d1aa5-107">次の手順に従って、作成するワークフローのタイプを選択し、ワークフロー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-107">Follow these steps to select the type of workflow to create and open the workflow editor.</span></span>

1.  <span data-ttu-id="d1aa5-108">新しいワークフローを作成するモジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-108">Open the module that you want to create a new workflow for.</span></span> <span data-ttu-id="d1aa5-109">たとえば、購買要求ワークフローを作成するには、[**調達**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-109">For example, to create a workflow for purchase requisitions, click **Procurement and sourcing**.</span></span>
2.  <span data-ttu-id="d1aa5-110">[**設定**] &gt; [**\[モジュール名\] ワークフロー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-110">Click **Setup** &gt; **\[Module name\] workflows**.</span></span>
3.  <span data-ttu-id="d1aa5-111">アクション ウィンドウのリスト ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-111">On the list page that appears, on the Action Pane, click **New**.</span></span>
4.  <span data-ttu-id="d1aa5-112">[**ワークフローの作成**] ページで、作成するワークフローのタイプを選択し、[**ワークフローの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-112">On the **Create workflow** page, select the type of workflow to create, and then click **Create workflow**.</span></span> <span data-ttu-id="d1aa5-113">ワークフロー エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-113">The workflow editor appears.</span></span> <span data-ttu-id="d1aa5-114">ワークフローをデザインするには、次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-114">You can now use the following procedures to design the workflow.</span></span>

## <a name="drag-workflow-elements-onto-the-canvas"></a><span data-ttu-id="d1aa5-115">キャンバスへのワークフロー要素のドラッグ</span><span class="sxs-lookup"><span data-stu-id="d1aa5-115">Drag workflow elements onto the canvas</span></span>
<span data-ttu-id="d1aa5-116">ワークフロー エディターの [**ワークフロー要素**] 領域には、ワークフローに追加できる要素があります。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-116">The **Workflow elements** area of the workflow editor contains the elements that you can add to your workflow.</span></span> <span data-ttu-id="d1aa5-117">ワークフローに要素を追加するには、要素をキャンバスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-117">To add elements to the workflow, drag them onto the canvas.</span></span>

## <a name="connect-the-elements"></a><span data-ttu-id="d1aa5-118">要素の接続</span><span class="sxs-lookup"><span data-stu-id="d1aa5-118">Connect the elements</span></span>
<span data-ttu-id="d1aa5-119">あるワークフロー要素と別のワークフロー要素を接続するには、要素の上にポインターを移動して、接続ポイントが表示されるまで保持します。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-119">To connect one workflow element to another, hold the pointer over an element until connection points appear.</span></span> <span data-ttu-id="d1aa5-120">接続ポイントをクリックし、別の要素にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-120">Click a connection point, and drag it to another element.</span></span> <span data-ttu-id="d1aa5-121">すべての要素を接続してください。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-121">Be sure to connect all the elements.</span></span>

## <a name="configure-the-properties-of-the-workflow"></a><span data-ttu-id="d1aa5-122">ワークフローのプロパティのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d1aa5-122">Configure the properties of the workflow</span></span>
<span data-ttu-id="d1aa5-123">次の手順に従って、ワークフローのプロパティをコンフィギュレーションします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-123">Follow these steps to configure the properties of the workflow.</span></span>

1.  <span data-ttu-id="d1aa5-124">どのワークフロー要素も選択されていないようにするため、キャンバスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-124">Click the canvas to make sure that no workflow element is selected.</span></span>
2.  <span data-ttu-id="d1aa5-125">[**プロパティ**] をクリックして、ワークフローの [**プロパティ**] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-125">Click **Properties** to open the **Properties** page for the workflow.</span></span>
3.  <span data-ttu-id="d1aa5-126">[ワークフローのプロパティのコンフィギュレーション](configure-workflow-properties.md) トピックで示されている次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-126">Follow the procedures in the [Configure the properties of a workflow](configure-workflow-properties.md) topic.</span></span>

## <a name="configure-the-elements-of-the-workflow"></a><span data-ttu-id="d1aa5-127">ワークフローの要素のコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d1aa5-127">Configure the elements of the workflow</span></span>
<span data-ttu-id="d1aa5-128">キャンバスにドラッグした各要素をコンフィギュレーションします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-128">Configure each element that you dragged onto the canvas.</span></span> <span data-ttu-id="d1aa5-129">各ワークフロー要素をコンフィギュレーションする方法については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-129">For information about how to configure each workflow element, see the following topics:</span></span>

-   [<span data-ttu-id="d1aa5-130">手動タスクのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d1aa5-130">Configure a manual task</span></span>](configure-manual-task-workflow.md)
-   [<span data-ttu-id="d1aa5-131">自動化タスクのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d1aa5-131">Configure an automated task</span></span>](configure-automated-task-workflow.md)
-   [<span data-ttu-id="d1aa5-132">承認プロセスのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d1aa5-132">Configure an approval process</span></span>](configure-approval-process-workflow.md)
-   [<span data-ttu-id="d1aa5-133">承認ステップのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d1aa5-133">Configure an approval step</span></span>](configure-approval-step-workflow.md)
-   [<span data-ttu-id="d1aa5-134">手動決定のコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d1aa5-134">Configure a manual decision</span></span>](configure-manual-decision-workflow.md)
-   [<span data-ttu-id="d1aa5-135">条件付き意思決定のコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d1aa5-135">Configure a conditional decision</span></span>](configure-conditional-decision-workflow.md)
-   [<span data-ttu-id="d1aa5-136">並列活動のコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d1aa5-136">Configure a parallel activity</span></span>](configure-parallel-activity-workflow.md)
-   [<span data-ttu-id="d1aa5-137">並列分岐のコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d1aa5-137">Configure a parallel branch</span></span>](configure-parallel-branch-workflow.md)
-   [<span data-ttu-id="d1aa5-138">行項目ワークフローのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d1aa5-138">Configure a line-item workflow</span></span>](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a><span data-ttu-id="d1aa5-139">エラーまたは警告の解決</span><span class="sxs-lookup"><span data-stu-id="d1aa5-139">Resolve any errors or warnings</span></span>
<span data-ttu-id="d1aa5-140">ワークフロー エディターの下部にある [**エラーおよび警告**] ウィンドウには、ワークフローに対して生成されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-140">The **Errors and warnings** pane at the bottom of the workflow editor shows messages that have been generated for the workflow.</span></span> <span data-ttu-id="d1aa5-141">エラーまたは警告が発生した要素を特定するには、エラーまたは警告メッセージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-141">To find the element where an error or warning occurred, double-click the error or warning message.</span></span> <span data-ttu-id="d1aa5-142">ワークフローを有効にする前に、エラーと警告をすべて解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-142">You must resolve all errors and warnings before you can make the workflow active.</span></span>

## <a name="save-and-activate-the-workflow"></a><span data-ttu-id="d1aa5-143">ワークフローの保存と有効化</span><span class="sxs-lookup"><span data-stu-id="d1aa5-143">Save and activate the workflow</span></span>
<span data-ttu-id="d1aa5-144">ワークフローを保存して有効化する準備が整ったら、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-144">When you're ready to save and activate the workflow, follow these steps.</span></span>

1.  <span data-ttu-id="d1aa5-145">[**保存して終了**] をクリックして、ワークフロー エディターを閉じ、[**ワークフローの保存**] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-145">Click **Save and close** to close the workflow editor and open the **Save workflow** page.</span></span>
2.  <span data-ttu-id="d1aa5-146">ワークフローに加えた変更に関するコメントを入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-146">Enter comments about the changes that you've made to the workflow, and then click **OK**.</span></span>
3.  <span data-ttu-id="d1aa5-147">エラーと警告がすべて解決されると、[**ワークフローの有効化**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-147">If all errors and warnings have been resolved, the **Activate workflow** page appears.</span></span> <span data-ttu-id="d1aa5-148">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-148">Select one of the following options:</span></span>
    -   <span data-ttu-id="d1aa5-149">ワークフローのこのバージョンを有効にするには、[**新しいバージョンの有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-149">To activate this version of the workflow, click **Activate the new version**.</span></span> <span data-ttu-id="d1aa5-150">ワークフローが有効な場合は、ユーザーが、処理するドキュメントをワークフローに送信できます。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-150">When a workflow is active, users can submit documents to it for processing.</span></span>
    -   <span data-ttu-id="d1aa5-151">このバージョンを有効にしない場合は、[**新しいバージョンを有効にしない**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-151">If you don't want to activate this version, click **Do not activate the new version**.</span></span> <span data-ttu-id="d1aa5-152">ワークフローは後で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1aa5-152">You can activate the workflow later.</span></span>





