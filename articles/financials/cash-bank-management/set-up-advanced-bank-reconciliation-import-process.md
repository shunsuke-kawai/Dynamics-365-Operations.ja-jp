---
title: "詳細な口座調整のインポート プロセスの設定"
description: "詳細な口座調整機能では、電子口座取引明細書をインポートし、Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition での銀行トランザクションに合わせて自動的に調整することができます。 この資料では、口座取引明細書のインポート機能を設定する方法について説明します。"
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 785da18a851c4d040843f49ca9f1b9ae12d701d3
ms.contentlocale: ja-jp
ms.lasthandoff: 06/29/2017


---

# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a><span data-ttu-id="52edd-104">詳細な口座調整のインポート プロセスの設定</span><span class="sxs-lookup"><span data-stu-id="52edd-104">Set up the advanced bank reconciliation import process</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="52edd-105">詳細な口座調整機能では、電子口座取引明細書をインポートし、Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition での銀行トランザクションに合わせて自動的に調整することができます。</span><span class="sxs-lookup"><span data-stu-id="52edd-105">The Advanced bank reconciliation feature lets you import electronic bank statements and automatically reconcile them with bank transactions in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="52edd-106">この資料では、口座取引明細書のインポート機能を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="52edd-106">This article explains how to set up the import functionality for your bank statements.</span></span> 

<span data-ttu-id="52edd-107">口座取引明細書のインポートの設定は、電子口座取引明細書の形式によって異なります。</span><span class="sxs-lookup"><span data-stu-id="52edd-107">The setup for bank statement import varies, depending on the format of your electronic bank statement.</span></span> <span data-ttu-id="52edd-108">Finance and Operations は、ISO20022、MT940、および BAI2 の 3 つの口座取引明細書の形式を包括的にサポートしています。</span><span class="sxs-lookup"><span data-stu-id="52edd-108">Finance and Operations supports three bank statement formats out of the box: ISO20022, MT940, and BAI2.</span></span>

## <a name="sample-files"></a><span data-ttu-id="52edd-109">サンプル ファイル</span><span class="sxs-lookup"><span data-stu-id="52edd-109">Sample files</span></span>
<span data-ttu-id="52edd-110">すべての 3 つの形式には、電子口座取引明細書を元の形式から、Finance and Operations で使用できる形式に変換するファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="52edd-110">For all three formats, you must have files that translate the electronic bank statement from the original format to a format that Finance and Operations can use.</span></span> <span data-ttu-id="52edd-111">Microsoft Visual Studio のアプリケーション エクスプローラーの [**リソース**] ノードの下に必要なリソース ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="52edd-111">You can find the required resource files under the **Resources** node in Application Explorer in Microsoft Visual Studio.</span></span> <span data-ttu-id="52edd-112">ファイルを見つけたら、1 つのわかる場所にコピーして、設定プロセス中に容易にアップロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="52edd-112">After you find the files, copy them to a single known location, so that you can more easily upload them during the setup process.</span></span>

