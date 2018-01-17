---
title: "MPOS/CPOS でのデモ データの画面レイアウト"
description: "このトピックでは、Microsoft Dynamics 365 for Retail の販売時点管理 (POS) のデモ データ セットに含まれている画面レイアウトに関する情報を提供します。"
author: zlinster
manager: AnnBe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.search.scope: Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: zlinster
ms.search.validFrom: 2017-10-05
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 563c89c75e2136294f8f841bec094c2aeb85d580
ms.openlocfilehash: b758b48230e8d9fabdccbe267a6ad6b9e74af0ff
ms.contentlocale: ja-jp
ms.lasthandoff: 10/17/2017

---

# <a name="demo-data-screen-layouts-in-mposcpos"></a><span data-ttu-id="982d5-103">MPOS/CPOS でのデモ データの画面レイアウト</span><span class="sxs-lookup"><span data-stu-id="982d5-103">Demo data screen layouts in MPOS/CPOS</span></span>

<span data-ttu-id="982d5-104">このトピックでは、Microsoft Dynamics 365 for Retail の販売時点管理 (POS) のデモ データ セットに含まれている画面レイアウトに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="982d5-104">This topic provides information about the screen layouts that are included with the demo data set for the point of sale (POS) experiences in Microsoft Dynamics 365 for Retail.</span></span>

## <a name="overview"></a><span data-ttu-id="982d5-105">概要</span><span class="sxs-lookup"><span data-stu-id="982d5-105">Overview</span></span>

<span data-ttu-id="982d5-106">Retail のデモデータに含まれているサンプル画面レイアウトは、さまざまな小売セグメント、店員の役割、およびデバイスに最適化されたコンテンツを提供します。</span><span class="sxs-lookup"><span data-stu-id="982d5-106">The sample screen layouts that are included with Retail demo data provide content that is optimized for various retail segments, store worker roles, and devices.</span></span> <span data-ttu-id="982d5-107">1 つのレイアウトに複数のレイアウトサイズとボタングリッドの組み合わせを含めることで、店員によるデバイスとステーション間の移動を確実にカバーできます。</span><span class="sxs-lookup"><span data-stu-id="982d5-107">A single layout can contain several layout sizes and combinations of button grids, to help ensure coverage as store workers move between devices and stations.</span></span> <span data-ttu-id="982d5-108">このトピックでは、これらのレイアウトの違いや、レイアウトが提供する操作や全体的なエクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="982d5-108">This topic highlights the differences between these layouts, the operations that they provide, and the overall experiences that they deliver.</span></span>

![クロス デバイス デモ データのレイアウト](../retail/media/demo-screen-layouts-fig-1-1.png)

## <a name="anatomy-of-a-screen-layout-id"></a><span data-ttu-id="982d5-110">画面レイアウト ID の構造</span><span class="sxs-lookup"><span data-stu-id="982d5-110">Anatomy of a screen layout ID</span></span>

<span data-ttu-id="982d5-111">Retail で画面レイアウトを検索するには **Retail** > **チャンネル設定** > **POS 設定** > **POS** > **画面レイアウト** の順で移動します。</span><span class="sxs-lookup"><span data-stu-id="982d5-111">To find screen layouts in Retail, go to **Retail** > **Channel setup** > **POS setup** > **POS** > **Screen layouts**.</span></span>

![Retail の画面レイアウト ページ](../retail/media/demo-screen-layouts-fig-2-1.png)

<span data-ttu-id="982d5-113">画面レイアウト ID は、最大 10 文字です。</span><span class="sxs-lookup"><span data-stu-id="982d5-113">Screen layout IDs can have a maximum of 10 characters.</span></span> <span data-ttu-id="982d5-114">ID は、次の 3 つの情報と順序で構成された文字列です。</span><span class="sxs-lookup"><span data-stu-id="982d5-114">The ID is a string that consists of three pieces of information, in this order:</span></span>

1. <span data-ttu-id="982d5-115">法人</span><span class="sxs-lookup"><span data-stu-id="982d5-115">Company</span></span>
2. <span data-ttu-id="982d5-116">レイアウトバージョン</span><span class="sxs-lookup"><span data-stu-id="982d5-116">Layout version</span></span>
3. <span data-ttu-id="982d5-117">個人</span><span class="sxs-lookup"><span data-stu-id="982d5-117">Persona</span></span>

### <a name="company"></a><span data-ttu-id="982d5-118">法人</span><span class="sxs-lookup"><span data-stu-id="982d5-118">Company</span></span>

