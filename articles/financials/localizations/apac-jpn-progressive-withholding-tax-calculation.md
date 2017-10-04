---
title: "累進的源泉徴収税"
description: "このトピックでは、日本の累進的源泉徴収税に関する情報を提供します。 日本の法的要件では、請求金額に比例する期間に基づいて税率が変化します。 支払金額に基づいて、税金の比率も変わります。"
author: RichardLuan
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 265164
ms.assetid: 5ee3e381-31c4-48ac-9488-0eb1bc524cf5
ms.search.region: Japan
ms.author: riluan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6e1826fb325039192b4dafa1c9fdda54d42d78ca
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="progressive-withholding-tax"></a><span data-ttu-id="8eb70-105">累進的源泉徴収税</span><span class="sxs-lookup"><span data-stu-id="8eb70-105">Progressive withholding tax</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8eb70-106">このトピックでは、日本の累進的源泉徴収税に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8eb70-106">This topic provides information about progressive withholding tax in Japan.</span></span> <span data-ttu-id="8eb70-107">日本の法的要件では、請求金額に比例する期間に基づいて税率が変化します。</span><span class="sxs-lookup"><span data-stu-id="8eb70-107">Per the legal requirement in Japan, the tax percentage changes, depending on the interval in proportion to the invoice amount.</span></span> <span data-ttu-id="8eb70-108">支払金額に基づいて、税金の比率も変わります。</span><span class="sxs-lookup"><span data-stu-id="8eb70-108">The tax ratio also changes, based on the payment amount.</span></span>

<a name="tax-calculation"></a><span data-ttu-id="8eb70-109">税額の計算</span><span class="sxs-lookup"><span data-stu-id="8eb70-109">Tax calculation</span></span>
---------------

-   <span data-ttu-id="8eb70-110">[**正味金額の割合**] – [**正味金額の割合**] 方式は [**発生元**] フィールドの既定値です。</span><span class="sxs-lookup"><span data-stu-id="8eb70-110">**Percentage of net amount** – The **Percentage of net amount** method is the default value in the **Origin** field.</span></span> <span data-ttu-id="8eb70-111">源泉徴収税は、購入金額の割合として計算され、その他の売上税はすべて除外されます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-111">The withholding tax is calculated as a percentage of the purchase amount, excluding any other sales taxes.</span></span>
-   <span data-ttu-id="8eb70-112">[**総額の割合**] – 源泉徴収税は、総購入金額の割合として計算され、その他の売上税がすべて含まれます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-112">**Percentage of gross amount** – The withholding tax is calculated as a percentage of the gross purchase amount, including any other sales taxes.</span></span>

<span data-ttu-id="8eb70-113">源泉徴収税コードは、合計額と範囲金額のいずれかで計算されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-113">You can set up a withholding tax code so that it's calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="8eb70-114">[**源泉徴収税コード**] ページで、[**計算** クイック タブの [**計算方法**] フィールドを使用して、源泉徴収税コードの計算方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="8eb70-114">Use the **Calculation method** field on the **Calculation** FastTab of the **Withholding tax codes** page to select how a withholding tax code is calculated.</span></span>

-   <span data-ttu-id="8eb70-115">[**合計額**] – 課税対象額全体に税率が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-115">**Whole amount** – The tax rate is applied to the whole taxable amount.</span></span>
-   <span data-ttu-id="8eb70-116">[**間隔**] – 課税対象額が複数に分かれ、それぞれ特定の源泉徴収税率の範囲に分かれます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-116">**Interval** – The taxable amount is divided into parts, each of which falls in a range that has a specific withholding tax rate.</span></span> <span data-ttu-id="8eb70-117">所定の範囲に分類された部分的金額は、その範囲の税率で課税されます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-117">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="8eb70-118">各金額間隔に対して計算された税額の合計が源泉徴収税となります。</span><span class="sxs-lookup"><span data-stu-id="8eb70-118">The withholding tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

