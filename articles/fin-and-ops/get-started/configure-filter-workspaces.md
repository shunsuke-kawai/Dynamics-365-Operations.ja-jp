---
title: "ワークスペースのフィルター処理およびコンフィギュレーション"
description: "この記事は、ワークスペースを構成してフィルター処理する方法の概要について説明します。"
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 17491
ms.assetid: 541e6012-4680-4684-8494-e9b5ca4684ee
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 754cd81a4550318de7003d847fafb2bcc7414b32
ms.contentlocale: ja-jp
ms.lasthandoff: 07/18/2017

---

# <a name="configure-and-filter-workspaces"></a><span data-ttu-id="f9103-103">ワークスペースのフィルター処理およびコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="f9103-103">Configure and filter workspaces</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f9103-104">この記事は、ワークスペースを構成してフィルター処理する方法の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9103-104">This article provides an overview about how to configure and filter workspaces.</span></span>

<a name="configuring-a-workspace"></a><span data-ttu-id="f9103-105">ワークスペースのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="f9103-105">Configuring a workspace</span></span>
-----------------------

<span data-ttu-id="f9103-106">ワークスペース全体に適用される設定を変更することにより、ワークスペースの外観と動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f9103-106">You can change the appearance and behavior of some workspaces by updating settings that apply to the whole workspace.</span></span> <span data-ttu-id="f9103-107">ワークスペースが構成できる場合、[アクション] ウィンドウには設定を変更するボタンがあり、これをクリックするように指示が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9103-107">When a workspace can be configured, the Action Pane includes a button that instructs you to click it to make configuration changes.</span></span> <span data-ttu-id="f9103-108">たとえば次の図では、**自分のワークスペースのコンフィギュレーション**というボタンが表示されています。</span><span class="sxs-lookup"><span data-stu-id="f9103-108">For example, in the following illustration, the button is named **Configure my workspace**.</span></span> 

