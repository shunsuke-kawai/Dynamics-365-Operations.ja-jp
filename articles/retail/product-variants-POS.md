---
title: "販売時点管理の在庫検索"
description: "このトピックでは、販売時点管理 (POS) での在庫情報を表示するために使用できるオプションについて説明します。"
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: ff11cf7b23c48675b108d7d03d241fcec2cb792a
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="inventory-lookup-in-the-point-of-sale"></a><span data-ttu-id="9aec6-103">販売時点管理の在庫検索</span><span class="sxs-lookup"><span data-stu-id="9aec6-103">Inventory lookup in the Point of Sale</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="9aec6-104">販売時点管理 (POS) での在庫の検索は、小売業者がリアルタイムのオペレーショナル エクセレンスを達成し、店舗、POS、およびバック オフィスに接続することにより情報を取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9aec6-104">Inventory lookup in the point of sale (POS) helps retailers achieve real-time operational excellence and gain insights by connecting stores, the POS, and the back office.</span></span> <span data-ttu-id="9aec6-105">この機能は、店舗と流通センター間での製品在庫の正確なリアルタイム ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-105">This functionality provides an accurate real-time view of product inventory across stores and distribution centers.</span></span> <span data-ttu-id="9aec6-106">また、リアルタイムで計画在庫を改善することにより、小売業者がさらに効率性およびコスト削減を向上するのを助けます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-106">It also helps retailers drive additional efficiencies and cost savings by improving inventory planning in real time.</span></span>

<span data-ttu-id="9aec6-107">組織間の在庫の正確なリアルタイム表示により、店舗関係者が適切なタイミングで、より優れた顧客サービスを提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9aec6-107">An accurate real-time view of inventory across an organization helps store associates provide timely, superior customer service.</span></span> <span data-ttu-id="9aec6-108">最も重要な時点は、顧客が購入決定をする準備ができている時点です。</span><span class="sxs-lookup"><span data-stu-id="9aec6-108">The moment that matters most is the moment when the customer is ready to make a purchase decision.</span></span> <span data-ttu-id="9aec6-109">製品の出荷や受取を正確に保証できるように、店舗のレジ担当者が、リアルタイムの在庫情報に精通していることが重要です。</span><span class="sxs-lookup"><span data-stu-id="9aec6-109">It's important that cashiers in the store have real-time inventory information at their fingertips, so that they can accurately promise product delivery and pickup.</span></span>

<span data-ttu-id="9aec6-110">[**Retail Modern POS**] ワークスペースまたは [**Retail Cloud POS**] ワークスペースから [**在庫検索**] ページを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-110">You can open the **Inventory lookup** page from the **Retail Modern POS** workspace or the **Retail Cloud POS** workspace.</span></span>

![POS ホーム ページの在庫検索タイル](media/POSHomepage.png)

<span data-ttu-id="9aec6-112">[**在庫検索**] ページで、数値キーボードを使用して、製品番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-112">On the **Inventory lookup** page, you can use the numeric keyboard to enter a product number.</span></span> <span data-ttu-id="9aec6-113">次に複数の店舗および倉庫の手持ち在庫数量を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-113">You can then view the on-hand quantity for multiple stores and warehouses.</span></span>

![標準の在庫検索ページ](media/InventoryLookUp.png)

<span data-ttu-id="9aec6-115">**引当済** および **注文済** 数量も各場所ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-115">**Reserved** and **Ordered** quantities are also shown for each location.</span></span>

- <span data-ttu-id="9aec6-116">**引当済** – この数量は、その場所で指定した商品番号に対するバック オフィスからの **引当済現物数** 値を参照します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-116">**Reserved** – This quantity refers to the **Physical reserved** value from the back office for the specified product number at the location.</span></span>
- <span data-ttu-id="9aec6-117">**注文済** – この数量は、その場所で指定した商品番号に対するバック オフィスからの **発注済合計数** 値を参照します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-117">**Ordered** – This quantity refers to the **Ordered in total** value from the back office for the specified product number at the location.</span></span>

## <a name="locations-that-inventory-availability-information-is-shown-for"></a><span data-ttu-id="9aec6-118">在庫の使用可能な情報が表示される場所</span><span class="sxs-lookup"><span data-stu-id="9aec6-118">Locations that inventory availability information is shown for</span></span>

<span data-ttu-id="9aec6-119">場所のリストには、エンティティの 2 つのタイプが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-119">The list of locations includes two types of entities:</span></span>

