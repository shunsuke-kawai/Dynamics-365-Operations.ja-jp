---
title: "店舗でのフルフィルメントを設定"
description: "このトピックでは、店舗注文のフルフィルメントの設定方法における概要を説明します。"
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: 
ms.search.region: Global
ms.author: rubencdelgado
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 346f5b7a5fbbe2c41aaa54e0b36fe0c46baec0af
ms.openlocfilehash: bb4d8fae432eca7fe9163dcb0763fff5c8d465f0
ms.contentlocale: ja-jp
ms.lasthandoff: 12/20/2017

---


# <a name="set-up-order-fulfillment-for-stores"></a><span data-ttu-id="4c9d0-103">店舗における注文のフルフィルメントを設定</span><span class="sxs-lookup"><span data-stu-id="4c9d0-103">Set up order fulfillment for stores</span></span>

## <a name="overview"></a><span data-ttu-id="4c9d0-104">概要</span><span class="sxs-lookup"><span data-stu-id="4c9d0-104">Overview</span></span>
<span data-ttu-id="4c9d0-105">多くの小売業者は、注文する店舗を有効化することで、注文のフルフィルメントを最適化したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-105">Many retailers would like to optimize order fulfillment by enabling stores to fill orders.</span></span> <span data-ttu-id="4c9d0-106">店舗レベルでの注文のフルフィルメントは、特定の店舗の過剰在庫のシナリオを軽減するために役立ちます。また、店舗が余分な能力を持っているか、店舗が顧客とのより近い輸送距離内に位置する場合に、物流の視点から必要とされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-106">Order fulfillment at the store level can help to ease overstock scenarios for a specific store, or may be needed from a logistical standpoint in cases where a store has extra capacity or is located within closer shipping distance to the customer.</span></span> <span data-ttu-id="4c9d0-107">これに対処するために、販売時点管理で統一された注文のフィルフィルメントの操作が利用できます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-107">To address this need, a unified order fulfillment operation is available at the point of sale.</span></span>

<span data-ttu-id="4c9d0-108">特定の店舗でのフィルフィルメントの注文は、ヘッダーまたは注文の明細行で指示された店舗の倉庫が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-108">Orders for fulfillment at a specific store has the store's warehouse designated on the header or lines of the order.</span></span> 

<span data-ttu-id="4c9d0-109">販売時点管理での注文フルフィルメントの操作によって、注文を処理するための販売時点管理に、1 つの作業領域が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-109">The order fulfillment operation in the point of sale provides a single work area in the point of sale that can be used to process orders.</span></span> <span data-ttu-id="4c9d0-110">これには、注文の受付、出荷済にマーキング、または店舗での受け取り開始のすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-110">This includes everything from accepting the order, to marking it as shipped, or initiating store pickup.</span></span> 

## <a name="set-up-the-order-fulfillment-operation"></a><span data-ttu-id="4c9d0-111">注文のフルフィルメント操作を設定</span><span class="sxs-lookup"><span data-stu-id="4c9d0-111">Set up the order fulfillment operation</span></span>

<span data-ttu-id="4c9d0-112">注文のフルフィルメント、[操作 ID 928](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-operations)、は販売時点管理の、店舗の注文フルフィルメント作業領域へのアクセスに利用できます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-112">Order fulfillment, [Operation ID 928](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-operations), can be used to access the store order fulfillment work area in the point of sale.</span></span> 

<span data-ttu-id="4c9d0-113">手順に従って、[ボタン グリッドに工程を追加](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts) から、販売時点管理での注文のフルフィルメントを呼び出す際に使用するパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-113">Follow the steps in [Add the operation to a button grid](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts) to specify which parameter to use when invoking order fulfillment at the point of sale.</span></span> <span data-ttu-id="4c9d0-114">既定では、注文のフルフィルメント工程を指定した後、[**すべての注文**] が選択されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-114">By default, after specifying the order fulfillment operations, the **All orders** is selected.</span></span> <span data-ttu-id="4c9d0-115">このパラメーターで構成される場合に、工程が現在の店舗にてフルフィルメントの全注文明細行を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-115">When configured with this parameter, the operation will list all order lines for fulfillment at the current store.</span></span> <span data-ttu-id="4c9d0-116">また、ユーザーが店舗から出荷する注文を見たい時だけボタンに割り当てられ使用可能とされるのは、**出荷する注文** です。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-116">Also available is **Orders to ship**, which can be assigned to a button and utilized when the user only wants to see orders that will ship out of the store.</span></span> <span data-ttu-id="4c9d0-117">最後に、**集荷の注文** です。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-117">Finally, there is **Orders for pick up**.</span></span> <span data-ttu-id="4c9d0-118">販売時点管理で呼び出されると、店舗で集荷される注文のみをリストします。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-118">When invoked at the point of sale, this only lists orders to be picked up at the store.</span></span> <span data-ttu-id="4c9d0-119">別のパラメーターは、フルフィルメントの注文を表示するさまざまな方法をユーザーに付与し異なるボタンへ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-119">The different parameters can be assigned to different buttons to give the user a variety of ways to view order fulfillment.</span></span> 

