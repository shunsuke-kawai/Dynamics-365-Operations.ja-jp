---
title: "製品情報の概要"
description: "このトピックでは、製品情報の管理に関する情報を提供します。 製品情報の管理では、すべての法人の製品定義、カテゴリ、識別子、および製品の特定のコンフィギュレーションを業務プロセスに合わせて共有します。"
author: cvocph
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductListPage, EcoResProductVariantMaintainWorkspace
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: cvocph
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: 3a6a41f192b1c79f0f8ee40bf62c8b30ee7200c8
ms.contentlocale: ja-jp
ms.lasthandoff: 09/14/2017

---

# <a name="product-information-overview"></a><span data-ttu-id="b9186-104">製品情報の概要</span><span class="sxs-lookup"><span data-stu-id="b9186-104">Product information overview</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

<span data-ttu-id="b9186-105">このトピックでは、製品情報の管理に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b9186-105">This topic provides information about product information management.</span></span> <span data-ttu-id="b9186-106">製品情報の管理では、すべての法人の製品定義、カテゴリ、識別子、および製品の特定のコンフィギュレーションを業務プロセスに合わせて共有します。</span><span class="sxs-lookup"><span data-stu-id="b9186-106">Product information management works with a shared product definition, categorization, and identifiers across all legal entities, and also specific configurations of a product, to fit into the business processes.</span></span> 

<span data-ttu-id="b9186-107">製品情報は、すべての業界のサプライ チェーンと小売アプリケーションのバックボーンです。</span><span class="sxs-lookup"><span data-stu-id="b9186-107">Product information is the backbone of supply chain and retail applications across all industries.</span></span> <span data-ttu-id="b9186-108">これは、製品に関する情報を集中管理することに重点を置くプロセスや技術を指します (たとえば、サプライ チェーン全体で)。</span><span class="sxs-lookup"><span data-stu-id="b9186-108">It refers to processes and technologies that focus on centrally managing information about products (for example, across supply chains).</span></span> <span data-ttu-id="b9186-109">製品定義、文書、属性、および使用される識別子を共有することは重要です。</span><span class="sxs-lookup"><span data-stu-id="b9186-109">It's crucial that shared product definitions, documentation, attributes, and identifiers be used.</span></span> <span data-ttu-id="b9186-110">ビジネス ソリューションのさまざまなモジュールでは、特定の製品、製品ファミリー、または製品カテゴリに関連する業務プロセスを管理するために製品固有の情報およびコンフィギュレーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9186-110">In the various modules of a business solution, product-specific information and configuration are required in order to manage the business processes that are related to specific products, product families, or product categories.</span></span>

## <a name="product-definition"></a><span data-ttu-id="b9186-111">製品定義</span><span class="sxs-lookup"><span data-stu-id="b9186-111">Product definition</span></span>

<span data-ttu-id="b9186-112">製品は、主に、製品番号、名前、および説明によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="b9186-112">A product is primarily defined by a product number, name, and description.</span></span> <span data-ttu-id="b9186-113">しかし、製品またはサービスを説明するためには、他のデータも必要です:</span><span class="sxs-lookup"><span data-stu-id="b9186-113">However, other data is also required in order to describe a product or service:</span></span>

- <span data-ttu-id="b9186-114">製品タイプ: 品目またはサービス</span><span class="sxs-lookup"><span data-stu-id="b9186-114">Product type: Item or service</span></span>
- <span data-ttu-id="b9186-115">製品サブタイプ: 特徴的製品または製品マスター</span><span class="sxs-lookup"><span data-stu-id="b9186-115">Product subtype: Distinct products or product masters</span></span>
- <span data-ttu-id="b9186-116">製品バリアント モデルの定義:</span><span class="sxs-lookup"><span data-stu-id="b9186-116">Definition of the product variant model:</span></span>

     - <span data-ttu-id="b9186-117">製品分析コードおよび分析コード グループ</span><span class="sxs-lookup"><span data-stu-id="b9186-117">Product dimensions and dimension groups</span></span>
     - <span data-ttu-id="b9186-118">製品の分類</span><span class="sxs-lookup"><span data-stu-id="b9186-118">Product nomenclature</span></span>
     - <span data-ttu-id="b9186-119">製品コンフィギュレーション モデル</span><span class="sxs-lookup"><span data-stu-id="b9186-119">Product configuration models</span></span>

