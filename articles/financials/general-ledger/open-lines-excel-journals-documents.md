---
title: "Excel から仕訳帳明細行とドキュメントを発行する"
description: "このトピックでは、Microsoft Excel の一般仕訳帳のドキュメント明細行入力および発行方法について説明します。 ここには、入力するトランザクションのタイプに応じて、使用できるさまざまなテンプレートに関する情報が含まれています。"
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1e30b8d01dc398c91bb7ade7ebb48301ae2e9189
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="publish-journal-lines-and-documents-from-excel"></a><span data-ttu-id="53457-104">Excel から仕訳帳明細行とドキュメントを発行する</span><span class="sxs-lookup"><span data-stu-id="53457-104">Publish journal lines and documents from Excel</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="53457-105">このトピックでは、Microsoft Excel の一般仕訳帳のドキュメント明細行入力および発行方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="53457-105">This topic explains how to enter and publish lines for general journals from Microsoft Excel.</span></span> <span data-ttu-id="53457-106">ここには、入力するトランザクションのタイプに応じて、使用できるさまざまなテンプレートに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53457-106">It includes information about the various templates that you can use, depending on the type of transactions that you're entering.</span></span>

<span data-ttu-id="53457-107">ユーザーは、Microsoft Excel から財務仕訳帳の明細行を入力および発行することができます。</span><span class="sxs-lookup"><span data-stu-id="53457-107">Users can enter and publish lines for financial journals from Microsoft Excel.</span></span> <span data-ttu-id="53457-108">ユーザーが仕訳帳を作成した後、[**Excel で明細行を開く**] ボタンは使用できるテンプレートを表示します。</span><span class="sxs-lookup"><span data-stu-id="53457-108">After a user creates a journal, the **Open lines in Excel** button displays the templates that are available.</span></span> <span data-ttu-id="53457-109">テンプレートは特定のシナリオをサポートするように設計されていますが、勘定タイプのすべての組み合わせが仕訳帳でサポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="53457-109">Templates are designed to support specific scenarios, however not every combination of account type is supported in the journal.</span></span> <span data-ttu-id="53457-110">次の表は、利用可能なテンプレートとそれらがサポートする勘定タイプを示しています。</span><span class="sxs-lookup"><span data-stu-id="53457-110">The following table shows the templates that are available and the account types which they support.</span></span>
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| <span data-ttu-id="53457-111">[**テンプレート**]</span><span class="sxs-lookup"><span data-stu-id="53457-111">**Template**</span></span>             | <span data-ttu-id="53457-112">[**サポートされる勘定タイプ**]</span><span class="sxs-lookup"><span data-stu-id="53457-112">**Supported account types**</span></span>                                                                                             | <span data-ttu-id="53457-113">[**テンプレートへのアクセス方法**]</span><span class="sxs-lookup"><span data-stu-id="53457-113">**How to access the template**</span></span>                                                          |
| <span data-ttu-id="53457-114">仕訳元帳明細行</span><span class="sxs-lookup"><span data-stu-id="53457-114">Ledger journal lines</span></span>     | <span data-ttu-id="53457-115">勘定: 元帳、顧客、仕入先、銀行の相手勘定: 元帳、顧客、仕入先、銀行間でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="53457-115">Account: Ledger, Customer, Vendor, Bank Offset account: Ledger, Customer, Vendor, Bank Intercompany is supported.</span></span>       | <span data-ttu-id="53457-116">一般仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-116">General journal</span></span>                                                                         |
| <span data-ttu-id="53457-117">仕入帳</span><span class="sxs-lookup"><span data-stu-id="53457-117">Invoice register</span></span>         | <span data-ttu-id="53457-118">勘定: 仕入先の相手勘定: 会社間元帳ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="53457-118">Account: Vendor Offset account: Ledger Intercompany isn't supported.</span></span>                                                    | <span data-ttu-id="53457-119">AP 仕入帳</span><span class="sxs-lookup"><span data-stu-id="53457-119">AP invoice register</span></span>                                                                     |
| <span data-ttu-id="53457-120">請求仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-120">Invoice journal</span></span>          | <span data-ttu-id="53457-121">勘定: 仕入先の相手勘定: 会社間元帳でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="53457-121">Accounts: Vendor Offset account: Ledger Intercompany is supported.</span></span>                                                      | <span data-ttu-id="53457-122">AP 請求仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-122">AP invoice journal</span></span>                                                                      |
| <span data-ttu-id="53457-123">仕入先請求書</span><span class="sxs-lookup"><span data-stu-id="53457-123">Vendor invoice</span></span>           |                                                                                                                         | <span data-ttu-id="53457-124">仕入先請求書</span><span class="sxs-lookup"><span data-stu-id="53457-124">Vendor invoice</span></span>                                                                          |
| <span data-ttu-id="53457-125">顧客請求書仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-125">Customer invoice journal</span></span> | <span data-ttu-id="53457-126">勘定: 顧客の相手勘定: 会社間元帳でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="53457-126">Account: Customer Offset account: Ledger Intercompany is supported.</span></span>                                                     | <span data-ttu-id="53457-127">一般仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-127">General journal</span></span>                                                                         |
| <span data-ttu-id="53457-128">自由書式の請求書</span><span class="sxs-lookup"><span data-stu-id="53457-128">Free text invoice</span></span>        |                                                                                                                         | <span data-ttu-id="53457-129">[**自由書式の請求書**] ページで、[**Excel で開く**] (Microsoft Office のアイコン) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53457-129">On the **Free text invoice** page, click **Open in Excel** (the Microsoft Office icon).</span></span> |
| <span data-ttu-id="53457-130">固定資産仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-130">Fixed assets journal</span></span>     | <span data-ttu-id="53457-131">元帳、銀行、顧客、または仕入先への資産。</span><span class="sxs-lookup"><span data-stu-id="53457-131">Asset to ledger, bank, customer, or vendor.</span></span> <span data-ttu-id="53457-132">会社間ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="53457-132">Intercompany isn't supported.</span></span>                                               | <span data-ttu-id="53457-133">固定資産仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-133">Fixed asset journal</span></span>                                                                     |
| <span data-ttu-id="53457-134">仕入先支払仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-134">Vendor payment journal</span></span>   | <span data-ttu-id="53457-135">勘定: 仕入先の相手勘定: 銀行間でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="53457-135">Account: Vendor Offset account: Ledger, Bank Intercompany is supported.</span></span>                                                 | <span data-ttu-id="53457-136">仕入先支払仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-136">Vendor payment journal</span></span>                                                                  |
| <span data-ttu-id="53457-137">顧客支払仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-137">Customer payment journal</span></span> | <span data-ttu-id="53457-138">勘定: 顧客の相手勘定: 銀行間でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="53457-138">Account: Customer Offset account: Ledger, Bank Intercompany is supported.</span></span>                                               | <span data-ttu-id="53457-139">顧客支払仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-139">Customer payment journal</span></span>                                                                |
| <span data-ttu-id="53457-140">プロジェクト経費仕訳帳</span><span class="sxs-lookup"><span data-stu-id="53457-140">Project expense journal</span></span>  | <span data-ttu-id="53457-141">勘定: プロジェクト元帳、顧客、仕入先、仕入先の相手勘定: プロジェクト、元帳、顧客、仕入先会社間でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="53457-141">Account: Project, Ledger, Customer, Vendor Offset account: Project, Ledger, Customer, Vendor Intercompany is supported.</span></span> | <span data-ttu-id="53457-142">一般仕訳帳への経費 (プロジェクト管理および会計で)</span><span class="sxs-lookup"><span data-stu-id="53457-142">General journal Expense (under Project management and accounting)</span></span>                       |

