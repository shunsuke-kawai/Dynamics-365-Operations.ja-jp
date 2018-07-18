---
title: "コードの移行 - マウスのダブルクリック"
description: "Microsoft Dynamics 365 for Finance and Operations では、mouseDblClick() のオーバーライドが推奨されず、新しいコントロールにこのロジックを移動する必要があります。"
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 28331
ms.assetid: ba33ee49-2053-4e3c-b0fa-123c9410265d
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: b7ab55762a281ebb1116a0b81ddc24dce24c7c13
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="code-migration---mouse-double-click"></a><span data-ttu-id="fc1ad-103">コードの移行 - マウスのダブルクリック</span><span class="sxs-lookup"><span data-stu-id="fc1ad-103">Code migration - Mouse double-click</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fc1ad-104">Microsoft Dynamics 365 for Finance and Operations では、mouseDblClick() のオーバーライドが推奨されず、新しいコントロールにこのロジックを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-104">In Microsoft Dynamics 365 for Finance and Operations, the mouseDblClick() override has been deprecated, and you will have to move this logic to new controls.</span></span>

<span data-ttu-id="fc1ad-105">Microsoft Dynamics AX 2012 では、マウスをダブルクリックするイベントがさまざまな理由で使用されていました。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-105">In Microsoft Dynamics AX 2012, the mouse double-click event was used for various reasons.</span></span> <span data-ttu-id="fc1ad-106">たとえば、より良いユーザー エクスペリエンスを提供するのを助け、特定のシナリオを実行する代替方法を提供しました。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-106">For example, it helped provide a better user experience and provided an alternative way to run certain scenarios.</span></span> <span data-ttu-id="fc1ad-107">共通の使用パターンの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-107">Here are some examples of common usage patterns:</span></span>

-   <span data-ttu-id="fc1ad-108">2 つのリストまたはツリー コントロールの間での要素の移動</span><span class="sxs-lookup"><span data-stu-id="fc1ad-108">Moving elements between two lists or tree controls</span></span>
-   <span data-ttu-id="fc1ad-109">選択したフィールドに関する詳細を取得するための新しいフォームを開いています</span><span class="sxs-lookup"><span data-stu-id="fc1ad-109">Opening a new form to get more details about the selected field</span></span>
-   <span data-ttu-id="fc1ad-110">複雑なビジネス ロジックを実行</span><span class="sxs-lookup"><span data-stu-id="fc1ad-110">Running complex business logic</span></span>
-   <span data-ttu-id="fc1ad-111">ルックアップでフィールドを選択</span><span class="sxs-lookup"><span data-stu-id="fc1ad-111">Selecting a field in a lookup</span></span>

<span data-ttu-id="fc1ad-112">Finance and Operations では、**mouseDblClick()** のオーバーライドが推奨されず、開発者は実装されたロジックに応じて新しいコントロールにこのロジックを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-112">In Finance and Operations, the **mouseDblClick()** override has been deprecated, and developers will have to move this logic to new controls, depending on the logic that was implemented.</span></span>

## <a name="strategy-overview"></a><span data-ttu-id="fc1ad-113">戦略の概要</span><span class="sxs-lookup"><span data-stu-id="fc1ad-113">Strategy overview</span></span>
<span data-ttu-id="fc1ad-114">フォームの使用を開始する前に、「mouseDblClick コントロール メソッドは非推奨であり使用しないでください」というすべてのベスト プラクティス警告メッセージを修正することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-114">Before you begin to use the form, it's a good idea to fix all best practice warning messages that state, “The mouseDblClick control method has been deprecated and should not be used.”</span></span> <span data-ttu-id="fc1ad-115">それ以外の場合、フォームが使えなくなるか、限られた方法で動作する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-115">Otherwise, the form might be useless, or it might work only in limited ways.</span></span>

## <a name="migrate-code-from-mousedblclick-methods"></a><span data-ttu-id="fc1ad-116">mouseDblClick() メソッドからのコードの移行</span><span class="sxs-lookup"><span data-stu-id="fc1ad-116">Migrate code from mouseDblClick() methods</span></span>
<span data-ttu-id="fc1ad-117">先に述べたように、Dynamics AX 2012 で **mouseDblClick()** メソッドを使用するさまざまな理由がありました。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-117">As we mentioned earlier, there were various reasons for using the **mouseDblClick()** method in Dynamics AX 2012.</span></span> <span data-ttu-id="fc1ad-118">このセクションでは、最も一般的なシナリオのいくつかを移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-118">This section explains how to migrate some of the most common scenarios.</span></span>