| <span data-ttu-id="982d5-119">文字</span><span class="sxs-lookup"><span data-stu-id="982d5-119">Letter</span></span> | <span data-ttu-id="982d5-120">法人</span><span class="sxs-lookup"><span data-stu-id="982d5-120">Company</span></span>         |
|--------|-----------------|
| <span data-ttu-id="982d5-121">A</span><span class="sxs-lookup"><span data-stu-id="982d5-121">A</span></span>      | <span data-ttu-id="982d5-122">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="982d5-122">Adventure Works</span></span> |
| <span data-ttu-id="982d5-123">F</span><span class="sxs-lookup"><span data-stu-id="982d5-123">F</span></span>      | <span data-ttu-id="982d5-124">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="982d5-124">Fabrikam</span></span>        |
| <span data-ttu-id="982d5-125">C</span><span class="sxs-lookup"><span data-stu-id="982d5-125">C</span></span>      | <span data-ttu-id="982d5-126">Contoso</span><span class="sxs-lookup"><span data-stu-id="982d5-126">Contoso</span></span>         |

### <a name="layout-version"></a><span data-ttu-id="982d5-127">レイアウトバージョン</span><span class="sxs-lookup"><span data-stu-id="982d5-127">Layout version</span></span>

| <span data-ttu-id="982d5-128">バージョン番号</span><span class="sxs-lookup"><span data-stu-id="982d5-128">Version number</span></span> | <span data-ttu-id="982d5-129">説明</span><span class="sxs-lookup"><span data-stu-id="982d5-129">Description</span></span>                                                                                |
|----------------|--------------------------------------------------------------------------------------------|
| <span data-ttu-id="982d5-130">3</span><span class="sxs-lookup"><span data-stu-id="982d5-130">3</span></span>              | <span data-ttu-id="982d5-131">さまざまなデバイスや縦横比の複数の画面のサイズをサポートする基本バージョン</span><span class="sxs-lookup"><span data-stu-id="982d5-131">The base version that supports multiple screen sizes for various devices and aspect ratios</span></span> |
| <span data-ttu-id="982d5-132">3.1</span><span class="sxs-lookup"><span data-stu-id="982d5-132">3.1</span></span>            | <span data-ttu-id="982d5-133">**お勧めの製品**パネル用の追加サポートのある基本バージョン</span><span class="sxs-lookup"><span data-stu-id="982d5-133">The base version that has additional support for the **Recommended products** panel</span></span>        |

### <a name="persona"></a><span data-ttu-id="982d5-134">個人</span><span class="sxs-lookup"><span data-stu-id="982d5-134">Persona</span></span>

