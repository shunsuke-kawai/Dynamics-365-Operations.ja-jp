---
title: "監査ポリシー ルール"
description: "経費精算書、仕入先請求書、および発注書が、作成したポリシー ルールに準拠しているかどうか評価するには、監査ポリシーを使用できます。 監査ポリシーに関連付けられているすべてのルールが、指定したスケジュールに従ってバッチ モードで実行されます。  各ポリシー ルールは、ポリシー ルール タイプのインスタンスです。 各ポリシー ルール タイプに対して、一度に 1 つのポリシー ルールだけ有効にできます。"
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 31c3fac2117fbc580e0c40d840a037f3073d66b4
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="audit-policy-rules"></a><span data-ttu-id="420d2-106">監査ポリシー ルール</span><span class="sxs-lookup"><span data-stu-id="420d2-106">Audit policy rules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="420d2-107">経費精算書、仕入先請求書、および発注書が、作成したポリシー ルールに準拠しているかどうか評価するには、監査ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="420d2-107">You can use audit policies to evaluate expense reports, vendor invoices, and purchase orders to make sure that they comply with policy rules that you create.</span></span> <span data-ttu-id="420d2-108">監査ポリシーに関連付けられているすべてのルールが、指定したスケジュールに従ってバッチ モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="420d2-108">All of the rules that are associated with an audit policy are run in batch mode, according to a schedule that you specify.</span></span>  <span data-ttu-id="420d2-109">各ポリシー ルールは、ポリシー ルール タイプのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="420d2-109">Each policy rule is an instance of a policy rule type.</span></span> <span data-ttu-id="420d2-110">各ポリシー ルール タイプに対して、一度に 1 つのポリシー ルールだけ有効にできます。</span><span class="sxs-lookup"><span data-stu-id="420d2-110">For each policy rule type, only one policy rule can be active at a time.</span></span> 

<a name="queries-and-query-types"></a><span data-ttu-id="420d2-111">クエリおよびクエリ タイプ</span><span class="sxs-lookup"><span data-stu-id="420d2-111">Queries and query types</span></span>
-----------------------