### <a name="moving-items-between-two-lists-controls"></a><span data-ttu-id="fc1ad-119">2 つのリスト コントロール間での項目の移動</span><span class="sxs-lookup"><span data-stu-id="fc1ad-119">Moving items between two lists controls</span></span>

<span data-ttu-id="fc1ad-120">Dynamics AX 2012 では、2 つのリスト コントロールに並べて表示されている場合に、リスト パネル シナリオでマウスのダブルクリックがよく使用されていました。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-120">In Dynamics AX 2012, a mouse double-click was often used in List Panel scenarios, where two list controls appeared side by side.</span></span> <span data-ttu-id="fc1ad-121">ユーザーが 1 つのリスト コントロール内の品目をダブルクリックした場合、その品目が 2 つ目のリスト コントロールに移動されました。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-121">Often, when a user double-clicked an item in one list control, that item was moved to the second list control.</span></span> <span data-ttu-id="fc1ad-122">Finance and Operations での **mouseDblClick()** シナリオの移行では、リスト パネルのパターンへの配置が関係します。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-122">Migration of this **mouseDblClick()** scenario in Finance and Operations involves alignment to the List Panel pattern.</span></span> <span data-ttu-id="fc1ad-123">次のように、この使用パターンを移行するための 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-123">You have two options for migrating this usage pattern:</span></span>

-   <span data-ttu-id="fc1ad-124">**SysListPanel** クラス自体を使用します。これは、2 つのリスト コントロール間でアイテムを移動するためのロジックとボタンを提供します。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-124">Use the **SysListPanel** class itself, which provides the logic and the buttons for moving items between the two list controls.</span></span>
-   <span data-ttu-id="fc1ad-125">**SysListPanel** クラス (リストが ListView ではないため、またはクラスが特定の状況に適していないため)、リスト パネルのサブパターンに従ってコントロールを手動でモデル化できます。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-125">If you can't use the **SysListPanel** class (because the lists aren't ListViews, or the class isn't appropriate for the given situation), you can manually model the controls by following the List Panel sub-pattern.</span></span> <span data-ttu-id="fc1ad-126">このパターンには、リスト間でアイテムを移動するためのボタンが含まれていますが、開発者はこれらのボタンを動作させるための正しいロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-126">This pattern includes buttons for moving items between lists, but the developer will have to add the correct logic to make these buttons work.</span></span>

### <a name="opening-a-new-form"></a><span data-ttu-id="fc1ad-127">新しいフォームを開いています</span><span class="sxs-lookup"><span data-stu-id="fc1ad-127">Opening a new form</span></span>

<span data-ttu-id="fc1ad-128">Dynamics AX 2012 の別の一般的な使用パターンでは、ユーザーがフィールドをダブルクリックすると、そのフィールドに関する詳細な情報を表示する新規フォームを開けました。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-128">In another common usage pattern in Dynamics AX 2012, the user double-clicked a field to open a new form that showed more detailed information about that field.</span></span> <span data-ttu-id="fc1ad-129">次のように、この使用パターンを移行するためのいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-129">You have several options for migrating this usage pattern:</span></span>

