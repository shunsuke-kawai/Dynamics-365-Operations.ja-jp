--- 
title: "発生主義スキーマの作成"
description: "このタスク ガイドは、発生主義スキーマの作成について説明します。"
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 324be23a1e26de0d05c7cf6a61567f7260d0c390
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="create-accrual-schemes"></a><span data-ttu-id="b0b93-103">発生主義スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="b0b93-103">Create accrual schemes</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b0b93-104">このタスク ガイドは、発生主義スキーマの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-104">This task guide steps through creating an accrual scheme.</span></span> <span data-ttu-id="b0b93-105">このタスクでは、USMF というデモ会社を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="b0b93-106">[総勘定元帳] > [仕訳帳の設定] > [発生主義スキーマ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-106">Go to General ledger > Journal setup > Accrual schemes.</span></span>
2. <span data-ttu-id="b0b93-107">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0b93-107">Click New.</span></span>
3. <span data-ttu-id="b0b93-108">[発生主義スキーマ ID] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-108">In the Accrual identification field, type a value.</span></span>
4. <span data-ttu-id="b0b93-109">[発生主義スキーマの説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-109">In the Description of accrual scheme field, type a value.</span></span>
5. <span data-ttu-id="b0b93-110">[借方] フィールドで、任意の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-110">In the Debit field, specify the desired values.</span></span>
    * <span data-ttu-id="b0b93-111">定義した主勘定は、仕訳帳伝票の明細行の借方主勘定と置き換えられ、元帳計上トランザクションに基づく繰延の取消にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0b93-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="b0b93-112">[貸方] フィールドで、任意の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-112">In the Credit field, specify the desired values.</span></span>
    * <span data-ttu-id="b0b93-113">定義した主勘定は、仕訳帳伝票の明細行の貸方主勘定と置き換えられ、元帳計上トランザクションに基づく繰延の取消にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0b93-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="b0b93-114">トランザクションの転記時に、どのように伝票を判別するかを [伝票] フィールドで選択します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-114">In the Voucher field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="b0b93-115">[説明] フィールドに、転記されるトランザクションを説明する値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-115">In the Description field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="b0b93-116">[期間の頻度] フィールドで、トランザクションの発生頻度を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-116">In the Period frequency field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="b0b93-117">[期間別の発生数] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-117">In the Number of occurrences by period field, enter a number.</span></span>
11. <span data-ttu-id="b0b93-118">[トランザクションの転記] フィールドで、トランザクションを転記する時期 (「毎月」など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0b93-118">In the Post transactions field, select when the transactions should be posted, such as Monthly.</span></span>

