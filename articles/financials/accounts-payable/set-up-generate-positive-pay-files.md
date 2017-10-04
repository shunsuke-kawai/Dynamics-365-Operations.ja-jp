---
title: "確認後支払ファイルの設定と生成"
description: "この記事は、確認後支払を設定し、確認後支払ファイルを生成する方法を説明します。"
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8294eb2861f48402c8489b84cc5f139408a22262
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="set-up-and-generate-positive-pay-files"></a><span data-ttu-id="38696-103">確認後支払ファイルの設定と生成</span><span class="sxs-lookup"><span data-stu-id="38696-103">Set up and generate positive pay files</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="38696-104">この記事は、確認後支払を設定し、確認後支払ファイルを生成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="38696-104">This article explains how to set up positive pay and generate positive pay files.</span></span> 

<span data-ttu-id="38696-105">確認後支払を設定し、銀行に渡す小切手の電子リストを生成します。</span><span class="sxs-lookup"><span data-stu-id="38696-105">Set up positive pay to generate an electronic list of checks that is provided to the bank.</span></span> <span data-ttu-id="38696-106">次に、小切手が銀行に提出されたら、銀行はそれを小切手リストと比較します。</span><span class="sxs-lookup"><span data-stu-id="38696-106">Then, when a check is presented to the bank, the bank compares it with the list of checks.</span></span> <span data-ttu-id="38696-107">小切手がリストの小切手と一致する場合、銀行は小切手を決済します。</span><span class="sxs-lookup"><span data-stu-id="38696-107">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="38696-108">小切手がリスト内の小切手と一致しない場合、銀行は確認のために小切手を保留にします。</span><span class="sxs-lookup"><span data-stu-id="38696-108">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