| <span data-ttu-id="982d5-135">省略形</span><span class="sxs-lookup"><span data-stu-id="982d5-135">Abbreviation</span></span> | <span data-ttu-id="982d5-136">個人</span><span class="sxs-lookup"><span data-stu-id="982d5-136">Persona</span></span>       | <span data-ttu-id="982d5-137">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="982d5-137">Contents</span></span> |
|--------------|---------------|----------|
| <span data-ttu-id="982d5-138">CSH</span><span class="sxs-lookup"><span data-stu-id="982d5-138">CSH</span></span>          | <span data-ttu-id="982d5-139">出納係</span><span class="sxs-lookup"><span data-stu-id="982d5-139">Cashier</span></span>       | <span data-ttu-id="982d5-140">レジ担当者のレイアウトには、顧客の注文、返品、割引、無効化、およびギフト カードなど、すべてのトランザクションに関連する工程が含まれます。</span><span class="sxs-lookup"><span data-stu-id="982d5-140">Cashier layouts include all transaction-related operations, such as customer orders, returns, discounts, voids, and gift cards.</span></span> <span data-ttu-id="982d5-141">これらのレイアウトには、価格チェック、在庫検索、在庫数などの在庫管理の毎日のタスクも含まれます。</span><span class="sxs-lookup"><span data-stu-id="982d5-141">These layouts also include daily tasks for inventory management, such price checks, inventory lookups, and stock counts.</span></span> <span data-ttu-id="982d5-142">開始時金額、シフトの停止、タイム レコーダーなど基本的なシフト管理も提供されます。</span><span class="sxs-lookup"><span data-stu-id="982d5-142">Basic shift management is also provided for start amounts, suspending shifts, and time clock.</span></span> |
| <span data-ttu-id="982d5-143">マネージャー</span><span class="sxs-lookup"><span data-stu-id="982d5-143">MGR</span></span>          | <span data-ttu-id="982d5-144">店長</span><span class="sxs-lookup"><span data-stu-id="982d5-144">Store Manager</span></span> | <span data-ttu-id="982d5-145">店舗マネージャー レイアウトには、キャッシュレイアウトにあるすべてのトランザクションに関連する操作の他、税の上書きも含まれます。</span><span class="sxs-lookup"><span data-stu-id="982d5-145">Store Manager layouts include all transaction-related operations that are found in the Cashier layouts but also include tax overrides.</span></span> <span data-ttu-id="982d5-146">また、これらのレイアウトには、価格チェック、在庫検索、在庫数などの在庫管理の毎日のタスクも含まれます。</span><span class="sxs-lookup"><span data-stu-id="982d5-146">These layouts also include daily tasks for inventory management, such as price checks, inventory lookups, and stock counts.</span></span> <span data-ttu-id="982d5-147">シフトの開始、停止、終了のためのシフト管理が提供されます。</span><span class="sxs-lookup"><span data-stu-id="982d5-147">Shift management is provided for starting, suspending, and closing shifts.</span></span> <span data-ttu-id="982d5-148">さらに、レイアウトには、入力、削除、支払/入金申告、金庫や銀行預金の引き出し操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="982d5-148">Additionally, the layouts include drawer operations for entries, removals, tender declarations, and safe and bank drops.</span></span> <span data-ttu-id="982d5-149">最後に、これらのレイアウトにはパフォーマンスレポートへのアクセスが含まれ、XおよびZレポートを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="982d5-149">Finally, these layouts include access to performance reports, and enable X and Z reports to be printed.</span></span> |
| <span data-ttu-id="982d5-150">STK</span><span class="sxs-lookup"><span data-stu-id="982d5-150">STK</span></span>          | <span data-ttu-id="982d5-151">在庫係</span><span class="sxs-lookup"><span data-stu-id="982d5-151">Stock Clerk</span></span>   | <span data-ttu-id="982d5-152">在庫係レイアウトは、在庫管理のために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="982d5-152">Stock Clerk layouts are optimized for inventory management.</span></span> <span data-ttu-id="982d5-153">価格チェック、在庫検索、ピッキングと入荷、在庫数確認、キット分解などの日常業務へのアクセスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="982d5-153">They include access to daily tasks for price checks, inventory lookups, picking and receiving, stock counts, and kit disassembly.</span></span> <span data-ttu-id="982d5-154">これらのレイアウトは、タイム レコーダー、シフトの停止などの基本的なシフト操作も提供します。</span><span class="sxs-lookup"><span data-stu-id="982d5-154">These layouts also provide basic shift operations for time clock and suspending shifts.</span></span> <span data-ttu-id="982d5-155">これらのレイアウトは、主にバックオフィスタスクを対象としていますが、在庫担当者はトランザクションの画面のレジ担当者と同じ操作をしています。</span><span class="sxs-lookup"><span data-stu-id="982d5-155">Although these layouts are intended mainly for back-office tasks, stock clerks have the same operations as cashiers for transaction screens.</span></span> |

### <a name="example-layout"></a><span data-ttu-id="982d5-156">レイアウトの例</span><span class="sxs-lookup"><span data-stu-id="982d5-156">Example layout</span></span>

<span data-ttu-id="982d5-157">これは、Fabrikam 社の、レイアウトバージョン 3、店長個人の画面レイアウト ID の例です。</span><span class="sxs-lookup"><span data-stu-id="982d5-157">Here is an example of a screen layout ID for the Fabrikam company, layout version 3, and the Store Manager persona:</span></span>

<span data-ttu-id="982d5-158">F3MGR</span><span class="sxs-lookup"><span data-stu-id="982d5-158">F3MGR</span></span>

<span data-ttu-id="982d5-159">次の図は、Fabrikam 店長のようこそ画面の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="982d5-159">The following illustration shows an example of the Welcome screen for a Fabrikam store manager.</span></span>

![Fabrikam 店長のようこそ画面](../retail/media/demo-screen-layouts-fig-2-2.png)

## <a name="layout-sizes"></a><span data-ttu-id="982d5-161">レイアウト サイズ</span><span class="sxs-lookup"><span data-stu-id="982d5-161">Layout sizes</span></span>

### <a name="full-vs-compact-layouts"></a><span data-ttu-id="982d5-162">圧縮レイアウト対完全</span><span class="sxs-lookup"><span data-stu-id="982d5-162">Full vs. compact layouts</span></span>

