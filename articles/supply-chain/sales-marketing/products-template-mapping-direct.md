---
title: "Sales 製品への Finance and Operations の製品の直接同期"
description: "このトピックでは、Microsoft Dynamics 365 for Finance and Operations, Enterprise edition の製品を Microsoft Dynamics 365 for Sales の製品に同期するときに使用されるテンプレートと基本的なタスクについて説明します。"
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6c68c4482cacf70f003669cf335e52e47425d2f7
ms.contentlocale: ja-jp
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="d6452-103">Sales 製品への Finance and Operations の製品の直接同期</span><span class="sxs-lookup"><span data-stu-id="d6452-103">Synchronize products directly from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="d6452-104">見込顧客を現金化するソリューションを使用する前に、[Dynamics 365 データ統合](/common-data-service/entity-reference/dynamics-365-integration) をよく理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6452-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="d6452-105">このトピックでは、Microsoft Dynamics 365 for Finance and Operations、Enterprise Edition から Microsoft Dynamics 365 for Sales に直接製品を同期させるために使用されるテンプレートと基本的なタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d6452-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="d6452-106">見込み客の現金化へのデータフロー</span><span class="sxs-lookup"><span data-stu-id="d6452-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="d6452-107">見込み客の現金化ソリューションは、Finance and Operations と Sales のインスタンス間でデータを同期するため、データの統合機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6452-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="d6452-108">データ統合機能で利用可能な見込み顧客を現金化するテンプレートは、Finance and Operations と Sales 間での勘定、連絡先、製品および販売見積、販売注文、および売上請求書データの流れを可能にします。</span><span class="sxs-lookup"><span data-stu-id="d6452-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="d6452-109">次の図は、Finance and Operations と Sales の間でデータを同期させる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6452-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="d6452-110">[![見込み客の現金化へのデータフロー](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="d6452-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="d6452-111">テンプレートおよびタスク</span><span class="sxs-lookup"><span data-stu-id="d6452-111">Templates and tasks</span></span>

<span data-ttu-id="d6452-112">利用可能なテンプレートにアクセスするには、[PowerApps 管理者センター](https://preview.admin.powerapps.com/dataintegration) を開きます。</span><span class="sxs-lookup"><span data-stu-id="d6452-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="d6452-113">**プロジェクト**を選択した後、右上隅にある **新しいプロジェクト** を選択してパブリック テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d6452-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="d6452-114">以下のテンプレートと基本的なタスクは、Finance and Operations から Sales に製品を同期させるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6452-114">The following template and underlying tasks are used to synchronize products from Finance and Operations to Sales.</span></span>

- <span data-ttu-id="d6452-115">**データ統合でのテンプレートの名前:** 製品 (Finance and Operations から Sales) - 直接</span><span class="sxs-lookup"><span data-stu-id="d6452-115">**Name of the template in Data integration:** Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="d6452-116">**データ統合プロジェクトのタスク名:** 製品</span><span class="sxs-lookup"><span data-stu-id="d6452-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="d6452-117">製品の同期が発生する前に、同期タスクは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d6452-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="d6452-118">エンティティ セット</span><span class="sxs-lookup"><span data-stu-id="d6452-118">Entity set</span></span>

| <span data-ttu-id="d6452-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d6452-119">Finance and Operations</span></span>     | <span data-ttu-id="d6452-120">売上</span><span class="sxs-lookup"><span data-stu-id="d6452-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="d6452-121">販売可能なリリース済製品</span><span class="sxs-lookup"><span data-stu-id="d6452-121">Sellable released products</span></span> | <span data-ttu-id="d6452-122">製品</span><span class="sxs-lookup"><span data-stu-id="d6452-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="d6452-123">エンティティのフロー</span><span class="sxs-lookup"><span data-stu-id="d6452-123">Entity flow</span></span>

<span data-ttu-id="d6452-124">製品は Finance and Operations で管理され、売上に同期されます。</span><span class="sxs-lookup"><span data-stu-id="d6452-124">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="d6452-125">Finance and Operations の**販売可能なリリース済製品**のデータ エンティティは、*販売可能*な製品のみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d6452-125">The **Sellable released products** data entity in Finance and Operations exports only products that are *sellable*.</span></span> <span data-ttu-id="d6452-126">販売可能製品には、販売注文で使用する必要のある情報があります。</span><span class="sxs-lookup"><span data-stu-id="d6452-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="d6452-127">[リリースされた製品] ページで [検証] 機能を使用して製品を検証する場合も、同じルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6452-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="d6452-128">[製品番号] がキーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6452-128">The product number is used as a key.</span></span> <span data-ttu-id="d6452-129">これは、製品バリアントが [製品バリアント] ごとの個別の [Product ID] で Sales に同期されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d6452-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="d6452-130">売上の見込顧客を現金化するソリューション</span><span class="sxs-lookup"><span data-stu-id="d6452-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="d6452-131">Sales では、新しい [外部管理] フィールドが製品に追加され、特定の製品が外部で維持されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d6452-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="d6452-132">デフォルトでは、値は Sales へのインポート時に [はい] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d6452-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="d6452-133">使用可能な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d6452-133">The following values are available:</span></span>

- <span data-ttu-id="d6452-134">**はい** – 製品が Finance and Operations に由来し、Sales では編集できません。</span><span class="sxs-lookup"><span data-stu-id="d6452-134">**Yes** – The product originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="d6452-135">**いいえ** – 製品は Sales に直接入力します。</span><span class="sxs-lookup"><span data-stu-id="d6452-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="d6452-136">**(空白)** – 見込顧客を現金化するソリューションを有効にする前に、製品が Sales に存在します。</span><span class="sxs-lookup"><span data-stu-id="d6452-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="d6452-137">**外部管理**フィールドは、外部管理された製品を持つ見積および受注のみが Finance and Operations に同期されることを保証するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d6452-137">The **Is Externally Maintained** field helps guarantee that only quotations and sales orders that have externally maintained products will be synchronized to Finance and Operations.</span></span>

<span data-ttu-id="d6452-138">外部管理の製品が、同じ通貨で最初に有効な価格リストに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d6452-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="d6452-139">価格リストは、名前がアルファベット順で構成されています。</span><span class="sxs-lookup"><span data-stu-id="d6452-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="d6452-140">Finance and Operations の製品販売価格は価格リストの価格として使用されています。</span><span class="sxs-lookup"><span data-stu-id="d6452-140">The product sales price from Finance and Operations is used as the price on the price list.</span></span> <span data-ttu-id="d6452-141">したがって、Finance and Operations の製品販売通貨ごとに、Sales の価格リストが必要です。</span><span class="sxs-lookup"><span data-stu-id="d6452-141">Therefore, there must be a price list in Sales for every product sales currency in Finance and Operations.</span></span> <span data-ttu-id="d6452-142">リリースされた販売可能商品の通貨は、製品が輸出される法人の会計通貨に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d6452-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> <span data-ttu-id="d6452-143">製品の同期は、一致する通貨を含む価格リストなしでは成功しません。</span><span class="sxs-lookup"><span data-stu-id="d6452-143">Product synchronization won't succeed unless there is a price list that has a matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="d6452-144">前提条件とマッピングの設定</span><span class="sxs-lookup"><span data-stu-id="d6452-144">Preconditions and mapping setup</span></span>

- <span data-ttu-id="d6452-145">一番最初の同期を実行する前に、Finance and Operation の既存製品に対して [特徴的製品テーブル] を全て入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6452-145">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Finance and Operations.</span></span> <span data-ttu-id="d6452-146">このジョブが完了するまで、既存の製品は同期されません。</span><span class="sxs-lookup"><span data-stu-id="d6452-146">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="d6452-147">Finance and Operations の場合は、[検索] を使用し、[**特徴的製品テーブルの設定**] を検索します。</span><span class="sxs-lookup"><span data-stu-id="d6452-147">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="d6452-148">[特徴的製品テーブル] を選択し、ジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="d6452-148">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="d6452-149">このジョブには、1回のみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6452-149">This job must be run only one time.</span></span>

- <span data-ttu-id="d6452-150">[SalesUnitSymbol] から [DefaultUnit (Name)] へのマッピングに、Finance and Operations と Sales の間における販売量測定単位 (UOM) に必要な値マップが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d6452-150">Make sure that the required value map for the selling unit of measure (UOM) between Finance and Operations and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="d6452-151">**単位グループ** (**defaultuomscheduleid.name**) の値マップを更新し、Sales の**単位グループ**に一致させます。</span><span class="sxs-lookup"><span data-stu-id="d6452-151">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="d6452-152">デフォルトのテンプレート値は、**既定単位**です。</span><span class="sxs-lookup"><span data-stu-id="d6452-152">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="d6452-153">Finance and Operations からのすべての製品の販売 UOM が Sales に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d6452-153">Make sure that the selling UOMs for all products from Finance and Operations exist in Sales.</span></span>
- <span data-ttu-id="d6452-154">価格リストが、Finance and Operations の製品販売通貨ごとに Sales に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d6452-154">Make sure that price lists exist in Sales for every product sales currency in Finance and Operations.</span></span>
- <span data-ttu-id="d6452-155">Sales で製品を作成すると、**ドラフト**または**有効**のステータスになります。</span><span class="sxs-lookup"><span data-stu-id="d6452-155">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="d6452-156">動作は、Sales の [設定] > [管理] > [システムの設定] > [販売] で制御されます。</span><span class="sxs-lookup"><span data-stu-id="d6452-156">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="d6452-157">作成時にステータスが [ドラフト] である製品は、見積書または販売注文に追加する前に有効化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6452-157">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="d6452-158">データ統合のテンプレートのマッピング</span><span class="sxs-lookup"><span data-stu-id="d6452-158">Template mapping in Data integration</span></span>

<span data-ttu-id="d6452-159">次の図は、データ インテグレーターのテンプレート マッピングの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6452-159">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="d6452-160">マッピングは、Sales から Finance and Operations にどのフィールド情報を同期するかを表示します。</span><span class="sxs-lookup"><span data-stu-id="d6452-160">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![データ インテグレーターのテンプレートのマッピング](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="d6452-162">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d6452-162">Related topics</span></span>

[<span data-ttu-id="d6452-163">見込顧客を現金化</span><span class="sxs-lookup"><span data-stu-id="d6452-163">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="d6452-164">Sales から Finance and Operations の顧客への勘定の直接同期</span><span class="sxs-lookup"><span data-stu-id="d6452-164">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="d6452-165">Sales から Finance and Operations の連絡先または顧客への連絡先の直接同期</span><span class="sxs-lookup"><span data-stu-id="d6452-165">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="d6452-166">販売注文ヘッダーおよび明細行の Finance and Operations から Sales への直接同期</span><span class="sxs-lookup"><span data-stu-id="d6452-166">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)

[<span data-ttu-id="d6452-167">売上請求書ヘッダーおよび直接明細行の Finance and Operations から Sales への直接同期</span><span class="sxs-lookup"><span data-stu-id="d6452-167">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)