- <span data-ttu-id="b9186-120">製品と 1 つ以上のカテゴリの関連付け</span><span class="sxs-lookup"><span data-stu-id="b9186-120">Association of the product with one or more categories</span></span>
- <span data-ttu-id="b9186-121">製品およびカテゴリ属性の定義</span><span class="sxs-lookup"><span data-stu-id="b9186-121">Definition of the product and category attributes</span></span>
- <span data-ttu-id="b9186-122">製品画像</span><span class="sxs-lookup"><span data-stu-id="b9186-122">Product images</span></span>
- <span data-ttu-id="b9186-123">アタッチメント</span><span class="sxs-lookup"><span data-stu-id="b9186-123">Attachments</span></span>
- <span data-ttu-id="b9186-124">測定単位および関連する変換</span><span class="sxs-lookup"><span data-stu-id="b9186-124">Units of measure and related conversions</span></span>
- <span data-ttu-id="b9186-125">すべての名前と説明の翻訳</span><span class="sxs-lookup"><span data-stu-id="b9186-125">Translations for all names and descriptions</span></span>

## <a name="distribution-export-and-import-of-product-data"></a><span data-ttu-id="b9186-126">配分、エクスポート、および製品データのインポート</span><span class="sxs-lookup"><span data-stu-id="b9186-126">Distribution, export, and import of product data</span></span>

<span data-ttu-id="b9186-127">製品定義は、Microsoft Dynamics 365 for Finance and Operations、Enterprise エディションで作成できます。</span><span class="sxs-lookup"><span data-stu-id="b9186-127">The product definition can be created in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="b9186-128">製品ライフサイクル管理 (PLM)、製品データ管理 (PDM)、製品情報管理 (PIM) システムからインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b9186-128">It can also be imported from product lifecycle management (PLM), product data management (PDM), or product information management (PIM) systems.</span></span> <span data-ttu-id="b9186-129">複数の Finance and Operations インスタンスが使用されている場合、1 つのインスタンスは通常、他のすべてのインスタンスの製品データのマスターとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9186-129">When more than one instance of Finance and Operations is used, one instance is typically used as the master of the product data for all other instances.</span></span> <span data-ttu-id="b9186-130">この方法は、1 つのインスタンスから別のインスタンスへの製品定義データのエクスポートおよびインポートを可能にする大量のデータ エンティティによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b9186-130">This approach is supported by a large set of data entities that enable the export and import of product definition data from one instance to another.</span></span>

<span data-ttu-id="b9186-131">多くのインスタンスに製品データの配分をサポートするために、Finance and Operations では Common Data Service を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9186-131">To support the distribution of product data to many instances, Finance and Operations lets you use the Common Data Service.</span></span> <span data-ttu-id="b9186-132">製品定義は、Finance and Operations のインスタンスから Common Data Service にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="b9186-132">The product definitions can be exported from an instance of Finance and Operations to the Common Data Service.</span></span> <span data-ttu-id="b9186-133">製品定義を使用して、Microsoft Dynamics 365 for Sales などの他のビジネス アプリケーションに製品データをプロビジョニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="b9186-133">The product definitions can then be used to provision other business applications, such as Microsoft Dynamics 365 for Sales, with product data.</span></span>

<span data-ttu-id="b9186-134">動的および迅速な組織では、製品情報のデータが毎日変わることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9186-134">Note that, in dynamic and agile organizations, product information data changes every day.</span></span> <span data-ttu-id="b9186-135">したがって、正確および実際の製品データの管理は、それ自体が重要な業務プロセスです。</span><span class="sxs-lookup"><span data-stu-id="b9186-135">Therefore, maintenance of accurate and actual product data is a critical business process on its own.</span></span>

