---
title: "Commerce Runtime の概要"
description: "この記事では、Commerce Runtime (CRT) のアーキテクチャと構成に関する情報を提供します。 CRT は、ビジネス ロジックをカプセル化するポータブル .NET ライブラリの集合です。 小売チャネルのエンジンとして機能します。"
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: robinr
ms.search.scope: Operations, Retail
ms.custom: 218654
ms.assetid: ac422f7e-bc71-4b42-b8c1-4702c6c18421
ms.search.region: Global
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6d381248857e73e43000727b40d0ba183829c979
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="commerce-runtime-overview"></a><span data-ttu-id="a748e-105">Commerce Runtime の概要</span><span class="sxs-lookup"><span data-stu-id="a748e-105">Commerce runtime overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a748e-106">この記事では、Commerce Runtime (CRT) のアーキテクチャと構成に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a748e-106">This article provides information about the architecture and configuration of Commerce Runtime (CRT).</span></span> <span data-ttu-id="a748e-107">CRT は、ビジネス ロジックをカプセル化するポータブル .NET ライブラリの集合です。</span><span class="sxs-lookup"><span data-stu-id="a748e-107">The CRT is a collection of portable .NET libraries that encapsulate business logic.</span></span> <span data-ttu-id="a748e-108">小売チャネルのエンジンとして機能します。</span><span class="sxs-lookup"><span data-stu-id="a748e-108">It serves as the engine for the retail channel.</span></span> 

<a name="commerce-runtime-architecture"></a><span data-ttu-id="a748e-109">Commerce Runtime のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="a748e-109">Commerce Runtime architecture</span></span>
-----------------------------

<span data-ttu-id="a748e-110">次の図は、Retail Commerce Runtime (CRT) 用の Microsoft Dynamics 365 のコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="a748e-110">The following diagram shows the components of the Microsoft Dynamics 365 for Retail Commerce Runtime (CRT).</span></span> 

<span data-ttu-id="a748e-111">[![コマース ランタイム コンポーネント](./media/crt-architecture-1024x793.jpg)](./media/crt-architecture.jpg)</span><span class="sxs-lookup"><span data-stu-id="a748e-111">[![Commerce Runtime components](./media/crt-architecture-1024x793.jpg)](./media/crt-architecture.jpg)</span></span>

### <a name="data-access"></a><span data-ttu-id="a748e-112">データ アクセス</span><span class="sxs-lookup"><span data-stu-id="a748e-112">Data access</span></span>

<span data-ttu-id="a748e-113">データベースの上は、データ アクセス レイヤーです。</span><span class="sxs-lookup"><span data-stu-id="a748e-113">On top of the database is a data access layer.</span></span> <span data-ttu-id="a748e-114">データ アクセス レイヤーでは、生データがメモリ内のオブジェクトに変換されます。</span><span class="sxs-lookup"><span data-stu-id="a748e-114">In the data access layer, raw data is translated into objects in memory.</span></span> <span data-ttu-id="a748e-115">たとえば、オブジェクトは、製品である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a748e-115">For example, an object might be a product.</span></span> <span data-ttu-id="a748e-116">製品は、価格や色などの属性を持ちます。</span><span class="sxs-lookup"><span data-stu-id="a748e-116">Products have attributes, such as price and color.</span></span> <span data-ttu-id="a748e-117">データ アクセス レイヤーには、オブジェクトを操作するための機能があります。</span><span class="sxs-lookup"><span data-stu-id="a748e-117">The data access layer has functions that you can use to manipulate the objects.</span></span> <span data-ttu-id="a748e-118">ストアド プロシージャは、サービスとワークフローで使用できるデータ エンティティにデータベースからデータのパケットを渡します。</span><span class="sxs-lookup"><span data-stu-id="a748e-118">Stored procedures pass packets of data from the database to data entities that can be used in services and workflows.</span></span> <span data-ttu-id="a748e-119">Dynamics 365 for Retail に追加する新しいフィールドを含めるように、データのパケットを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="a748e-119">You can update the packets of data to include new fields that you add in Dynamics 365 for Retail.</span></span>

### <a name="services"></a><span data-ttu-id="a748e-120">サービス</span><span class="sxs-lookup"><span data-stu-id="a748e-120">Services</span></span>

