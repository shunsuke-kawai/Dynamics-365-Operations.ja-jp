---
title: "勘定科目表名の計画"
description: "この記事では、組織の勘定科目表を計画する際に役立つ情報を提供します。"
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 848da7ec8f4a7915f3b78945b808b564f4510434
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="7ce67-103">勘定科目表名の計画</span><span class="sxs-lookup"><span data-stu-id="7ce67-103">Plan your chart of accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7ce67-104">この記事では、組織の勘定科目表を計画する際に役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7ce67-104">This article provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="7ce67-105">組織の財務情報を追跡および管理するには、勘定科目表を設定します。</span><span class="sxs-lookup"><span data-stu-id="7ce67-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="7ce67-106">勘定科目表は、財務フレームワークを定義する勘定の集合です。</span><span class="sxs-lookup"><span data-stu-id="7ce67-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="7ce67-107">これらの勘定のトランザクションをさらに追跡するためには、財務分析コードと呼ばれる区分を追加します。</span><span class="sxs-lookup"><span data-stu-id="7ce67-107">To further track the transactions in these accounts, you can add segments, which are known as financial dimensions.</span></span> <span data-ttu-id="7ce67-108">たとえば、経費勘定には、部門、コスト センター、および目的という財務分析コードが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ce67-108">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="7ce67-109">ユーザー定義のルールは、勘定構造や詳細なルールとも呼ばれ、これらの財務分析コードを主勘定およびその他の財務分析コードに関連付ける方法や、トランザクションを入力する方法を指示します。</span><span class="sxs-lookup"><span data-stu-id="7ce67-109">User-defined rules, which are known as account structures and advanced rules, determine how financial dimensions are attached to the main accounts and other financial dimensions, and also how transactions are entered.</span></span> 

<span data-ttu-id="7ce67-110">勘定科目表は、法人の一般会計科目の構造化された一覧です。</span><span class="sxs-lookup"><span data-stu-id="7ce67-110">The chart of accounts is a structured list of a legal entity’s general ledger accounts.</span></span> <span data-ttu-id="7ce67-111">この一覧は、所轄官庁や株主への財務報告を準備するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ce67-111">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="7ce67-112">勘定はタイプごとにグループ化され、さらに大きなカテゴリに集約されます。</span><span class="sxs-lookup"><span data-stu-id="7ce67-112">The accounts are grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="7ce67-113">最も大きなレベルでは、収益および費用 (営業勘定) と資産および負債 (残高勘定) にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="7ce67-113">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span> 

<span data-ttu-id="7ce67-114">勘定科目表は、組織のすべての法人によって共有および使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ce67-114">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="7ce67-115">法人に使用される勘定科目表は、[**元帳**] ページで定義されます。</span><span class="sxs-lookup"><span data-stu-id="7ce67-115">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span> 

<span data-ttu-id="7ce67-116">組織の勘定科目表の構成を計画するときは、次のようなさまざまな要因を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ce67-116">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

-   <span data-ttu-id="7ce67-117">組織が拠点を置く国または地域の報告要件</span><span class="sxs-lookup"><span data-stu-id="7ce67-117">The reporting requirements of the country/region where your organization is based</span></span>
-   <span data-ttu-id="7ce67-118">自分の法人のレポート要件</span><span class="sxs-lookup"><span data-stu-id="7ce67-118">The reporting requirements of your legal entity</span></span>
-   <span data-ttu-id="7ce67-119">外部組織または組織にとって必要な細分化の程度</span><span class="sxs-lookup"><span data-stu-id="7ce67-119">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="7ce67-120">**勘定科目表**ページで、勘定科目表を作成します。</span><span class="sxs-lookup"><span data-stu-id="7ce67-120">Create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="7ce67-121">主勘定は、**勘定科目表**ページまたは**主勘定**ページから作成できます。</span><span class="sxs-lookup"><span data-stu-id="7ce67-121">Main accounts can be created from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="7ce67-122">自分の主勘定には、勘定科目表の区切り文字として使用される特殊文字を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7ce67-122">Your main accounts shouldn't use any special characters that are used as chart of accounts delimiters.</span></span> <span data-ttu-id="7ce67-123">勘定科目表の区切り記号と同じ特殊文字を使用した場合、動作が不安定になることがあります。また、勘定と分析コードの組み合わせを入力するとき、常にルックアップまたはポップアップを使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ce67-123">If you do have a special character that is the same as your chart of accounts delimiter, you may experience instability, or the need to always use lookups or the flyout when entering account and dimension combinations.</span></span> <span data-ttu-id="7ce67-124">詳細については、「[主勘定の作成](tasks/create-account-structures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ce67-124">For more information, see [Create a main account](tasks/create-account-structures.md).</span></span>


<span data-ttu-id="7ce67-125">主勘定を主勘定カテゴリにリンクし、既定の財務諸表を変更を加えずに使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ce67-125">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="7ce67-126">したがって、より迅速かつ簡単にレポートを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="7ce67-126">Therefore, you can more quickly and easily design and maintain reports.</span></span> 

<span data-ttu-id="7ce67-127">**勘定構造のコンフィギュレーション** ページを使用して、勘定構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="7ce67-127">Use the **Configure account structures** page to create account structures.</span></span> <span data-ttu-id="7ce67-128">勘定構造では、有効な組み合わせを定義します。</span><span class="sxs-lookup"><span data-stu-id="7ce67-128">Account structures define valid combinations.</span></span> <span data-ttu-id="7ce67-129">組み合わせは、主勘定と共に、勘定科目表を形成します。</span><span class="sxs-lookup"><span data-stu-id="7ce67-129">The combinations, together with main accounts, form a chart of accounts.</span></span>  <span data-ttu-id="7ce67-130">詳細については、「[勘定構造の作成](tasks/create-main-account.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ce67-130">For more information, see [Create account structures](tasks/create-main-account.md).</span></span>

<span data-ttu-id="7ce67-131">**法人の上書き**</span><span class="sxs-lookup"><span data-stu-id="7ce67-131">**Legal entity overrides**</span></span> 

<span data-ttu-id="7ce67-132">主勘定には、ある法人に対して有効でないものもあり、特定の期間だけ有効なものもあります。</span><span class="sxs-lookup"><span data-stu-id="7ce67-132">Not all main accounts are valid for all legal entities and some may only be relevant for a specific time period.</span></span> <span data-ttu-id="7ce67-133">このシナリオでは、[法人の上書き] セクションを使用して、主勘定を保留にする法人の指定、法人のオーナーの指定、分析コードの有効期間の指定ができます。</span><span class="sxs-lookup"><span data-stu-id="7ce67-133">In this scenario the Legal entity overrides section can be used to identify which companies the main account should be suspended for, who the owner is and the time period the dimension is active.</span></span> <span data-ttu-id="7ce67-134">共有レベルの上書きを、法人レベルの上書きより強い制限にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7ce67-134">The overrides at the shared level cannot be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="7ce67-135">詳細については、次のトピックを参照してください。「[財務分析コード](financial-dimensions.md)」
「[詳細ルール構造の作成と割当](tasks/create-assign-advanced-rule-structures.md)」</span><span class="sxs-lookup"><span data-stu-id="7ce67-135">For more information, see the following topics: [Financial dimensions](financial-dimensions.md)
[Create and assign advanced rule structures](tasks/create-assign-advanced-rule-structures.md)</span></span>



