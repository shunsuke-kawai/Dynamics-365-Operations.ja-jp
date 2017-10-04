---
title: "単位間会計のバランス仕訳帳"
description: "この記事は、差引勘定する財務分析コードを [元帳] ページで選択したときに仕訳帳がどのように自動的に差引勘定されるかを示します。"
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: f45d180dc8dcafb0579e76b890dd5d516df5b8c0
ms.contentlocale: ja-jp
ms.lasthandoff: 06/29/2017


---

# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="3677a-103">単位間会計のバランス仕訳帳</span><span class="sxs-lookup"><span data-stu-id="3677a-103">Balanced journals for interunit accounting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3677a-104">この記事は、差引勘定する財務分析コードを [元帳] ページで選択したときに仕訳帳がどのように自動的に差引勘定されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="3677a-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="3677a-105">会計項目は財務分析コード値のレベルで収支を合わせないため、仕訳帳の収支を合わせるための追加の会計項目が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="3677a-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="3677a-106">これらの勘定項目は、**自動トランザクションの勘定**ページで**単位間 - 借方**と**単位間 - 貸方**を使用して主勘定を決定します。</span><span class="sxs-lookup"><span data-stu-id="3677a-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="3677a-107">たとえば、勘定科目の 2 番目の区分である [分岐] は、差引勘定する財務分析コードとして選択され、次の勘定項目が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3677a-107">For example, Branch, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

|                      |           |
|----------------------|-----------|
| <span data-ttu-id="3677a-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="3677a-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="3677a-109">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="3677a-109">100.00 DR</span></span> |
| <span data-ttu-id="3677a-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="3677a-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="3677a-111">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="3677a-111">100.00 DR</span></span> |
| <span data-ttu-id="3677a-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="3677a-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="3677a-113">200.00 CR</span><span class="sxs-lookup"><span data-stu-id="3677a-113">200.00 CR</span></span> |

<span data-ttu-id="3677a-114">この場合、次の残高が決定されます:</span><span class="sxs-lookup"><span data-stu-id="3677a-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="3677a-115">ブランチ MSP = 100.00 CR</span><span class="sxs-lookup"><span data-stu-id="3677a-115">For Branch MSP = 100.00 CR</span></span>
-   <span data-ttu-id="3677a-116">ブランチ NY = 100.00 DR</span><span class="sxs-lookup"><span data-stu-id="3677a-116">For Branch NY = 100.00 DR</span></span>

<span data-ttu-id="3677a-117">したがって、次の勘定項目は、このエントリが財務分析コード値のレベルで仕訳帳を差引勘定するように自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="3677a-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

|                                   |           |
|-----------------------------------|-----------|
| <span data-ttu-id="3677a-118">(単位間の借方) – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="3677a-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="3677a-119">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="3677a-119">100.00 DR</span></span> |
| <span data-ttu-id="3677a-120">(単位間の借方) – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="3677a-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="3677a-121">100.00 CR</span><span class="sxs-lookup"><span data-stu-id="3677a-121">100.00 CR</span></span> |





