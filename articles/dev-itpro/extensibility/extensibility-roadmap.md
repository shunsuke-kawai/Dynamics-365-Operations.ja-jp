---
title: "アプリケーション拡張機能ロードマップ"
description: "このトピックでは、コードをオーバーレイ ベースから拡張ベースに変換するための要件とスケジュールについて説明します。"
author: FrankDahl
manager: AnnBe
ms.date: 07/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 89563
ms.assetid: 
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2017-07-10
ms.dyn365.ops.version: Platform update 1
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 535e6c441f22d1bc60ddc894cad4c3af82deba05
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="application-extensibility-roadmap"></a><span data-ttu-id="81689-103">アプリケーション拡張機能ロードマップ</span><span class="sxs-lookup"><span data-stu-id="81689-103">Application extensibility roadmap</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81689-104">実装およびアップグレード作業を減らすことは、Microsoft Dynamics 365 for Finance and Operations 開発チームの主要なイニシアティブです。</span><span class="sxs-lookup"><span data-stu-id="81689-104">Reducing implementation and upgrade effort is a major initiative for the Microsoft Dynamics 365 for Finance and Operations development team.</span></span> <span data-ttu-id="81689-105">この構想のメリットは、短期間で、Microsoft とパートナーからの新しいイノベーションを利用でき、総保有コストが削減され、品質向上を実現できることです。</span><span class="sxs-lookup"><span data-stu-id="81689-105">The benefits of this initiative are to enable you to quickly take advantage of new innovations from Microsoft and your partners, reduce the total cost of ownership, and improve quality.</span></span> <span data-ttu-id="81689-106">この取り組みの主要な部分は、製品のカスタマイズ方法を変更することです。</span><span class="sxs-lookup"><span data-stu-id="81689-106">A major part of this initiative is to change the customization approach for the product.</span></span> <span data-ttu-id="81689-107">Dynamics AX 2012 では、いくつかの拡張機能が製品に追加されました。</span><span class="sxs-lookup"><span data-stu-id="81689-107">In Dynamics AX 2012, several extension capabilities were added to the product.</span></span> <span data-ttu-id="81689-108">たとえば、プリイベントとポストイベントのメソッドを使用する、イベントに基づくカスタマイズの機能が導入されました。</span><span class="sxs-lookup"><span data-stu-id="81689-108">For example, the ability to do event-based customization using methods pre-and post-events was introduced.</span></span> <span data-ttu-id="81689-109">拡張子の機能は、Dynamics 365 for Finance and Operations への進化の中で成長し続けています。</span><span class="sxs-lookup"><span data-stu-id="81689-109">Extension capabilities have continued to grow in the evolution to Dynamics 365 for Finance and Operations.</span></span>  

<span data-ttu-id="81689-110">拡張子ベース カスタマイズには、特に実装およびアップグレードの作業量を削減する場合に、オーバーレイヤー ベースのカスタマイズの従来のアプローチよりもいくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="81689-110">Extension-based customizations have several advantages over the legacy approach of overlayering-based customizations, especially when it comes to reducing implementation and upgrade effort.</span></span>  
+ <span data-ttu-id="81689-111">オーバーレイヤー ベースのカスタマイズには、コード アップグレード、再コンパイル時刻、広範なテストが必要です。</span><span class="sxs-lookup"><span data-stu-id="81689-111">Overlayering-based customizations require code upgrade, recompile time, and extensive testing.</span></span> <span data-ttu-id="81689-112">これにより、修正プログラムをシームレスに適用する機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="81689-112">This limits the ability to seamlessly apply hot fixes.</span></span> <span data-ttu-id="81689-113">これらの原価は、お客様が Microsoft やパートナーの新機能を含む新しいバージョンにアップグレードする際の阻害要因となります。</span><span class="sxs-lookup"><span data-stu-id="81689-113">These costs can be an inhibitor for customers to upgrade to newer versions containing innovations from Microsoft and partners.</span></span>  
+ <span data-ttu-id="81689-114">拡張子ベース カスタマイズはまた、開発経験を改善します。</span><span class="sxs-lookup"><span data-stu-id="81689-114">Extension-based customizations also improve the development experience.</span></span> <span data-ttu-id="81689-115">オーバーレイされたカスタマイズを含むモデルは、基本オブジェクトと同じパッケージにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81689-115">Models containing overlayered customizations must be in the same package as the base objects.</span></span> <span data-ttu-id="81689-116">これにより、コンパイル サイクルが長くなり、パッケージの配布が大規模になります。</span><span class="sxs-lookup"><span data-stu-id="81689-116">This results in longer compile cycles and larger package distributions.</span></span> <span data-ttu-id="81689-117">拡張子では、基準オブジェクトから分離して単体テストを行う方がはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="81689-117">Extensions are also much easier to unit test in isolation from the base object.</span></span>  
+ <span data-ttu-id="81689-118">拡張機能ベースのカスタマイズを通じてアップグレード コストを削減すると、サポートが必要なリリースの組み合わせが減るため、パートナーのサポート マトリックスが減少します。</span><span class="sxs-lookup"><span data-stu-id="81689-118">Reducing upgrade costs through extension-based customizations reduces the support matrix for partners as fewer release combinations will need to be supported.</span></span>