-   <span data-ttu-id="fc1ad-130">フィールドの詳細を表示するバッキング フォームを開くには、シングルクリックを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-130">Use a single-click to open a backing form that shows more details about a field.</span></span> <span data-ttu-id="fc1ad-131">この機能は、テーブル関係に基づいている多くのフィールドで自動的に実装され、コントロールの **jumpRef()** メソッドをオーバーライドすることで手動で実装できます。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-131">This functionality is automatically implemented for many fields that are based on table relations, and you can implement it manually by overriding the **jumpRef()** method on a control.</span></span> <span data-ttu-id="fc1ad-132">推奨される移行工順は、コードを **mouseDblClick()** から **jumpRef()** オーバーライドへ移動して、ナビゲーションがシステム内のその他のフィールドとつながるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-132">The preferred migration route is to move the code from **mouseDblClick()** into a **jumpRef()** override, so that the navigation will be aligned with other fields in the system.</span></span>
-   <span data-ttu-id="fc1ad-133">フォームで新しいボタンをモデル化して、**mouseDblClick()** メソッドからボタンの **clicked()** メソッドにロジックを移動します。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-133">Model a new button on the form, and move the logic from the **mouseDblClick()** method into the button's **clicked()** method.</span></span> <span data-ttu-id="fc1ad-134">この方法は、**jumpRef()** のオーバーライドが存在しない、非入力フィールド コントロール (たとえば、ツリー コントロール) に対してのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-134">You should use this approach only for non-input field controls (for example, a Tree control) in which a **jumpRef()** override doesn't exist.</span></span>
-   <span data-ttu-id="fc1ad-135">右クリックのコンテキスト メニュー (ショートカット メニュー) オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-135">Add a right-click context menu (shortcut menu) option.</span></span> <span data-ttu-id="fc1ad-136">ただし、コンテキスト メニューのコマンドを指定する UX ガイドラインは、**常に**ページの他の場所で使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-136">However, note that UX guidelines specify that the commands on context menus should **always** be available in other locations on the page.</span></span> <span data-ttu-id="fc1ad-137">**詳細の表示**コマンドは、**jumpRef()** メソッドを上書きしたコントロールの右クリック コンテキスト メニューに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-137">A **View details** command is automatically added to the right-click context menu for controls that have an overridden **jumpRef()** method.</span></span> <span data-ttu-id="fc1ad-138">したがって、このアプローチは、以前の移行ルート (新しいボタンのモデリング) へのオプションの追加としてのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-138">Therefore, this approach should be used only as an optional addition to the previous migration route (modeling a new button).</span></span> <span data-ttu-id="fc1ad-139">Finance and Operations のコンテキスト メニュー オプションを追加する方法の詳細については、[コードの移行: コンテキスト メニュー](code-migration-context-menus.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-139">For more information about how to add context menu options in Finance and Operations, see [Code migration: Context menus](code-migration-context-menus.md).</span></span>

### <a name="moving-logic-to-a-button-control"></a><span data-ttu-id="fc1ad-140">ボタン コントロールへのロジックの移動</span><span class="sxs-lookup"><span data-stu-id="fc1ad-140">Moving logic to a button control</span></span>

<span data-ttu-id="fc1ad-141">Dynamics AX 2012 の別の一般的な使用パターンでは、ダブルクリックで複雑なビジネス ロジックを実行できました。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-141">In another common usage pattern in Dynamics AX 2012, the double-click caused complex business logic to run.</span></span> <span data-ttu-id="fc1ad-142">このシナリオで、優先される移行工順とは、フォームに新しいボタンをモデル化することであり、次にロジックを **mouseDblClick()** から新しいボタンの **clicked()** メソッドに移動します。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-142">For this scenario, the preferred migration route is to model a new button on the form, and then move the logic from **mouseDblClick()** into the new button's **clicked()** method.</span></span>

### <a name="selecting-a-field-in-a-lookup"></a><span data-ttu-id="fc1ad-143">ルックアップでフィールドを選択</span><span class="sxs-lookup"><span data-stu-id="fc1ad-143">Selecting a field in a lookup</span></span>

<span data-ttu-id="fc1ad-144">Dynamics AX 2012 の一部のカスタム ルックアップでは、ユーザーがグリッドの行 (またはツリーの要素) をダブルクリックして値を選択し、ルックアップを閉じることができるように、コードが追加されました。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-144">In some custom lookups in Dynamics AX 2012, code was added so that the user could double-click a row in a grid (or an element in a tree) to select the value and close the lookup.</span></span> <span data-ttu-id="fc1ad-145">このシナリオでは、推奨される移行工順とは、ルックアップ フォームの下部にある**選択**ボタンを追加し、レコード選択を有効にすることです。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-145">For this scenario, the recommended migration route is to add a **Select** button at the bottom of the lookup form to enable record selection.</span></span>

## <a name="ux-guidelines"></a><span data-ttu-id="fc1ad-146">UX ガイドライン</span><span class="sxs-lookup"><span data-stu-id="fc1ad-146">UX guidelines</span></span>
<span data-ttu-id="fc1ad-147">マウスのダブルクリック メソッドを移行する際、次のガイドラインを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-147">As you migrate mouse double-click methods, you should consider the following guidelines:</span></span>

-   <span data-ttu-id="fc1ad-148">コントロール間で項目を移動するには、可能であれば **SysListPanel** クラスまたは ListPanel パターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-148">To move items between controls, use the **SysListPanel** class or the ListPanel pattern whenever possible.</span></span>
-   <span data-ttu-id="fc1ad-149">マウスのダブルクリック ロジックに置き換わるボタンを追加するとき、できるだけ (コンテキストに依存する方法で) コントロールの近くにボタンを配置します。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-149">When you add buttons to replace mouse double-click logic, put the button as close as possible (contextually) to the control.</span></span>
-   <span data-ttu-id="fc1ad-150">場合によっては、フォームを再設計して **mouseDblClick()** メソッド内に存在していたロジックに対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc1ad-150">In some cases, you might have to redesign the form to accommodate the logic that was present in the **mouseDblClick()** method.</span></span>




