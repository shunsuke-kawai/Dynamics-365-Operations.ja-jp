--- 
title: "仕入先支払の概要"
description: "このガイドでは、仕入先支払の作成に使用するさまざまな方法について説明します。また、支払提案の使用方法または手動で 1 回限りの支払入力方法についても説明します。"
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 020d147744df24b2065e66e5fc68ed5d5479127b
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="vendor-payment-overview"></a><span data-ttu-id="9ea83-103">仕入先支払の概要</span><span class="sxs-lookup"><span data-stu-id="9ea83-103">Vendor payment overview</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9ea83-104">このガイドでは、仕入先支払の作成に使用するさまざまな方法について説明します。また、支払提案の使用方法または手動で 1 回限りの支払入力方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-104">This task guide will walk you through various methods used to create vendor payments, including how to use a payment proposal or manually entering a one-off payment.</span></span> <span data-ttu-id="9ea83-105">この手順では、USMF というデモ会社を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-105">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="9ea83-106">[買掛金勘定] > [支払] > [支払仕訳帳] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-106">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="9ea83-107">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-107">Click New.</span></span>
3. <span data-ttu-id="9ea83-108">仕入先支払を保存する支払仕訳帳を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-108">Select the payment journal in which to save the vendor payments.</span></span> 
4. <span data-ttu-id="9ea83-109">仕訳帳を選択するか、または手動で仕訳帳を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-109">Select the journal or manually enter it.</span></span>
5. <span data-ttu-id="9ea83-110">[明細行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-110">Click Lines.</span></span>
6. <span data-ttu-id="9ea83-111">[支払提案] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-111">Click Payment proposal.</span></span>
7. <span data-ttu-id="9ea83-112">[支払提案の作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-112">Click Create payment proposal.</span></span>
    * <span data-ttu-id="9ea83-113">支払提案は、支払の請求書を選択するために使用するクエリです。</span><span class="sxs-lookup"><span data-stu-id="9ea83-113">The payment proposal is a query used to select invoices for payment.</span></span> <span data-ttu-id="9ea83-114">仕入先支払を作成または生成する前に、支払請求書のリストを編集できます。</span><span class="sxs-lookup"><span data-stu-id="9ea83-114">You can edit the list of invoices to pay before creating or generating the vendor payments.</span></span>  
8. <span data-ttu-id="9ea83-115">期日別の請求書、現金割引、またはその両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-115">Select invoices for payment by due date, cash discount, or both.</span></span> 
9. <span data-ttu-id="9ea83-116">期日または現金割引と比較する日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-116">Enter the date for comparing to the due date or cash discount.</span></span> 
10. <span data-ttu-id="9ea83-117">オプション: すべての支払に使用される支払期日を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-117">Optional: Enter a payment date used for all payments.</span></span>
    * <span data-ttu-id="9ea83-118">ここで入力された日付は、期日または現金割引日に関係なく、作成されたすべての支払の支払期日です。</span><span class="sxs-lookup"><span data-stu-id="9ea83-118">The date entered here will be the payment date for all payments created, regardless of the due date or cash discount date.</span></span>  
11. <span data-ttu-id="9ea83-119">オプション: 支払期日として使用できる最短支払日を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-119">Optional: Enter a minimum payment date which may be used as the payment date.</span></span>
    * <span data-ttu-id="9ea83-120">最短支払期日は、支払を作成するときに使用する最も早い日付です。</span><span class="sxs-lookup"><span data-stu-id="9ea83-120">The minimum payment date will be the earliest date used when creating payments.</span></span> <span data-ttu-id="9ea83-121">たとえば、請求書の期日が最短支払期日以降の場合、最も遅い日に請求書の支払をするには、期日は最短支払期日の代わりに支払日になります。</span><span class="sxs-lookup"><span data-stu-id="9ea83-121">For example, if an invoice has a due date after the minimum payment date, the due date will become the payment date instead of the minimum payment date in order to pay the invoice on the latest possible date.</span></span>  
12. <span data-ttu-id="9ea83-122">[対象に含めるレコード] で追加のクエリの制限を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-122">Enter additional query restrictions under Records to include.</span></span>
    * <span data-ttu-id="9ea83-123">一般に、フィルターは、仕入先グループまたは支払方法により支払に対して選択される請求書を制限するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-123">The filter is often used to restrict the invoices selected for payment by vendor group or method of payment.</span></span> <span data-ttu-id="9ea83-124">たとえば、この支払を行った際の小切手で支払った請求書のみに制限するフィルターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9ea83-124">For example, you may add a filter to only pay invoices by cheque in this pay run.</span></span>  
13. <span data-ttu-id="9ea83-125">追加のクエリの制限または支払の既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-125">Enter additional query restriction or payment defaults.</span></span> 
    * <span data-ttu-id="9ea83-126">支払通貨を定義したり、またはこの支払を行う際に集中支払を有効にするために、追加のパラメータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ea83-126">The additional parameters can be used to define the payment currency or to enable centralized payments for this pay run.</span></span>  
14. <span data-ttu-id="9ea83-127">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-127">Click OK.</span></span>
    * <span data-ttu-id="9ea83-128">[OK] をクリックすると、クエリの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ea83-128">After clicking OK, the results of the query will appear.</span></span> <span data-ttu-id="9ea83-129">支払に選択された請求書のリストをプレビューしない場合は、[パラメータ] クイック タブに戻り、[請求書をプレビューせずに支払を作成する] の設定を [はい] に変更します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-129">If you don't want to preview the list of invoices selected to pay, you can go back to the Parameters fast tab and change the setting Create payments without invoice preview = Yes.</span></span>  
15. <span data-ttu-id="9ea83-130">選択した請求書の仕入先に対して作成される支払を表示するには、[支払概要の表示] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-130">Choose the Show payment overview button to view the payments that will be created for the vendor on the invoice selected.</span></span>
16. <span data-ttu-id="9ea83-131">支払を非表示にするには、[支払概要の非表示] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-131">Choose the Hide payment overview button to hide the payments.</span></span> 
17. <span data-ttu-id="9ea83-132">[支払の作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-132">Click Create payments.</span></span>
    * <span data-ttu-id="9ea83-133">[支払の作成] を選択する前に、グリッドを右クリックして、Excel へ請求書の一覧をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="9ea83-133">Before choosing Create payments, you can right click on the grid and export the list of invoices to Excel.</span></span> <span data-ttu-id="9ea83-134">[支払の作成] ボタンは、支払仕訳帳に仕入先支払を作成します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-134">The Create payments button will create the vendor payments in the payment journal.</span></span>  
18. <span data-ttu-id="9ea83-135">支払をスキャンして、すべての支払に対して定義されている支払方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-135">Scan your payments and make sure the method of payment is defined for all payments.</span></span> 
    * <span data-ttu-id="9ea83-136">小切手の印刷または電子支払の作成などの支払を生成する場合、支払方法を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ea83-136">If you generate the payments, such as printing a cheque or creating an electronic payment, the method of payment must be defined.</span></span> <span data-ttu-id="9ea83-137">支払方法は、支払の払出元となる銀行口座が既定値になります。</span><span class="sxs-lookup"><span data-stu-id="9ea83-137">The method of payment will also default the bank account from the payment will be made.</span></span>  
19. <span data-ttu-id="9ea83-138">1 回限りの支払を作成するには、[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-138">Click New to create a one-off payment.</span></span>
    * <span data-ttu-id="9ea83-139">転記前ならいつでも、支払仕訳帳に 1 回限りの支払を追加できます。</span><span class="sxs-lookup"><span data-stu-id="9ea83-139">A one-off payment can be added to a payment journal at any time prior to posting.</span></span> <span data-ttu-id="9ea83-140">これを行うには、支払提案を使用する代わりに、[新規] ボタンをクリックして手動で支払情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-140">This is done by clicking the New button and adding the payment information manually, rather then using the Payment proposal.</span></span>  
20. <span data-ttu-id="9ea83-141">支払が作成される仕入先を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-141">Select the vendor to whom the payment will be made.</span></span>
21. <span data-ttu-id="9ea83-142">支払が必要な請求書がある場合、[トランザクションの決済] を選択して支払の請求書を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-142">If an invoice exists to pay, select Settle transactions to select the invoice for payment.</span></span>
    * <span data-ttu-id="9ea83-143">前払の場合は、この手順はオプションです。</span><span class="sxs-lookup"><span data-stu-id="9ea83-143">If this is a prepayment, this step is optional.</span></span> <span data-ttu-id="9ea83-144">請求書を選択せずに支払を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9ea83-144">You can create the payment without selecting any invoice.</span></span>  
22. <span data-ttu-id="9ea83-145">支払われる請求書をマークします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-145">Mark any invoices that will be paid.</span></span>
    * <span data-ttu-id="9ea83-146">[トランザクションの決済] を使用して支払の請求書を選択する場合、支払をマークした請求書および [決済金額] に入力した金額に基づき、支払金額が自動的に計算されます。</span><span class="sxs-lookup"><span data-stu-id="9ea83-146">If you use the Settle transactions to select the invoices for payment, the payment amount will automatically be calculated based on what invoices you mark for payment, and what amount you enter in the Amount to settle.</span></span>  
23. <span data-ttu-id="9ea83-147">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-147">Click OK.</span></span>
24. <span data-ttu-id="9ea83-148">支払を削除する場合は、行をマークします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-148">If you want to delete a payment, mark the row.</span></span>
25. <span data-ttu-id="9ea83-149">[削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-149">Click Delete.</span></span>
    * <span data-ttu-id="9ea83-150">[支払の削除] は、支払を削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="9ea83-150">Deleting a payment will only delete the payment.</span></span> <span data-ttu-id="9ea83-151">支払をマークした請求書は、後から別の支払によって支払うことができます。</span><span class="sxs-lookup"><span data-stu-id="9ea83-151">Any invoices marked for payment will still be available to be paid by another payment.</span></span>  
26. <span data-ttu-id="9ea83-152">[はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-152">Click Yes.</span></span>
27. <span data-ttu-id="9ea83-153">小切手の印刷、または電子支払ファイルを作成するには、[支払の生成] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-153">Choose Generate payment to print Cheques or create the electronic payment file.</span></span>
28. <span data-ttu-id="9ea83-154">生成する支払の支払方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-154">Select the method of payment that you want to generate.</span></span>
    * <span data-ttu-id="9ea83-155">支払仕訳帳には、小切手と電子支払の両方の支払が含まれますが、一度に 1 つの支払タイプのみが生成できます。</span><span class="sxs-lookup"><span data-stu-id="9ea83-155">The payment journal can contains payments for both Cheques and electronic payments, but you can only generate one payment type at a time.</span></span>  
29. <span data-ttu-id="9ea83-156">支払を生成する銀行口座を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-156">Select the bank account from which to generate the payments.</span></span>
30. <span data-ttu-id="9ea83-157">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-157">Click OK.</span></span>
    * <span data-ttu-id="9ea83-158">選択した支払方法と銀行口座が一致した支払に対してのみ、支払を生成します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-158">Payments will only be generated for payments that match the Method of payment and Bank account you selected.</span></span>  
31. <span data-ttu-id="9ea83-159">小切手を生成する場合、その小切手の正しい出力先を確認するためのドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-159">If you are generating Cheques, choose Document to ensure the correct print destination for the Cheques.</span></span>
32. <span data-ttu-id="9ea83-160">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-160">Click OK.</span></span>
33. <span data-ttu-id="9ea83-161">[OK] をクリックして支払を生成します。</span><span class="sxs-lookup"><span data-stu-id="9ea83-161">Click OK to generate the payments.</span></span>
34. <span data-ttu-id="9ea83-162">すべての支払が承認され、生成された場合は、[転記] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ea83-162">Click Post if all the payments are approved and generated.</span></span> 