<span data-ttu-id="982d5-163">画面レイアウトには、フルデバイスとコンパクトデバイスの両方のコンフィギュレーションを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="982d5-163">A screen layout can have configurations for both full devices and compact devices.</span></span> <span data-ttu-id="982d5-164">したがって、ユーザーは、1 つの画面レイアウトに割り当てられ、さまざまなサイズとフォーム係数を店舗内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="982d5-164">Therefore, a user can be assigned to a single screen layout that will work across various sizes and form factors in the store.</span></span>

- <span data-ttu-id="982d5-165">**Modern POS - Full** - 通常、フル レイアウトは PC モニタまたはタブレットなどの大型ディスプレイに最適です。</span><span class="sxs-lookup"><span data-stu-id="982d5-165">**Modern POS - Full** – Typically, full layouts are best used for larger displays, such as desktop computer monitors or tablets.</span></span> <span data-ttu-id="982d5-166">ユーザーは、レイアウトに含まれる UI 要素を選択し、要素のサイズと配置を指定し、詳細なプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="982d5-166">Users can select the UI elements that the layout includes, specify the size and placement of those elements, and configure their detailed properties.</span></span> <span data-ttu-id="982d5-167">フル レイアウトは、縦向きおよび横向きの両方のコンフィギュレーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="982d5-167">Full layouts support both portrait and landscape configurations.</span></span>
- <span data-ttu-id="982d5-168">**Modern POS - Compact** - コンパクトなレイアウトは、通常、携帯電話や小型タブレットに最適です。</span><span class="sxs-lookup"><span data-stu-id="982d5-168">**Modern POS - Compact** – Typically, compact layouts are best used for phones or small tablets.</span></span> <span data-ttu-id="982d5-169">コンパクト デバイスでは、設計の可能性が限られています。</span><span class="sxs-lookup"><span data-stu-id="982d5-169">Design possibilities are limited for compact devices.</span></span> <span data-ttu-id="982d5-170">ユーザーは、領収書ウインドウおよび合計ウインドウの列とフィールドをコンフィギュレーションできます。</span><span class="sxs-lookup"><span data-stu-id="982d5-170">Users can configure the columns and fields for the receipt pane and the totals pane.</span></span>

### <a name="screen-resolutions-that-are-provided"></a><span data-ttu-id="982d5-171">提供される画面解像度</span><span class="sxs-lookup"><span data-stu-id="982d5-171">Screen resolutions that are provided</span></span>

<span data-ttu-id="982d5-172">次の表は、標準的な画面解像度で提供されているレイアウト サイズを示しています。</span><span class="sxs-lookup"><span data-stu-id="982d5-172">The following table shows the layout sizes that are provided for typical screen resolutions.</span></span>

