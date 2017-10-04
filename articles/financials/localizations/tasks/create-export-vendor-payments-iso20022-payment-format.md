--- 
title: "ISO20022 支払形式を使用した仕入先支払の作成とエクスポート"
description: "この手順では、仕入先支払仕訳帳で支払明細行を作成する方法、および ISO2022 口座振替の例を使用して仕入先支払ファイルを生成する方法を示します。"
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7cc90bc86cd489b124a806c480632dd53ba47f3f
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="061e5-103">ISO20022 支払形式を使用した仕入先支払の作成とエクスポート</span><span class="sxs-lookup"><span data-stu-id="061e5-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="061e5-104">この手順では、仕入先支払仕訳帳で支払明細行を作成する方法、および ISO2022 口座振替の例を使用して仕入先支払ファイルを生成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="061e5-104">This procedure shows how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span> 

<span data-ttu-id="061e5-105">この手順の作成に使用するデモ データの会社は DEMF です。</span><span class="sxs-lookup"><span data-stu-id="061e5-105">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="061e5-106">これは、5 つのうち 5 つ目の手順で、電子レポートのコンフィギュレーションを使用する仕入先支払処理を説明しています。</span><span class="sxs-lookup"><span data-stu-id="061e5-106">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="061e5-107">この手順は、Dynamics 365 for Operations、バージョン 1611 に追加された機能です。</span><span class="sxs-lookup"><span data-stu-id="061e5-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-payment-lines"></a><span data-ttu-id="061e5-108">支払明細行の作成</span><span class="sxs-lookup"><span data-stu-id="061e5-108">Create payment lines</span></span>
1. <span data-ttu-id="061e5-109">[買掛金勘定] > [支払] > [支払仕訳帳] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="061e5-109">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="061e5-110">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="061e5-110">Click New.</span></span>
3. <span data-ttu-id="061e5-111">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="061e5-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="061e5-112">[名前] フィールドで値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="061e5-112">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="061e5-113">[明細行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="061e5-113">Click Lines.</span></span>
6. <span data-ttu-id="061e5-114">[支払提案] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="061e5-114">Click Payment proposal.</span></span>
7. <span data-ttu-id="061e5-115">[支払提案の作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="061e5-115">Click Create payment proposal.</span></span>
8. <span data-ttu-id="061e5-116">[対象に含めるレコード] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="061e5-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="061e5-117">[フィルター] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="061e5-117">Click Filter.</span></span>
10. <span data-ttu-id="061e5-118">一覧で、[仕入先] テーブルの行および [仕入先] フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="061e5-118">In the list, select the row for Vendors table and Vendor account field.</span></span>
11. <span data-ttu-id="061e5-119">[基準] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="061e5-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="061e5-120">支払う仕入先トランザクションを選択するためのあらゆる基準を適用できます。この例では、DE-001 を仕入先として使用します。</span><span class="sxs-lookup"><span data-stu-id="061e5-120">You can apply any criteria for selecting vendor transactions to pay, for this example use DE-001 as a vendor account.</span></span>  
12. <span data-ttu-id="061e5-121">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="061e5-121">Click OK.</span></span>
13. <span data-ttu-id="061e5-122">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="061e5-122">Click OK.</span></span>
14. <span data-ttu-id="061e5-123">[支払の作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="061e5-123">Click Create payments.</span></span>

## <a name="generate-an-iso20022-payment-file"></a><span data-ttu-id="061e5-124">ISO20022 支払ファイルの生成</span><span class="sxs-lookup"><span data-stu-id="061e5-124">Generate an ISO20022 payment file</span></span>

