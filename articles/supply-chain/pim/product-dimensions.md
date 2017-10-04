---
title: "製品分析コード"
description: "4 つの製品分析コードがあります - 色、構成、サイズ、およびスタイルです。 分析コード グループで製品分析コードを組み合わせて、製品マスターに分析コード グループを割り当てます。 製品分析コードの組み合わせは、製品バリアントの定義方法を決定します。"
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: 105324f146f28bc61e87dff1089b367958ff9062
ms.contentlocale: ja-jp
ms.lasthandoff: 09/14/2017

---

# <a name="product-dimensions"></a><span data-ttu-id="34f88-105">製品分析コード</span><span class="sxs-lookup"><span data-stu-id="34f88-105">Product dimensions</span></span>

[!include[banner](../includes/banner.md)]

[!include[Retail name](../includes/retail-name.md)]


<span data-ttu-id="34f88-106">4 つの製品分析コードがあります - 色、構成、サイズ、およびスタイルです。</span><span class="sxs-lookup"><span data-stu-id="34f88-106">There are four product dimensions -  Color, Configuration, Size and Style.</span></span> <span data-ttu-id="34f88-107">分析コード グループで製品分析コードを組み合わせて、製品マスターに分析コード グループを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34f88-107">You combine product dimensions in dimension groups and assign dimension groups to product masters.</span></span> <span data-ttu-id="34f88-108">製品分析コードの組み合わせは、製品バリアントの定義方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="34f88-108">The combinations of product dimensions determine how product variants are defined.</span></span>

<span data-ttu-id="34f88-109">製品分析コードは、製品バリアントを識別するために役立つ特性です。</span><span class="sxs-lookup"><span data-stu-id="34f88-109">Product dimensions are characteristics that serve to identify a product variant.</span></span> <span data-ttu-id="34f88-110">製品バリアントを定義するために製品分析コードの組み合わせを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34f88-110">You can use combinations of product dimensions to define product variants.</span></span> <span data-ttu-id="34f88-111">製品バリアントを作成するには、製品マスターに対して少なくとも 1 つ製品分析コードを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34f88-111">You must define at least one product dimension for a product master in order to create a product variant.</span></span>
<span data-ttu-id="34f88-112">製品バリアント</span><span class="sxs-lookup"><span data-stu-id="34f88-112">Product variants</span></span>
----------------

<span data-ttu-id="34f88-113">製品バリアントは品目とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="34f88-113">Product variants are also referred to as items.</span></span> <span data-ttu-id="34f88-114">品目は、有形製品のことで、サービスとは異なるものです。</span><span class="sxs-lookup"><span data-stu-id="34f88-114">An item is a tangible product, which is not the same as a service.</span></span> <span data-ttu-id="34f88-115">サービス タイプの製品マスターを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="34f88-115">It is also possible to define a product master with the Service type.</span></span> <span data-ttu-id="34f88-116">[Service] タイプを使用して、サービスを含む製品バリアントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="34f88-116">By using the Service type, you can specify product variants that include services.</span></span> <span data-ttu-id="34f88-117">たとえば、上級顧問や若手のコンサルタントによって実行される、コンサルタント作業および作業の製品バリアントに、製品マスターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="34f88-117">For example, you can specify a product master for Consultancy work and product variants for work that is performed by senior consultants and junior consultants.</span></span>

## <a name="product-dimensions"></a><span data-ttu-id="34f88-118">製品分析コード</span><span class="sxs-lookup"><span data-stu-id="34f88-118">Product dimensions</span></span>
<span data-ttu-id="34f88-119">次の 4 つの製品分析コードがあります: 色、構成、サイズ、およびスタイルです。</span><span class="sxs-lookup"><span data-stu-id="34f88-119">The following product dimensions are available: Configuration, Color, Size, and Style.</span></span> <span data-ttu-id="34f88-120">製品バリアントは、製品分析コードの値に基づいて生成することができます。</span><span class="sxs-lookup"><span data-stu-id="34f88-120">A product variant can be generated based on the product dimension values.</span></span>

