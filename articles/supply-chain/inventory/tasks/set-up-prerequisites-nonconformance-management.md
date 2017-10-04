---
title: "管理の前提条件の設定"
description: "この手順を使用して不適合管理プロセスを有効化します。"
author: perlynne
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 842a9441158defca74d1b203a1b2509773ba8919
ms.contentlocale: ja-jp
ms.lasthandoff: 09/12/2017

---
# <a name="set-up-prerequisites-for-management"></a><span data-ttu-id="d17b5-103">管理の前提条件の設定</span><span class="sxs-lookup"><span data-stu-id="d17b5-103">Set up prerequisites for management</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d17b5-104">この手順を使用して不適合管理プロセスを有効化します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-104">Use this procedure to enable nonconformance management processes.</span></span> <span data-ttu-id="d17b5-105">不適合とは、品質上の問題がある手順または品目を表し、その説明には問題の原因およびタイプが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-105">A nonconformance describes a procedure or item that has a quality problem, where the descriptive information includes the source and type of problem.</span></span> <span data-ttu-id="d17b5-106">この手順では、デモ データの会社 USMF を使用します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-106">This procedure uses the USMF demo data company.</span></span> <span data-ttu-id="d17b5-107">通常この手順は品質マネージャーが実施します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-107">This procedure is typically performed by a quality manager.</span></span>