| <span data-ttu-id="52edd-113">リソース名</span><span class="sxs-lookup"><span data-stu-id="52edd-113">Resource name</span></span>                                           | <span data-ttu-id="52edd-114">ファイル名</span><span class="sxs-lookup"><span data-stu-id="52edd-114">File name</span></span>                            |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="52edd-115">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-115">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>              | <span data-ttu-id="52edd-116">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-116">BAI2CSV-to-BAI2XML.xslt</span></span>              |
| <span data-ttu-id="52edd-117">BankStmtImport\_BAI2XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-117">BankStmtImport\_BAI2XML\_to\_Reconciliation\_xslt</span></span>       | <span data-ttu-id="52edd-118">BAI2XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-118">BAI2XML-to-Reconciliation.xslt</span></span>       |
| <span data-ttu-id="52edd-119">BankStmtImport\_BankReconciliation\_to\_Composite\_xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-119">BankStmtImport\_BankReconciliation\_to\_Composite\_xslt</span></span> | <span data-ttu-id="52edd-120">BankReconciliation-to-Composite.xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-120">BankReconciliation-to-Composite.xslt</span></span> |
| <span data-ttu-id="52edd-121">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-121">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span>   | <span data-ttu-id="52edd-122">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-122">ISO20022XML-to-Reconciliation.xslt</span></span>   |
| <span data-ttu-id="52edd-123">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-123">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>            | <span data-ttu-id="52edd-124">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-124">MT940TXT-to-MT940XML.xslt</span></span>            |
| <span data-ttu-id="52edd-125">BankStmtImport\_MT940XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-125">BankStmtImport\_MT940XML\_to\_Reconciliation\_xslt</span></span>      | <span data-ttu-id="52edd-126">MT940XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="52edd-126">MT940XML-to-Reconciliation.xslt</span></span>      |
| <span data-ttu-id="52edd-127">BankStmtImport\_SampleBankCompositeEntity\_xml</span><span class="sxs-lookup"><span data-stu-id="52edd-127">BankStmtImport\_SampleBankCompositeEntity\_xml</span></span>          | <span data-ttu-id="52edd-128">SampleBankCompositeEntity.xml</span><span class="sxs-lookup"><span data-stu-id="52edd-128">SampleBankCompositeEntity.xml</span></span>        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="52edd-129">口座取引明細書の形式と技術的な配置の例</span><span class="sxs-lookup"><span data-stu-id="52edd-129">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="52edd-130">詳細な口座調整のインポート ファイルの技術的な配置の定義、および 3 つの関連する口座取引明細書のサンプル ファイルの例を以下に示します。https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="52edd-130">Below are examples of the advanced bank reconciliation import file technical layout definitions and three related bank statement example files: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  

| <span data-ttu-id="52edd-131">技術的なレイアウトの定義</span><span class="sxs-lookup"><span data-stu-id="52edd-131">Technical layout definition</span></span>                             | <span data-ttu-id="52edd-132">口座取引明細書のサンプル ファイル</span><span class="sxs-lookup"><span data-stu-id="52edd-132">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="52edd-133">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="52edd-133">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="52edd-134">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="52edd-134">MT940StatementExample</span></span>                |
| <span data-ttu-id="52edd-135">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="52edd-135">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="52edd-136">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="52edd-136">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="52edd-137">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="52edd-137">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="52edd-138">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="52edd-138">BAI2StatementExample</span></span>                 |

 

## <a name="set-up-the-import-of-iso20022-bank-statements"></a><span data-ttu-id="52edd-139">ISO20022 口座取引明細書のインポートの設定</span><span class="sxs-lookup"><span data-stu-id="52edd-139">Set up the import of ISO20022 bank statements</span></span>
<span data-ttu-id="52edd-140">最初に、データ エンティティ フレームワークを使用して「ISO20022 口座取引明細書」の口座取引明細書の形式処理グループを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52edd-140">First, you must define the bank statement format processing group for ISO20022 bank statements by using the data entity framework.</span></span>