<span data-ttu-id="34f88-121">サイズ、色およびスタイルなどの製品分析コード値は、[**サイズ**]、[**色**] および [**スタイル**] ページで作成できます。これらのページは、次の場所からアクセスできます: [**製品情報管理** &gt; **設定** &gt; **分析コードおよびバリアント グループ** &gt; **サイズ / 色 / スタイル**]。</span><span class="sxs-lookup"><span data-stu-id="34f88-121">Product dimensions values such as Size, Color and Style can be created on the **Size**, **Color** and **Style** pages, which can be accessed from the following locations: **Product information management** &gt; **Setup** &gt; **Dimension and variant Groups** &gt; **Sizes/Colors/Styles**.</span></span> <span data-ttu-id="34f88-122">[コンフィギュレーション分析コード] の製品分析コードの値は、通常、[製品コンフィギュレーター] または [分析コード ベースのコンフィギュレーター] を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="34f88-122">Product dimension values for the Configuration dimension are typically created using either the Product configurator or the Dimension-based configurator.</span></span> <span data-ttu-id="34f88-123">製品分析コードは**製品分析コード** ページで作成および管理することもできます。以下の場所からアクセス可能です。</span><span class="sxs-lookup"><span data-stu-id="34f88-123">Product dimensions can also be created and maintained on the **Product dimensions** page, which can be accessed from the following locations:</span></span>
-   <span data-ttu-id="34f88-124">[**製品情報管理**] &gt; [**製品**] &gt; [**製品マスター**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="34f88-124">Click **Product information management** &gt; **Products** &gt; **Product masters**.</span></span> <span data-ttu-id="34f88-125">[**アクション ペイン**] で、[**製品分析コード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34f88-125">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="34f88-126">[**製品情報管理**] &gt; [**製品**] &gt; [**すべての製品および製品マスター**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="34f88-126">Click **Product information management** &gt; **Products** &gt; **All products and product masters**.</span></span> <span data-ttu-id="34f88-127">製品マスターを選択します。</span><span class="sxs-lookup"><span data-stu-id="34f88-127">Select a product master.</span></span> <span data-ttu-id="34f88-128">[**アクション ペイン**] で、[**製品分析コード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34f88-128">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="34f88-129">[**製品情報管理**] &gt; [**リリースされた製品**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="34f88-129">Click **Product information management** &gt; **Released products**.</span></span> <span data-ttu-id="34f88-130">製品マスターを選択します。</span><span class="sxs-lookup"><span data-stu-id="34f88-130">Select a product master.</span></span> <span data-ttu-id="34f88-131">[**アクション ペイン**] で、[**製品**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34f88-131">On the **Action Pane**, click **Product**.</span></span> <span data-ttu-id="34f88-132">**製品マスター** グループで、**製品分析コード**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34f88-132">In the **Product master** group, click **Product dimensions**.</span></span>

<span data-ttu-id="34f88-133">1 つの品目に対して作成できるバリアントの数は、可能な製品分析コードの組み合わせの数により制限されます。</span><span class="sxs-lookup"><span data-stu-id="34f88-133">The number of variants that you can create for an item is limited by the number of possible product dimension combinations.</span></span>
| <span data-ttu-id="34f88-134">**ヒント**</span><span class="sxs-lookup"><span data-stu-id="34f88-134">**Tip**</span></span>                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="34f88-135">たとえば、ある注文明細行上で製品を使用する場合、製品分析コードを選択して、使用する製品バリアントを特定します。</span><span class="sxs-lookup"><span data-stu-id="34f88-135">When you use a product on, for example, an order line, you select the product dimensions to identify the product variant that you want to work with.</span></span> |

## <a name="example"></a><span data-ttu-id="34f88-136">例</span><span class="sxs-lookup"><span data-stu-id="34f88-136">Example</span></span>
<span data-ttu-id="34f88-137">ある会社がデニム ジーンズを販売しています。</span><span class="sxs-lookup"><span data-stu-id="34f88-137">A company sells denim jeans.</span></span> <span data-ttu-id="34f88-138">品目 "ジーンズ" には、色分析コードとサイズ分析コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="34f88-138">The item, Jeans, uses the Color and Size product dimensions.</span></span> <span data-ttu-id="34f88-139">販売されるジーンズには、3 種類の色と 6 種類のサイズがあります。</span><span class="sxs-lookup"><span data-stu-id="34f88-139">The jeans are sold in three different colors and six different sizes.</span></span> <span data-ttu-id="34f88-140">色: 青、黒、茶。サイズ: XS、S、M、L、XL、XXL。すべてのサイズで 3 色すべてが用意されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="34f88-140">Colors: Blue, Black, Brown Sizes: XS, S, M, L, XL, XXL Not all sizes are available in all the three colors.</span></span> <span data-ttu-id="34f88-141">すべての組み合わせが使用可能な場合、18 タイプのジーンズを作成します。</span><span class="sxs-lookup"><span data-stu-id="34f88-141">If all combinations were available, it would create 18 different types of jeans.</span></span> <span data-ttu-id="34f88-142">この例では、次の 9 種類の製品バリアントの組み合わせのみ作成されます。</span><span class="sxs-lookup"><span data-stu-id="34f88-142">In this example, only the following nine product variant combinations are produced.</span></span>

| <span data-ttu-id="34f88-143">色</span><span class="sxs-lookup"><span data-stu-id="34f88-143">Color</span></span> | <span data-ttu-id="34f88-144">サイズ</span><span class="sxs-lookup"><span data-stu-id="34f88-144">Size</span></span> |
|-------|------|
| <span data-ttu-id="34f88-145">青</span><span class="sxs-lookup"><span data-stu-id="34f88-145">Blue</span></span>  | <span data-ttu-id="34f88-146">XS</span><span class="sxs-lookup"><span data-stu-id="34f88-146">XS</span></span>   |
| <span data-ttu-id="34f88-147">青</span><span class="sxs-lookup"><span data-stu-id="34f88-147">Blue</span></span>  | <span data-ttu-id="34f88-148">S</span><span class="sxs-lookup"><span data-stu-id="34f88-148">S</span></span>    |
| <span data-ttu-id="34f88-149">青</span><span class="sxs-lookup"><span data-stu-id="34f88-149">Blue</span></span>  | <span data-ttu-id="34f88-150">M</span><span class="sxs-lookup"><span data-stu-id="34f88-150">M</span></span>    |
| <span data-ttu-id="34f88-151">黒</span><span class="sxs-lookup"><span data-stu-id="34f88-151">Black</span></span> | <span data-ttu-id="34f88-152">M</span><span class="sxs-lookup"><span data-stu-id="34f88-152">M</span></span>    |
| <span data-ttu-id="34f88-153">黒</span><span class="sxs-lookup"><span data-stu-id="34f88-153">Black</span></span> | <span data-ttu-id="34f88-154">L</span><span class="sxs-lookup"><span data-stu-id="34f88-154">L</span></span>    |
| <span data-ttu-id="34f88-155">黒</span><span class="sxs-lookup"><span data-stu-id="34f88-155">Black</span></span> | <span data-ttu-id="34f88-156">XL</span><span class="sxs-lookup"><span data-stu-id="34f88-156">XL</span></span>   |
| <span data-ttu-id="34f88-157">茶</span><span class="sxs-lookup"><span data-stu-id="34f88-157">Brown</span></span> | <span data-ttu-id="34f88-158">L</span><span class="sxs-lookup"><span data-stu-id="34f88-158">L</span></span>    |
| <span data-ttu-id="34f88-159">茶</span><span class="sxs-lookup"><span data-stu-id="34f88-159">Brown</span></span> | <span data-ttu-id="34f88-160">XL</span><span class="sxs-lookup"><span data-stu-id="34f88-160">XL</span></span>   |
| <span data-ttu-id="34f88-161">茶</span><span class="sxs-lookup"><span data-stu-id="34f88-161">Brown</span></span> | <span data-ttu-id="34f88-162">XXL</span><span class="sxs-lookup"><span data-stu-id="34f88-162">XXL</span></span>  |