<span data-ttu-id="420d2-112">監査ポリシー ルールを作成する場合は、最初にポリシー ルール タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="420d2-112">When you create an audit policy rule, you first select a policy rule type.</span></span> <span data-ttu-id="420d2-113">ポリシー ルール タイプは、ポリシー ルールを作成するための開始点として使用するアプリケーション オブジェクト ツリー (AOT) のクエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="420d2-113">The policy rule type specifies the Application Object Tree (AOT) query to use as the starting point for creating the policy rule.</span></span> <span data-ttu-id="420d2-114">また、ポリシー ルールに使用するクエリ タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="420d2-114">It also specifies the query type to use for the policy rule.</span></span> <span data-ttu-id="420d2-115">クエリは、ポリシー ルールが評価する元伝票を決定します。</span><span class="sxs-lookup"><span data-stu-id="420d2-115">The query determines the source document that the policy rule evaluates.</span></span> <span data-ttu-id="420d2-116">また、法人および日付の両方を識別する元伝票のフィールド指定して、監査するドキュメントを選択する際に使用します。</span><span class="sxs-lookup"><span data-stu-id="420d2-116">It also specifies the fields in the source document that identify both the legal entity and the date to use when documents are selected for audit.</span></span> <span data-ttu-id="420d2-117">クエリ タイプは、クエリ ページと監査ポリシー ルール ページの既定のフィールドを制御します。</span><span class="sxs-lookup"><span data-stu-id="420d2-117">The query type controls the default fields in the query page and in the Audit policy rule page.</span></span> <span data-ttu-id="420d2-118">次の表に、監査ポリシー ルールに使用できるクエリ タイプを示します。</span><span class="sxs-lookup"><span data-stu-id="420d2-118">The following table shows the query types that are available for audit policy rules.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="420d2-119">クエリ タイプ</span><span class="sxs-lookup"><span data-stu-id="420d2-119">Query type</span></span></th>
<th><span data-ttu-id="420d2-120">目的</span><span class="sxs-lookup"><span data-stu-id="420d2-120">Purpose</span></span></th>
<th><span data-ttu-id="420d2-121">詳細</span><span class="sxs-lookup"><span data-stu-id="420d2-121">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="420d2-122">条件付</span><span class="sxs-lookup"><span data-stu-id="420d2-122">Conditional</span></span></td>
<td><span data-ttu-id="420d2-123">指定した値に対して元伝票属性を評価します。</span><span class="sxs-lookup"><span data-stu-id="420d2-123">Evaluate source document attributes against specified values.</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="420d2-124">集計</span><span class="sxs-lookup"><span data-stu-id="420d2-124">Aggregate</span></span></td>
<td><span data-ttu-id="420d2-125">数値の集計によるポリシー ルールに対して複数の元伝票または元伝票明細行を評価します。</span><span class="sxs-lookup"><span data-stu-id="420d2-125">Evaluate multiple source documents or source document lines against a policy rule by aggregating numeric values.</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="420d2-126">サンプリング</span><span class="sxs-lookup"><span data-stu-id="420d2-126">Sampling</span></span></td>
<td><span data-ttu-id="420d2-127">元伝票から指定した割合をランダムに選択して、ポリシー違反について評価します。</span><span class="sxs-lookup"><span data-stu-id="420d2-127">Randomly select a specified percentage of the source documents to evaluate for policy violations.</span></span></td>
<td><span data-ttu-id="420d2-128">このオプションを選択する際、監査ポリシー ルール ページを使用して、監査のためにランダムに選択するドキュメントの割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="420d2-128">When you select this option, use the Audit policy rule page to specify the percentage of documents to randomly select for audit.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="420d2-129">複製</span><span class="sxs-lookup"><span data-stu-id="420d2-129">Duplicate</span></span></td>
<td><span data-ttu-id="420d2-130">指定したフィールドに重複するエントリが含まれているかどうかを決定するために、元伝票を評価します。</span><span class="sxs-lookup"><span data-stu-id="420d2-130">Evaluate source documents to determine whether they contain duplicate entries in specified fields.</span></span></td>
<td><span data-ttu-id="420d2-131">このオプションを選択する際、監査ポリシー ルール ページを使用して、ドキュメントが重複するエントリを評価するときに、ドキュメント選択の日付範囲の開始に追加する日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="420d2-131">When you select this option, use the Audit policy rule page to specify the number of days to add to the start of the document selection date range when documents are evaluated for duplicate entries.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="420d2-132">リスト検索</span><span class="sxs-lookup"><span data-stu-id="420d2-132">List search</span></span></td>
<td><span data-ttu-id="420d2-133">特定のエンティティの元伝票を評価します。</span><span class="sxs-lookup"><span data-stu-id="420d2-133">Evaluate source documents for specific entities.</span></span></td>
<td><span data-ttu-id="420d2-134">クエリのルート ドキュメントは、監査するドキュメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="420d2-134">The root document of the query defines the document that is being audited.</span></span> <span data-ttu-id="420d2-135">クエリは dirpartytable テーブルへの参照が含まれるリストのクエリである必要があります。</span><span class="sxs-lookup"><span data-stu-id="420d2-135">The query must be a list query that includes a reference to the dirpartytable table.</span></span> <span data-ttu-id="420d2-136">このオプションは、次の AOT のクエリでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="420d2-136">This option can be used only with the following AOT queries:</span></span>
<ul>
<li><span data-ttu-id="420d2-137"><span class="ui">AuditPolicyExpenseList</span> (経費精算書が監視対象の従業員)</span><span class="sxs-lookup"><span data-stu-id="420d2-137"><span class="ui">AuditPolicyExpenseList</span> (Expense report monitored employees)</span></span></li>
<li><span data-ttu-id="420d2-138"><span class="ui">AuditPolicyPurchList</span> (発注書が監視対象の仕入先)</span><span class="sxs-lookup"><span data-stu-id="420d2-138"><span class="ui">AuditPolicyPurchList</span> (Purchase order monitored vendors)</span></span></li>
<li><span data-ttu-id="420d2-139"><span class="ui">AuditPolicyVendInvoiceList</span> (仕入先請求書によって監視する仕入先)</span><span class="sxs-lookup"><span data-stu-id="420d2-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Vendor invoice monitored vendors)</span></span></li>
</ul>
<span data-ttu-id="420d2-140">このオプションを選択する際、監査ポリシー ルール ページで監視対象のエンティティを指定します。</span><span class="sxs-lookup"><span data-stu-id="420d2-140">When you select this option, specify the monitored entities in the Audit policy rule page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="420d2-141">キーワード検索</span><span class="sxs-lookup"><span data-stu-id="420d2-141">Keyword search</span></span></td>
<td><span data-ttu-id="420d2-142">元伝票を評価して、特定の語を含んでいるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="420d2-142">Evaluate source documents to determine whether they contain certain words.</span></span></td>
<td><span data-ttu-id="420d2-143">このオプションを選択する際、監査ポリシー ルール ページで検索する語を入力します。</span><span class="sxs-lookup"><span data-stu-id="420d2-143">When you select this option, enter the words to look for in the Audit policy rule page.</span></span> <span data-ttu-id="420d2-144">監査ポリシー ルール ページでは、入力した語について評価するテーブルおよびフィールドを指定できるオプションも含まれています。</span><span class="sxs-lookup"><span data-stu-id="420d2-144">The Audit policy rule page also includes options that let you specify the tables and fields to evaluate for the words you entered.</span></span></td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a><span data-ttu-id="420d2-145">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="420d2-145">Common parameters</span></span>
<span data-ttu-id="420d2-146">特定の監査ポリシーのすべてのポリシー ルールは、同じバッチ パラメーターおよび同じドキュメント選択日付範囲を共有します。</span><span class="sxs-lookup"><span data-stu-id="420d2-146">All of the policy rules for a particular audit policy share the same batch parameters and the same document selection date range.</span></span> <span data-ttu-id="420d2-147">ポリシーのこれらのパラメーターは、追加のオプション ページで指定されます。</span><span class="sxs-lookup"><span data-stu-id="420d2-147">These parameters are specified for the policy in the Additional options page.</span></span>



<a name="see-also"></a><span data-ttu-id="420d2-148">参照</span><span class="sxs-lookup"><span data-stu-id="420d2-148">See also</span></span>
--------

<span data-ttu-id="420d2-149">[監査ポリシー違反およびケース](audit-policy-violations-cases.md)
[元伝票の監査ポリシーの定義](tasks/define-audit-policies-source-documents.md)</span><span class="sxs-lookup"><span data-stu-id="420d2-149">[Audit policy violations and cases](audit-policy-violations-cases.md)
[Define audit policies for source documents](tasks/define-audit-policies-source-documents.md)</span></span>


