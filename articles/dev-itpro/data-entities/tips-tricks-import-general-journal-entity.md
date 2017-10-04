---
title: "一般仕訳エンティティを使用して伝票をインポートするためのベスト プラクティス"
description: "このトピックでは、一般仕訳エンティティを使用して一般仕訳帳にデータをインポートするためのヒントを提供します。"
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: a45a75d23c77af86b55866f99a97343a210ec777
ms.contentlocale: ja-jp
ms.lasthandoff: 07/18/2017

---

# <a name="best-practices-for-importing-vouchers-using-the-general-journal-entity"></a><span data-ttu-id="da136-103">一般仕訳エンティティを使用して伝票をインポートするためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="da136-103">Best practices for importing vouchers using the General journal entity</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="da136-104">このトピックでは、一般仕訳エンティティを使用して一般仕訳帳にデータをインポートするためのヒントを提供します。</span><span class="sxs-lookup"><span data-stu-id="da136-104">This topic provides tips for importing data into the General journal by using the General journal entity.</span></span>  

<span data-ttu-id="da136-105">一般仕訳エンティティを使用して、勘定または相手勘定タイプが **元帳、顧客、仕入先、または銀行** の伝票をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="da136-105">You can use the General journal entity to import vouchers that have an account or offset account type of **Ledger, Customer, Vendor, or Bank**.</span></span> <span data-ttu-id="da136-106">伝票は、[**勘定**] フィールドと [**相手勘定**] フィールドの両方を使用して 1 行として入力できます。もしくは複数行の伝票として入力できますが、その場合は [**勘定**] フィールドだけが使用されている (また [**相手勘定**] が各明細行で空白のままになっている) ことになります。</span><span class="sxs-lookup"><span data-stu-id="da136-106">The voucher can be entered as one line, using both the **Account** field and the **Offset account** field, or as a multi-line voucher, where only the **Account** field is used (and the **Offset account** is left blank on each line).</span></span> <span data-ttu-id="da136-107">一般仕訳帳エンティティではすべての勘定タイプのサポートはされません。</span><span class="sxs-lookup"><span data-stu-id="da136-107">The General journal entity doesn't support every account type.</span></span> <span data-ttu-id="da136-108">代わりに、異なる勘定タイプの組み合わせが必要なシナリオのために、他のエンティティが存在します。</span><span class="sxs-lookup"><span data-stu-id="da136-108">Instead, other entities exist for scenarios where different combinations of account types are required.</span></span> <span data-ttu-id="da136-109">たとえば、プロジェクト トランザクションをインポートするには、プロジェクト経費仕訳帳エンティティを使用します。</span><span class="sxs-lookup"><span data-stu-id="da136-109">For example, to import a project transaction, use the Project expense journal entity.</span></span> <span data-ttu-id="da136-110">各エンティティは特定のシナリオをサポートするように設計されています。つまり、追加のフィールドはそれらのシナリオのエンティティで使用できても異なるシナリオのエンティティでは使用できない場合があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="da136-110">Each entity is designed to support specific scenarios, which means additional fields may be available in entities for those scenarios but not in entities for a different scenario.</span></span>

## <a name="setup"></a><span data-ttu-id="da136-111">段取り</span><span class="sxs-lookup"><span data-stu-id="da136-111">Setup</span></span>
<span data-ttu-id="da136-112">一般仕訳エンティティを使用してインポートする前に、次の設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="da136-112">Before you import by using the General journal entity, validate the following setup:</span></span>

