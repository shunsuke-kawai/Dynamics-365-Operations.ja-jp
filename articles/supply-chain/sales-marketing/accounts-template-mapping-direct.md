---
title: "Sales から Finance and Operations の顧客への勘定の直接同期"
description: "このトピックでは、Microsoft Dynamics 365 for Sales から Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition に勘定を同期させるために使用されるテンプレートと基本的なタスクについて説明します。"
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
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
ms.openlocfilehash: 16bbca2d9eb8c3d9c33752404ebecbe4415517a2
ms.contentlocale: ja-jp
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-accounts-directly-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="3b19f-103">Sales から Finance and Operations の顧客への勘定の直接同期</span><span class="sxs-lookup"><span data-stu-id="3b19f-103">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="3b19f-104">見込顧客を現金化するソリューションを使用する前に、[Dynamics 365 データ統合](/common-data-service/entity-reference/dynamics-365-integration) をよく理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b19f-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="3b19f-105">このトピックでは、Microsoft Dynamics 365 for Sales から Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition に勘定を直接同期させるために使用されるテンプレートと基本的なタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3b19f-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="3b19f-106">見込み客の現金化へのデータフロー</span><span class="sxs-lookup"><span data-stu-id="3b19f-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="3b19f-107">見込み客の現金化ソリューションは、Finance and Operations と Sales のインスタンス間でデータを同期するため、データの統合機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b19f-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span>  <span data-ttu-id="3b19f-108">データ統合機能で利用可能な見込み顧客を現金化するテンプレートは、Finance and Operations と Sales 間での勘定、連絡先、製品および販売見積、販売注文、および売上請求書データの流れを可能にします。</span><span class="sxs-lookup"><span data-stu-id="3b19f-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="3b19f-109">次の図は、Finance and Operations と Sales の間でデータを同期させる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3b19f-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="3b19f-110">[![見込み客の現金化へのデータフロー](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="3b19f-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="3b19f-111">テンプレートおよびタスク</span><span class="sxs-lookup"><span data-stu-id="3b19f-111">Templates and tasks</span></span>

<span data-ttu-id="3b19f-112">利用可能なテンプレートにアクセスするには、[PowerApps 管理者センター](https://preview.admin.powerapps.com/dataintegration) を開きます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="3b19f-113">**プロジェクト**を選択した後、右上隅にある **新しいプロジェクト** を選択してパブリック テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b19f-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="3b19f-114">Sales から Finance and Operations への勘定同期には、以下のテンプレートと基本的なタスクが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-114">The following template and underlying task are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="3b19f-115">**データ統合におけるテンプレートの名前:**  勘定 (Sales からFinance and Operations ) - 直接</span><span class="sxs-lookup"><span data-stu-id="3b19f-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="3b19f-116">**プロジェクトのタスクの名前:** - 勘定 - 顧客</span><span class="sxs-lookup"><span data-stu-id="3b19f-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="3b19f-117">アカウント/顧客の同期が発生する前に、同期タスクは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3b19f-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="3b19f-118">エンティティ セット</span><span class="sxs-lookup"><span data-stu-id="3b19f-118">Entity set</span></span>

| <span data-ttu-id="3b19f-119">売上</span><span class="sxs-lookup"><span data-stu-id="3b19f-119">Sales</span></span>    | <span data-ttu-id="3b19f-120">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3b19f-120">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="3b19f-121">口座</span><span class="sxs-lookup"><span data-stu-id="3b19f-121">Accounts</span></span> | <span data-ttu-id="3b19f-122">顧客 V2</span><span class="sxs-lookup"><span data-stu-id="3b19f-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="3b19f-123">エンティティのフロー</span><span class="sxs-lookup"><span data-stu-id="3b19f-123">Entity flow</span></span>

<span data-ttu-id="3b19f-124">勘定は Sales で管理され、Finance and Operations に顧客として同期されます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-124">Accounts are managed in Sales and synchronized to Finance and Operations as customers.</span></span> <span data-ttu-id="3b19f-125">これらの顧客の **外部管理** プロパティを **はい** に設定し、Sales から生成される顧客を追跡します。</span><span class="sxs-lookup"><span data-stu-id="3b19f-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="3b19f-126">請求時に、この情報は、売上に同期される請求書のフィルター処理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="3b19f-127">売上の見込顧客を現金化するソリューション</span><span class="sxs-lookup"><span data-stu-id="3b19f-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="3b19f-128">**勘定番号**フィールドは、**勘定**ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-128">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="3b19f-129">統合をサポートするため固有なナチュラル キーとなっています。</span><span class="sxs-lookup"><span data-stu-id="3b19f-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="3b19f-130">顧客関係管理 (CRM) ソリューションのナチュラル キー機能は、すでに **勘定番号** フィールドを使用しているが、勘定ごとに一意の **勘定番号** 値を使用していない顧客に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b19f-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="3b19f-131">現時点では、統合ソリューションは、このケースをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3b19f-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="3b19f-132">新しいアカウントが作成され、**勘定番号**値が存在しない場合、番号順序を使用して自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="3b19f-133">その値は**勘定**で構成され、続いて番号順序が増加し、6 文字の接尾辞が続きます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="3b19f-134">次に例を示します: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="3b19f-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="3b19f-135">売上の統合ソリューションが適用されている場合、アップグレード スクリプトにより、売上の既存のアカウントの、**勘定番号**フィールドが設定されます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="3b19f-136">**勘定番号** 値がない場合は、前述した番号順序を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b19f-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="3b19f-137">前提条件とマッピングの設定</span><span class="sxs-lookup"><span data-stu-id="3b19f-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="3b19f-138">**CustomerGroupId** マッピングは、Finance and Operations で有効な値に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b19f-138">The **CustomerGroupId** mapping must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="3b19f-139">既定値を指定するか、値マップを使用して値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="3b19f-140">既定のテンプレートの値は **10** です。</span><span class="sxs-lookup"><span data-stu-id="3b19f-140">The default template value is **10**.</span></span>

- <span data-ttu-id="3b19f-141">次のマッピングを追加することによって、Finance and Operations で必要な手動更新の数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="3b19f-142">たとえば、**国/地域**または**市町村**のデフォルト値または値マップを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="3b19f-143">**SiteId** – Finance and Operations で見積書および販売注文を生成するにはサイトが必要です。</span><span class="sxs-lookup"><span data-stu-id="3b19f-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="3b19f-144">デフォルトのサイトは、製品から、または注文ヘッダーの顧客から取得できます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="3b19f-145">既定のテンプレートの値は **1** です。</span><span class="sxs-lookup"><span data-stu-id="3b19f-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="3b19f-146">**WarehouseId** – Finance and Operations で見積書および販売注文を処理するには倉庫が必要です。</span><span class="sxs-lookup"><span data-stu-id="3b19f-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="3b19f-147">デフォルト倉庫は、製品から、または Finance and Operations の受注ヘッダーの顧客から取得できます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span>

        <span data-ttu-id="3b19f-148">既定のテンプレートの値は **13** です。</span><span class="sxs-lookup"><span data-stu-id="3b19f-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="3b19f-149">**LanguageId** – Finance and Operations で見積書および販売注文を生成するには言語が必要です。</span><span class="sxs-lookup"><span data-stu-id="3b19f-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="3b19f-150">既定では、顧客からの注文ヘッダの言語が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b19f-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="3b19f-151">既定のテンプレートの値は **アメリカ英語** です。</span><span class="sxs-lookup"><span data-stu-id="3b19f-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="3b19f-152">データ統合のテンプレートのマッピング</span><span class="sxs-lookup"><span data-stu-id="3b19f-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="3b19f-153">[支払条件]、[運賃条件]、[配送条件]、[送付方法]、および [配送モード] フィールドは、既定のマッピングには含まれていません。</span><span class="sxs-lookup"><span data-stu-id="3b19f-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="3b19f-154">これらのフィールドをマップするには、エンティティ間で同期される組織内のデータに固有の値マッピングを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b19f-154">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="3b19f-155">次の図は、データ統合のテンプレート マッピングの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="3b19f-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="3b19f-156">マッピングは、Sales から Finance and Operations にどのフィールド情報を同期するかを表示します。</span><span class="sxs-lookup"><span data-stu-id="3b19f-156">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![データ統合のテンプレートのマッピング](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="3b19f-158">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3b19f-158">Related topics</span></span>


[<span data-ttu-id="3b19f-159">見込顧客を現金化</span><span class="sxs-lookup"><span data-stu-id="3b19f-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="3b19f-160">Sales から Finance and Operations の顧客への勘定の直接同期</span><span class="sxs-lookup"><span data-stu-id="3b19f-160">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="3b19f-161">Sales から Finance and Operations の連絡先または顧客への連絡先の直接同期</span><span class="sxs-lookup"><span data-stu-id="3b19f-161">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="3b19f-162">販売注文ヘッダーおよび明細行の Finance and Operations から Sales への直接同期</span><span class="sxs-lookup"><span data-stu-id="3b19f-162">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)

[<span data-ttu-id="3b19f-163">売上請求書ヘッダーおよび直接明細行の Finance and Operations から Sales への直接同期</span><span class="sxs-lookup"><span data-stu-id="3b19f-163">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)