<span data-ttu-id="8eb70-119">**注記:** 異なる計算方法の源泉徴収税コードは 1 つの源泉徴収税グループに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="8eb70-119">**Note:** Withholding tax codes of different calculation methods can't be attached in a single withholding tax group.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8eb70-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="8eb70-120">Prerequisites</span></span>
| <span data-ttu-id="8eb70-121">タスク</span><span class="sxs-lookup"><span data-stu-id="8eb70-121">Task</span></span>                                                                                  | 
|---------------------------------------------------------------------------------------|
| <span data-ttu-id="8eb70-122">源泉徴収税コードと源泉徴収税グループの設定</span><span class="sxs-lookup"><span data-stu-id="8eb70-122">Set up withholding tax codes and withholding tax groups.</span></span>                              |  
| <span data-ttu-id="8eb70-123">新しい支払仕訳帳を作成し、未処理トランザクションを決済して、支払仕訳帳を転記します。</span><span class="sxs-lookup"><span data-stu-id="8eb70-123">Create a new payment journal, settle open transactions, and post the payment journal.</span></span> |   

1.  <span data-ttu-id="8eb70-124">[**源泉徴収税コード**] ページで、次の情報を持つ源泉徴収税コードを作成します。</span><span class="sxs-lookup"><span data-stu-id="8eb70-124">On the **Withholding tax codes** page, create withholding tax codes that have the following information:</span></span>
    -   <span data-ttu-id="8eb70-125">[**計算**] クイック タブの計算の基準と計算方法</span><span class="sxs-lookup"><span data-stu-id="8eb70-125">Origin and calculation method on the **Calculation** FastTab</span></span>
    -   <span data-ttu-id="8eb70-126">[**値**] ページの制限 (課税対象額の範囲間隔) と値</span><span class="sxs-lookup"><span data-stu-id="8eb70-126">Limits (taxable amount interval) and values on the **Values** page</span></span>