## <a name="enable-quality-management-processes-within-the-company"></a><span data-ttu-id="d17b5-108">社内品質管理プロセスの有効化</span><span class="sxs-lookup"><span data-stu-id="d17b5-108">Enable quality management processes within the company</span></span>
1. <span data-ttu-id="d17b5-109">[在庫管理] > [設定] > [在庫および倉庫管理パラメーター] を表示します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="d17b5-110">品質管理タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="d17b5-111">[品質管理を使用する] フィールドで [はい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-111">Select Yes in the Use quality management field.</span></span>
    * <span data-ttu-id="d17b5-112">このパラメータを選択して会社の品質管理プロセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-112">Select this parameter to enable quality management processes for the company.</span></span>  
4. <span data-ttu-id="d17b5-113">[時間レート] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-113">In the Hourly rate field, enter a number.</span></span>
    * <span data-ttu-id="d17b5-114">[時間レート] フィールドを使用して国内通貨で時給レートを入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-114">Use the Hourly rate field to enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="d17b5-115">時給レートは、不適合に関連する工程の原価計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-115">The hourly rate is used for calculating costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="d17b5-116">時間あたりのレートと算出原価は、不適合の参照情報を提供するものであり、他の機能に作用することはありません。</span><span class="sxs-lookup"><span data-stu-id="d17b5-116">The hourly rate and calculated costs provide reference information for a nonconformance, and they do not interact with other functionality.</span></span>  
5. <span data-ttu-id="d17b5-117">[レポートの設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-117">Click Report setup.</span></span>
    * <span data-ttu-id="d17b5-118">このページを使用して、異なる種類の品質管理レポートで使用される品質レポートのメモのタイプを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-118">This page allows you define the quality report note types that will be used on different kinds of quality management reports.</span></span>  
6. <span data-ttu-id="d17b5-119">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-119">Close the page.</span></span>
7. <span data-ttu-id="d17b5-120">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-120">Close the page.</span></span>

## <a name="enable-user-for-nonconformance-processing"></a><span data-ttu-id="d17b5-121">不適合処理に対しユーザーを有効化</span><span class="sxs-lookup"><span data-stu-id="d17b5-121">Enable user for nonconformance processing</span></span>
1. <span data-ttu-id="d17b5-122">[システム管理] > [ユーザー] > [ユーザー] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-122">Go to System administration > Users > Users.</span></span>
    * <span data-ttu-id="d17b5-123">不適合の承認を処理する場合、不適合を承認または否認するユーザーには、[ユーザー] ページで「名前」の値が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17b5-123">To process the approval of a nonconformance the user who  approves or rejects nonconformances must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="d17b5-124">ドキュメントのメモを使用するには、ユーザー オプションで [ドキュメントの処理] も有効化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17b5-124">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
2. <span data-ttu-id="d17b5-125">クイック フィルターを使用して、レコードを見つけます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d17b5-126">たとえば、[名前] フィールドで「Ricardo」という値を使用してフィルターを実行します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-126">For example, filter on the Name field with a value of 'Ricardo'.</span></span>
    * <span data-ttu-id="d17b5-127">フィルターを使用して不適合のレコードを承認または否認するユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-127">Use the filter to find the user who will be approving or rejecting the nonconformance records.</span></span>  
3. <span data-ttu-id="d17b5-128">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-128">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d17b5-129">不適合の承認を処理する場合、不適合を承認または否認するユーザーには、[ユーザー] ページで「名前」の値が割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d17b5-129">To process the approval of a nonconformance, make sure the user who approves or rejects nonconformances has a “Name” value assigned on the Users page.</span></span>  
4. <span data-ttu-id="d17b5-130">[ユーザー オプション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-130">Click User options.</span></span>
5. <span data-ttu-id="d17b5-131">[基本設定] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-131">Click the Preferences tab.</span></span>
6. <span data-ttu-id="d17b5-132">[ドキュメントの処理の有効化] フィールドで [はい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-132">Select Yes in the Enable document handling field.</span></span>
    * <span data-ttu-id="d17b5-133">ドキュメントのメモを使用するには、ユーザー オプションで [ドキュメントの処理] も有効化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17b5-133">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
7. <span data-ttu-id="d17b5-134">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-134">Close the page.</span></span>
8. <span data-ttu-id="d17b5-135">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-135">Close the page.</span></span>
9. <span data-ttu-id="d17b5-136">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-136">Close the page.</span></span>

## <a name="define-diagnostic-types-for-nonconformance-processing"></a><span data-ttu-id="d17b5-137">不適合処理の診断タイプの定義</span><span class="sxs-lookup"><span data-stu-id="d17b5-137">Define diagnostic types for nonconformance processing</span></span>
1. <span data-ttu-id="d17b5-138">[在庫管理] > [設定] > [品質管理] > [診断タイプ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-138">Go to Inventory management > Setup > Quality management > Diagnostic types.</span></span>
    * <span data-ttu-id="d17b5-139">診断アクションの分類を定義するためには、診断タイプ ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-139">Use the Diagnostic types page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="d17b5-140">訂正は、承認された不適合に対して行う必要のある診断アクションのタイプ、担当者、要求された完了日、予定の完了日などを識別します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-140">A correction identifies what type of diagnostic action should be taken on an approved nonconformance, who should perform it, and the requested and planned completion date.</span></span>  
2. <span data-ttu-id="d17b5-141">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-141">Click New.</span></span>
3. <span data-ttu-id="d17b5-142">[診断] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-142">In the Diagnostic field, type a value.</span></span>
4. <span data-ttu-id="d17b5-143">[説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-143">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d17b5-144">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-144">Close the page.</span></span>

## <a name="define-quality-charges-for-nonconformance-processing"></a><span data-ttu-id="d17b5-145">不適合処理の品質諸費用の定義</span><span class="sxs-lookup"><span data-stu-id="d17b5-145">Define quality charges for nonconformance processing</span></span>
1. <span data-ttu-id="d17b5-146">[在庫管理] > [設定] > [品質管理] > [品質諸費用] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-146">Go to Inventory management > Setup > Quality management > Quality charges.</span></span>
    * <span data-ttu-id="d17b5-147">[品質諸費用] ページを使用して、不適合に関連する行程で使用される請求の分類を定義します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-147">Use the Quality charges page to define a classification of charges that will used in operations related to nonconformances.</span></span>  
2. <span data-ttu-id="d17b5-148">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-148">Click New.</span></span>
3. <span data-ttu-id="d17b5-149">[諸費用コード] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-149">In the Charges code field, type a value.</span></span>
4. <span data-ttu-id="d17b5-150">[説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-150">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d17b5-151">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-151">Close the page.</span></span>

## <a name="define-the-operations-for-nonconformance-processing"></a><span data-ttu-id="d17b5-152">不適合処理の行程の定義</span><span class="sxs-lookup"><span data-stu-id="d17b5-152">Define the operations for nonconformance processing</span></span>
1. <span data-ttu-id="d17b5-153">[在庫管理] > [設定] > [品質管理] > [工程] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-153">Go to Inventory management > Setup > Quality management > Operations.</span></span>
    * <span data-ttu-id="d17b5-154">[行程] ページを使用して、承認済の不適合に対して実行することができる作業の分類を定義します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-154">Use the Operations page to define a classification of the work that may be performed for an approved nonconformance.</span></span> <span data-ttu-id="d17b5-155">行程をを不適合に関連付ける際、その操作を実行するために必要な関連する材料、労働時間、雑費などの情報を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-155">When you relate an operation to a nonconformance, you can define information about the associated material, labor hours, and miscellaneous charges that are required to perform the operation.</span></span> <span data-ttu-id="d17b5-156">この情報は、この工程を実行するための見積原価を計算する基準を提供します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-156">This information provides the basis for calculating an estimated cost for performing the operation.</span></span>  
2. <span data-ttu-id="d17b5-157">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-157">Click New.</span></span>
3. <span data-ttu-id="d17b5-158">[行程] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-158">In the Operation field, type a value.</span></span>
4. <span data-ttu-id="d17b5-159">[説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-159">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d17b5-160">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-160">Close the page.</span></span>

## <a name="define-problem-types-for-nonconformance-processing"></a><span data-ttu-id="d17b5-161">不適合処理の問題タイプの定義</span><span class="sxs-lookup"><span data-stu-id="d17b5-161">Define problem types for nonconformance processing</span></span>
1. <span data-ttu-id="d17b5-162">[在庫管理] > [設定] > [品質管理] > [問題タイプ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-162">Go to Inventory management > Setup > Quality management > Problem types.</span></span>
    * <span data-ttu-id="d17b5-163">[問題タイプ] ページを使用して、さまざまな不適合タイプで発生する品質上の問題の分類を定義します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-163">Use the Problem types page to define a classification of quality problems that are encountered in the various nonconformance types.</span></span> <span data-ttu-id="d17b5-164">不適合タイプには、[内部]、[顧客]、[仕入先]、[サービス要求]、[生産]、[連産品の生産] があります。</span><span class="sxs-lookup"><span data-stu-id="d17b5-164">The nonconformance types include Internal, Customer, Vendor, Service request, Production, and Co-product production.</span></span> <span data-ttu-id="d17b5-165">1 つの問題タイプを複数の不適合タイプに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-165">A single problem type can be associated with multiple nonconformance types.</span></span>  
2. <span data-ttu-id="d17b5-166">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-166">Click New.</span></span>
3. <span data-ttu-id="d17b5-167">[問題タイプ] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-167">In the Problem type field, type a value.</span></span>
4. <span data-ttu-id="d17b5-168">[説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-168">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d17b5-169">[不適合タイプ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-169">Click Non conformance types.</span></span>
    * <span data-ttu-id="d17b5-170">[不適合タイプ] ページを使用して、1 つ以上の不適合タイプでの問題タイプの使用を承認します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-170">Use the Non conformance types page to authorize the use of a problem type for one or more of the nonconformance types.</span></span> <span data-ttu-id="d17b5-171">たとえば、欠陥コードに関連した問題タイプは、すべての不適合タイプに適用できます。一方、顧客の苦情に関する問題タイプは、顧客およびサービス要求の不適合タイプにしか適用できません。</span><span class="sxs-lookup"><span data-stu-id="d17b5-171">For example, a problem type regarding a defect code could apply to all nonconformance types, whereas a problem type about customer complaints may only apply to the customer and service request nonconformance types.</span></span>  
6. <span data-ttu-id="d17b5-172">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-172">Click New.</span></span>
7. <span data-ttu-id="d17b5-173">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-173">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="d17b5-174">[不適合タイプ] フィールドで、オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-174">In the Non conformance type field, select an option.</span></span>
9. <span data-ttu-id="d17b5-175">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-175">Close the page.</span></span>
10. <span data-ttu-id="d17b5-176">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-176">Close the page.</span></span>

## <a name="define-quarantine-zones-for-nonconformance-processing"></a><span data-ttu-id="d17b5-177">不適合処理の検査ゾーンの定義</span><span class="sxs-lookup"><span data-stu-id="d17b5-177">Define quarantine zones for nonconformance processing</span></span>
1. <span data-ttu-id="d17b5-178">[在庫管理] > [設定] > [品質管理] > [検査ゾーン] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-178">Go to Inventory management > Setup > Quality management > Quarantine zones.</span></span>
2. <span data-ttu-id="d17b5-179">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17b5-179">Click New.</span></span>
3. <span data-ttu-id="d17b5-180">[検査ゾーン] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-180">In the Quarantine zone field, type a value.</span></span>
4. <span data-ttu-id="d17b5-181">[説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17b5-181">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d17b5-182">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17b5-182">Close the page.</span></span>