| <span data-ttu-id="982d5-173">レイアウト タイプ</span><span class="sxs-lookup"><span data-stu-id="982d5-173">Layout type</span></span> | <span data-ttu-id="982d5-174">解像度</span><span class="sxs-lookup"><span data-stu-id="982d5-174">Resolution</span></span> | <span data-ttu-id="982d5-175">縦横比</span><span class="sxs-lookup"><span data-stu-id="982d5-175">Aspect ratio</span></span> | <span data-ttu-id="982d5-176">ターゲット表示</span><span class="sxs-lookup"><span data-stu-id="982d5-176">Target display</span></span>          |
|-------------|------------|--------------|-------------------------|
| <span data-ttu-id="982d5-177">最適化\*</span><span class="sxs-lookup"><span data-stu-id="982d5-177">Compact\*</span></span>   | <span data-ttu-id="982d5-178">480 × 853</span><span class="sxs-lookup"><span data-stu-id="982d5-178">480 × 853</span></span>  | <span data-ttu-id="982d5-179">16:9</span><span class="sxs-lookup"><span data-stu-id="982d5-179">16:9</span></span>         | <span data-ttu-id="982d5-180">電話</span><span class="sxs-lookup"><span data-stu-id="982d5-180">Phones</span></span>                  |
| <span data-ttu-id="982d5-181">完全</span><span class="sxs-lookup"><span data-stu-id="982d5-181">Full</span></span>        | <span data-ttu-id="982d5-182">1024 × 768</span><span class="sxs-lookup"><span data-stu-id="982d5-182">1024 × 768</span></span> | <span data-ttu-id="982d5-183">4:3</span><span class="sxs-lookup"><span data-stu-id="982d5-183">4:3</span></span>          | <span data-ttu-id="982d5-184">タブレット</span><span class="sxs-lookup"><span data-stu-id="982d5-184">Tablets</span></span>                 |
| <span data-ttu-id="982d5-185">完全\*</span><span class="sxs-lookup"><span data-stu-id="982d5-185">Full\*</span></span>      | <span data-ttu-id="982d5-186">1280 × 720</span><span class="sxs-lookup"><span data-stu-id="982d5-186">1280 × 720</span></span> | <span data-ttu-id="982d5-187">16:9</span><span class="sxs-lookup"><span data-stu-id="982d5-187">16:9</span></span>         | <span data-ttu-id="982d5-188">タブレット</span><span class="sxs-lookup"><span data-stu-id="982d5-188">Tablets</span></span>                 |
| <span data-ttu-id="982d5-189">完全</span><span class="sxs-lookup"><span data-stu-id="982d5-189">Full</span></span>        | <span data-ttu-id="982d5-190">1366 × 768</span><span class="sxs-lookup"><span data-stu-id="982d5-190">1366 × 768</span></span> | <span data-ttu-id="982d5-191">16:9</span><span class="sxs-lookup"><span data-stu-id="982d5-191">16:9</span></span>         | <span data-ttu-id="982d5-192">タブレット、大きい画面</span><span class="sxs-lookup"><span data-stu-id="982d5-192">Tablets, larger screens</span></span> |
| <span data-ttu-id="982d5-193">完全</span><span class="sxs-lookup"><span data-stu-id="982d5-193">Full</span></span>        | <span data-ttu-id="982d5-194">1440 × 960</span><span class="sxs-lookup"><span data-stu-id="982d5-194">1440 × 960</span></span> | <span data-ttu-id="982d5-195">3:2</span><span class="sxs-lookup"><span data-stu-id="982d5-195">3:2</span></span>          | <span data-ttu-id="982d5-196">タブレット、大きい画面</span><span class="sxs-lookup"><span data-stu-id="982d5-196">Tablets, larger screens</span></span> |

<span data-ttu-id="982d5-197">\*これらの追加レイアウト サイズは、Adventure WorksとFabrikamレイアウトでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="982d5-197">\* These additional layout sizes are available only in Adventure Works and Fabrikam layouts.</span></span>


>[!TIP]
> <span data-ttu-id="982d5-198">POSでは、現在のアプリケーション ウィンドウの画面解像度に使用される最も近いサイズに基づいて、レイアウトのサイズが自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="982d5-198">POS automatically selects layout sizes, based on the closest size that is available for the screen resolution of the current app window.</span></span> <span data-ttu-id="982d5-199">Retail Modern POS (MPOS) または Retail Cloud POS (CPOS) で、現在使用されている画面レイアウト ID とレイアウトの解像度を知るには、**設定** ページを開き、**セッション情報** セクションを見ます。</span><span class="sxs-lookup"><span data-stu-id="982d5-199">To find the screen layout ID and layout resolution that are currently used, in Retail Modern POS (MPOS) or Retail Cloud POS (CPOS), open the **Settings** page, and look in the **Session information** section.</span></span> <span data-ttu-id="982d5-200">現在のアプリケーションまたはブラウザーのフレームの実際のウィンドウの解像度を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="982d5-200">You can also see the actual window resolution for your current application or browser frame.</span></span> <span data-ttu-id="982d5-201">この情報を得た後に、**チャンネル設定** > **POS設定** > **POS** > **画面レイアウト**で、Retail のレイアウトコンテンツのソースを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="982d5-201">After you have this information, you can find the source of the layout content in Retail by going to **Channel setup** > **POS setup** > **POS** > **Screen layouts**.</span></span>


![Retail と POS での画面レイアウトとレイアウトの解像度/サイズ](../retail/media/demo-screen-layouts-fig-3-1.png)

## <a name="companies-and-brands"></a><span data-ttu-id="982d5-203">会社およびブランド</span><span class="sxs-lookup"><span data-stu-id="982d5-203">Companies and brands</span></span>

<span data-ttu-id="982d5-204">各架空の会社では、さまざまな小売セグメントを対象としており、会社の市場用に調整された製品カタログが含まれています。</span><span class="sxs-lookup"><span data-stu-id="982d5-204">Each fictitious company is targeted to a different retail segment and includes product catalogs that are tuned for the company's market.</span></span> <span data-ttu-id="982d5-205">各企業は、その製品に付属する独自のビジュアルブランドを持っています。</span><span class="sxs-lookup"><span data-stu-id="982d5-205">Each company has a unique visual brand that accompanies its products.</span></span> <span data-ttu-id="982d5-206">ブランド要素には、アクセントの色、濃いまたは薄いテーマ、およびエクスペリエンスを提供する付属の写真が含まれます。</span><span class="sxs-lookup"><span data-stu-id="982d5-206">Branding elements include the accent color, dark or light theme, and accompanying photographs that provide realistic experiences.</span></span>