<span data-ttu-id="a748e-121">データ アクセス レイヤーの上は、サービス レイヤーです。</span><span class="sxs-lookup"><span data-stu-id="a748e-121">On top of the data access layer is a services layer.</span></span> <span data-ttu-id="a748e-122">リアルタイム データのクエリを処理します。</span><span class="sxs-lookup"><span data-stu-id="a748e-122">Services query for real-time data.</span></span> <span data-ttu-id="a748e-123">これらのサービスを使用して、既存の機能をカスタマイズしたり、新しい機能を含む独自のサービスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a748e-123">You can use these services to customize existing functionality, or you can add your own services that include new functionality.</span></span>

### <a name="workflows"></a><span data-ttu-id="a748e-124">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="a748e-124">Workflows</span></span>

<span data-ttu-id="a748e-125">サービス レイヤーの上は、ワークフロー レイヤーです。</span><span class="sxs-lookup"><span data-stu-id="a748e-125">On top of the services layer is the workflow layer.</span></span> <span data-ttu-id="a748e-126">ワークフローは、業務プロセスを定義するサービスとビジネス ロジックの集合です。</span><span class="sxs-lookup"><span data-stu-id="a748e-126">A workflow is a collection of services and business logic that, together, define business processes.</span></span> <span data-ttu-id="a748e-127">たとえば、顧客がカートに品目を追加すると、価格の取得、検証の実行、在庫数量の確認、出荷費用の計算、税計算、および割引計算をするためワークフローを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a748e-127">For example, when a customer adds an item to the cart, you can use a workflow to get the price, perform validation, check the inventory quantity, calculate shipping charges, calculate tax, and calculate discounts.</span></span> <span data-ttu-id="a748e-128">Dynamics 365 for Retail に含まれているワークフローを使用することも、新しいワークフローを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a748e-128">You can use the workflows that are included in Dynamics 365 for Retail, or you can create new workflows.</span></span> <span data-ttu-id="a748e-129">ワークフローを使用して、業務プロセスの一部としてサードパーティ製システムに接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="a748e-129">You can even use a workflow to connect to a third-party system as part of your business processes.</span></span>

### <a name="api"></a><span data-ttu-id="a748e-130">API</span><span class="sxs-lookup"><span data-stu-id="a748e-130">API</span></span>

<span data-ttu-id="a748e-131">ワークフロー レイヤーーの上は、アプリケーション プログラミング インターフェイス (API) レイヤーです。</span><span class="sxs-lookup"><span data-stu-id="a748e-131">On top of the workflow layer is the application programming interface (API) layer.</span></span> <span data-ttu-id="a748e-132">項目に関する情報の取得、価格の計算、配送料の計算、および発注などのタスクのために API を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a748e-132">You can use the API for tasks such as getting information about items, calculating prices, calculating shipping charges, and placing orders.</span></span> <span data-ttu-id="a748e-133">業務プロセスに合わせて API を拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="a748e-133">You can extend the API to fit your business processes.</span></span>

## <a name="commerce-runtime-configuration"></a><span data-ttu-id="a748e-134">Commerce Runtime のコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="a748e-134">Commerce Runtime configuration</span></span>
<span data-ttu-id="a748e-135">サービスは、CRT コンフィギュレーション ファイルのタイプとして列挙されます。</span><span class="sxs-lookup"><span data-stu-id="a748e-135">Services are enumerated as types in the CRT configuration file.</span></span> <span data-ttu-id="a748e-136">タイプを CRT 構成ファイルに追加して、どのサービスが CRT に読み込まれるかコントロールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a748e-136">You can add types in the CRT configuration file to control which services are loaded in the CRT.</span></span> <span data-ttu-id="a748e-137">コンフィギュレーション ファイルに一覧表示された順序でサービスが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a748e-137">Services are loaded in the order in which they are listed in the configuration file.</span></span> <span data-ttu-id="a748e-138">すべての既定サービスは自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a748e-138">All the default services are loaded automatically.</span></span> <span data-ttu-id="a748e-139">ただし、既定のサービスのいずれかの上に新しいサービスを追加する場合、新しいサービスは既定のサービスに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a748e-139">However, if you add a new service above one of the default services, the new service replaces the default service.</span></span>