### <a name="enable-users-to-access-order-fulfillment-at-the-point-of-sale"></a><span data-ttu-id="4c9d0-120">販売時点管理にて注文のフルフィルメントへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-120">Enable users to access order fulfillment at the point of sale.</span></span> 

<span data-ttu-id="4c9d0-121">注文のフルフィルメント操作は、そのまま使用できる独自のアクセス許可を持っていませんが、将来的に、ユーザーは [**注文の取得を許可**] のアクセス許可に、販売時点管理から操作の呼び出しを要求する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-121">The order fulfillment operation does not have its own permission out-of-the-box, but in the future, users may require the **Allow retrieve order** permission to invoke the operation from the point of sale.</span></span>

<span data-ttu-id="4c9d0-122">店舗レベルの構成設定では、販売時点管理の範囲内から注文明細行を手動で受け入れる必要があるかどうかを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-122">At the store level, a configuration setting is available to determines whether an order line must be accepted manually from within the point of sale.</span></span> <span data-ttu-id="4c9d0-123">構成オプションが設定されていない場合は、注文明細行は既定で承諾されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-123">If that configuration option is not set, order lines will be accepted by default.</span></span> <span data-ttu-id="4c9d0-124">構成オプションが有効とされている場合、販売時点管理のユーザーは [**注文の受け入れを許可**] のアクセス許可を取得し、販売時点管理の範囲内で注文を受け入れるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-124">If that configuration option is turned on, users at the point of sale will need to have the **Allow accept order** permission to accept orders from within the point of sale.</span></span> 


### <a name="enable-manual-order-acceptance"></a><span data-ttu-id="4c9d0-125">手動受注の有効</span><span class="sxs-lookup"><span data-stu-id="4c9d0-125">Enable manual order acceptance</span></span>

<span data-ttu-id="4c9d0-126">既定により、店舗に割り当てられる注文明細行は、[**受入済**] としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-126">Be default, order lines assigned to a store are marked as **Accepted**.</span></span> <span data-ttu-id="4c9d0-127">つまり、割り当てられた店舗から充当され、それ以上の割り当てを受けることはないと仮定されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-127">This means that it is assumed they will be fulfilled from the assigned store and will not be subject to further assignment.</span></span> <span data-ttu-id="4c9d0-128">場合によっては、小売業者が達成できる前に手動で受注希望の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-128">In certain cases, retailers may want to manually accept orders before they can be fulfilled.</span></span> <span data-ttu-id="4c9d0-129">たとえば、店舗が短期で配置され注文を達成することができない場合、店長は特定の日に適切に処理が可能だと思うほど多くの注文を受理します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-129">For example, if a store is short staffed and is unable to fulfill orders, a store manager will only accept as many orders for processing as they feel can adequately be processed in a given day.</span></span> <span data-ttu-id="4c9d0-130">注文を受理するまで、さまざまな店舗にバック オフィスで再割り当てされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-130">Until an order is accepted, it may be reassigned by the back office to a different store.</span></span> <span data-ttu-id="4c9d0-131">この方法により、注文受付は注文が店舗で認められ、達成されることを示す方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-131">In this way, order acceptance also provides a way to indicate that an order has been acknowledged by a store and will be fulfilled.</span></span> 

<span data-ttu-id="4c9d0-132">店舗集配の注文明細行は、常に [**"保留中"**] とマークされ、受理の対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-132">Order lines for store pickup are marked as always marked as **Pending** and are not subject to acceptance.</span></span>