<span data-ttu-id="f9103-109">[![ワークスペースの構成とフィルター](./media/configure-and-filter-workspaces.png)](./media/configure-and-filter-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="f9103-109">[![configure-and-filter-workspaces](./media/configure-and-filter-workspaces.png)](./media/configure-and-filter-workspaces.png)</span></span>   

<span data-ttu-id="f9103-110">ボタンをクリックすると、ワークスペースの定義済設定を変更できるダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9103-110">When you click the button, a dialog appears, where you can modify the predefined settings for the workspace.</span></span> <span data-ttu-id="f9103-111">このダイアログに表示される特定の設定は、各ワークスペースによって異なり、ワークスペースで使用できる特定のコントロールや業務データによっても異なります。</span><span class="sxs-lookup"><span data-stu-id="f9103-111">The specific settings that you see in this dialog vary by workspace, and depend on the specific controls and business data that are available in the workspace.</span></span> 

<span data-ttu-id="f9103-112">[![マイ ワークスペースの構成](./media/configure-my-workspace.png)](./media/configure-my-workspace.png)</span><span class="sxs-lookup"><span data-stu-id="f9103-112">[![configure-my-workspace](./media/configure-my-workspace.png)](./media/configure-my-workspace.png)</span></span>

## <a name="filtering-a-workspace"></a><span data-ttu-id="f9103-113">ワークスペースのフィルタ処理</span><span class="sxs-lookup"><span data-stu-id="f9103-113">Filtering a workspace</span></span>
<span data-ttu-id="f9103-114">多くのワークスペースでは、表示される内容をフィルタ処理することができます。</span><span class="sxs-lookup"><span data-stu-id="f9103-114">Many workspaces let you filter the content that appears in them.</span></span> <span data-ttu-id="f9103-115">使用できるコントロールにより、ワークスペースのすべて内容や、ワークスペースの特定のセクションにある内容をフィルタ処理できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9103-115">The controls that are available might let you filter all the content in the workspace or only the content in a specific section of the workspace.</span></span> <span data-ttu-id="f9103-116">ワークスペースのフィルターは、ルックアップ、コンボ ボックス、自由書式のテキスト フィールド、または他のコントロール タイプである場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9103-116">The filters on workspaces can be lookups, combo boxes, free-form text fields, or other types of controls.</span></span> <span data-ttu-id="f9103-117">ただし、次のセクションで説明するように、それぞれのフィルタのタイプは同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="f9103-117">However, every type of filter has the same effects, as described in the following sections.</span></span>

### <a name="workspace-wide-filters"></a><span data-ttu-id="f9103-118">ワークスペース全体のフィルター</span><span class="sxs-lookup"><span data-stu-id="f9103-118">Workspace-wide filters</span></span>

<span data-ttu-id="f9103-119">ワークスペース全体のフィルターを使用すると、ワークスペース全体をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f9103-119">You can filter the whole workspace by using a workspace-wide filter.</span></span> <span data-ttu-id="f9103-120">ワークスペース全体のフィルターは、ワークスペースの左上隅にあります。</span><span class="sxs-lookup"><span data-stu-id="f9103-120">A workspace-wide filter appears in the upper-left corner of the workspace.</span></span> <span data-ttu-id="f9103-121">ドロップダウン リストで特定の値を選択すると、その選択内容に基づいてワークスペースのコンテンツがフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="f9103-121">When you select a specific value in the drop-down list, the contents of the workspace are filtered based on that selection.</span></span> 

<span data-ttu-id="f9103-122">[![ワークスペース フィルター](./media/workspace-filter.png)](./media/workspace-filter.png)</span><span class="sxs-lookup"><span data-stu-id="f9103-122">[![workspace-filter](./media/workspace-filter.png)](./media/workspace-filter.png)</span></span> 

<span data-ttu-id="f9103-123">クリックしてフィルターを開くと、複数のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9103-123">When you click to open the filter, you're presented with several options.</span></span> 

<span data-ttu-id="f9103-124">[![展開済ワークスペース フィルター](./media/workspace-filter-expanded.png)](./media/workspace-filter-expanded.png)</span><span class="sxs-lookup"><span data-stu-id="f9103-124">[![workspace-filter-expanded](./media/workspace-filter-expanded.png)](./media/workspace-filter-expanded.png)</span></span> 

<span data-ttu-id="f9103-125">オプションに基づいワークスペースのてフィルターを適用するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f9103-125">Select an option to filter the workspace based on that option.</span></span>

### <a name="workspace-section-filters"></a><span data-ttu-id="f9103-126">ワークスペース セクション フィルター</span><span class="sxs-lookup"><span data-stu-id="f9103-126">Workspace section filters</span></span>

<span data-ttu-id="f9103-127">ワークスペースのそれぞれのセクションにフィルタが存在する場合は、各セクションを個別にフィルタ処理できます。</span><span class="sxs-lookup"><span data-stu-id="f9103-127">If individual sections of the workspace have filters, you can filter each section separately.</span></span> <span data-ttu-id="f9103-128">次の図では、フィルター (テキスト「フィルター」を含むフィールド) は自由書式のテキスト フィールドのフィルターの例です。</span><span class="sxs-lookup"><span data-stu-id="f9103-128">In the following illustration, the filter (the field that contains the text "Filter") is an example of a free-form text field filter.</span></span> 

<span data-ttu-id="f9103-129">[![ワークスペース セクション フィルター](./media/workspace-section-filters.png)](./media/workspace-section-filters.png)</span><span class="sxs-lookup"><span data-stu-id="f9103-129">[![workspace-section-filters](./media/workspace-section-filters.png)](./media/workspace-section-filters.png)</span></span> 

<span data-ttu-id="f9103-130">ワークスペース全体のフィルターと同じように、希望のフィルター値を選択または入力して、セクションのコンテンツを絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="f9103-130">As with a workspace-wide filter, select or enter a value in the field to filter the contents of the section.</span></span>