-   <span data-ttu-id="da136-113">**仕訳帳バッチ番号の番号順序の設定** - 既定では、一般仕訳エンティティを使用してインポートする場合、仕訳帳バッチ番号は、総勘定元帳パラメーターで定義された番号順序を使用します。</span><span class="sxs-lookup"><span data-stu-id="da136-113">**Number sequence setup for the journal batch number** - By default, when you import by using the General journal entity, the journal batch number uses the number sequence that is defined in the General ledger parameters.</span></span> <span data-ttu-id="da136-114">仕訳帳バッチ番号の番号順序を [**手動**] に設定する場合、既定の番号は適用されません。</span><span class="sxs-lookup"><span data-stu-id="da136-114">If you set the number sequence for the journal batch number to **Manual**, a default number isn't applied.</span></span> <span data-ttu-id="da136-115">この設定はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="da136-115">This setup isn't supported.</span></span>
-   <span data-ttu-id="da136-116">**財務分析コードの構成** - エンティティを使用してトランザクションをインポートするとき、すべての組織は財務分析コードの順序を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da136-116">**Financial dimension configuration** - Every organization must define the order of financial dimensions when entities are used to import transactions.</span></span> <span data-ttu-id="da136-117">順序は、[**勘定分析コードの統合**] 形式のために、[**総勘定元帳**] &gt; [**勘定科目表**] &gt; [**分析コード**] &gt; [**アプリケーション統合用の財務分析コードの構成**] &gt; [**データ エンティティの選択**] で定義されます。</span><span class="sxs-lookup"><span data-stu-id="da136-117">The order is defined for the **Ledger dimensions integration** format, at **General ledger** &gt; **Chart of accounts** &gt; **Dimensions** &gt; **Financial dimension configuration for integrating applications** &gt; **Select data entities**.</span></span> <span data-ttu-id="da136-118">インポートする勘定科目のセグメントには、同じ順序が必要です。</span><span class="sxs-lookup"><span data-stu-id="da136-118">The segments of the ledger account that is imported must have the same order.</span></span> <span data-ttu-id="da136-119">それ以外の場合、インポート中にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="da136-119">Otherwise, an error will occur during import.</span></span>

## <a name="general-journal-entity-setup"></a><span data-ttu-id="da136-120">一般仕訳エンティティの設定</span><span class="sxs-lookup"><span data-stu-id="da136-120">General journal entity setup</span></span>
<span data-ttu-id="da136-121">データ管理の 2 つの設定は既定の仕訳帳バッチ番号または伝票番号を適用する方法に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="da136-121">Two settings in Data management affect how the default journal batch number or voucher number is applied:</span></span>

-   <span data-ttu-id="da136-122">**セット ベースのプロセス** (データ エンティティで)</span><span class="sxs-lookup"><span data-stu-id="da136-122">**Set-based processing** (on the data entity)</span></span>
-   <span data-ttu-id="da136-123">**自動生成** (フィールド マッピングで)</span><span class="sxs-lookup"><span data-stu-id="da136-123">**Auto-generated** (on the field mapping)</span></span>

<span data-ttu-id="da136-124">以下のセクションでは、これらの設定の影響について説明し、仕訳帳バッチ番号と伝票番号を生成する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="da136-124">The following sections describe the effect of these settings, and also explain how journal batch numbers and voucher numbers are generated.</span></span>

### <a name="journal-batch-number"></a><span data-ttu-id="da136-125">仕訳帳バッチ番号</span><span class="sxs-lookup"><span data-stu-id="da136-125">Journal batch number</span></span>