<span data-ttu-id="4c9d0-133">手動受け入れまたは注文明細行を有効にするには、**小売** > **チャンネル** > **小売店舗** > **すべての小売店舗** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-133">To turn on manual acceptance or order lines, navigate to **Retail** > **Channels** > **Retail stores** > **All retail stores**.</span></span> <span data-ttu-id="4c9d0-134">店舗を選択し、店舗の詳細を表示する店舗 ID をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-134">Select the store and click in the store ID to view the store's details.</span></span> <span data-ttu-id="4c9d0-135">[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-135">Click **Edit**.</span></span> <span data-ttu-id="4c9d0-136">[**一般**] クイック タブで、[**注文のフルフィルメント**] サブ ヘッダーを選び、[**いいえ**] から [**はい**] に **手動受理** を変更します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-136">On the **General** FastTab, locate the **Order fulfillment** subheader and change **Manual accept** from **No** to **Yes**.</span></span> 

### <a name="enable-reject-order-line-capability"></a><span data-ttu-id="4c9d0-137">注文明細行の機能の拒否を有効</span><span class="sxs-lookup"><span data-stu-id="4c9d0-137">Enable reject order line capability</span></span>

<span data-ttu-id="4c9d0-138">注文明細行は、販売時点管理からも拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-138">Order lines can also be rejected from the point of sale.</span></span> <span data-ttu-id="4c9d0-139">注文明細行の拒否すると、その店舗では実行されず、注文明細行が別の店舗または倉庫に再割り当てされます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-139">Rejecting an order line signifies that it will not be fulfilled at that store and sends the order line back for reassignment to another store or warehouse.</span></span> <span data-ttu-id="4c9d0-140">注文明細行の否認アクセス許可は、作業者に関連付けられる POS アクセス許可グループの [**否認注文の許可**] のアクセス許可を通して付与されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-140">Order line rejection permission is granted through the **Allow reject order** permission in the POS permission group associated with the worker.</span></span> <span data-ttu-id="4c9d0-141">明細行を否認する間、小売業者は作業者に拒否の理由を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-141">While rejecting a line, the retailers can mandate their workers to provide a reason for rejection.</span></span> <span data-ttu-id="4c9d0-142">これは、[**情報コード活動**] タイプの [**注文のフルフィルメント**] 情報コードを使用し、チャンネルに関連付けられている機能プロファイルの [**注文明細行の否認**] に情報コードを割り当てることで実現できます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-142">This can be achieved by using info codes of **Info code activity** type **Order fulfillment** and assigning the info code to **Reject order line** in the functionality profile associated with the channel.</span></span> 

