---
title: "会社間勘定の設定"
description: "このトピックは、日次仕訳帳、ベンダー請求書仕訳帳、支払仕訳帳などの会計割り当ておよび財務仕訳帳の会社間仕訳帳を使用できるように会社間の会計を設定する方法に関して説明します。"
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 9c5e73d97f6f52a417cb71dc5bfb57658765aaa1
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="intercompany-accounting-setup"></a><span data-ttu-id="59435-103">会社間勘定の設定</span><span class="sxs-lookup"><span data-stu-id="59435-103">Intercompany accounting setup</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="59435-104">このトピックは、日次仕訳帳、ベンダー請求書仕訳帳、支払仕訳帳などの会計割り当ておよび財務仕訳帳の会社間仕訳帳を使用できるように会社間の会計を設定する方法に関して説明します。</span><span class="sxs-lookup"><span data-stu-id="59435-104">This topic explains how to set up intercompany accounting so that you can use intercompany journals for ledger allocations and financial journals, such as daily journals, vendor invoice journals, and payment journals.</span></span>

<span data-ttu-id="59435-105">会社間仕訳帳は、日次仕訳帳、ベンダー請求書仕訳帳、会計割り当ておよび一括支払など、さまざまなタイミングで作成できます。</span><span class="sxs-lookup"><span data-stu-id="59435-105">Intercompany journals can be created in various scenarios, such as for daily journals, vendor invoice journals, ledger allocations, and centralized payments.</span></span> <span data-ttu-id="59435-106">これらのシナリオを有効にするには、会社間会計を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59435-106">To enable these scenarios, you must set up intercompany accounting.</span></span>

## <a name="define-main-accounts"></a><span data-ttu-id="59435-107">主勘定を定義する</span><span class="sxs-lookup"><span data-stu-id="59435-107">Define main accounts</span></span>
<span data-ttu-id="59435-108">最初に、貸し勘定項目および借り勘定項目に使用する会社間主勘定を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59435-108">First, you must create the intercompany main accounts to use for the Due to and Due from accounting entries.</span></span> <span data-ttu-id="59435-109">会社間勘定項目の調整および削除を簡略化するために、会社ごとに固有の主勘定を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59435-109">It's a good idea to use unique main accounts for each company, to simplify the reconciliation and elimination of intercompany accounting entries.</span></span> <span data-ttu-id="59435-110">トレーディング パートナまたはカウンターパート ディメンションを使用して内部取引先を識別する場合、このディメンションは、内部取引会計で定義されている主勘定の固定ディメンションとして定義することができます。</span><span class="sxs-lookup"><span data-stu-id="59435-110">If you're using a trading partner or counterpart dimension to identify the intercompany party, you can define this dimension as a fixed dimension on the main account that is defined in Intercompany accounting.</span></span> <span data-ttu-id="59435-111">主勘定を設定するときは、**主勘定**ページで、[**主勘定タイプ**] フィールドを [**貸借対照表**] に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59435-111">When you set up the main accounts, you should set the **Main account type** field to **Balance sheet** on the **Main accounts** page.</span></span>

## <a name="define-journal-names"></a><span data-ttu-id="59435-112">仕訳帳名の定義</span><span class="sxs-lookup"><span data-stu-id="59435-112">Define journal names</span></span>
<span data-ttu-id="59435-113">次に、仕訳帳名を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59435-113">Next, you must define a journal name.</span></span> <span data-ttu-id="59435-114">**仕訳帳名**ページで、[**仕訳帳タイプ**] フィールドを [**毎日**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="59435-114">Set the **Journal type** field to **Daily** on the **Journal names** page.</span></span> <span data-ttu-id="59435-115">会社間会計に対して特定の仕訳帳名を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59435-115">It's a good idea to use a specific journal name for intercompany accounting.</span></span>