### <a name="company-segment-and-visual-characteristics"></a><span data-ttu-id="982d5-207">会社のセグメントと視覚的な特性</span><span class="sxs-lookup"><span data-stu-id="982d5-207">Company segment and visual characteristics</span></span>

| <span data-ttu-id="982d5-208">法人</span><span class="sxs-lookup"><span data-stu-id="982d5-208">Company</span></span>         | <span data-ttu-id="982d5-209">保管場所</span><span class="sxs-lookup"><span data-stu-id="982d5-209">Location</span></span> | <span data-ttu-id="982d5-210">区分</span><span class="sxs-lookup"><span data-stu-id="982d5-210">Segment</span></span>        | <span data-ttu-id="982d5-211">アクセント</span><span class="sxs-lookup"><span data-stu-id="982d5-211">Accent</span></span> | <span data-ttu-id="982d5-212">テーマ</span><span class="sxs-lookup"><span data-stu-id="982d5-212">Theme</span></span> |
|-----------------|----------|----------------|--------|-------|
| <span data-ttu-id="982d5-213">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="982d5-213">Adventure Works</span></span> | <span data-ttu-id="982d5-214">シアトル</span><span class="sxs-lookup"><span data-stu-id="982d5-214">Seattle</span></span>  | <span data-ttu-id="982d5-215">スポーツ用品</span><span class="sxs-lookup"><span data-stu-id="982d5-215">Sporting Goods</span></span> | <span data-ttu-id="982d5-216">青</span><span class="sxs-lookup"><span data-stu-id="982d5-216">Blue</span></span>   | <span data-ttu-id="982d5-217">濃い色</span><span class="sxs-lookup"><span data-stu-id="982d5-217">Dark</span></span>  |
| <span data-ttu-id="982d5-218">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="982d5-218">Fabrikam</span></span>        | <span data-ttu-id="982d5-219">ヒューストン</span><span class="sxs-lookup"><span data-stu-id="982d5-219">Houston</span></span>  | <span data-ttu-id="982d5-220">ファッション</span><span class="sxs-lookup"><span data-stu-id="982d5-220">Fashion</span></span>        | <span data-ttu-id="982d5-221">緑</span><span class="sxs-lookup"><span data-stu-id="982d5-221">Green</span></span>  | <span data-ttu-id="982d5-222">淡い</span><span class="sxs-lookup"><span data-stu-id="982d5-222">Light</span></span> |
| <span data-ttu-id="982d5-223">Contoso</span><span class="sxs-lookup"><span data-stu-id="982d5-223">Contoso</span></span>         | <span data-ttu-id="982d5-224">ボストン</span><span class="sxs-lookup"><span data-stu-id="982d5-224">Boston</span></span>   | <span data-ttu-id="982d5-225">電子</span><span class="sxs-lookup"><span data-stu-id="982d5-225">Electronics</span></span>    | <span data-ttu-id="982d5-226">赤</span><span class="sxs-lookup"><span data-stu-id="982d5-226">Red</span></span>    | <span data-ttu-id="982d5-227">濃い色</span><span class="sxs-lookup"><span data-stu-id="982d5-227">Dark</span></span>  |


>[!NOTE]
> <span data-ttu-id="982d5-228">Adventure WorksとFabrikamは、2つの主要ブランドです。</span><span class="sxs-lookup"><span data-stu-id="982d5-228">Adventure Works and Fabrikam are the two flagship brands.</span></span> <span data-ttu-id="982d5-229">Contoso は使用可能ですが、すべてのレイアウトが提供されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="982d5-229">Contoso is available, but not all layouts have been provided.</span></span>


<span data-ttu-id="982d5-230">次の図は、3つの架空企業のようこそページとトランザクション ページの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="982d5-230">The following illustrations show examples of the welcome page and transaction page for the three fictitious companies.</span></span>

### <a name="adventure-works"></a><span data-ttu-id="982d5-231">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="982d5-231">Adventure Works</span></span>

![Adventure Works のデモ データ ウェルカムページ](../retail/media/demo-screen-layouts-fig-4-1a.png)

![Adventure Works のデモ データ トランザクションページ](../retail/media/demo-screen-layouts-fig-4-1b.png)