<span data-ttu-id="81689-119">これらの理由により、製品モデルを徐々にシールしてきており、拡張ベース カスタマイズのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="81689-119">For these reasons, we have gradually been sealing the product models, so they only support extension-based customizations.</span></span> <span data-ttu-id="81689-120">**AppPlatform** および **AppFoundation** が最初のものでした。</span><span class="sxs-lookup"><span data-stu-id="81689-120">**AppPlatform** and **AppFoundation** were the first.</span></span> <span data-ttu-id="81689-121">これらのモデルは、プラットフォーム更新プログラム 3 (2016 年 11 月) にオーバーレイされてシールされました。</span><span class="sxs-lookup"><span data-stu-id="81689-121">These models were sealed for overlayering in Platform update 3 (November 2016).</span></span> <span data-ttu-id="81689-122">これらのモデルにはバイナリ更新プログラムが月ごとに提供されており、アップグレード コストを削減しより速いリズムで顧客にイノベーションを届けるという目標を達成しています。</span><span class="sxs-lookup"><span data-stu-id="81689-122">Binary updates are now provided to these models on a monthly basis, achieving our goals of reducing upgrade cost and delivering innovation to our customers at a faster cadence.</span></span> 

<span data-ttu-id="81689-123">Microsoft Dynamics 365 for Finance and Operations リリース 8.0 では、すべての製品モデルをシールドしました。</span><span class="sxs-lookup"><span data-stu-id="81689-123">With Microsoft Dynamics 365 for Finance and Operations release 8.0, we have sealed all product models.</span></span> <span data-ttu-id="81689-124">現在、拡張機能ベースのカスタマイズのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="81689-124">Now only extension based customizations are supported.</span></span>

<span data-ttu-id="81689-125">次の図は、オーバーレイから、拡張機能に移動したときに従ったロードマップを示しています。</span><span class="sxs-lookup"><span data-stu-id="81689-125">The following illustration shows the roadmap we followed as we moved to extensions, away from overlayering.</span></span>

![拡張性ロードマップ](media/extensibility-roadmap.jpg)

> [!NOTE]
> <span data-ttu-id="81689-127">ソフト シールは、オーバーレイ時にコンパイラの警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="81689-127">A soft seal results in a compiler warning upon overlayering.</span></span> <span data-ttu-id="81689-128">ハード シールは、オーバーレイ時にコンパイラのエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="81689-128">A hard seal results in a compiler error upon overlayering.</span></span> 

<span data-ttu-id="81689-129">最新のサポート ポリシーは、リリースから 3 年間のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="81689-129">The Modern support policy provides three years of support for a release.</span></span> <span data-ttu-id="81689-130">この場合、オーバーレイ コードは Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 リリースで 2017 年 11 月 から始まり、3 年間サポートが続行されます。</span><span class="sxs-lookup"><span data-stu-id="81689-130">Given this, overlayered code will continue to be supported for three years starting November 2017 on the Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 release.</span></span> <span data-ttu-id="81689-131">ただし、このコードは、オーバーレイ コードが拡張機能に移動されるまでは、後続の製品リリースに移動されません。</span><span class="sxs-lookup"><span data-stu-id="81689-131">However, this code will not be moved forward to subsequent product releases until the overlayered code is moved to extensions.</span></span>  

<span data-ttu-id="81689-132">この目標を達成するために、Microsoft、パートナー、顧客には相当量の作業があります。</span><span class="sxs-lookup"><span data-stu-id="81689-132">There is a substantial amount of work for Microsoft, partners, and customers to accomplish this goal.</span></span> <span data-ttu-id="81689-133">ワークショップ、営業時間、ヘルプ トピック、および他のリソースは、このエコシステムのトレーニングおよび共同作業で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="81689-133">Workshops, office hours, Help topics, and additional resources are available for training and collaboration in this ecosystem.</span></span> <span data-ttu-id="81689-134">内部的には、コア プラットフォームとアプリケーションの両方でより多くの拡張性を構築する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="81689-134">Internally, we are ready to build more extensibility features in both the core platform and the application.</span></span> <span data-ttu-id="81689-135">パートナーが拡張機能に移行しているときにパターンを定義するために、AppSource に関するアプリケーションに対して、パートナーと密接に連携して作業しています。</span><span class="sxs-lookup"><span data-stu-id="81689-135">We’re working closely with partners with applications on AppSource to define patterns as they migrate to extensions.</span></span>

<span data-ttu-id="81689-136">アップグレード時の摩擦が緩和されるというメリットが得られ、イノベーションが実現されるため、オーバーレイを削除する作業を行う価値があります。</span><span class="sxs-lookup"><span data-stu-id="81689-136">The benefits of reducing upgrade friction and enabling innovation uptake will be worth the effort to remove overlayering.</span></span>
