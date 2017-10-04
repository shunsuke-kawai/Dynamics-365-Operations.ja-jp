---
title: "詳細な口座調整の概要"
description: "この記事は、高度な口座調整プロセスのフローについて説明します。 高度な口座調整機能では、銀行トランザクション内で自動的に調整できる口座取引明細書をインポートできます。"
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 33150777222faa97af7488c59ab13cb0fb9e8e2c
ms.contentlocale: ja-jp
ms.lasthandoff: 06/29/2017


---

# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="d6b6d-104">詳細な口座調整の概要</span><span class="sxs-lookup"><span data-stu-id="d6b6d-104">Advanced bank reconciliation overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d6b6d-105">この記事は、高度な口座調整プロセスのフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="d6b6d-106">高度な口座調整機能では、銀行トランザクション内で自動的に調整できる口座取引明細書をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="d6b6d-107">詳細な口座調整機能により、口座取引明細書のインポートをすることができます。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="d6b6d-108">インポートした口座取引明細書は、次に自動的に銀行トランザクション内から調整されます。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="d6b6d-109">詳細な口座調整のフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="d6b6d-110">口座取引明細書のインポートを設定します。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="d6b6d-111">データ エンティティ フレームワークを使用して口座取引明細書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="d6b6d-112">ISO20022、BAI2、MT940、の 3 つの一般的な口座取引明細書の形式が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="d6b6d-113">機能は、任意の形式に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="d6b6d-114">詳細な口座調整に使用する番号順序を設定して、口座調整の照合ルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="d6b6d-115">調整の照合ルールは、調整プロセス中に口座取引明細行および Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 銀行トランザクション明細行をフィルタ処理するために使用される一連の基準です。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 for Finance and Operations, Enterprise edition bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="d6b6d-116">業務内容によって、1 つ以上の照合ルールを設定して、調整プロセスを自動化また最適化できます。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="d6b6d-117">Finance and Operations の銀行トランザクションを使用して、口座取引明細書を調整します。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-117">Reconcile bank statements with Finance and Operations bank transactions.</span></span>
    -   <span data-ttu-id="d6b6d-118">口座調整仕訳の自動照合と作成を実行します。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="d6b6d-119">口座取引明細書と Finance and Operations の銀行トランザクションを並べて表示します。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-119">View bank statements and Finance and Operations bank transactions side by side.</span></span>
    -   <span data-ttu-id="d6b6d-120">口座取引明細書には表示されるが Finance and Operations には表示されない場合、Finance and Operations に銀行のトランザクションを自動的に転記します。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-120">Automatically post Finance and Operations bank transactions if they appear on a bank statement but don't appear in Finance and Operations.</span></span>
    -   <span data-ttu-id="d6b6d-121">調整明細書を生成します。</span><span class="sxs-lookup"><span data-stu-id="d6b6d-121">Generate a reconciliation statement.</span></span>