-   <span data-ttu-id="da136-126">一般仕訳エンティティの [**セット ベースのプロセス**] の設定は、仕訳帳バッチ番号の生成方法には影響しません。</span><span class="sxs-lookup"><span data-stu-id="da136-126">The **Set-based processing** setting on the General journal entity doesn't affect the way that journal batch numbers are generated.</span></span>
-   <span data-ttu-id="da136-127">[**仕訳帳バッチ番号**] フィールドが [**自動生成**] に設定されている場合、インポートされるすべての行に対して新しい仕訳帳バッチ番号が作成されます。</span><span class="sxs-lookup"><span data-stu-id="da136-127">If the **Journal batch number** field is set to **Auto-generated**, a new journal batch number is created for every line that is imported.</span></span> <span data-ttu-id="da136-128">この動作はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="da136-128">This behavior isn't recommended.</span></span> <span data-ttu-id="da136-129">[**自動生成**] の設定は、[**マッピング詳細**] タブの [**マップ詳細**] の下のインポート プロジェクトにあります。</span><span class="sxs-lookup"><span data-stu-id="da136-129">The **Auto-generated** setting is found on the import project, under **View map**, on the **Mapping details** tab.</span></span>
-   <span data-ttu-id="da136-130">[**仕訳帳バッチ番号**] フィールドが [**自動生成**] に設定されていない場合、仕訳帳バッチ番号は次のように作成されます。</span><span class="sxs-lookup"><span data-stu-id="da136-130">If the **Journal batch number** field isn't set to **Auto-generated**, the journal batch number is created as follows:</span></span>
    -   <span data-ttu-id="da136-131">インポートしたファイルで定義されている仕訳帳バッチ番号が、既存の未転記日次仕訳帳と一致する場合、一致する仕訳帳バッチ番号を持つすべての行が既存の仕訳帳にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="da136-131">If the journal batch number that is defined in the imported file matches an existing, unposted daily journal, all lines that have a matching journal batch number are imported into the existing journal.</span></span> <span data-ttu-id="da136-132">明細行は転記済仕訳帳バッチ番号にインポートされることはありません。</span><span class="sxs-lookup"><span data-stu-id="da136-132">Lines are never imported into a posted journal batch number.</span></span> <span data-ttu-id="da136-133">代わりに、新しい番号が作成されます。</span><span class="sxs-lookup"><span data-stu-id="da136-133">Instead, a new number is created.</span></span>
    -   <span data-ttu-id="da136-134">インポートしたファイルで定義されている仕訳帳バッチ番号が、既存の未転記日次仕訳帳と一致しない場合、同じ仕訳帳バッチ番号を持つすべての行が新しい仕訳帳の下にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="da136-134">If the journal batch number that is defined in the imported file doesn't match an existing, unposted daily journal, all lines that have the same journal batch number are grouped under a new journal.</span></span> <span data-ttu-id="da136-135">たとえば、1 の仕訳帳バッチ番号を持つすべての行が新しい仕訳帳にインポートされ、2 の仕訳帳バッチ番号を持つすべての行は、2 番目の新しい仕訳帳にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="da136-135">For example, all lines that have a journal batch number of 1 are imported into a new journal, and all lines that have a journal batch number of 2 are imported into a second new journal.</span></span> <span data-ttu-id="da136-136">仕訳帳バッチ番号は、総勘定元帳のパラメーターで定義されている番号順序を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="da136-136">The journal batch number is created by using the number sequence that is defined in the General ledger parameters.</span></span>

### <a name="voucher-number"></a><span data-ttu-id="da136-137">伝票番号</span><span class="sxs-lookup"><span data-stu-id="da136-137">Voucher number</span></span>