- <span data-ttu-id="9aec6-120">**小売店舗** – Retail で現在の店舗に対する店舗ロケーター グループを使用してコンフィギュレーションされる店舗の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-120">**Retail stores** – The list shows stores that are configured by using the store locator group for the current store in the Retail headquarters.</span></span> 
- <span data-ttu-id="9aec6-121">**流通センター** – 物流センター (倉庫など) のさまざまなタイプを Microsoft Dynamics 365 for Retail でコンフィギュレーションできます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-121">**Distribution centers** – Various types of distribution centers (such as warehouses) can be configured in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="9aec6-122">ただし、一覧は **標準** 既定のタイプの物流センターに対してのみ使用可能な在庫情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-122">However, the list shows inventory availability information only for distribution centers of the **Standard** default type.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="9aec6-123">使用可能な在庫情報は、POS の **輸送**、**検査**、および **ルートの商品** タイプの倉庫に対しては表示されません。</span><span class="sxs-lookup"><span data-stu-id="9aec6-123">Inventory availability information isn't shown for warehouses of the **Transit**, **Quarantine**, and **Goods in Route** types for the POS.</span></span>

<span data-ttu-id="9aec6-124">[**在庫検索**] ページで、現在の手持在庫数量、引当数量、および注文済数量に加えて、各店舗の納期回答可能在庫 (ATP) 数量を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-124">On the **Inventory lookup** page, you can view available to promise (ATP) quantities for each store, in addition to the current on-hand quantities, reserved quantities, and ordered quantities.</span></span> <span data-ttu-id="9aec6-125">ATP 情報を表示する店舗を選択し、次に **店舗の使用可能性を表示** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-125">Select the store to view the ATP information for, and then select **Show store availability**.</span></span>