## <a name="product-masters-and-product-variants"></a><span data-ttu-id="b9186-136">製品マスターと製品バリアント</span><span class="sxs-lookup"><span data-stu-id="b9186-136">Product masters and product variants</span></span>

<span data-ttu-id="b9186-137">製品がお客様の要件に迅速に適応されなければならないアジャイル環境では、製品定義は、特徴的製品の代わりに一連の製品を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9186-137">In an agile world, where products must be quickly adapted to customer requirements, product definitions specify a set of products instead of distinct products.</span></span> <span data-ttu-id="b9186-138">Microsoft Dynamics 365 for Finance and Operations では、これらの汎用製品は [*製品マスター*] として知られています。</span><span class="sxs-lookup"><span data-stu-id="b9186-138">In Microsoft Dynamics 365 for Finance and Operations, those generic products are known as *product masters*.</span></span> <span data-ttu-id="b9186-139">製品マスターは、特徴的製品が業務プロセスでどのように説明され、動作されるかを指定する定義およびルールを保持します。</span><span class="sxs-lookup"><span data-stu-id="b9186-139">Product masters hold the definition and rules that specify how distinct products are described and behave in business processes.</span></span> <span data-ttu-id="b9186-140">これらの定義に基づいて、特徴的製品を生成できます。</span><span class="sxs-lookup"><span data-stu-id="b9186-140">Based on these definitions, distinct products can be generated.</span></span> <span data-ttu-id="b9186-141">これらの特徴的製品は、[*製品バリアント*] として知られています。</span><span class="sxs-lookup"><span data-stu-id="b9186-141">These distinct products are known as *product variants*.</span></span>

<span data-ttu-id="b9186-142">Finance and Operation では、製品マスターは製品分析コード グループおよびビジネス ルールを指定するコンフィギュレーション テクノロジに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="b9186-142">In Finance and Operations, a product master is associated with a product dimension group and a configuration technology to specify the business rules.</span></span> <span data-ttu-id="b9186-143">製品分析コード (色、サイズ、スタイル、およびコンフィギュレーション) は、関連製品の特定の動作を定義および追跡するためにアプリケーション全体で使用できる特定の属性セットです。</span><span class="sxs-lookup"><span data-stu-id="b9186-143">The product dimensions (Color, Size, Style, and Configuration) are a specific set of attributes that can be used throughout the application to define and track specific behaviors of the related products.</span></span> <span data-ttu-id="b9186-144">これらの分析コードは、ユーザーが製品を検索して識別するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b9186-144">These dimensions also help users search for and identify the products.</span></span>

## <a name="configuration-technologies"></a><span data-ttu-id="b9186-145">コンフィギュレーション テクノロジ</span><span class="sxs-lookup"><span data-stu-id="b9186-145">Configuration technologies</span></span>

<span data-ttu-id="b9186-146">3 つのコンフィギュレーション テクノロジから選択できます:</span><span class="sxs-lookup"><span data-stu-id="b9186-146">You can choose among three configuration technologies:</span></span>