### <a name="fabrikam"></a><span data-ttu-id="982d5-234">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="982d5-234">Fabrikam</span></span>

![Fabrikam のデモ データ ウェルカムページ](../retail/media/demo-screen-layouts-fig-4-2a.png)

![Fabrikam のデモ データ トランザクション](../retail/media/demo-screen-layouts-fig-4-2b.png)

### <a name="contoso"></a><span data-ttu-id="982d5-237">Contoso</span><span class="sxs-lookup"><span data-stu-id="982d5-237">Contoso</span></span>

![Contosoのデモ データのレイアウト](../retail/media/demo-screen-layouts-fig-4-3.png)

## <a name="user-sign-in-matrix"></a><span data-ttu-id="982d5-239">ユーザー ログ イン マトリックス</span><span class="sxs-lookup"><span data-stu-id="982d5-239">User sign in matrix</span></span>

<span data-ttu-id="982d5-240">ユーザーには、さまざまな画面レイアウトが提供されています。</span><span class="sxs-lookup"><span data-stu-id="982d5-240">Users have been provided for the various screen layouts.</span></span> <span data-ttu-id="982d5-241">次の表を使用すると、どの画面にもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="982d5-241">By using the following table, you should be able to access any of the screens.</span></span> <span data-ttu-id="982d5-242">適切な演算子 ID を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="982d5-242">Just sign in by using an appropriate operator ID.</span></span>

| <span data-ttu-id="982d5-243">法人</span><span class="sxs-lookup"><span data-stu-id="982d5-243">Company</span></span>         | <span data-ttu-id="982d5-244">画面レイアウト ID</span><span class="sxs-lookup"><span data-stu-id="982d5-244">Screen layout ID</span></span> | <span data-ttu-id="982d5-245">個人</span><span class="sxs-lookup"><span data-stu-id="982d5-245">Persona</span></span>          | <span data-ttu-id="982d5-246">オペレーター ID</span><span class="sxs-lookup"><span data-stu-id="982d5-246">Operator IDs</span></span>           |
|-----------------|------------------|---------------   |------------------------|
| <span data-ttu-id="982d5-247">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="982d5-247">Adventure Works</span></span> | <span data-ttu-id="982d5-248">A3MGR</span><span class="sxs-lookup"><span data-stu-id="982d5-248">A3MGR</span></span>            | <span data-ttu-id="982d5-249">店長</span><span class="sxs-lookup"><span data-stu-id="982d5-249">Store Manager</span></span>    | <span data-ttu-id="982d5-250">000154, 000137, 000073</span><span class="sxs-lookup"><span data-stu-id="982d5-250">000154, 000137, 000073</span></span> |
| <span data-ttu-id="982d5-251">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="982d5-251">Adventure Works</span></span> | <span data-ttu-id="982d5-252">A3CSH</span><span class="sxs-lookup"><span data-stu-id="982d5-252">A3CSH</span></span>            | <span data-ttu-id="982d5-253">出納係</span><span class="sxs-lookup"><span data-stu-id="982d5-253">Cashier</span></span>          | <span data-ttu-id="982d5-254">000150, 000175, 000165</span><span class="sxs-lookup"><span data-stu-id="982d5-254">000150, 000175, 000165</span></span> |
| <span data-ttu-id="982d5-255">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="982d5-255">Adventure Works</span></span> | <span data-ttu-id="982d5-256">A3STK</span><span class="sxs-lookup"><span data-stu-id="982d5-256">A3STK</span></span>            | <span data-ttu-id="982d5-257">在庫係</span><span class="sxs-lookup"><span data-stu-id="982d5-257">Stock Clerk</span></span>      | <span data-ttu-id="982d5-258">000155, 000181, 000152</span><span class="sxs-lookup"><span data-stu-id="982d5-258">000155, 000181, 000152</span></span> |
| <span data-ttu-id="982d5-259">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="982d5-259">Fabrikam</span></span>        | <span data-ttu-id="982d5-260">F3MGR</span><span class="sxs-lookup"><span data-stu-id="982d5-260">F3MGR</span></span>            | <span data-ttu-id="982d5-261">店長</span><span class="sxs-lookup"><span data-stu-id="982d5-261">Store Manager</span></span>    | <span data-ttu-id="982d5-262">000160, 000168, 000163</span><span class="sxs-lookup"><span data-stu-id="982d5-262">000160, 000168, 000163</span></span> |
| <span data-ttu-id="982d5-263">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="982d5-263">Fabrikam</span></span>        | <span data-ttu-id="982d5-264">F3CSH</span><span class="sxs-lookup"><span data-stu-id="982d5-264">F3CSH</span></span>            | <span data-ttu-id="982d5-265">出納係</span><span class="sxs-lookup"><span data-stu-id="982d5-265">Cashier</span></span>          | <span data-ttu-id="982d5-266">000161, 000113, 000114</span><span class="sxs-lookup"><span data-stu-id="982d5-266">000161, 000113, 000114</span></span> |
| <span data-ttu-id="982d5-267">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="982d5-267">Fabrikam</span></span>        | <span data-ttu-id="982d5-268">F3STK</span><span class="sxs-lookup"><span data-stu-id="982d5-268">F3STK</span></span>            | <span data-ttu-id="982d5-269">在庫係</span><span class="sxs-lookup"><span data-stu-id="982d5-269">Stock Clerk</span></span>      | <span data-ttu-id="982d5-270">000164, 000112, 000123</span><span class="sxs-lookup"><span data-stu-id="982d5-270">000164, 000112, 000123</span></span> |
| <span data-ttu-id="982d5-271">Contoso</span><span class="sxs-lookup"><span data-stu-id="982d5-271">Contoso</span></span>         | <span data-ttu-id="982d5-272">C3MGR</span><span class="sxs-lookup"><span data-stu-id="982d5-272">C3MGR</span></span>            | <span data-ttu-id="982d5-273">店長</span><span class="sxs-lookup"><span data-stu-id="982d5-273">Store Manager</span></span>    | <span data-ttu-id="982d5-274">000100, 000111</span><span class="sxs-lookup"><span data-stu-id="982d5-274">000100, 000111</span></span>         |
| <span data-ttu-id="982d5-275">Contoso</span><span class="sxs-lookup"><span data-stu-id="982d5-275">Contoso</span></span>         | <span data-ttu-id="982d5-276">C3CSH</span><span class="sxs-lookup"><span data-stu-id="982d5-276">C3CSH</span></span>            | <span data-ttu-id="982d5-277">出納係</span><span class="sxs-lookup"><span data-stu-id="982d5-277">Cashier</span></span>          | <span data-ttu-id="982d5-278">000110, 000120</span><span class="sxs-lookup"><span data-stu-id="982d5-278">000110, 000120</span></span>         |
| <span data-ttu-id="982d5-279">Contoso</span><span class="sxs-lookup"><span data-stu-id="982d5-279">Contoso</span></span>         | <span data-ttu-id="982d5-280">適用できません</span><span class="sxs-lookup"><span data-stu-id="982d5-280">Not applicable</span></span>   | <span data-ttu-id="982d5-281">在庫係</span><span class="sxs-lookup"><span data-stu-id="982d5-281">Stock Clerk</span></span>      | <span data-ttu-id="982d5-282">適用できません</span><span class="sxs-lookup"><span data-stu-id="982d5-282">Not applicable</span></span>         |


