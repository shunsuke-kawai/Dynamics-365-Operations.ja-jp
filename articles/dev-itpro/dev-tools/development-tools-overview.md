---
title: "開発ツールの概要"
description: "Visual Studio 2015 は、単一の開発用統合開発環境 (IDE) です。"
author: robadawy
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 23401
ms.assetid: 
ms.search.region: Global
ms.author: robadawy
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: abd030d5f772aec3f99447569ec143d15e2b878e
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="development-tools-overview"></a><span data-ttu-id="dbd90-103">開発ツールの概要</span><span class="sxs-lookup"><span data-stu-id="dbd90-103">Development tools overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="what-are-the-development-tools"></a><span data-ttu-id="dbd90-104">開発ツールとは</span><span class="sxs-lookup"><span data-stu-id="dbd90-104">What are the development tools?</span></span>
<span data-ttu-id="dbd90-105">Microsoft Dynamics AX 2012 からの重要な変更は、Microsoft Dynamics 365 for Finance and Operations にリッチ クライアント アプリケーション (ax32.exe) が含まれていないことです。</span><span class="sxs-lookup"><span data-stu-id="dbd90-105">A notable change from Microsoft Dynamics AX 2012 is that Microsoft Dynamics 365 for Finance and Operations does not include a rich-client application (ax32.exe).</span></span> <span data-ttu-id="dbd90-106">開発の観点では、Microsoft Dynamics AX 2012 の開発環境、MorphX が使用されなくなることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dbd90-106">From a development perspective, this means that the Microsoft Dynamics AX 2012 development environment, MorphX, is no longer used.</span></span> <span data-ttu-id="dbd90-107">代わりに、アプリケーション開発は Visual Studio でのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="dbd90-107">In its place, the application development is carried out exclusively in Visual Studio.</span></span> <span data-ttu-id="dbd90-108">開発ツールは、デバッグおよびローカル テストのシナリオを含むすべての開発タスクをサポートします。</span><span class="sxs-lookup"><span data-stu-id="dbd90-108">The development tools support all of the development tasks, including debugging and local testing scenarios.</span></span> <span data-ttu-id="dbd90-109">開発経験の主な目的は、使い慣れた Microsoft Dynamics AX 2012 の概念を保持しながら、Visual Studio のフレームワークおよびパラダイムにシームレスに順応することです。</span><span class="sxs-lookup"><span data-stu-id="dbd90-109">A primary goal of the development experience is to keep familiar Microsoft Dynamics AX 2012 concepts, and seamlessly adapt them to the Visual Studio framework and paradigms.</span></span>

<span data-ttu-id="dbd90-110">Visual Studio 2015 は、単一の開発用統合開発環境 (IDE) です。</span><span class="sxs-lookup"><span data-stu-id="dbd90-110">Visual Studio 2015 is the exclusive integrated development environment (IDE) for development.</span></span> <span data-ttu-id="dbd90-111">すべてのアプリケーション開発作業がそのアプリケーションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="dbd90-111">All of your application development work will be performed with it.</span></span> <span data-ttu-id="dbd90-112">このセクションでは、開発ツールのインストール時に Visual Studio に追加される主な機能の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="dbd90-112">This section is an overview of the main features that are added to Visual Studio when the development tools are installed.</span></span>