![ATP 数量](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a><span data-ttu-id="9aec6-127">すべてのバリアントを表示するマトリックス ビューに基づく分析コードを開く</span><span class="sxs-lookup"><span data-stu-id="9aec6-127">Opening the Dimension based matrix view to show all variants</span></span>

<span data-ttu-id="9aec6-128">製品マスターの [**製品の詳細** ]ページ、または [**在庫検索**] ページで、ページの下部にあるアプリケーション バーから [**すべてのバリアントの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-128">On the **Product details** page of a product master, or on the **Inventory lookup** page, select **View all variants** from the app-bar at bottom of the page.</span></span> <span data-ttu-id="9aec6-129">これらのページからの初期起動に対する [**分析コードに基づくマトリックス**] ビューは、現在の店舗の製品のすべてのバリアントに対して使用可能な在庫情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-129">The **Dimension based matrix** view for the initial launch from these pages shows the inventory availability information for all variants of a product for the current store.</span></span>

> [!NOTE]
> <span data-ttu-id="9aec6-130">[**すべてのバリアントの表示**] ボタンは、製品バリアントを持つ品目製品マスターに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-130">The **View all variants** button is available only for item product masters that have product variants.</span></span> <span data-ttu-id="9aec6-131">スタンドアロン製品やキットには使用できません。</span><span class="sxs-lookup"><span data-stu-id="9aec6-131">It isn't available for standalone products or kits.</span></span>

![在庫検索ページですべてのバリアント ボタンを表示します](media/StandardToMatrix.png)

<span data-ttu-id="9aec6-133">製品マスターの [**製品の詳細**] ページの [**すべてのバリアントを表示**] を選択して、または [**在庫検索**] ページで、場所を選択せずに、現在の店舗の製品のすべてのバリアントに対して使用可能な在庫情報を表示する [**分析コード に基づくマトリックス**] ビューに移動します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-133">Select **View all variants** on the **Product details** page of a product master, or on the **Inventory lookup** page, without selecting a location, to go to the **Dimension based matrix** view to view the inventory availability information for all variants of a product for the current store.</span></span>

![在庫検索ぺージに対する分析コードに基づくマトリックス ビュー](media/Matrix.png)

> [!NOTE]
> <span data-ttu-id="9aec6-135">前の図では、選択した製品に対して分析コードの表示順序が構成されていなかったため、分析コードの表示順序はアルファベット順です。</span><span class="sxs-lookup"><span data-stu-id="9aec6-135">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="9aec6-136">[**分析コードに基づくマトリックス**] ビューで、製品バリアントのセルには、右下隅にある手持在庫の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9aec6-136">In the **Dimension based matrix** view, the cells for the product variants include an on-hand value in the lower-right corner.</span></span> <span data-ttu-id="9aec6-137">次の表では、さまざまな値の意味について説明します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-137">The following table explains the meaning of the various values.</span></span>

| <span data-ttu-id="9aec6-138">手持の金額</span><span class="sxs-lookup"><span data-stu-id="9aec6-138">On-hand value</span></span>                            | <span data-ttu-id="9aec6-139">説明</span><span class="sxs-lookup"><span data-stu-id="9aec6-139">Description</span></span> |
|------------------------------------------|-------------|
| <span data-ttu-id="9aec6-140">0 (ゼロ) よりも大きい数値</span><span class="sxs-lookup"><span data-stu-id="9aec6-140">Numeric value that is more than 0 (zero)</span></span> | <span data-ttu-id="9aec6-141">バリアントは選択した場所にリリースされており、セルに追加のアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-141">A variant has been released to the selected location, and you can perform additional actions in the cell.</span></span> <span data-ttu-id="9aec6-142">(これらのアクションについては、このトピックの後半で、詳しく説明します。)</span><span class="sxs-lookup"><span data-stu-id="9aec6-142">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="9aec6-143">**0** (ゼロ)</span><span class="sxs-lookup"><span data-stu-id="9aec6-143">**0** (zero)</span></span>                             | <span data-ttu-id="9aec6-144">バリアントが選択した場所にリリースされていても、品目は選択した場所で使用できません。</span><span class="sxs-lookup"><span data-stu-id="9aec6-144">A variant has been released to the selected location, but the item isn't available in selected location.</span></span> <span data-ttu-id="9aec6-145">ただし、セルに追加のアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-145">However, you can perform additional actions in the cell.</span></span> <span data-ttu-id="9aec6-146">(これらのアクションについては、このトピックの後半で、詳しく説明します。)</span><span class="sxs-lookup"><span data-stu-id="9aec6-146">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="9aec6-147">**該当なし** または無効なセル</span><span class="sxs-lookup"><span data-stu-id="9aec6-147">**n/a** or an inactive cell</span></span>              | <span data-ttu-id="9aec6-148">バリアントは選択した場所にリリースされておらず、セルに追加のアクションを実行することができません。</span><span class="sxs-lookup"><span data-stu-id="9aec6-148">A variant hasn't been released to the selected location, and you can't perform additional actions in the cell.</span></span> |

<span data-ttu-id="9aec6-149">使用する新しい分析コードを選択することで、分析コードのピボットを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-149">You can also change the pivot for dimensions by selecting the new dimension to use.</span></span> 

![ピボットを変更します](media/ChangePivot.png)

![変更済ピボット](media/PivotChanged.png)

> [!NOTE]
> <span data-ttu-id="9aec6-152">前の図では、選択した製品の分析コードの表示順序がユーザー設定 (アルファベットでない) です。</span><span class="sxs-lookup"><span data-stu-id="9aec6-152">In the preceding illustrations, the display order of the dimensions for the selected product is custom (non-alphabetic).</span></span> <span data-ttu-id="9aec6-153">バック オフィスで設定されている分析コードの表示順序に基づいています。</span><span class="sxs-lookup"><span data-stu-id="9aec6-153">It's based on the dimension display order that is set in the back office.</span></span>

<span data-ttu-id="9aec6-154">また、[**分析コードに基づくマトリックス**] ビューで、店舗スタッフの生産性を向上させるためにその他のアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-154">Additionally, in the **Dimension based matrix** view, more actions can be performed to help boost a store associate's productivity.</span></span> <span data-ttu-id="9aec6-155">次にいくつか例を挙げます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-155">Here are some examples:</span></span>

- <span data-ttu-id="9aec6-156">他の場所でのすべての製品バリアントの引当可能在庫数を検索するため、店舗の場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-156">Change the store location to look up the inventory availability of all product variants at other locations.</span></span> <span data-ttu-id="9aec6-157">これらの場所には、**標準** 既定のタイプの店舗ロケーター グループおよび流通センターに他の店舗を含みます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-157">These locations include other stores in the store locator group and distribution centers of the **Standard** default type.</span></span>
- <span data-ttu-id="9aec6-158">現金売り、店舗の受取、またはアドレスへの出荷を使用して、顧客に個々の製品バリアントを販売します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-158">Sell an individual product variant to a customer by using cash and carry, in-store pickup, or shipment to an address.</span></span>
- <span data-ttu-id="9aec6-159">特定の場所での個々の製品バリアントに対する ATP 情報を、顧客に提供します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-159">Provide the customer with ATP information for an individual product variant at a specific location.</span></span>

![バリアント タイルでの追加のアクション](media/VariantActions.png)

> [!NOTE]
> <span data-ttu-id="9aec6-161">前の図では、選択した製品に対して分析コードの表示順序が構成されていなかったため、分析コードの表示順序はアルファベット順です。</span><span class="sxs-lookup"><span data-stu-id="9aec6-161">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="9aec6-162">以下の表で、利用できる追加のアクションに関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-162">The following table provides more information about the additional actions that are available.</span></span>


|        <span data-ttu-id="9aec6-163">アクション</span><span class="sxs-lookup"><span data-stu-id="9aec6-163">Action</span></span>        |                                                                                                                    <span data-ttu-id="9aec6-164">説明</span><span class="sxs-lookup"><span data-stu-id="9aec6-164">Description</span></span>                                                                                                                    |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       <span data-ttu-id="9aec6-165">すぐに販売</span><span class="sxs-lookup"><span data-stu-id="9aec6-165">Sell now</span></span>       |                               <span data-ttu-id="9aec6-166">トランザクションに選択した品目バリアントを追加し、トランザクション画面にユーザーをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="9aec6-166">Add the selected item variant to the transaction, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="9aec6-167">(このアクションは、選択した場所が物流センターの場合には使用できません。)</span><span class="sxs-lookup"><span data-stu-id="9aec6-167">(This action isn't available when the selected location is a distribution center.)</span></span>                               |
|   <span data-ttu-id="9aec6-168">店舗で集荷</span><span class="sxs-lookup"><span data-stu-id="9aec6-168">Pick up in store</span></span>   |      <span data-ttu-id="9aec6-169">選択した場所から集荷される製品バリアントの顧客注文を作成し、トランザクション画面にユーザーをリダイレクトます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-169">Create a customer order for the product variant that will be picked up from the selected location, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="9aec6-170">(このアクションは、選択した場所が物流センターの場合には使用できません。)</span><span class="sxs-lookup"><span data-stu-id="9aec6-170">(This action isn't available when the selected location is a distribution center.)</span></span>       |
|     <span data-ttu-id="9aec6-171">製品の出荷</span><span class="sxs-lookup"><span data-stu-id="9aec6-171">Ship product</span></span>     |                                                 <span data-ttu-id="9aec6-172">選択した場所から出荷される製品バリアントの顧客注文を作成し、トランザクション画面にユーザーをリダイレクトます。</span><span class="sxs-lookup"><span data-stu-id="9aec6-172">Create a customer order for the product variant that will be shipped from the selected location, and redirect the user to the transaction screen.</span></span>                                                 |
|     <span data-ttu-id="9aec6-173">適用の対象</span><span class="sxs-lookup"><span data-stu-id="9aec6-173">Availability</span></span>     |                                                                             <span data-ttu-id="9aec6-174">選択した場所の選択したバリアントの組み合わせに対する ATP 情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-174">Show the ATP information for the selected variant combination for the selected location.</span></span>                                                                              |
|  <span data-ttu-id="9aec6-175">すべての場所を表示します</span><span class="sxs-lookup"><span data-stu-id="9aec6-175">Show all locations</span></span>  | <span data-ttu-id="9aec6-176">標準の在庫検索ビューに切り替え、店舗ロケーター グループ、および <strong>標準/既定</strong> タイプの流通センターのすべての店舗間で品目バリアントの使用可能な在庫情報を強調します。</span><span class="sxs-lookup"><span data-stu-id="9aec6-176">Switch to the standard inventory lookup view, and highlight inventory availability information for the item variant across all stores in the store locator group, and also in distribution centers of the <strong>Standard/Default</strong> type.</span></span> |
| <span data-ttu-id="9aec6-177">製品の詳細表示</span><span class="sxs-lookup"><span data-stu-id="9aec6-177">View product details</span></span> |                                                                         <span data-ttu-id="9aec6-178">関連付けられている製品マスターの [<strong>製品の詳細</strong>] ページに、ユーザーをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="9aec6-178">Redirect the user to the <strong>Product details</strong> page of the associated product master.</span></span>                                                                          |