<span data-ttu-id="53457-143">行が公開されると、それらの行が財務仕訳帳に設定されているルールに準拠していることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="53457-143">When the lines are published, they are validated to make sure that they comply with the rules that are set up in the financial journals.</span></span> <span data-ttu-id="53457-144">行が公開されると、ユーザーは Microsoft Dynamics 365 for Finance and Operations、Enterprise Edition から伝票を編集または投稿することができます。</span><span class="sxs-lookup"><span data-stu-id="53457-144">After the lines are published, users can edit or post the vouchers from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> 

<span data-ttu-id="53457-145">テンプレートに財務分析コードを追加するには、追加の変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="53457-145">To add financial dimensions to a template, additional changes are required.</span></span> <span data-ttu-id="53457-146">詳細については、「[Microsoft Excel テンプレートに分析コードを追加する](/dynamics365/unified-operations/dev-itpro/financial/add-dimensions-excel-templates)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53457-146">For additional information, see [Add dimensions to the Microsoft Excel template](/dynamics365/unified-operations/dev-itpro/financial/add-dimensions-excel-templates).</span></span> <span data-ttu-id="53457-147">エンティティに分析コードを追加した後は、Excel デザイナーで使用でき、テンプレートに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="53457-147">After dimensions are added to the entity, they are available in the Excel designer and can be added to the template.</span></span>