### <a name="application-explorer"></a><span data-ttu-id="dbd90-113">アプリケーション エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="dbd90-113">Application Explorer</span></span>
<span data-ttu-id="dbd90-114">Visual Studio で、モデル ストアはアプリケーション エクスプローラーで表されます。</span><span class="sxs-lookup"><span data-stu-id="dbd90-114">In Visual Studio, the model store is represented by the Application Explorer.</span></span> <span data-ttu-id="dbd90-115">**表示**メニューで、**アプリケーション** **エクスプローラー**をクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="dbd90-115">On the **View** menu, click **Application** **Explorer** to open it.</span></span> <span data-ttu-id="dbd90-116">アプリケーション エクスプローラーは、Microsoft Dynamics AX 2012 をよく理解しているアプリケーション オブジェクト ツリー (AOT) に対応します。</span><span class="sxs-lookup"><span data-stu-id="dbd90-116">The Application Explorer corresponds to the Application Object Tree (AOT) that you may be familiar with in Microsoft Dynamics AX 2012.</span></span> <span data-ttu-id="dbd90-117">アプリケーション エクスプローラーを使用して、アプリケーションを定義するモデル ストア内の要素を参照および操作します。</span><span class="sxs-lookup"><span data-stu-id="dbd90-117">Use the Application Explorer to browse and interact with the elements in the model store that define the applications.</span></span> <span data-ttu-id="dbd90-118">次の図は、アプリケーション エクスプローラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="dbd90-118">The following illustration shows the Application Explorer.</span></span> <span data-ttu-id="dbd90-119">詳細については、[アプリケーション エクスプローラー](application-explorer.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbd90-119">For more details, see [Application Explorer](application-explorer.md).</span></span>

![アプリケーション エクスプローラー](media/1_devotoolsconcept.png)

### <a name="the-project-template"></a><span data-ttu-id="dbd90-121">プロジェクト テンプレート</span><span class="sxs-lookup"><span data-stu-id="dbd90-121">The project template</span></span>
<span data-ttu-id="dbd90-122">単純なアプリケーションであっても、そのモデルには多数の要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dbd90-122">Even a simple application can have a large number of elements in its model.</span></span> <span data-ttu-id="dbd90-123">モデルに使用する要素を整理および管理するために、**業務プロジェクト** テンプレートが Visual Studio に追加されました。</span><span class="sxs-lookup"><span data-stu-id="dbd90-123">The **Operations Project** template has been added to Visual Studio to help you organize and manage the elements that you are working with for a model.</span></span> <span data-ttu-id="dbd90-124">このプロジェクトを使用して、モデル要素の設計、作成、およびをテストをします。</span><span class="sxs-lookup"><span data-stu-id="dbd90-124">You will use the project to design, build, and test model elements.</span></span> <span data-ttu-id="dbd90-125">1 つの Visual Studio ソリューション内に複数のプロジェクトがあることが一般的です。</span><span class="sxs-lookup"><span data-stu-id="dbd90-125">It’s common to have several projects within a single Visual Studio solution.</span></span> <span data-ttu-id="dbd90-126">次の図は、Visual Studio ソリューションの 3 つのプロジェクトを示しています。</span><span class="sxs-lookup"><span data-stu-id="dbd90-126">The following illustration shows three projects in a Visual Studio solution.</span></span> <span data-ttu-id="dbd90-127">詳細については、[プロジェクト](projects.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbd90-127">For more details, see [Projects](projects.md).</span></span>

![ソリューション エクスプローラー](media/2_devotoolsconcept.png)

### <a name="element-designers"></a><span data-ttu-id="dbd90-129">要素デザイナー</span><span class="sxs-lookup"><span data-stu-id="dbd90-129">Element designers</span></span>
<span data-ttu-id="dbd90-130">Visual Studio Tools には、アプリケーション内の要素の種類ごとのデザイナーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dbd90-130">The Visual Studio tools contain designers for each kind of element in the application.</span></span> <span data-ttu-id="dbd90-131">要素を作成または変更するときは、これらのデザイナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbd90-131">You will use these designers when you create or modify elements.</span></span> <span data-ttu-id="dbd90-132">次の図は、フォーム要素の要素デザイナーを示しています。</span><span class="sxs-lookup"><span data-stu-id="dbd90-132">The following illustration shows the element designer for a form element.</span></span> <span data-ttu-id="dbd90-133">詳細については、[要素デザイナー](element-designers.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbd90-133">For more details, see [Element designers](element-designers.md).</span></span>

![要素デザイナー](media/3_devotoolsconcept.png)

### <a name="code-editor"></a><span data-ttu-id="dbd90-135">コード エディター</span><span class="sxs-lookup"><span data-stu-id="dbd90-135">Code editor</span></span>
<span data-ttu-id="dbd90-136">X++ コードは、Visual Studio 用のコード エディタに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="dbd90-136">The X++ code is written in the code editor for Visual Studio.</span></span> <span data-ttu-id="dbd90-137">開発者がコード エディターに期待する標準機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dbd90-137">The standard features that a developer expects from the code editor are supported.</span></span> <span data-ttu-id="dbd90-138">たとえば、コードのセクションは折りたたみ可能です。</span><span class="sxs-lookup"><span data-stu-id="dbd90-138">For example, sections of code are collapsible.</span></span> <span data-ttu-id="dbd90-139">IntelliSense は、コードを書き込みまたは変更するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="dbd90-139">IntelliSense provides guidance as you write or modify code.</span></span> <span data-ttu-id="dbd90-140">詳細については、[コード エディター](code-editor.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbd90-140">For more details, see [Code editor](code-editor.md).</span></span>

![コード エディター](media/4_devotoolsconcept.png)

### <a name="dynamics-365-menu"></a><span data-ttu-id="dbd90-142">Dynamics 365 メニュー</span><span class="sxs-lookup"><span data-stu-id="dbd90-142">Dynamics 365 menu</span></span>
<span data-ttu-id="dbd90-143">このツールは **Dynamics 365** メニューを Visual Studio に追加します。</span><span class="sxs-lookup"><span data-stu-id="dbd90-143">The tools add the **Dynamics 365** menu to Visual Studio.</span></span> <span data-ttu-id="dbd90-144">開発プロセス中に使用するいくつかのツールは、ここで入手できます。</span><span class="sxs-lookup"><span data-stu-id="dbd90-144">Several tools that you will use during the development process are found here.</span></span> <span data-ttu-id="dbd90-145">たとえば、モデルを管理するツールは、メニューからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="dbd90-145">For example, the tools for managing models are accessed from the menu.</span></span>