## <a name="define-intercompany-accounting-setup"></a><span data-ttu-id="59435-116">会社間会計設定を定義する</span><span class="sxs-lookup"><span data-stu-id="59435-116">Define intercompany accounting setup</span></span>
<span data-ttu-id="59435-117">**会社間会計**ページは、お互いに取引できる法人のペアを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="59435-117">The **Intercompany accounting** page is used to create the pairs of legal entities that can transact with each other.</span></span> <span data-ttu-id="59435-118">会社間会計設定は共有されているため、すべての法人内から設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="59435-118">The Intercompany accounting setup is shared, so the setup is visible from within all legal entities.</span></span> <span data-ttu-id="59435-119">新しい法人のペアを作成する場合、目的とする会社に対して、どの法人を元の会社とするかを把握している必要があります。</span><span class="sxs-lookup"><span data-stu-id="59435-119">When creating a new legal entity pair, ensure that you are aware of which legal entity is defined as the originating company versus the destination company.</span></span> <span data-ttu-id="59435-120">会社間のトランザクションが行われる場合、トランザクションはどの法人がトランザクションを開始するかまたは起源となるかについて決定します。</span><span class="sxs-lookup"><span data-stu-id="59435-120">When entering intercompany transactions, the transaction determines which legal entity is initiating or originating the transaction.</span></span> <span data-ttu-id="59435-121">たとえば、会社間会計が USMF (元) および USSI (目的先) に対して設定されています。</span><span class="sxs-lookup"><span data-stu-id="59435-121">For example, the intercompany accounting is setup for USMF (originating) and USSI (destination).</span></span> <span data-ttu-id="59435-122">ある USSI がアクティブなユーザーが、USMF との内部取引を開始すると、内部会社会計は発信元である USMF に対してのみ定義されるため、取引は転記されません。</span><span class="sxs-lookup"><span data-stu-id="59435-122">If a user is active in USSI and enters an intercompany transaction with USMF, the transaction will not post because the intercompany accounting is only defined for USMF being the originator.</span></span> <span data-ttu-id="59435-123">いずれかの会社が取引を開始することができる場合は、相互設定のための第 2 の法人のペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59435-123">If either company can originate a transaction, you will need to create a second legal entity pair for the reciprocal setup.</span></span> 

<span data-ttu-id="59435-124">元の法人と目的の法人の両方の、**借方取引先企業 (元)** および**クレジット取引先企業 (目的先)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="59435-124">Select the **Debit account (Due from)** and **Credit account (Due to)** for both the originating and destination legal entity.</span></span> <span data-ttu-id="59435-125">宛先の会社でトランザクションが作成されたときに使用する**仕訳帳名**を定義します。</span><span class="sxs-lookup"><span data-stu-id="59435-125">Define which **Journal name** will be used when the transaction is created in the destination company.</span></span> <span data-ttu-id="59435-126">元の会社の仕訳帳は、会社間取引の作成時にユーザーによって選択されているので、すでにわかっています。</span><span class="sxs-lookup"><span data-stu-id="59435-126">The journal for the originating company is already known because it's selected by the user when creating the intercompany transaction.</span></span> 

<span data-ttu-id="59435-127">最後に、現金割引や集中支払の実現損益などの金額を支援する会計をどの法人が受け取るかを選択します。</span><span class="sxs-lookup"><span data-stu-id="59435-127">Finally, select which legal entity will receive the accounting for supporting amounts, such as cash discount or realized gains/losses for centralized payments.</span></span> 

<span data-ttu-id="59435-128">相互的な関係は、最初の法人ペアが作成された後に、**会社間会計**ページで [**相互的関係の作成**] ボタンを使用することにより簡単に設定できます。</span><span class="sxs-lookup"><span data-stu-id="59435-128">A reciprocal relationship can easily be set up on the **Intercompany accounting** page by using the **Create reciprocal relationship** button after the first legal entity pair is created.</span></span> <span data-ttu-id="59435-129">相互的なペアが作成された場合、目的先の会社の情報が元の会社にコピーされ、その更新が相互に反映されます。</span><span class="sxs-lookup"><span data-stu-id="59435-129">When the reciprocal pair is created, the information for the destination company is copied to the originating company and vice versa.</span></span> <span data-ttu-id="59435-130">目的先の会社に対して定義された仕訳帳は残ります。</span><span class="sxs-lookup"><span data-stu-id="59435-130">The journal defined for the destination company will remain.</span></span> <span data-ttu-id="59435-131">ほとんどの組織では、仕訳帳の名前に対して同じ命名規則を使用しているので、仕訳帳名は同じです。</span><span class="sxs-lookup"><span data-stu-id="59435-131">Most organizations use the same naming convention for their journal names, so that the journal name is the same.</span></span> <span data-ttu-id="59435-132">仕訳帳の名前が異なる場合、仕訳帳が存在せず異なる仕訳帳が選択されているということを注意するために、フィールドに警告が発せられます。</span><span class="sxs-lookup"><span data-stu-id="59435-132">If the journal name is different, a warning will appear on the field to notify you that the journal doesn't exist and a different journal can be selected.</span></span>