1.  <span data-ttu-id="52edd-141">**ワークスペース** &gt; **データ管理**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52edd-141">Go to **Workspaces** &gt; **Data management**.</span></span>
2.  <span data-ttu-id="52edd-142">**インポート**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-142">Click **Import**.</span></span>
3.  <span data-ttu-id="52edd-143">「**ISO20022**」などの形式の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="52edd-143">Enter a name for the format, such as **ISO20022**.</span></span>
4.  <span data-ttu-id="52edd-144">[**ソース データ形式**] フィールドを [**XML-Element**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-144">Set the **Source data format** field to **XML-Element**.</span></span>
5.  <span data-ttu-id="52edd-145">[**エンティティ名**] フィールドを [**口座取引明細書**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-145">Set the **Entity name** field to **Bank statements**.</span></span>
6.  <span data-ttu-id="52edd-146">インポート ファイルをアップロードするには、[**アップロード**] をクリックし、参照して先ほど保存した「**SampleBankCompositeEntity.xml**」ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-146">To upload the import files, click **Upload**, and then browse to select the **SampleBankCompositeEntity.xml** file that you saved earlier.</span></span>
7.  <span data-ttu-id="52edd-147">口座取引明細書のエンティティがアップロードされ、マッピングが完了した後、エンティティの [**マップの表示**] アクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-147">After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.</span></span>
8.  <span data-ttu-id="52edd-148">口座取引明細書のエンティティは、4 つの別々のエンティティで構成される複合エンティティです。</span><span class="sxs-lookup"><span data-stu-id="52edd-148">The Bank statements entity is a composite entity that consists of four separate entities.</span></span> <span data-ttu-id="52edd-149">一覧で、[**BankStatementDocumentEntity**] を選択し、次に [**マップの表示**] アクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-149">In the list, select **BankStatementDocumentEntity**, and then click the **View map** action.</span></span>
9.  <span data-ttu-id="52edd-150">[**変換**] タブで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-150">On the **Transformations** tab, click **New**.</span></span>
10. <span data-ttu-id="52edd-151">シーケンス番号 1 で、[**ファイルのアップロード**] をクリックし, 先ほど保存した「**ISO20022XML-to-Reconciliation.xslt**」ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-151">For sequence number 1, click **Upload file**, and select the **ISO20022XML-to-Reconciliation.xslt** file that you saved earlier.</span></span> <span data-ttu-id="52edd-152">**注記:** Finance and Operations 変換ファイルは、標準形式で作成されます。</span><span class="sxs-lookup"><span data-stu-id="52edd-152">**Note:** Finance and Operations transformation files are built for the standard format.</span></span> <span data-ttu-id="52edd-153">銀行は多くの場合、この形式と異なるため、口座取引明細書の形式にマップする変換ファイルを更新する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="52edd-153">Because banks often diverge from this format, you may have to update the transformation file to map to your bank statement format.</span></span> <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. <span data-ttu-id="52edd-154">**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-154">Click **New**.</span></span>
12. <span data-ttu-id="52edd-155">シーケンス番号 2 で、[**ファイルのアップロード**] をクリックし, 先ほど保存した「**BankReconciliation-to-Composite.xslt**」ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-155">For sequence number 2, click **Upload file**, and select the **BankReconciliation-to-Composite.xslt** file that you saved earlier.</span></span>
13. <span data-ttu-id="52edd-156">[**変換の適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-156">Click **Apply transforms**.</span></span>

<span data-ttu-id="52edd-157">形式の処理グループを設定した後の次の手順は、「ISO20022 口座取引明細書」の口座取引明細書の形式ルールを定義することです。</span><span class="sxs-lookup"><span data-stu-id="52edd-157">After the format processing group is set up, the next step is to define the bank statement format rules for ISO20022 bank statements.</span></span>

1.  <span data-ttu-id="52edd-158">**現金および銀行管理** &gt; **設定** &gt; **詳細な口座調整の設定** &gt; **口座取引明細書の形式**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52edd-158">Go to **Cash and bank management** &gt; **Setup** &gt; **Advanced bank reconciliation setup** &gt; **Bank statement format**.</span></span>
2.  <span data-ttu-id="52edd-159">**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-159">Click **New**.</span></span>
3.  <span data-ttu-id="52edd-160">「**ISO20022**」のように明細書の形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-160">Specify a statement format, such as **ISO20022**.</span></span>
4.  <span data-ttu-id="52edd-161">形式の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="52edd-161">Enter a name for the format.</span></span>
5.  <span data-ttu-id="52edd-162">[**処理グループ**] フィールドを「**ISO20022**」などの先ほど定義したグループに設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-162">Set the **Processing group** field to the group that you defined earlier, such as **ISO20022**.</span></span>
6.  <span data-ttu-id="52edd-163">[**XML ファイル**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-163">Select the **XML file** check box.</span></span>

<span data-ttu-id="52edd-164">最後の手順は、詳細な口座調整を有効にし、銀行口座の明細書の形式を設定することです。</span><span class="sxs-lookup"><span data-stu-id="52edd-164">The last step is to enable Advanced bank reconciliation and set the statement format on the bank account.</span></span>

1.  <span data-ttu-id="52edd-165">**現金および銀行管理** &gt; **銀行口座**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52edd-165">Go to **Cash and bank management** &gt; **Bank accounts**.</span></span>
2.  <span data-ttu-id="52edd-166">銀行口座を選択し、ファイルを開いて詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="52edd-166">Select the bank account, and open it to view the details.</span></span>
3.  <span data-ttu-id="52edd-167">[**調整**] タブで、[**詳細な口座調整**] オプションを [**はい**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-167">On the **Reconciliation** tab, set the **Advanced bank reconciliation** option to **Yes**.</span></span>
4.  <span data-ttu-id="52edd-168">[**明細書形式**] フィールドを「**ISO20022**」などの先ほど作成した形式に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-168">Set the **Statement format** field to the format that you created earlier, such as **ISO20022**.</span></span>

## <a name="set-up-the-import-of-mt940-bank-statements"></a><span data-ttu-id="52edd-169">MT940 口座取引明細書のインポートの設定</span><span class="sxs-lookup"><span data-stu-id="52edd-169">Set up the import of MT940 bank statements</span></span>
<span data-ttu-id="52edd-170">最初に、データ エンティティ フレームワークを使用して、「MT940 口座取引明細書」の口座取引明細書の形式処理グループを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52edd-170">First, you must define the bank statement format processing group for MT940 bank statements by using the data entity framework.</span></span>

1.  <span data-ttu-id="52edd-171">**ワークスペース** &gt; **データ管理**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52edd-171">Go to **Workspaces** &gt; **Data management**.</span></span>
2.  <span data-ttu-id="52edd-172">**インポート**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-172">Click **Import**.</span></span>
3.  <span data-ttu-id="52edd-173">「**MT940**」などの形式の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="52edd-173">Enter a name for the format, such as **MT940**.</span></span>
4.  <span data-ttu-id="52edd-174">[**ソース データ形式**] フィールドを [**XML-Element**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-174">Set the **Source data format** field to **XML-Element**.</span></span>
5.  <span data-ttu-id="52edd-175">[**エンティティ名**] フィールドを [**口座取引明細書**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-175">Set the **Entity name** field to **Bank statements**.</span></span>
6.  <span data-ttu-id="52edd-176">インポート ファイルをアップロードするには、[**アップロード**] をクリックし、次に参照して先ほど保存した「**SampleBankCompositeEntity.xml**」ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-176">To upload import files, click **Upload**, and then browse to select the **SampleBankCompositeEntity.xml** file that you saved earlier.</span></span>
7.  <span data-ttu-id="52edd-177">口座取引明細書のエンティティがアップロードされ、マッピングが完了した後、エンティティの [**マップの表示**] アクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-177">After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.</span></span>
8.  <span data-ttu-id="52edd-178">口座取引明細書のエンティティは、4 つの別々のエンティティで構成される複合エンティティです。</span><span class="sxs-lookup"><span data-stu-id="52edd-178">The Bank statements entity is a composite entity that consists of four separate entities.</span></span> <span data-ttu-id="52edd-179">一覧で、[**BankStatementDocumentEntity**] を選択し、次に [**マップの表示**] アクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-179">In the list, select **BankStatementDocumentEntity**, and then click the **View map** action.</span></span>
9.  <span data-ttu-id="52edd-180">[**変換**] タブで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-180">On the **Transformations** tab, click **New**.</span></span>
10. <span data-ttu-id="52edd-181">シーケンス番号 1 で、[**ファイルのアップロード**] をクリックし、先ほど保存した「**MT940TXT-to-MT940XML.xslt**」ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-181">For sequence number 1, click **Upload file**, and select the **MT940TXT-to-MT940XML.xslt** file that you saved earlier.</span></span>
11. <span data-ttu-id="52edd-182">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-182">Click **New**.</span></span>
12. <span data-ttu-id="52edd-183">シーケンス番号 2 で、[**ファイルのアップロード**] をクリックし、先ほど保存した「**MT940XML-to-Reconciliation.xslt**」ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-183">For sequence number 2, click **Upload file**, and select the **MT940XML-to-Reconciliation.xslt** file that you saved earlier.</span></span> <span data-ttu-id="52edd-184">**注記:** Finance and Operations 変換ファイルは、標準形式で作成されます。</span><span class="sxs-lookup"><span data-stu-id="52edd-184">**Note:** Finance and Operations transformation files are built for the standard format.</span></span> <span data-ttu-id="52edd-185">銀行は多くの場合、この形式と異なるため、口座取引明細書の形式にマップする変換ファイルを更新する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="52edd-185">Because banks often diverge from this format, you may have to update the transformation file to map to your bank statement format.</span></span> <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. <span data-ttu-id="52edd-186">**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-186">Click **New**.</span></span>
14. <span data-ttu-id="52edd-187">シーケンス番号 3 で、[**ファイルのアップロード**] をクリックし、先ほど保存した「**BankReconciliation-to-Composite.xslt**」ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-187">For sequence number 3, click **Upload file**, and select the **BankReconciliation-to-Composite.xslt** file that you saved earlier.</span></span>
15. <span data-ttu-id="52edd-188">[**変換の適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-188">Click **Apply transforms**.</span></span>

<span data-ttu-id="52edd-189">形式の処理グループを設定したら、次に、「MT940 口座取引明細書」の口座取引明細書の形式ルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="52edd-189">After the format processing group is set up, the next step is to define the bank statement format rules for MT940 bank statements.</span></span>

1.  <span data-ttu-id="52edd-190">**現金および銀行管理** &gt; **設定** &gt; **詳細な口座調整の設定** &gt; **口座取引明細書の形式**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52edd-190">Go to **Cash and bank management** &gt; **Setup** &gt; **Advanced bank reconciliation setup** &gt; **Bank statement format**.</span></span>
2.  <span data-ttu-id="52edd-191">**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-191">Click **New**.</span></span>
3.  <span data-ttu-id="52edd-192">「**MT940**」などの明細書の形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-192">Specify a statement format, such as **MT940**.</span></span>
4.  <span data-ttu-id="52edd-193">形式の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="52edd-193">Enter a name for the format.</span></span>
5.  <span data-ttu-id="52edd-194">[**処理グループ**] フィールドを「**MT940**」などの先ほど定義したグループに設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-194">Set the **Processing group** field to the group that you defined earlier, such as **MT940**.</span></span>
6.  <span data-ttu-id="52edd-195">[**ファイル タイプ**] フィールドを [**txt**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-195">Set the **File type** field to **txt**.</span></span>

<span data-ttu-id="52edd-196">最後の手順は、詳細な口座調整を有効にし、銀行口座の明細書の形式を設定することです。</span><span class="sxs-lookup"><span data-stu-id="52edd-196">The last step is to enable Advanced bank reconciliation and set the statement format on the bank account.</span></span>

1.  <span data-ttu-id="52edd-197">**現金および銀行管理** &gt; **銀行口座**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52edd-197">Go to **Cash and bank management** &gt; **Bank accounts**.</span></span>
2.  <span data-ttu-id="52edd-198">銀行口座を選択し、ファイルを開いて詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="52edd-198">Select the bank account, and open it to view the details.</span></span>
3.  <span data-ttu-id="52edd-199">[**調整**] タブで、[**詳細な口座調整**] オプションを [**はい**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-199">On the **Reconciliation** tab, set the **Advanced bank reconciliation** option to **Yes**.</span></span>
4.  <span data-ttu-id="52edd-200">選択内容、および詳細な口座調整を有効にしたことを確認した時点で、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-200">When you're prompted to confirm your selection and enable Advanced bank reconciliation, click **OK**.</span></span>
5.  <span data-ttu-id="52edd-201">[**明細書形式**] フィールドを「**MT940**」などの先ほど作成した形式に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-201">Set the **Statement format** field to the format that you created earlier, such as **MT940**.</span></span>

## <a name="set-up-the-import-of-bai2-bank-statements"></a><span data-ttu-id="52edd-202">BAI2 口座取引明細書のインポートの設定</span><span class="sxs-lookup"><span data-stu-id="52edd-202">Set up the import of BAI2 bank statements</span></span>
<span data-ttu-id="52edd-203">最初に、データ エンティティ フレームワークを使用して「BAI2 口座取引明細書」の口座取引明細書の形式処理グループを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52edd-203">First, you must define the bank statement format processing group for BAI2 bank statements by using the data entity framework.</span></span>

1.  <span data-ttu-id="52edd-204">**ワークスペース** &gt; **データ管理**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52edd-204">Go to **Workspaces** &gt; **Data management**.</span></span>
2.  <span data-ttu-id="52edd-205">**インポート**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-205">Click **Import**.</span></span>
3.  <span data-ttu-id="52edd-206">「**BAI2**」などの形式の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="52edd-206">Enter a name for the format, such as **BAI2**.</span></span>
4.  <span data-ttu-id="52edd-207">[**ソース データ形式**] フィールドを [**XML-Element**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-207">Set the **Source data format** field to **XML-Element**.</span></span>
5.  <span data-ttu-id="52edd-208">[**エンティティ名**] フィールドを [**口座取引明細書**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-208">Set the **Entity name** field to **Bank statements**.</span></span>
6.  <span data-ttu-id="52edd-209">インポート ファイルをアップロードするには、[**アップロード**] をクリックし、次に参照して先ほど保存した「**SampleBankCompositeEntity.xml**」ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-209">To upload import files, click **Upload**, and then browse to select the **SampleBankCompositeEntity.xml** file that you saved earlier.</span></span>
7.  <span data-ttu-id="52edd-210">口座取引明細書のエンティティがアップロードされ、マッピングが完了した後、エンティティの [**マップの表示**] アクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-210">After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.</span></span>
8.  <span data-ttu-id="52edd-211">口座取引明細書のエンティティは、4 つの別々のエンティティで構成される複合エンティティです。</span><span class="sxs-lookup"><span data-stu-id="52edd-211">The Bank statements entity is a composite entity that consists of four separate entities.</span></span> <span data-ttu-id="52edd-212">一覧で、[**BankStatementDocumentEntity**] を選択し、次に [**マップの表示**] アクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-212">In the list, select **BankStatementDocumentEntity**, and then click the **View map** action.</span></span>
9.  <span data-ttu-id="52edd-213">[**変換**] タブで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-213">On the **Transformations** tab, click **New**.</span></span>
10. <span data-ttu-id="52edd-214">シーケンス番号 1 で、[**ファイルのアップロード**] をクリックし、先ほど保存した「**BAI2CSV-to-BAI2XML.xslt**」ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-214">For sequence number 1, click **Upload file**, and select the **BAI2CSV-to-BAI2XML.xslt** file that you saved earlier.</span></span>
11. <span data-ttu-id="52edd-215">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-215">Click **New**.</span></span>
12. <span data-ttu-id="52edd-216">シーケンス番号 2 で、[**ファイルのアップロード**] をクリックし、先ほど保存した「**BAI2XML-to-Reconciliation.xslt**」ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-216">For sequence number 2, click **Upload file**, and select the **BAI2XML-to-Reconciliation.xslt** file that you saved earlier.</span></span> <span data-ttu-id="52edd-217">**注記:** Finance and Operations 変換ファイルは、標準形式で作成されます。</span><span class="sxs-lookup"><span data-stu-id="52edd-217">**Note:** Finance and Operations transformation files are built for the standard format.</span></span> <span data-ttu-id="52edd-218">銀行は多くの場合、この形式と異なるため、口座取引明細書の形式にマップする変換ファイルを更新する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="52edd-218">Because banks often diverge from this format, and you may have to update the transformation file to map to your bank statement format.</span></span> <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. <span data-ttu-id="52edd-219">**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-219">Click **New**.</span></span>
14. <span data-ttu-id="52edd-220">シーケンス番号 3 で、[**ファイルのアップロード**] をクリックし、先ほど保存した「**BankReconciliation-to-Composite.xslt**」ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-220">For sequence number 3, click **Upload file**, and select the **BankReconciliation-to-Composite.xslt** file that you saved earlier.</span></span>
15. <span data-ttu-id="52edd-221">[**変換の適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-221">Click **Apply transforms**.</span></span>

<span data-ttu-id="52edd-222">形式の処理グループを設定した後は、BAI2 口座取引明細書の口座取引明細書の形式のルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="52edd-222">After the format processing group is set up, the next step is to define the bank statement format rules for BAI2 bank statements.</span></span>

1.  <span data-ttu-id="52edd-223">**現金および銀行管理** &gt; **設定** &gt; **詳細な口座調整の設定** &gt; **口座取引明細書の形式**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52edd-223">Go to **Cash and bank management** &gt; **Setup** &gt; **Advanced bank reconciliation setup** &gt; **Bank statement format**.</span></span>
2.  <span data-ttu-id="52edd-224">**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-224">Click **New**.</span></span>
3.  <span data-ttu-id="52edd-225">「**BAI2**」などの明細書の形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-225">Specify a statement format, such as **BAI2**.</span></span>
4.  <span data-ttu-id="52edd-226">形式の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="52edd-226">Enter a name for the format.</span></span>
5.  <span data-ttu-id="52edd-227">[**処理グループ**] フィールドを「**BAI2**」などの先ほど定義したグループに設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-227">Set the **Processing group** field to the group that you defined earlier, such as **BAI2**.</span></span>
6.  <span data-ttu-id="52edd-228">[**ファイル タイプ**] フィールドを [**txt**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-228">Set the **File type** field to **txt**.</span></span>

<span data-ttu-id="52edd-229">最後の手順は、詳細な口座調整を有効にし、銀行口座の明細書の形式を設定することです。</span><span class="sxs-lookup"><span data-stu-id="52edd-229">The last step is to enable Advanced bank reconciliation and set the statement format on the bank account.</span></span>

1.  <span data-ttu-id="52edd-230">**現金および銀行管理** &gt; **銀行口座**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52edd-230">Go to **Cash and bank management** &gt; **Bank accounts**.</span></span>
2.  <span data-ttu-id="52edd-231">銀行口座を選択し、ファイルを開いて詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="52edd-231">Select the bank account, and open it to view the details.</span></span>
3.  <span data-ttu-id="52edd-232">[**調整**] タブで、[**詳細な口座調整**] オプションを [**はい**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-232">On the **Reconciliation** tab, set the **Advanced bank reconciliation** option to **Yes**.</span></span>
4.  <span data-ttu-id="52edd-233">選択内容、および詳細な口座調整を有効にしたことを確認した時点で、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-233">When you're prompted to confirm your selection and enable Advanced bank reconciliation, click **OK**.</span></span>
5.  <span data-ttu-id="52edd-234">[**明細書形式**] フィールドを「**BAI2**」などの先ほど作成した形式に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-234">Set the **Statement format** field to the format that you created earlier, such as **BAI2**.</span></span>

## <a name="test-the-bank-statement-import"></a><span data-ttu-id="52edd-235">口座取引明細書のインポートのテスト</span><span class="sxs-lookup"><span data-stu-id="52edd-235">Test the bank statement import</span></span>
<span data-ttu-id="52edd-236">最後の手順では、口座取引明細書がインポートできることをテストします。</span><span class="sxs-lookup"><span data-stu-id="52edd-236">The final step is to test that you can import your bank statement.</span></span>

1.  <span data-ttu-id="52edd-237">**現金および銀行管理** &gt; **銀行口座**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52edd-237">Go to **Cash and bank management** &gt; **Bank accounts**.</span></span>
2.  <span data-ttu-id="52edd-238">詳細な口座調整機能が有効な銀行口座を選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-238">Select the bank account that Advanced bank reconciliation functionality is enabled for.</span></span>
3.  <span data-ttu-id="52edd-239">[**調整**] タブで、[**口座取引明細書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-239">On the **Reconcile** tab, click **Bank statements**.</span></span>
4.  <span data-ttu-id="52edd-240">[**口座取引明細書**] ページで、[**明細書のインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-240">On the **Bank statement** page, click **Import statement**.</span></span>
5.  <span data-ttu-id="52edd-241">[**銀行口座**] フィールドを選択した銀行口座に設定します。</span><span class="sxs-lookup"><span data-stu-id="52edd-241">Set the **Bank account** field to the selected bank account.</span></span> <span data-ttu-id="52edd-242">[**明細書形式**] フィールドは、銀行口座の設定に基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="52edd-242">The **Statement format** field will be set automatically, based on the setting on the bank account.</span></span>
6.  <span data-ttu-id="52edd-243">[**参照**] をクリックし、電子口座取引明細書ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="52edd-243">Click **Browse**, and select your electronic bank statement file.</span></span>
7.  <span data-ttu-id="52edd-244">[**アップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52edd-244">Click **Upload**.</span></span>
8.  <span data-ttu-id="52edd-245">[**OK**] をクリックします</span><span class="sxs-lookup"><span data-stu-id="52edd-245">Click **OK**.</span></span>

<span data-ttu-id="52edd-246">インポートが成功した場合、明細書がインポートされたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52edd-246">If the import is successful, you will receive a message that states that your statement was imported.</span></span> <span data-ttu-id="52edd-247">インポートが失敗した場合、[**データ管理**] ワークスペースの [**ジョブ履歴**] セクションで、ジョブを検索します。</span><span class="sxs-lookup"><span data-stu-id="52edd-247">If the import wasn't successful, in the **Data management** workspace, in the **Job history** section, find the job.</span></span> <span data-ttu-id="52edd-248">ジョブの [**実行の詳細**] をクリックして、[**実行の要約**] ページを開き、次に [**実行ログの表示**] をクリックしてインポート エラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="52edd-248">Click **Execution details** for the job to open the **Execution summary** page, and then click **View execution log** to view the import errors.</span></span>