-   <span data-ttu-id="da136-138">一般仕訳エンティティの [**セット ベースのプロセス**] 設定を使用する場合、伝票番号をインポートされたファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da136-138">When you use the **Set-based processing** setting on the General journal entity, the voucher number must be provided in the imported file.</span></span> <span data-ttu-id="da136-139">伝票が分散されていない場合でも、一般仕訳帳内のすべてのトランザクションには、インポートしたファイルで指定された伝票番号が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="da136-139">Every transaction in the General journal is assigned the voucher number that is provided in the imported file, even if the voucher isn’t balanced.</span></span> <span data-ttu-id="da136-140">セット ベースのプロセスを使用し、なお、伝票番号に対して定義されている番号順序を使用する場合は、2016 年 2 月のリリースで修正プログラムが提供されています。</span><span class="sxs-lookup"><span data-stu-id="da136-140">If you want to use set-based processing, but you also want to use the number sequence that is defined for voucher numbers, a hotfix has been provided for the February 2016 release.</span></span> <span data-ttu-id="da136-141">修正プログラムの番号は 3170316 で、Lifecycle Services (LCS) からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="da136-141">The hotfix number is 3170316 and available for download from Lifecycle services (LCS).</span></span> <span data-ttu-id="da136-142">詳細については、 [Lifecycle Services から修正プログラムをダウンロード](..\migration-upgrade\download-hotfix-lcs.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da136-142">For more information, see [Download hotfixes from Lifecycle Services](..\migration-upgrade\download-hotfix-lcs.md).</span></span>
    -   <span data-ttu-id="da136-143">この機能を有効にするには、インポートに使用される仕訳帳名で、[**転記時の番号配賦**] を [**はい**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="da136-143">To enable this functionality, on the journal name that is used for imports, set **Number allocation at posting** to **Yes**.</span></span>
    -   <span data-ttu-id="da136-144">伝票番号は、インポートしたファイルで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da136-144">A voucher number must still be defined in the imported file.</span></span> <span data-ttu-id="da136-145">ただし、この番号は一時的なもので、仕訳帳が転記されるときに伝票番号で上書きされます。</span><span class="sxs-lookup"><span data-stu-id="da136-145">However, this number is temporary and is overwritten by the voucher number when the journal is posted.</span></span> <span data-ttu-id="da136-146">一時伝票番号で、仕訳帳の明細行が正しくグループ化されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da136-146">You must make sure that the lines of the journal are grouped correctly by temporary voucher number.</span></span> <span data-ttu-id="da136-147">たとえば、転記の際に一時的な伝票番号が 1 の 3 つの明細行があるとします。</span><span class="sxs-lookup"><span data-stu-id="da136-147">For example, during posting, three lines are found that have a temporary voucher number of 1.</span></span> <span data-ttu-id="da136-148">3 つの明細行すべての一時的な伝票番号は、番号順序の次の番号で上書きされます。</span><span class="sxs-lookup"><span data-stu-id="da136-148">The temporary voucher number of all three lines is overwritten by the next number in the number sequence.</span></span> <span data-ttu-id="da136-149">これら 3 つの明細行がバランス済エントリではない場合、伝票は転記されていません。</span><span class="sxs-lookup"><span data-stu-id="da136-149">If those three lines aren’t a balanced entry, the voucher isn't posted.</span></span> <span data-ttu-id="da136-150">次に、一時的な伝票番号が 2 の行が見つかった場合は、この番号は、番号順序の次の伝票番号で上書きされます。</span><span class="sxs-lookup"><span data-stu-id="da136-150">Next, if lines are found that have a temporary voucher number of 2, this number is overwritten by the next voucher number in the number sequence, and so on.</span></span>

<!-- -->

-   <span data-ttu-id="da136-151">[**セット ベースのプロセス**] 設定を使用しない場合、インポートされたファイルで伝票番号を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="da136-151">When you don't use the **Set-based processing** setting, you do not need to provide a voucher number in the imported file.</span></span> <span data-ttu-id="da136-152">伝票番号は、仕訳帳名 ([**1 つの伝票のみ**]、[**残高との関連**] など) の設定に基づいて、インポート中に作成されます。</span><span class="sxs-lookup"><span data-stu-id="da136-152">The voucher numbers are created during import, based on the setup of the journal name (**One voucher only**, **In connection of balance**, and so on).</span></span> <span data-ttu-id="da136-153">たとえば、仕訳帳名が [**残高との関連**] として定義されている場合、最初の行は、新しい既定の伝票番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="da136-153">For example, if the journal name is defined as **In connection of balance**, the first line receives a new default voucher number.</span></span> <span data-ttu-id="da136-154">システムによって行が評価され、借方と貸方が等しいかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="da136-154">The system then evaluates the line to determine whether the debits equal the credits.</span></span> <span data-ttu-id="da136-155">行に相手勘定が存在する場合、インポートされる次の行は、新しい伝票番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="da136-155">If an offset account exists on the line, the next line that is imported receives a new voucher number.</span></span> <span data-ttu-id="da136-156">相手勘定が存在しない場合は、新しい行がインポートされる度に、システムにより、借方と貸方が等しいかどうかが評価されます。</span><span class="sxs-lookup"><span data-stu-id="da136-156">If no offset account exists, the system evaluates whether the debits equal the credits as each new line is imported.</span></span>
-   <span data-ttu-id="da136-157">[**伝票番号**] フィールドが [**自動生成**] に設定されている場合、インポートは成功しません。</span><span class="sxs-lookup"><span data-stu-id="da136-157">If the **Voucher number** field is set to **Auto-generated**, the import won't succeed.</span></span> <span data-ttu-id="da136-158">[**伝票番号**] フィールドの [**自動生成**] の設定はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="da136-158">The **Auto-generated** setting for the **Voucher number** field isn't supported.</span></span>

<span data-ttu-id="da136-159">既定では、一般仕訳帳エンティティは、セット ベースのプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="da136-159">By default, the General journal entity uses set-based processing.</span></span> <span data-ttu-id="da136-160">組織のビジネス要件を評価した後、[**セット ベースのプロセス**] 設定は [**データ管理**] ワークスペースの [**データ エンティティ**] をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="da136-160">After you evaluate the business requirements for your organization, you can change the **Set-based processing** setting by clicking **Data entities** in the **Data management** workspace.</span></span> <span data-ttu-id="da136-161">セットベースのプロセスを使用して、インポート処理を高速化します。</span><span class="sxs-lookup"><span data-stu-id="da136-161">Set-based processing is used to speed up the import process.</span></span> <span data-ttu-id="da136-162">セットベースのプロセスを使用しない場合は、一般仕訳帳エンティティ インポートのインポートは速度が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="da136-162">If you don't use set-based processing, import of the General journal entity import will be slower.</span></span>