- <span data-ttu-id="b9186-147">事前定義されたバリアントは、事前定義された品目分析コードによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="b9186-147">The predefined variants are defined by predefined product dimensions.</span></span> <span data-ttu-id="b9186-148">バリアント定義には、色、スタイル、およびサイズなど、特定の有効な分析コードの組み合わせの定義が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9186-148">The variant definition includes the definition of a specific valid combination of dimensions, such as Color, Style, and Size.</span></span> <span data-ttu-id="b9186-149">各組み合わせは、特徴的製品のバリアントを生成します。</span><span class="sxs-lookup"><span data-stu-id="b9186-149">Each combination produces a distinct product variant.</span></span>
- <span data-ttu-id="b9186-150">分析コードベースのコンフィギュレーションでは、通常、製造シナリオで使用され、部品表 (BOM) の定義でコンフィギュレーション分析コードを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b9186-150">The dimension-based configuration is typically used in manufacturing scenarios and lets you use the Configuration dimension in the definition of the bills of materials (BOMs).</span></span> <span data-ttu-id="b9186-151">特定のコンフィギュレーションが選択されていると、計画および生産のコンフィギュレーションで有効な BOM 明細行のサブセットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9186-151">After a specific configuration is selected, the system uses the subset of BOM lines that are valid for that configuration for planning and production.</span></span> <span data-ttu-id="b9186-152">1 つの共有 BOM が製品のすべてのコンフィギュレーションに使用されるため、この概念は [*グローバル BOM*] としても知られています。</span><span class="sxs-lookup"><span data-stu-id="b9186-152">This concept is also known as *global BOM*, because one shared BOM is used for all configurations of a product.</span></span>
- <span data-ttu-id="b9186-153">制約ベースの構成では、製品コンフィギュレーション モデルを使用して、すべての可能な属性および 1 つのモデルですべての可能な製品のバリアントを記述するために必要なコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b9186-153">The constraint-based configuration uses a product configuration model to describe all possible attributes and components that are required in order to describe all possible variants of a product in a single model.</span></span> <span data-ttu-id="b9186-154">属性の組み合わせの制約は、正規表現またはテーブル制約ベースによって表すことができます。</span><span class="sxs-lookup"><span data-stu-id="b9186-154">The constraints of combinations of attributes can be described through regular expressions or table-based constraints.</span></span> <span data-ttu-id="b9186-155">コンフィギュレーション モデルおよびコンフィギュレーションは、製品情報管理においてより重要になり、すべての業界で使用されています。</span><span class="sxs-lookup"><span data-stu-id="b9186-155">Configuration models and configurators become more important in product information management and are used across all industries.</span></span>

<span data-ttu-id="b9186-156">Finance and Operations の実装を計画する場合は、業務プロセスの正しいコンフィギュレーション テクノロジを選択することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="b9186-156">When you plan the implementation of Finance and Operations, it's very important that you choose the correct configuration technology for a business process.</span></span> <span data-ttu-id="b9186-157">製品は、実装後に 1 つのモデルから別のモデルに変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="b9186-157">A product can't be converted from one model to another after implementation.</span></span>

## <a name="product-variant-model-definition-workspace"></a><span data-ttu-id="b9186-158">製品バリアント モデル定義のワークスペース</span><span class="sxs-lookup"><span data-stu-id="b9186-158">Product variant model definition workspace</span></span>

<span data-ttu-id="b9186-159">[**製品バリアント モデル定義**] ワークスペースは、製品マスターの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="b9186-159">The **Product variant model definition** workspace gives an overview of the product masters.</span></span> <span data-ttu-id="b9186-160">特定の法人へのマスターおよび関連するバリアントのリリースのステータスも示します。</span><span class="sxs-lookup"><span data-stu-id="b9186-160">It also shows the status of the release of masters and related variants to specific legal entities.</span></span>

## <a name="released-products"></a><span data-ttu-id="b9186-161">リリースされた製品</span><span class="sxs-lookup"><span data-stu-id="b9186-161">Released products</span></span>

<span data-ttu-id="b9186-162">特定の法人にリリースされる製品は、[*リリース済製品*] として知られています。</span><span class="sxs-lookup"><span data-stu-id="b9186-162">The products that are released to a specific legal entity are known as *released products*.</span></span> <span data-ttu-id="b9186-163">製品は一度に 1 つの法人または多くの法人に一括してリリースすることができます。</span><span class="sxs-lookup"><span data-stu-id="b9186-163">Products can be released in bulk to one legal entity or many legal entities at a time.</span></span> <span data-ttu-id="b9186-164">製品のさまざまなプロパティおよび属性を法人単位で追加する必要がある場合には、[**リリース済製品の保守**] ワークスペースで、各法人または法人の下位組織で最近リリースされた製品を監視および完了させることができます。</span><span class="sxs-lookup"><span data-stu-id="b9186-164">Because various properties and attributes of the products might have to be added per legal entity, the **Released product maintenance** workspace lets you monitor and complete the recently released products in each legal entity, or in the suborganizations of a legal entity.</span></span>