## <a name="security-for-positive-pay-files"></a><span data-ttu-id="38696-109">確認後支払ファイルのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="38696-109">Security for positive pay files</span></span>
<span data-ttu-id="38696-110">確認後支払ファイルには、受取人と小切手金額に関する機密情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="38696-110">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="38696-111">したがって、ファイルを生成時から銀行がそのファイルを受領するまで、適切なセキュリティ対策をかならず使用します。</span><span class="sxs-lookup"><span data-stu-id="38696-111">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="38696-112">確認後支払ファイルは、Web ブラウザで指定した場所にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="38696-112">Positive pay files are downloaded to the location that is specified by your web browser.</span></span> <span data-ttu-id="38696-113">確認後支払ファイルには機密情報が含まれている場合があるので、承認されたユーザーのみが、Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 内のこの情報を生成および表示するためのアクセス権限を持つことが重要です。</span><span class="sxs-lookup"><span data-stu-id="38696-113">Because positive pay files can contain sensitive information, it's important that only authorized users have access to generate and view this information in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="38696-114">次の表を活用すれば、必要な権限を判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="38696-114">Use the following table to help you determine the privileges that are required.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38696-115">タスク</span><span class="sxs-lookup"><span data-stu-id="38696-115">Task</span></span></th>
<th><span data-ttu-id="38696-116">権限</span><span class="sxs-lookup"><span data-stu-id="38696-116">Privilege</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="38696-117">確認後支払ファイルを<strong>銀行口座</strong>リスト ページあるいは<strong>銀行口座</strong>ページから生成します。</span><span class="sxs-lookup"><span data-stu-id="38696-117">Generate positive pay files from the <strong>Bank accounts</strong> list page or the <strong>Bank accounts</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="38696-118"><strong>銀行の確認後支払情報の管理</strong>(BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="38696-118"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="38696-119"><strong>BankPositivePayExportEntityView</strong>(BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="38696-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="38696-120">[<strong>確認後支払ファイルを生成</strong>] ページから複数の法人と銀行口座の確認後支払ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="38696-120">Generate positive pay files for multiple legal entities and bank accounts from the <strong>Generate a positive pay file</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="38696-121"><strong>銀行の確認後支払情報の管理</strong>(BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="38696-121"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="38696-122"><strong>BankPositivePayExportEntityView</strong>(BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="38696-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="38696-123">[<strong>確認後支払ファイルの概要</strong>] ページで確認後支払ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="38696-123">View positive pay files on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="38696-124"><strong>複数の法人に関する銀行確認後支払情報の表示</strong>(BankPositivePayView)</span><span class="sxs-lookup"><span data-stu-id="38696-124"><strong>View bank positive pay information for multiple legal entities</strong> (BankPositivePayView)</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="38696-125">[<strong>確認後支払ファイルの概要</strong>] ページで銀行の確認後支払ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="38696-125">Confirm a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="38696-126"><strong>確認後支払ファイルの確認</strong>(BankPositivePayConfirm)</span><span class="sxs-lookup"><span data-stu-id="38696-126"><strong>Confirm positive payment file</strong> (BankPositivePayConfirm)</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="38696-127">[<strong>確認後支払ファイルの概要</strong>] ページで銀行の確認後支払ファイルを取り消します。</span><span class="sxs-lookup"><span data-stu-id="38696-127">Recall a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="38696-128">[<strong>確認後支払ファイルの取り消し</strong>] (BankPositivePayRecall)</span><span class="sxs-lookup"><span data-stu-id="38696-128"><strong>Recall positive pay file</strong> (BankPositivePayRecall)</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a><span data-ttu-id="38696-129">確認後支払形式の設定</span><span class="sxs-lookup"><span data-stu-id="38696-129">Set up a positive pay format</span></span>
<span data-ttu-id="38696-130">確認後支払ファイルは、データ エンティティを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="38696-130">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="38696-131">確認後支払ファイルを生成する前に、小切手情報を銀行と通信できる形式に変換するのに使用する変換入力形式を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38696-131">Before you can generate a positive pay file, you must set up a transformation input format that will be used to translate the check information into a format that can communicate with the bank.</span></span> <span data-ttu-id="38696-132">[**確認後支払形式**] ページで、ファイル形式の ID と説明を作成できます。</span><span class="sxs-lookup"><span data-stu-id="38696-132">On the **Positive pay format** page, you can create a file format identifier and a description.</span></span> <span data-ttu-id="38696-133">変換入力形式は、XML タイプにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38696-133">The transformation input format must be of the XML type.</span></span> <span data-ttu-id="38696-134">特定の形式は、使用している変換ファイルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="38696-134">The specific format depends on the transformation file that you're using.</span></span> <span data-ttu-id="38696-135">たとえば、サンプル XSLT (Extensible Stylesheet Language Transformations) ファイルは**XML-Element**形式を使用するよう指定されています。</span><span class="sxs-lookup"><span data-stu-id="38696-135">For example, the sample Extensible Stylesheet Language Transformations (XSLT) file that is provided uses the **XML-Element** format.</span></span> <span data-ttu-id="38696-136">[**変換に使用されるファイルのアップロード**] アクションを使用して、銀行が必要な形式の変換ファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="38696-136">Use the **Upload file used for transformation** action to specify the location of the transform file for the format that your bank requires.</span></span>

## <a name="example-xslt-file-for-positive-pay-file"></a><span data-ttu-id="38696-137">例: 確認後支払ファイル用 XSLT ファイル</span><span class="sxs-lookup"><span data-stu-id="38696-137">Example: XSLT file for positive pay file</span></span>
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
      <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
      <xsl:template match="/">
        <xsl:value-of select="'
    '" />
        <Document>
          <xsl:value-of select="'
    '" />
          <!--Header Begin-->
          <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
          <xsl:value-of select="'
    '" />
          <!--Header End-->
          <xsl:for-each select="Document/BankPositivePayExportEntity">
            <!--Cheque Detail begin-->
            <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
                <xsl:value-of select='string("Yes")'/>
              </xsl:when>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
                <xsl:value-of select='string("No")'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='string(" ")'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("Payment")'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='CHEQUENUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='AMOUNTCUR/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("BOA-#1812")'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
                <xsl:value-of select='VENDGROUP/text()'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='CUSTGROUP/text()'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="'
    '" />
          </xsl:for-each>
        </Document>
      </xsl:template>
    </xsl:stylesheet>

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a><span data-ttu-id="38696-138">銀行口座への確認後支払形式の割り当て</span><span class="sxs-lookup"><span data-stu-id="38696-138">Assign the positive pay format to a bank account</span></span>
<span data-ttu-id="38696-139">確認後支払情報を生成する銀行口座ごとに、前のセクションで指定した確認後支払形式を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="38696-139">For each bank account that you want to generate positive pay information for, you must assign the positive pay format that you specified in the previous section.</span></span> <span data-ttu-id="38696-140">[**銀行口座**] ページで、銀行口座に対応する確認後支払形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="38696-140">On the **Bank accounts** page, select the positive pay format that corresponds to the bank account.</span></span> <span data-ttu-id="38696-141">[**確認後の開始日**] フィールドに、確認後支払ファイルを生成する最初の日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="38696-141">In the **Positive pay start date** field, enter the first date to generate positive pay files.</span></span> <span data-ttu-id="38696-142">このフィールドに日付を入力することが重要です。</span><span class="sxs-lookup"><span data-stu-id="38696-142">It's important that you enter a date in this field.</span></span> <span data-ttu-id="38696-143">それ以外の場合は、生成する最初の確認後支払ファイルは、この銀行口座に対して作成されているすべての小切手が含まれます。</span><span class="sxs-lookup"><span data-stu-id="38696-143">Otherwise, the first positive pay file that you generate will include all checks that have ever been created for this bank account.</span></span>

## <a name="assign-a-number-sequence-for-positive-pay-files"></a><span data-ttu-id="38696-144">確認後支払ファイルの番号順序の割り当て</span><span class="sxs-lookup"><span data-stu-id="38696-144">Assign a number sequence for positive pay files</span></span>
<span data-ttu-id="38696-145">各確認後支払ファイルには固有の番号を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="38696-145">Each positive pay file must have a unique number.</span></span> <span data-ttu-id="38696-146">[**現金及び銀行管理パラメーター**] ページの [**番号順序**] タブを使用して確認後支払ファイルの番号順序を作成します。</span><span class="sxs-lookup"><span data-stu-id="38696-146">Use the **Number sequences** tab on the **Cash and bank management parameters** page to create a number sequence for positive pay files.</span></span>

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a><span data-ttu-id="38696-147">一つの銀行口座に対する確認後支払ファイルの生成</span><span class="sxs-lookup"><span data-stu-id="38696-147">Generate a positive pay file for a single bank account</span></span>
<span data-ttu-id="38696-148">一つの法人と一つの銀行口座に対する確認後支払ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="38696-148">You can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="38696-149">複数の法人と銀行口座の確認後支払ファイルを同時に生成する方法についての情報は、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38696-149">For information about how to generate positive pay files for multiple legal entities and bank accounts at the same time, see the next section.</span></span> <span data-ttu-id="38696-150">一つの法人と一つの銀行口座の確認後支払ファイルを生成するには、[**銀行口座**] ページから [**確認後支払ファイルの生成**] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="38696-150">To generate a positive pay file for a single legal entity and a single bank account, open the **Generate a positive pay file** dialog box from the **Bank accounts** page.</span></span> <span data-ttu-id="38696-151">[**締め日**] フィールドで、確認後支払ファイルに含める最終確認日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="38696-151">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="38696-152">この最終確認日付までに、確認後支払ファイルにまだ含まれていないすべての小切手がファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="38696-152">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a><span data-ttu-id="38696-153">複数の銀行口座に対する確認後支払ファイルの生成</span><span class="sxs-lookup"><span data-stu-id="38696-153">Generate a positive pay file for multiple bank accounts</span></span>
<span data-ttu-id="38696-154">複数の銀行口座の確認後支払ファイルを生成するには、[**確認後支払ファイルを生成**] 定期処理タスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="38696-154">To generate a positive pay file for multiple bank accounts, use the **Generate a positive pay file** periodic task.</span></span> <span data-ttu-id="38696-155">ファイルの確認後支払形式を選択し、すべての法人あるいは選択した法人に対してファイルを生成するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="38696-155">Select the positive pay format for the file, and specify whether to generate the file for all legal entities or for a selected legal entity.</span></span> <span data-ttu-id="38696-156">指定した確認後支払形式あるいは選択した銀行口座を使用するすべての銀行口座の確認後支払ファイルを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="38696-156">You can also generate the positive pay file for all bank accounts that use the specified positive pay format or for a selected bank account.</span></span> <span data-ttu-id="38696-157">[**締め日**] フィールドで、確認後支払ファイルに含める最終確認日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="38696-157">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="38696-158">この最終確認日付までに、確認後支払ファイルにまだ含まれていないすべての小切手がファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="38696-158">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="view-the-results-of-positive-pay-file-generation"></a><span data-ttu-id="38696-159">確認後支払ファイルの生成の結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="38696-159">View the results of positive pay file generation</span></span>
<span data-ttu-id="38696-160">確認後支払ファイルが生成された後、[**確認後支払ファイルの概要**] ページで結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="38696-160">After the positive pay file is generated, you can view the results on the **Positive pay file summary** page.</span></span> <span data-ttu-id="38696-161">個々の小切手の詳細を表示するには、[**確認後支払ファイル**] 詳細ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="38696-161">To view the details of the individual checks, use the **Positive pay file** details page.</span></span>

## <a name="confirm-a-positive-pay-file"></a><span data-ttu-id="38696-162">確認後支払ファイルを確認する</span><span class="sxs-lookup"><span data-stu-id="38696-162">Confirm a positive pay file</span></span>
<span data-ttu-id="38696-163">確認後支払ファイルに記載されている小切手が支払われた後、銀行から確認番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="38696-163">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="38696-164">その後、確認後支払ファイルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="38696-164">You can then confirm the positive pay file.</span></span> <span data-ttu-id="38696-165">[**確認後支払ファイルの概要**] ページで、ステータスが [**作成済み**] になっている確認後支払ファイルを選択し、次に [**確認入力**] アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="38696-165">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Enter confirmation** action.</span></span> <span data-ttu-id="38696-166">確認後支払ファイルを確認する際、銀行から受け取った確認番号が記録されます。</span><span class="sxs-lookup"><span data-stu-id="38696-166">When you confirm a positive pay file, the confirmation number that you received from the bank is recorded.</span></span>

## <a name="recall-a-positive-pay-file"></a><span data-ttu-id="38696-167">確認後支払ファイルの取り消し</span><span class="sxs-lookup"><span data-stu-id="38696-167">Recall a positive pay file</span></span>
<span data-ttu-id="38696-168">確認後支払ファイルを変更する必要がある場合は、それを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="38696-168">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="38696-169">[**確認後支払ファイルの概要**] ページで、ステータスが [**作成済み**] になっている確認後支払ファイルを選択し、次に [**取り消し**] アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="38696-169">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Recall** action.</span></span> <span data-ttu-id="38696-170">確認後支払ファイルの小切手ごとに、小切手が確認後支払ファイルに含まれているかどうかを示すフィールドがリセットされます。</span><span class="sxs-lookup"><span data-stu-id="38696-170">For each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span> <span data-ttu-id="38696-171">その後、取り消した小切手を含む新しい確認後支払ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="38696-171">You can then create a new positive pay file that includes the check that was recalled.</span></span>