>[!TIP]
> <span data-ttu-id="982d5-283">最適な結果を得るには、対応する店舗在庫場所で登録を有効にし、ログインしたときに使用するペルソナの会社に会社を設定します。</span><span class="sxs-lookup"><span data-stu-id="982d5-283">For best results, activate a register in the corresponding store location, and set the company to the company of the persona that you plan to use when you sign in.</span></span> <span data-ttu-id="982d5-284">これにより、エクスペリエンス全体で、視覚プロファイルやブランド イメージを合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="982d5-284">In this way, you help guarantee that the visual profile and branding images are aligned across the experience.</span></span> <span data-ttu-id="982d5-285">たとえば、レジ担当者用の Fabrikam レイアウトを表示する場合、ヒューストンストアのレジスターを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="982d5-285">For example, if you're interested in seeing a Fabrikam layout for a cashier, you should activate a register in the Houston store.</span></span>


<!-- Hiding until the content page is available on CustomerSource -->

<!-- ## Reference icons and images -->

<!-- The screen layouts, button grids, and visual profiles were created using images and icons that can be found in **Retail > Channel setup > POS setup > POS > Images**. -->

<!-- ![Images in Dynamics 365 for Retail](../retail/media/demo-screen-layouts-fig-5-1.png) -->

<!-- Use the [POS Icon and Image Mapping](../retail/media/POS_Icon_and_Image_Mapping.xlsx) reference spreadsheet to locate operation icons, reference photos, swap logos, or provide new images of your own that can be referenced in custom designs. -->

<!-- END HIDDEN CONTENT -->