### <a name="released-product-maintenance-workspace"></a><span data-ttu-id="b9186-165">[リリース済製品の保守] ワークスペース</span><span class="sxs-lookup"><span data-stu-id="b9186-165">Released product maintenance workspace</span></span>

<span data-ttu-id="b9186-166">[**リリース済製品の保守**] メニュー項目から [**リリース済製品の保守**] ワークスペースをコンフィギュレーションすることができます。</span><span class="sxs-lookup"><span data-stu-id="b9186-166">You can configure the **Released product maintenance** workspace from the **Configure my workspace** menu item.</span></span> <span data-ttu-id="b9186-167">カテゴリ階層およびカテゴリを選択し、ワークスペースをフィルタ処理します。</span><span class="sxs-lookup"><span data-stu-id="b9186-167">Select a category hierarchy and category to filter the workspace by.</span></span> <span data-ttu-id="b9186-168">ワークスペース内の関連する製品データを調整するには、[**最近リリース済の製品**] および [**リリース済製品の停止**] のタイム フェンスを日数で定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="b9186-168">To adjust the relevant product data in the workspace, you can also define, in days, the time fences for **Recently released products** and **Stopped released products**.</span></span>

<span data-ttu-id="b9186-169">ワークスペースは、タイルの集計および 2 つのリストで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b9186-169">The workspace consists of a summary of tiles and two lists.</span></span> <span data-ttu-id="b9186-170">[**オープンなケース**] リストでは、完了および終了していない選択した製品カテゴリ階層内の製品の製品変更ケースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9186-170">The **Open cases** list shows product change cases that have products in the selected product category hierarchy that aren't completed and closed.</span></span> <span data-ttu-id="b9186-171">[**最近リリース済**] リストには、ワークスペースのコンフィギュレーションで設定されているタイム フェンス内にリリースされた製品が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9186-171">The **Recently released** list shows products that have been released within the time fence that is set in the workspace configuration.</span></span> <span data-ttu-id="b9186-172">一覧の各品目について、検証が実行され、および検証ステータスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9186-172">For each item in the list, validation is run, and the validation status is shown.</span></span> <span data-ttu-id="b9186-173">このステータスは、法人の必要なコンフィギュレーションが完了していないことを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9186-173">This status might indicate that the required configurations for the legal entity hasn't been completed.</span></span> <span data-ttu-id="b9186-174">一覧から、[**リリース済製品の詳細**]、[**製品属性の保守**]、[**製品カテゴリの保守**]、[**既定の注文設定**]、および製品の必要なコンフィギュレーションを完了する [**テキストの翻訳**] ページに直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b9186-174">From the list, you can directly access the **Released product details**, **Product attribute maintenance**, **Product category maintenance**, **Default order settings**, and **Text translations** pages to complete the required configuration of the product.</span></span>

### <a name="manually-creating-a-new-released-product"></a><span data-ttu-id="b9186-175">新たにリリースされた製品を手動で作成する</span><span class="sxs-lookup"><span data-stu-id="b9186-175">Manually creating a new released product</span></span>

<span data-ttu-id="b9186-176">組織の業務プロセスおよびこの機能を使用するかどうかに関するルールに応じて、リリース済み製品を手動で一度に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="b9186-176">You can manually create a released product in a single run, depending on the organization's business processes and any rules about whether this function should be used.</span></span> <span data-ttu-id="b9186-177">この機能は、新しい製品を作成し、それを現在の法人に自動的にリリースします。</span><span class="sxs-lookup"><span data-stu-id="b9186-177">This function creates a new product and automatically releases it to the current legal entity.</span></span> <span data-ttu-id="b9186-178">新しい製品を作成するには、[**リリース済製品の保守**] ワークスペース、または [**リリースされた製品**] リスト ページ内の [**リリース済製品**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9186-178">To create a new product, click **Released products** in the **Released product maintenance** workspace or on the **Released product** list page.</span></span>