>[!Note]
><span data-ttu-id="4c9d0-143">[**情報コード活動**] タイプの [**注文のフルフィルメント**] 情報コードのみが、[**"注文明細行の否認**] アクションに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-143">Only the info codes of **Info code activity** type **Order fulfillment** can be assigned to the **"Reject order line** action.</span></span>

### <a name="synchronize-changes-to-the-channel-database"></a><span data-ttu-id="4c9d0-144">チャンネル データベースへの変更の同期</span><span class="sxs-lookup"><span data-stu-id="4c9d0-144">Synchronize changes to the channel database</span></span>

<span data-ttu-id="4c9d0-145">ボタン グリッドに工程が割り当てられた後、適切なアクセス許可が割り当てられ、そしてチャンネルがコンフィギュレーションされると、その変更はチャンネルのデータベースに同期させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-145">After the operation has been assigned to a button grid, the proper permissions have been assigned, and the channel is configured, the changes must be synchronized to the channel database.</span></span> <span data-ttu-id="4c9d0-146">そして、**小売** > **小売 IT** > **配送スケジュール** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-146">To do so, navigate to **Retail** > **Retail IT** > **Distribution schedule**.</span></span> <span data-ttu-id="4c9d0-147">スケジュール「1090 - レジスター」を選択し、ボタン グリッドの変更を同期した後、[**今すぐ実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-147">Select schedule "1090-Registers" to sync button grid changes and then click **Run now**.</span></span> <span data-ttu-id="4c9d0-148">次に、「1060 - スタッフ」を選択することで、アクセス許可の変更を同期し、[**今すぐ実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-148">Next, sync permissions changes by selecting "1060-Staff" and then click **Run now**.</span></span> <span data-ttu-id="4c9d0-149">次に、「1070 - チャンネル コンフィギュレーション」を選択することで、チャンネルの変更を同期し、[**今すぐ実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-149">Next, sync channel changes by selecting "1070-Channel configuration" and click **Run now**.</span></span> <span data-ttu-id="4c9d0-150">最後に、「1110 - グローバル コンフィギュレーション」を選択することで、新たに作成された否認理由の情報コードを同期し、[**今すぐ実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-150">Finally, sync the newly created info code for reject reason by selecting the "1110-Global configuration" and click **Run now**.</span></span>

## <a name="use-order-fulfillment-at-the-point-of-sale"></a><span data-ttu-id="4c9d0-151">販売時点管理での注文のフルフィルメントを使用</span><span class="sxs-lookup"><span data-stu-id="4c9d0-151">Use order fulfillment at the point of sale</span></span>

<span data-ttu-id="4c9d0-152">販売時管理を開き、注文のフルフィルメント操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-152">Open the point of sale and select the order fulfillment operation.</span></span> <span data-ttu-id="4c9d0-153">構成方法によっては、すべての明細行、集荷の注文明細行または注文明細行の出荷が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-153">Depending on how it is configured, either all lines, order lines for pickup, or order lines to ship will be listed.</span></span> 

### <a name="order-fulfillment-view"></a><span data-ttu-id="4c9d0-154">注文のフルフィルメントの表示</span><span class="sxs-lookup"><span data-stu-id="4c9d0-154">Order fulfillment view</span></span> 

<span data-ttu-id="4c9d0-155">注文のフルフィルメントの表示は、店舗でフルフィルメントの注文明細行をリストし、次の列を含みます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-155">The order fulfillment view lists order lines for fulfillment at the store and includes the following columns:</span></span>

  - <span data-ttu-id="4c9d0-156">注文番号</span><span class="sxs-lookup"><span data-stu-id="4c9d0-156">Order number</span></span>
  - <span data-ttu-id="4c9d0-157">製品番号</span><span class="sxs-lookup"><span data-stu-id="4c9d0-157">Product number</span></span>
  - <span data-ttu-id="4c9d0-158">説明</span><span class="sxs-lookup"><span data-stu-id="4c9d0-158">Description</span></span>
  - <span data-ttu-id="4c9d0-159">注文済数量</span><span class="sxs-lookup"><span data-stu-id="4c9d0-159">Quantity ordered</span></span>
  - <span data-ttu-id="4c9d0-160">配送指定日</span><span class="sxs-lookup"><span data-stu-id="4c9d0-160">Requested delivery date</span></span>
  - <span data-ttu-id="4c9d0-161">顧客名</span><span class="sxs-lookup"><span data-stu-id="4c9d0-161">Customer name</span></span>
  - <span data-ttu-id="4c9d0-162">フルフィルメントの状態</span><span class="sxs-lookup"><span data-stu-id="4c9d0-162">Fulfillment status</span></span>
  
<span data-ttu-id="4c9d0-163">特定の注文明細行の追加情報は、注文明細行を選択して、ログインした販売時点管理ヘッダーに表示されるユーザー / シフト情報のすぐ下にあるポップ アップ メニューを開けることで、表示可能になります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-163">Additional information for a specific order line can be viewed by selecting the order line and then opening the flyout menu located just below the logged in user/shift information shown in the point of sale header.</span></span> <span data-ttu-id="4c9d0-164">このメニューには、明細行の詳細用と注文詳細用の 2 つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-164">This menu includes 2 tabs: one for line details and another for order details.</span></span> <span data-ttu-id="4c9d0-165">明細行の詳細タブには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-165">The line details tab includes the following information:</span></span>

  - <span data-ttu-id="4c9d0-166">注文済数量</span><span class="sxs-lookup"><span data-stu-id="4c9d0-166">Quantity ordered</span></span>
  - <span data-ttu-id="4c9d0-167">出荷 / 集配されある残りの数量</span><span class="sxs-lookup"><span data-stu-id="4c9d0-167">Quantity remaining to be shipped/picked up</span></span>
  - <span data-ttu-id="4c9d0-168">ピッキング済数量</span><span class="sxs-lookup"><span data-stu-id="4c9d0-168">Quantity picked</span></span>
  - <span data-ttu-id="4c9d0-169">梱包済数量</span><span class="sxs-lookup"><span data-stu-id="4c9d0-169">Quantity packed</span></span>
  - <span data-ttu-id="4c9d0-170">請求済数量 (既に集配または出荷済)</span><span class="sxs-lookup"><span data-stu-id="4c9d0-170">Quantity invoiced (already picked up or shipped)</span></span>
  - <span data-ttu-id="4c9d0-171">荷渡方法</span><span class="sxs-lookup"><span data-stu-id="4c9d0-171">Mode of delivery</span></span>
  - <span data-ttu-id="4c9d0-172">配送先住所</span><span class="sxs-lookup"><span data-stu-id="4c9d0-172">Delivery address</span></span>
  
<span data-ttu-id="4c9d0-173">ポップ アップ メニューの詳細は、以下のような複数の注文レベルの詳細を提供するタブもあります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-173">The details flyout menu also has a tab that provides more order level details including:</span></span>

  - <span data-ttu-id="4c9d0-174">顧客名</span><span class="sxs-lookup"><span data-stu-id="4c9d0-174">Customer name</span></span>
  - <span data-ttu-id="4c9d0-175">顧客 ID</span><span class="sxs-lookup"><span data-stu-id="4c9d0-175">Customer ID</span></span>
  - <span data-ttu-id="4c9d0-176">注文番号</span><span class="sxs-lookup"><span data-stu-id="4c9d0-176">Order number</span></span>
  - <span data-ttu-id="4c9d0-177">注文合計</span><span class="sxs-lookup"><span data-stu-id="4c9d0-177">Order total</span></span>
  - <span data-ttu-id="4c9d0-178">注文残高</span><span class="sxs-lookup"><span data-stu-id="4c9d0-178">Order balance</span></span>
  
<span data-ttu-id="4c9d0-179">注文フルフィルメント表示の下部は、アクション ペインです。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-179">At the bottom of the order fulfillment view is an Action Pane.</span></span> <span data-ttu-id="4c9d0-180">注文の明細行に対して実行できる全てのアクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-180">This contains all of the actions that can be taken against an order line.</span></span> <span data-ttu-id="4c9d0-181">明細行の状態に基づいてアクションが利用できない場合、、そのアクションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-181">If an action is not available based on a line's status, that action will be unavailable.</span></span> 

<span data-ttu-id="4c9d0-182">既定では、注文は [**受入済**] の状態になります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-182">By default, orders will have a status of **Accepted**.</span></span> <span data-ttu-id="4c9d0-183">注文の状態は、注文明細行の一覧に列として表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-183">Order status can be viewed as a column in the list of order lines.</span></span> <span data-ttu-id="4c9d0-184">チャンネル レベルで [**手動受け入れ**] がコンフィギュレーションされている場合、出荷済の全ての明細行では [**"保留中"**] と表示され、達成可能になる前に、受理される必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-184">If **Manual accept** is configured at the channel level, all lines to be shipped will show as **Pending** and must be accepted before they can be fulfilled.</span></span> <span data-ttu-id="4c9d0-185">既定では、店舗集配の注文は [**"保留中"**] となり、受理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-185">Orders for store pickup are **Pending** by default and do not need to be accepted.</span></span>

### <a name="order-fulfillment-line-actions"></a><span data-ttu-id="4c9d0-186">注文フルフィルメントの明細行アクション</span><span class="sxs-lookup"><span data-stu-id="4c9d0-186">Order fulfillment line actions</span></span>

<span data-ttu-id="4c9d0-187">**編集** - 注文状態が保留中の場合、販売時点管理では編集が可能です。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-187">**Edit** - If an order status is pending, it can be edited at the point of sale.</span></span> <span data-ttu-id="4c9d0-188">既に部分的にピッキング、梱包、または請求済の注文は、注文のフルフィルメント表示からは編集できません。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-188">Orders that have already been partially picked, packed, or invoiced cannot be edited from the order fulfillment view.</span></span>

<span data-ttu-id="4c9d0-189">**受け入れ** - チャンネル レベルで [**手動受け入れ**] がコンフィギュレーションされる場合、明細行は注文フルフィルメントのプロセスを通過できる前に、最初に受け入れなければなりません。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-189">**Accept** - If **Manual accept** is configured at the channel level, lines must be first accepted before they can move through the order fulfillment process.</span></span>

<span data-ttu-id="4c9d0-190">[**ピッキング**] - ピッキング オプションは、いくつかのアクションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-190">**Pick** - The pick option supports several actions.</span></span> <span data-ttu-id="4c9d0-191">最初に、[**ピッキング**] が注文明細行のステータスを更新し、店舗の他のユーザーが同じ明細行をピッキングしないようにします。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-191">First, **Picking** updates the status of the order line so others in the store do not attempt to pick the same line.</span></span> <span data-ttu-id="4c9d0-192">次に、[**ピッキング リストの印刷**] で選択した明細行または明細行のピッキング リストを印刷し、その状態を [**ピッキング**] に更新します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-192">Next, **Print picking list** prints a picking list for the selected line or lines and also updates their status to **Picking**.</span></span> <span data-ttu-id="4c9d0-193">ピッキング リストの形式は、レシートの形式の一部として制御されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-193">Picking list formats are controlled as part of receipt formats.</span></span> <span data-ttu-id="4c9d0-194">レシート形式の設定方法の詳細については、[レシート テンプレートと印刷](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-194">For more information about how to set up receipt formats, see [Receipt templates and printing](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing).</span></span> <span data-ttu-id="4c9d0-195">最後に、[**ピッキング済としてマーク**] は明細行がピッキングされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-195">Finally, **Mark as picked** indicates the line has been picked.</span></span> <span data-ttu-id="4c9d0-196">[**ピッキング済としてマーク**] は、バック オフィスでの在庫トランザクションの対応を開始します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-196">**Mark as picked** initiates corresponding inventory transactions in the back office.</span></span> <span data-ttu-id="4c9d0-197">同時にすべての荷渡方法や注文間での複数の注文明細行のアクションに対して、ピッキング アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-197">Picking actions can be performed at the same time for multiple order lines across orders and for all modes of delivery.</span></span>

<span data-ttu-id="4c9d0-198">**否認** - 明細行または部分的な明細行を否認することができます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-198">**Reject** - Lines or partial lines can be rejected.</span></span> <span data-ttu-id="4c9d0-199">これにより、バックオフィスから別の店舗または倉庫に再割り当てが行われます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-199">This allows them to be reassigned from the back office to another store or warehouse.</span></span> <span data-ttu-id="4c9d0-200">明細行は、まだピッキングまたは梱包がされていない場合にのみ否認することができます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-200">Lines can only be rejected if they have not yet been picked or packed.</span></span> <span data-ttu-id="4c9d0-201">既にピッキングの梱包済みの明細行を否認するには、バック オフィスからその明細行のピッキングまたは梱包を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-201">To reject a line that has already been picked or packed, that line must be unpicked or unpacked from the back office.</span></span> 

<span data-ttu-id="4c9d0-202">**梱包** - 梱包オプションでは、選択した明細行の梱包明細を印刷する [**梱包明細の印刷**] アクションと、梱包済みとして明細行をマークしそしてバック オフィスで出荷済みとして明細行をマークする [**梱包済みとしてマーク**] アクションの 2 つのアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-202">**Pack** - The pack option supports two actions: **Print packing slip** will print a packing slip for the selected lines and **Mark as packed** will and mark the lines as packed and mark the lines as delivered in the back office.</span></span> <span data-ttu-id="4c9d0-203">同じ注文に属し、同じ荷渡方法である唯一の注文明細行は、同時に梱包することができます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-203">Only order lines that belong to the same order and have the same mode of delivery can be packed at the same time.</span></span> <span data-ttu-id="4c9d0-204">梱包明細の形式は、レシートの形式の一部として制御します。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-204">Packing slip formats are controlled as part of receipt formats.</span></span> <span data-ttu-id="4c9d0-205">レシート形式の設定方法の詳細については、[レシート テンプレートと印刷](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-205">For more information about how to set up receipt formats, see [Receipt templates and printing](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing).</span></span>

<span data-ttu-id="4c9d0-206">**出荷** - 出荷アクションでは、バック オフィスで [**出荷済**] として選択された明細行にマークします。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-206">**Ship** - The ship action will mark selected lines as **Delivered** in the back office.</span></span> <span data-ttu-id="4c9d0-207">明細行が完全に出荷された後は、もはや店舗のフルフィルメント表示に出ません。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-207">After a line has been fully shipped, it will no longer appear in the store fulfillment view.</span></span>

<span data-ttu-id="4c9d0-208">**集配** - 集配アクションでは、集配のトランザクション表示に明細行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-208">**Pickup** - The pickup action adds the lines to the transaction view for pickup.</span></span> <span data-ttu-id="4c9d0-209">現在集配されない注文の他の明細行がある場合、数量ゼロのトランザクション表示に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-209">If there are other lines on the order that aren't currently being picked up, they will be added to the transaction view with quantity zero.</span></span> <span data-ttu-id="4c9d0-210">明細行が完全に集配された後、もはや注文のフルフィルメント表示に出ません。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-210">After a line has been fully picked up, it will no longer appear in the order fulfillment view.</span></span> 

### <a name="order-fulfillment-filtering"></a><span data-ttu-id="4c9d0-211">注文のフルフィルメント フィルター</span><span class="sxs-lookup"><span data-stu-id="4c9d0-211">Order fulfillment filtering</span></span>

<span data-ttu-id="4c9d0-212">販売時点管理の注文のフルフィルメントは、フィルター処理が含まれており、必要なものをユーザーが検索しやすくなるようになります。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-212">Order fulfillment at the point of sale includes filtering to help the user easily find what they need.</span></span> <span data-ttu-id="4c9d0-213">フィルターは、[**販売時点管理**] 画面の下部にあるアクション ペイン上で変更できます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-213">Filters can be changed on the Action Pane at the bottom of the **Point of sale** screen.</span></span> <span data-ttu-id="4c9d0-214">既定では、工程の設定に基づいて、**配送タイプ**フィルターが適用されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-214">By default, a **Delivery type** filter is applied, based on how the operation is set up.</span></span> <span data-ttu-id="4c9d0-215">工程が、パラメーター [**すべての注文**] で設定されている場合、注文のフルフィルメントにアクセスすると、そのフィルターは適用されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-215">If the operation is set up with the parameter **All orders**, then that filter is applied when accessing order fulfillment.</span></span> <span data-ttu-id="4c9d0-216">同じことが [**店舗集配**] および [**ストアから出荷**] パラメータに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4c9d0-216">The same applies for the **Store pickup** and **Ship from store** parameters.</span></span> <span data-ttu-id="4c9d0-217">注文のフルフィルメントの表示に適用可能なその他のフィルターが含まれます:</span><span class="sxs-lookup"><span data-stu-id="4c9d0-217">Other filters that can be applied to the order fulfillment view include:</span></span>

  - <span data-ttu-id="4c9d0-218">顧客番号</span><span class="sxs-lookup"><span data-stu-id="4c9d0-218">Customer number</span></span>
  - <span data-ttu-id="4c9d0-219">顧客名</span><span class="sxs-lookup"><span data-stu-id="4c9d0-219">Customer name</span></span>
  - <span data-ttu-id="4c9d0-220">顧客の電子メール</span><span class="sxs-lookup"><span data-stu-id="4c9d0-220">Customer email</span></span>
  - <span data-ttu-id="4c9d0-221">注文番号</span><span class="sxs-lookup"><span data-stu-id="4c9d0-221">Order number</span></span>
  - <span data-ttu-id="4c9d0-222">荷渡方法</span><span class="sxs-lookup"><span data-stu-id="4c9d0-222">Mode of delivery</span></span>
  - <span data-ttu-id="4c9d0-223">受領番号</span><span class="sxs-lookup"><span data-stu-id="4c9d0-223">Receipt number</span></span>
  - <span data-ttu-id="4c9d0-224">チャネル参照 ID</span><span class="sxs-lookup"><span data-stu-id="4c9d0-224">Channel Reference ID</span></span>
  - <span data-ttu-id="4c9d0-225">元の店舗番号</span><span class="sxs-lookup"><span data-stu-id="4c9d0-225">Originating store number</span></span>
  - <span data-ttu-id="4c9d0-226">行ステータス</span><span class="sxs-lookup"><span data-stu-id="4c9d0-226">Line status</span></span>
  - <span data-ttu-id="4c9d0-227">作成日</span><span class="sxs-lookup"><span data-stu-id="4c9d0-227">Created date</span></span>
  - <span data-ttu-id="4c9d0-228">出荷日</span><span class="sxs-lookup"><span data-stu-id="4c9d0-228">Delivery date</span></span>
  - <span data-ttu-id="4c9d0-229">入荷日</span><span class="sxs-lookup"><span data-stu-id="4c9d0-229">Receipt date</span></span>