2.  <span data-ttu-id="8eb70-127">[**源泉徴収税グループ**] ページで、源泉徴収税グループを作成し、[**設定**] クイック タブの関連する源泉徴収税コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8eb70-127">On the **Withholding tax groups** page, create withholding tax groups, and add the relevant withholding tax codes on the **Setup** FastTab.</span></span> <span data-ttu-id="8eb70-128">[買掛金管理] の [**支払仕訳帳**] ページまたは [総勘定元帳] の [**一般仕訳帳**] ページで源泉徴収税を計算して転記します。</span><span class="sxs-lookup"><span data-stu-id="8eb70-128">You can calculate and post withholding tax on either the **Payment journal** page in Accounts payable or the **General journal** page in General ledger.</span></span> <span data-ttu-id="8eb70-129">仕入先の既定の源泉徴収税グループは、[**源泉徴収税グループ**] フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-129">The default withholding tax group for the vendor is shown in the **Withholding tax group** field.</span></span>
3.  <span data-ttu-id="8eb70-130">[**支払仕訳帳**] ページで、仕訳帳を選択するか [**新規**] をクリックして仕訳帳を作成し、[**明細行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8eb70-130">On the **Payment journal** page, select a journal or click **New** to create a journal, and then click **Lines**.</span></span>
4.  <span data-ttu-id="8eb70-131">支払期日を入力し、源泉徴収税を計算するために設定されている仕入先を選択します。</span><span class="sxs-lookup"><span data-stu-id="8eb70-131">Enter a payment date, and select the vendor account that is set up to calculate withholding tax.</span></span> <span data-ttu-id="8eb70-132">既定では、[**源泉徴収税グループ**] フィールドに仕入先の源泉徴収税グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-132">By default, the **Withholding tax group** field shows the withholding tax group for the vendor.</span></span> <span data-ttu-id="8eb70-133">別のグループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-133">You can select a different group.</span></span> <span data-ttu-id="8eb70-134">明細行に対して源泉徴収税を計算する必要がない場合は、フィールドの値を削除できます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-134">If no withholding tax should be calculated for the line, you can delete the field value.</span></span>
5.  <span data-ttu-id="8eb70-135">[**機能**] をクリックし、[**決済**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8eb70-135">Click **Functions**, and then click **Settlement**.</span></span> <span data-ttu-id="8eb70-136">支払いを行う未処理の請求書の [**マーク**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8eb70-136">Select the **Mark** option for the open invoices to pay.</span></span>
6.  <span data-ttu-id="8eb70-137">計算された源泉徴収税に関する情報ログの情報を確認してから、情報ログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-137">Verify the Infolog information about the calculated withholding tax, and then close the Infolog.</span></span>
7.  <span data-ttu-id="8eb70-138">オプション: 選択した各明細行の [**源泉徴収税**] タブをクリックして、計算された源泉徴収税を変更または削除します。</span><span class="sxs-lookup"><span data-stu-id="8eb70-138">Optional: Click the **Withholding tax** tab for each selected line to change or delete the calculated withholding tax.</span></span> <span data-ttu-id="8eb70-139">明細行を作成して情報を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-139">You can also create lines and enter the information.</span></span>
8.  <span data-ttu-id="8eb70-140">**未処理トランザクションの決済**ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-140">Close the **Settle open transactions** page.</span></span> <span data-ttu-id="8eb70-141">仕訳帳明細行の支払金額は源泉徴収税額だけ少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="8eb70-141">The payment amount on the journal line is reduced by the withholding tax amount.</span></span>
9.  <span data-ttu-id="8eb70-142">支払仕訳帳を検証および転記します。</span><span class="sxs-lookup"><span data-stu-id="8eb70-142">Validate and post the payment journal.</span></span>

## <a name="example-of-gross-amount"></a><span data-ttu-id="8eb70-143">総額の例</span><span class="sxs-lookup"><span data-stu-id="8eb70-143">Example of Gross amount</span></span>
<span data-ttu-id="8eb70-144">この例では、源泉徴収税は [**総額**] の [**割合の基準**] の値と [**間隔**] の [**計算方法**] の値を使用して計算されます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-144">In this example, withholding tax is calculated by using an **Origin of percentage** value of **Gross amount** and a **Calculation method** value of **Interval**.</span></span> <span data-ttu-id="8eb70-145">税率は次のように設定されます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-145">Tax rates are set up as follows.</span></span>

| <span data-ttu-id="8eb70-146">最小値と最大値 (課税対象額の範囲間隔)</span><span class="sxs-lookup"><span data-stu-id="8eb70-146">Minimum and maximum limit (Taxable amount interval)</span></span> | <span data-ttu-id="8eb70-147">値 (税率)</span><span class="sxs-lookup"><span data-stu-id="8eb70-147">Value (Tax rate)</span></span> |
|-----------------------------------------------------|------------------|
| <span data-ttu-id="8eb70-148">0.00 ～ 1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-148">0.00 to 1,000.00</span></span>                                    | <span data-ttu-id="8eb70-149">10%</span><span class="sxs-lookup"><span data-stu-id="8eb70-149">10 percent</span></span>       |
| <span data-ttu-id="8eb70-150">1,001.00 ～ 2,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-150">1,001.00 to 2,000.00</span></span>                                | <span data-ttu-id="8eb70-151">15%</span><span class="sxs-lookup"><span data-stu-id="8eb70-151">15 percent</span></span>       |
| <span data-ttu-id="8eb70-152">2,001.00 ～ 0.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-152">2,001.00 to 0.00</span></span>                                    | <span data-ttu-id="8eb70-153">20%</span><span class="sxs-lookup"><span data-stu-id="8eb70-153">20 percent</span></span>       |

<span data-ttu-id="8eb70-154">支払額: 11,000.00、10% の売上税 (1,000) を含む**全額支払 – 11,000.00** の計算:</span><span class="sxs-lookup"><span data-stu-id="8eb70-154">Payment amount: 11,000.00, which includes 10-percent sales tax (that is, 1,000) **Full payment – 11,000.00** Calculation:</span></span>

| <span data-ttu-id="8eb70-155">課税対象額の範囲間隔</span><span class="sxs-lookup"><span data-stu-id="8eb70-155">Taxable amount interval</span></span> | <span data-ttu-id="8eb70-156">税率</span><span class="sxs-lookup"><span data-stu-id="8eb70-156">Tax rate</span></span>   | <span data-ttu-id="8eb70-157">税間隔に基づいた分割支払額</span><span class="sxs-lookup"><span data-stu-id="8eb70-157">Payment amount split, based on the tax interval</span></span> | <span data-ttu-id="8eb70-158">源泉徴収税</span><span class="sxs-lookup"><span data-stu-id="8eb70-158">Withholding tax</span></span> |
|-------------------------|------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="8eb70-159">0 ～ 1,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-159">0–1,000</span></span>                 | <span data-ttu-id="8eb70-160">10%</span><span class="sxs-lookup"><span data-stu-id="8eb70-160">10 percent</span></span> | <span data-ttu-id="8eb70-161">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-161">1,000.00</span></span>                                        | <span data-ttu-id="8eb70-162">100.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-162">100.00</span></span>          |
| <span data-ttu-id="8eb70-163">1,001 ～ 2,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-163">1,001–2,000</span></span>             | <span data-ttu-id="8eb70-164">15%</span><span class="sxs-lookup"><span data-stu-id="8eb70-164">15 percent</span></span> | <span data-ttu-id="8eb70-165">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-165">1,000.00</span></span>                                        | <span data-ttu-id="8eb70-166">150.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-166">150.00</span></span>          |
| <span data-ttu-id="8eb70-167">2,001 ～ 0</span><span class="sxs-lookup"><span data-stu-id="8eb70-167">2,001–0</span></span>                 | <span data-ttu-id="8eb70-168">20%</span><span class="sxs-lookup"><span data-stu-id="8eb70-168">20 percent</span></span> | <span data-ttu-id="8eb70-169">9,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-169">9,000.00</span></span>                                        | <span data-ttu-id="8eb70-170">1,800.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-170">1,800.00</span></span>        |
|                         |            | <span data-ttu-id="8eb70-171">**合計 WHT 金額**</span><span class="sxs-lookup"><span data-stu-id="8eb70-171">**Total WHT amount**</span></span>                            | <span data-ttu-id="8eb70-172">**2,050.00**</span><span class="sxs-lookup"><span data-stu-id="8eb70-172">**2,050.00**</span></span>    |

<span data-ttu-id="8eb70-173">**一部支払 – 6,000.00** 計算:</span><span class="sxs-lookup"><span data-stu-id="8eb70-173">**Partial payment – 6,000.00** Calculation:</span></span>

| <span data-ttu-id="8eb70-174">課税対象額の範囲間隔</span><span class="sxs-lookup"><span data-stu-id="8eb70-174">Taxable amount interval</span></span> | <span data-ttu-id="8eb70-175">税率</span><span class="sxs-lookup"><span data-stu-id="8eb70-175">Tax rate</span></span>   | <span data-ttu-id="8eb70-176">税間隔に基づいた分割支払額</span><span class="sxs-lookup"><span data-stu-id="8eb70-176">Payment amount split, based on the tax interval</span></span> | <span data-ttu-id="8eb70-177">源泉徴収税</span><span class="sxs-lookup"><span data-stu-id="8eb70-177">Withholding tax</span></span> |
|-------------------------|------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="8eb70-178">0 ～ 1,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-178">0–1,000</span></span>                 | <span data-ttu-id="8eb70-179">10%</span><span class="sxs-lookup"><span data-stu-id="8eb70-179">10 percent</span></span> | <span data-ttu-id="8eb70-180">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-180">1,000.00</span></span>                                        | <span data-ttu-id="8eb70-181">100.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-181">100.00</span></span>          |
| <span data-ttu-id="8eb70-182">1,001 ～ 2,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-182">1,001–2,000</span></span>             | <span data-ttu-id="8eb70-183">15%</span><span class="sxs-lookup"><span data-stu-id="8eb70-183">15 percent</span></span> | <span data-ttu-id="8eb70-184">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-184">1,000.00</span></span>                                        | <span data-ttu-id="8eb70-185">150.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-185">150.00</span></span>          |
| <span data-ttu-id="8eb70-186">2,001 ～ 0</span><span class="sxs-lookup"><span data-stu-id="8eb70-186">2,001–0</span></span>                 | <span data-ttu-id="8eb70-187">20%</span><span class="sxs-lookup"><span data-stu-id="8eb70-187">20 percent</span></span> | <span data-ttu-id="8eb70-188">4,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-188">4,000.00</span></span>                                        | <span data-ttu-id="8eb70-189">800.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-189">800.00</span></span>          |
|                         |            | <span data-ttu-id="8eb70-190">**合計 WHT 金額**</span><span class="sxs-lookup"><span data-stu-id="8eb70-190">**Total WHT amount**</span></span>                            | <span data-ttu-id="8eb70-191">**1,050.00**</span><span class="sxs-lookup"><span data-stu-id="8eb70-191">**1,050.00**</span></span>    |

<span data-ttu-id="8eb70-192">**残高支払 – 5,000.00** 計算:</span><span class="sxs-lookup"><span data-stu-id="8eb70-192">**Balance payment – 5,000.00** Calculation:</span></span>

| <span data-ttu-id="8eb70-193">課税対象額の範囲間隔</span><span class="sxs-lookup"><span data-stu-id="8eb70-193">Taxable amount interval</span></span> | <span data-ttu-id="8eb70-194">税率</span><span class="sxs-lookup"><span data-stu-id="8eb70-194">Tax rate</span></span>   | <span data-ttu-id="8eb70-195">税間隔に基づいた分割支払額</span><span class="sxs-lookup"><span data-stu-id="8eb70-195">Payment amount split, based on the tax interval</span></span> | <span data-ttu-id="8eb70-196">源泉徴収税</span><span class="sxs-lookup"><span data-stu-id="8eb70-196">Withholding tax</span></span> |
|-------------------------|------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="8eb70-197">0 ～ 1,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-197">0–1,000</span></span>                 | <span data-ttu-id="8eb70-198">10%</span><span class="sxs-lookup"><span data-stu-id="8eb70-198">10 percent</span></span> | <span data-ttu-id="8eb70-199">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-199">1,000.00</span></span>                                        | <span data-ttu-id="8eb70-200">100.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-200">100.00</span></span>          |
| <span data-ttu-id="8eb70-201">1,001 ～ 2,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-201">1,001–2,000</span></span>             | <span data-ttu-id="8eb70-202">15%</span><span class="sxs-lookup"><span data-stu-id="8eb70-202">15 percent</span></span> | <span data-ttu-id="8eb70-203">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-203">1,000.00</span></span>                                        | <span data-ttu-id="8eb70-204">150.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-204">150.00</span></span>          |
| <span data-ttu-id="8eb70-205">2,001 ～ 0</span><span class="sxs-lookup"><span data-stu-id="8eb70-205">2,001–0</span></span>                 | <span data-ttu-id="8eb70-206">20%</span><span class="sxs-lookup"><span data-stu-id="8eb70-206">20 percent</span></span> | <span data-ttu-id="8eb70-207">3,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-207">3,000.00</span></span>                                        | <span data-ttu-id="8eb70-208">600.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-208">600.00</span></span>          |
|                         |            | <span data-ttu-id="8eb70-209">**合計 WHT 金額**</span><span class="sxs-lookup"><span data-stu-id="8eb70-209">**Total WHT amount**</span></span>                            | <span data-ttu-id="8eb70-210">**850.00**</span><span class="sxs-lookup"><span data-stu-id="8eb70-210">**850.00**</span></span>      |

## <a name="example-of-net-amount"></a><span data-ttu-id="8eb70-211">正味金額の例</span><span class="sxs-lookup"><span data-stu-id="8eb70-211">Example of Net amount</span></span>
<span data-ttu-id="8eb70-212">この例では、源泉徴収税は [**正味金額**] の [**割合の基準**] の値と [**間隔**] の [**計算方法**] の値を使用して計算されます。</span><span class="sxs-lookup"><span data-stu-id="8eb70-212">In this example, withholding tax is calculated by using an **Origin of percentage** value of **Net amount** and a **Calculation method** value of **Interval**.</span></span> <span data-ttu-id="8eb70-213">支払額: 11,000.00、10% の売上税 (1,000) を含む**全額支払 – 11,000.00** 源泉徴収税の計算基準 (税別) = 10,000.00 計算:</span><span class="sxs-lookup"><span data-stu-id="8eb70-213">Payment amount: 11,000.00, which includes 10-percent sales tax (that is, 1,000) **Full payment – 11,000.00** Base for withholding tax calculation, excluding tax = 10,000.00 Calculation:</span></span>

| <span data-ttu-id="8eb70-214">課税対象額の範囲間隔</span><span class="sxs-lookup"><span data-stu-id="8eb70-214">Taxable amount interval</span></span> | <span data-ttu-id="8eb70-215">税率</span><span class="sxs-lookup"><span data-stu-id="8eb70-215">Tax rate</span></span>   | <span data-ttu-id="8eb70-216">税間隔に基づいた分割支払額</span><span class="sxs-lookup"><span data-stu-id="8eb70-216">Payment amount split based on the tax interval</span></span> | <span data-ttu-id="8eb70-217">源泉徴収税</span><span class="sxs-lookup"><span data-stu-id="8eb70-217">Withholding tax</span></span> |
|-------------------------|------------|------------------------------------------------|-----------------|
| <span data-ttu-id="8eb70-218">0 ～ 1,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-218">0–1,000</span></span>                 | <span data-ttu-id="8eb70-219">10%</span><span class="sxs-lookup"><span data-stu-id="8eb70-219">10 percent</span></span> | <span data-ttu-id="8eb70-220">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-220">1,000.00</span></span>                                       | <span data-ttu-id="8eb70-221">100.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-221">100.00</span></span>          |
| <span data-ttu-id="8eb70-222">1,001 ～ 2,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-222">1,001–2,000</span></span>             | <span data-ttu-id="8eb70-223">15%</span><span class="sxs-lookup"><span data-stu-id="8eb70-223">15 percent</span></span> | <span data-ttu-id="8eb70-224">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-224">1,000.00</span></span>                                       | <span data-ttu-id="8eb70-225">150.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-225">150.00</span></span>          |
| <span data-ttu-id="8eb70-226">2,001 ～ 0</span><span class="sxs-lookup"><span data-stu-id="8eb70-226">2,001–0</span></span>                 | <span data-ttu-id="8eb70-227">20%</span><span class="sxs-lookup"><span data-stu-id="8eb70-227">20 percent</span></span> | <span data-ttu-id="8eb70-228">8,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-228">8,000.00</span></span>                                       | <span data-ttu-id="8eb70-229">1,600.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-229">1,600.00</span></span>        |
|                         |            | <span data-ttu-id="8eb70-230">**合計 WHT 金額**</span><span class="sxs-lookup"><span data-stu-id="8eb70-230">**Total WHT amount**</span></span>                           | <span data-ttu-id="8eb70-231">**1,850.00**</span><span class="sxs-lookup"><span data-stu-id="8eb70-231">**1,850.00**</span></span>    |

<span data-ttu-id="8eb70-232">**一部支払 – 6,000.00** 源泉徴収税の計算基準 (税別) = 5,455.00 計算:</span><span class="sxs-lookup"><span data-stu-id="8eb70-232">**Partial payment – 6,000.00** Base for withholding tax calculation, excluding tax = 5,455.00 Calculation:</span></span>

| <span data-ttu-id="8eb70-233">課税対象額の範囲間隔</span><span class="sxs-lookup"><span data-stu-id="8eb70-233">Taxable amount interval</span></span> | <span data-ttu-id="8eb70-234">税率</span><span class="sxs-lookup"><span data-stu-id="8eb70-234">Tax rate</span></span>   | <span data-ttu-id="8eb70-235">税間隔に基づいた分割支払額</span><span class="sxs-lookup"><span data-stu-id="8eb70-235">Payment amount split, based on the tax interval</span></span> | <span data-ttu-id="8eb70-236">源泉徴収税</span><span class="sxs-lookup"><span data-stu-id="8eb70-236">Withholding tax</span></span> |
|-------------------------|------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="8eb70-237">0 ～ 1,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-237">0–1,000</span></span>                 | <span data-ttu-id="8eb70-238">10%</span><span class="sxs-lookup"><span data-stu-id="8eb70-238">10 percent</span></span> | <span data-ttu-id="8eb70-239">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-239">1,000.00</span></span>                                        | <span data-ttu-id="8eb70-240">100.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-240">100.00</span></span>          |
| <span data-ttu-id="8eb70-241">1,001 ～ 2,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-241">1,001–2,000</span></span>             | <span data-ttu-id="8eb70-242">15%</span><span class="sxs-lookup"><span data-stu-id="8eb70-242">15 percent</span></span> | <span data-ttu-id="8eb70-243">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-243">1,000.00</span></span>                                        | <span data-ttu-id="8eb70-244">150.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-244">150.00</span></span>          |
| <span data-ttu-id="8eb70-245">2,001 ～ 0</span><span class="sxs-lookup"><span data-stu-id="8eb70-245">2,001–0</span></span>                 | <span data-ttu-id="8eb70-246">20%</span><span class="sxs-lookup"><span data-stu-id="8eb70-246">20 percent</span></span> | <span data-ttu-id="8eb70-247">3,455.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-247">3,455.00</span></span>                                        | <span data-ttu-id="8eb70-248">691.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-248">691.00</span></span>          |
|                         |            | <span data-ttu-id="8eb70-249">**合計 WHT 金額**</span><span class="sxs-lookup"><span data-stu-id="8eb70-249">**Total WHT amount**</span></span>                            | <span data-ttu-id="8eb70-250">**941.00**</span><span class="sxs-lookup"><span data-stu-id="8eb70-250">**941.00**</span></span>      |

<span data-ttu-id="8eb70-251">**残高支払 – 5,000.00** 源泉徴収税の計算基準 (税別) = 4,545.00 計算:</span><span class="sxs-lookup"><span data-stu-id="8eb70-251">**Balance payment – 5,000.00** Base for withholding tax calculation excluding tax = 4,545.00 Calculation:</span></span>

| <span data-ttu-id="8eb70-252">課税対象額の範囲間隔</span><span class="sxs-lookup"><span data-stu-id="8eb70-252">Taxable amount interval</span></span> | <span data-ttu-id="8eb70-253">税率</span><span class="sxs-lookup"><span data-stu-id="8eb70-253">Tax rate</span></span>   | <span data-ttu-id="8eb70-254">税間隔に基づいた分割支払額</span><span class="sxs-lookup"><span data-stu-id="8eb70-254">Payment amount split, based on the tax interval</span></span> | <span data-ttu-id="8eb70-255">源泉徴収税</span><span class="sxs-lookup"><span data-stu-id="8eb70-255">Withholding tax</span></span> |
|-------------------------|------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="8eb70-256">0 ～ 1,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-256">0–1,000</span></span>                 | <span data-ttu-id="8eb70-257">10%</span><span class="sxs-lookup"><span data-stu-id="8eb70-257">10 percent</span></span> | <span data-ttu-id="8eb70-258">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-258">1,000.00</span></span>                                        | <span data-ttu-id="8eb70-259">100.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-259">100.00</span></span>          |
| <span data-ttu-id="8eb70-260">1,001 ～ 2,000</span><span class="sxs-lookup"><span data-stu-id="8eb70-260">1,001–2,000</span></span>             | <span data-ttu-id="8eb70-261">15%</span><span class="sxs-lookup"><span data-stu-id="8eb70-261">15 percent</span></span> | <span data-ttu-id="8eb70-262">1,000.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-262">1,000.00</span></span>                                        | <span data-ttu-id="8eb70-263">150.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-263">150.00</span></span>          |
| <span data-ttu-id="8eb70-264">2,001 ～ 0</span><span class="sxs-lookup"><span data-stu-id="8eb70-264">2,001–0</span></span>                 | <span data-ttu-id="8eb70-265">20%</span><span class="sxs-lookup"><span data-stu-id="8eb70-265">20 percent</span></span> | <span data-ttu-id="8eb70-266">2,545.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-266">2,545.00</span></span>                                        | <span data-ttu-id="8eb70-267">509.00</span><span class="sxs-lookup"><span data-stu-id="8eb70-267">509.00</span></span>          |
|                         |            | <span data-ttu-id="8eb70-268">**合計 WHT 金額**</span><span class="sxs-lookup"><span data-stu-id="8eb70-268">**Total WHT amount**</span></span>                            | <span data-ttu-id="8eb70-269">**759.00**</span><span class="sxs-lookup"><span data-stu-id="8eb70-269">**759.00**</span></span>      |





