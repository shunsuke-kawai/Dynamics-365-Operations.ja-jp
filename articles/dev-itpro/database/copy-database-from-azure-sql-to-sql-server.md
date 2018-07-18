---
title: "Finance and Operations データベースをコピーする – Azure SQL を SQL Server にコピーする"
description: "このトピックでは、 Microsoft Dynamics 365 for Finance and Operations のデータベースを Azure ベースの環境から SQL Server ベースの環境に移動する方法について説明します。"
author: maertenm
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations
ms.custom: 203764
ms.assetid: 45efdabf-1714-4ba4-9a9d-217143a6c6e0
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 512797a1942e84846db69e1c344342c1d842debb
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="copy-a-finance-and-operations-database-from-azure-sql-database-to-a-sql-server-environment"></a><span data-ttu-id="ead30-103">Finance and Operations データベースを Azure SQL データベースから SQL Server 環境にコピーする</span><span class="sxs-lookup"><span data-stu-id="ead30-103">Copy a Finance and Operations database from Azure SQL Database to a SQL Server environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ead30-104">このトピックでは、Microsoft Dynamics 365 for Finance and Operations のデータベースを、Microsoft Azure に基づいた環境から Microsoft SQL Serverに基づく環境にエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ead30-104">This topic explains how to export a Microsoft Dynamics 365 for Finance and Operations database from an environment that is based on Microsoft Azure and import it into an environment that is based on Microsoft SQL Server.</span></span>

## <a name="overview"></a><span data-ttu-id="ead30-105">概要</span><span class="sxs-lookup"><span data-stu-id="ead30-105">Overview</span></span>

<span data-ttu-id="ead30-106">データベースを移動するには、sqlpackage.exe コマンドライン ツールを使用して Azure SQL データベースからデータベースをエクスポートし、Microsoft SQL Server 2016 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="ead30-106">To move a database, you use the sqlpackage.exe command-line tool to export the database from Azure SQL Database and then import it into Microsoft SQL Server 2016.</span></span> <span data-ttu-id="ead30-107">エクスポートされたデータのファイル名拡張子は .bacpac なので、このプロセスは多くの場合 *bacpac プロセス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ead30-107">Because the file name extension for the exported data is .bacpac, this process is often referred to as the *bacpac process*.</span></span>

<span data-ttu-id="ead30-108">データベース移動の高レベルのプロセスには、次のフェーズが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ead30-108">The high-level process for a database move includes the following phases:</span></span>

1. <span data-ttu-id="ead30-109">ソース データベースの複製を作成します。</span><span class="sxs-lookup"><span data-stu-id="ead30-109">Create a duplicate of the source database.</span></span>
2. <span data-ttu-id="ead30-110">データベースの準備のため SQL スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ead30-110">Run a SQL script to prepare the database.</span></span>
3. <span data-ttu-id="ead30-111">Azure SQL データベースからデータベースをエキスポートします。</span><span class="sxs-lookup"><span data-stu-id="ead30-111">Export the database from the Azure SQL database.</span></span>
4. <span data-ttu-id="ead30-112">SQL Server 2016 にデータベースをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ead30-112">Import the database into SQL Server 2016.</span></span>
5. <span data-ttu-id="ead30-113">データベースの更新のため SQL スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ead30-113">Run a SQL script to update the database.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ead30-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="ead30-114">Prerequisites</span></span>

<span data-ttu-id="ead30-115">データベースを移動するには、次の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-115">The following prerequisites must be met before you can move a database:</span></span>

- <span data-ttu-id="ead30-116">ソース環境 (つまりソース データベースに接続されている環境) は、ターゲット環境が実行されているプラットフォームのバージョンよりも前または同じバージョンの Finance and Operations プラットフォームを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-116">The source environment (that is, the environment that is connected to the source database) must run a version of the Finance and Operations platform that is earlier than or the same as the version of the platform that the destination environment runs.</span></span>
- <span data-ttu-id="ead30-117">その顧客が SQL アクセスを持つデータベースのみコピーできます。</span><span class="sxs-lookup"><span data-stu-id="ead30-117">Only a database that the customer has SQL access to can be copied.</span></span> <span data-ttu-id="ead30-118">実稼働環境をコピーする必要がある場合は、最初に、その環境をサンド ボックス環境にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-118">If you must copy the production environment, you must first copy that environment to the sandbox environment.</span></span> <span data-ttu-id="ead30-119">サンドボックス環境から作業します。</span><span class="sxs-lookup"><span data-stu-id="ead30-119">Then work from the sandbox environment.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ead30-120">この記事では、*サンドボックス* という用語を使用して SQL Azure データベースに接続されている標準またはプレミア承認テスト (レベル 2/3)、またはより高度な環境を示します。</span><span class="sxs-lookup"><span data-stu-id="ead30-120">In this article, we use the term *sandbox* to refer to a Standard or Premier Acceptance Testing (Tier 2/3) or higher environment connected to a SQL Azure database.</span></span>

- <span data-ttu-id="ead30-121">出力先の SQL Server 環境では、SQL Server 2016 Release to Manufacturing (RTM) (13.00.1601.5) 以降を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-121">The destination SQL Server environment must run SQL Server 2016 Release to Manufacturing (RTM) (13.00.1601.5) or later.</span></span> <span data-ttu-id="ead30-122">SQL Server 2016 の Community Technology Preview (CTP) バージョンでは、インポート処理中にエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-122">The Community Technology Preview (CTP) versions of SQL Server 2016 might cause errors during the import process.</span></span>
    > [!IMPORTANT] 
    > <span data-ttu-id="ead30-123">サンドボックス環境からデータベースをエクスポートするには、データベースをインポートする環境で同じバージョンの SQL Server Management Studio (SSMS) を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-123">To export a database from a sandbox environment, you must be running the same version of SQL Server Management Studio (SSMS) that is in the environment you will be importing the database to.</span></span> <span data-ttu-id="ead30-124">これにより、サンドボックス環境で Application Object Server (AOS) を実行するVMに [SQL Server Management Studio の最新バージョン](https://msdn.microsoft.com/en-us/library/mt238290.aspx)をインストールする必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-124">This may require you to install the [latest version of SQL Server Management Studio](https://msdn.microsoft.com/en-us/library/mt238290.aspx) on the VM that runs Application Object Server (AOS) in the sandbox environment.</span></span> <span data-ttu-id="ead30-125">AOS コンピューターで、bacpac エクスポートを実行します。</span><span class="sxs-lookup"><span data-stu-id="ead30-125">Do the bacpac export on that AOS computer.</span></span> <span data-ttu-id="ead30-126">この要件は 2 つの理由があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-126">There are two reasons for this requirement:</span></span>

    - <span data-ttu-id="ead30-127">SQL Server のサンドボックス インスタンスに対するインターネット プロトコル (IP) アクセス制限のため、その環境内のコンピュータのみがインスタンスに接続できます。</span><span class="sxs-lookup"><span data-stu-id="ead30-127">Because of an Internet Protocol (IP) access restriction on the sandbox instance of SQL Server, only computers in that environment can connect to the instance.</span></span>
    - <span data-ttu-id="ead30-128">エクスポートされた \*.bacpac ファイルは、Management Studio のバージョン固有の機能に依存する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-128">The exported \*.bacpac file may be dependent on version specific features of Management Studio.</span></span> <span data-ttu-id="ead30-129">データベースをエクスポートするために使用する SSMS バージョンが、bacpac をインポートするために使用する (ターゲット環境での) SSMS バージョン**より新しいものではない**ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ead30-129">Make sure the SSMS version that you use to export the database **is not newer** than the SSMS version (on the target environment) that you will be using to import the bacpac.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ead30-130">準備</span><span class="sxs-lookup"><span data-stu-id="ead30-130">Before you begin</span></span>

<span data-ttu-id="ead30-131">暗号化された環境固有の値を新しい環境にインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ead30-131">Encrypted and environment-specific values can't be imported into a new environment.</span></span> <span data-ttu-id="ead30-132">インポート処理を完了した後は、ターゲット環境内のソース環境から一部のデータを再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-132">After you've completed the import, you must re-enter some data from your source environment in your target environment.</span></span>

### <a name="document-the-values-of-encrypted-fields"></a><span data-ttu-id="ead30-133">暗号化されたフィールドの値を文書化</span><span class="sxs-lookup"><span data-stu-id="ead30-133">Document the values of encrypted fields</span></span>

<span data-ttu-id="ead30-134">データ暗号化に使用される証明書に関連する技術的な制限のため、データベースの暗号化されたフィールドに格納されている値はそのデータベースが新しい環境にインポートされた後は読み取れません。</span><span class="sxs-lookup"><span data-stu-id="ead30-134">Because of a technical limitation that is related to the certificate that is used for data encryption, values that are stored in encrypted fields in a database will be unreadable after that database is imported into a new environment.</span></span> <span data-ttu-id="ead30-135">したがって、インポート後、暗号化されたフィールドに格納されている値を手動で削除して再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-135">Therefore, after an import, you must manually delete and re-enter values that are stored in encrypted fields.</span></span> <span data-ttu-id="ead30-136">インポート後に暗号化されたフィールドに入力される新しい値は読み取り可能になります。</span><span class="sxs-lookup"><span data-stu-id="ead30-136">New values that are entered in encrypted fields after an import will be readable.</span></span> <span data-ttu-id="ead30-137">次のフィールドが影響されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-137">The following fields are affected.</span></span> <span data-ttu-id="ead30-138">フィールド名は Table.Field 形式で指定されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-138">The field names are given in Table.Field format.</span></span>

| <span data-ttu-id="ead30-139">フィールド名</span><span class="sxs-lookup"><span data-stu-id="ead30-139">Field name</span></span>                                               | <span data-ttu-id="ead30-140">値を設定する場所</span><span class="sxs-lookup"><span data-stu-id="ead30-140">Where to set the value</span></span> |
|----------------------------------------------------------|------------------------|
| <span data-ttu-id="ead30-141">CreditCardAccountSetup.SecureMerchantProperties</span><span class="sxs-lookup"><span data-stu-id="ead30-141">CreditCardAccountSetup.SecureMerchantProperties</span></span>          | <span data-ttu-id="ead30-142">**売掛金勘定** &gt; **支払設定** &gt; **支払サービス** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-142">Select **Accounts receivable** &gt; **Payments setup** &gt; **Payment services**.</span></span> |
| <span data-ttu-id="ead30-143">ExchangeRateProviderConfigurationDetails.Value</span><span class="sxs-lookup"><span data-stu-id="ead30-143">ExchangeRateProviderConfigurationDetails.Value</span></span>           | <span data-ttu-id="ead30-144">**総勘定元帳** &gt; **通貨** &gt; **為替レート プロバイダーを構成する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-144">Select **General ledger** &gt; **Currencies** &gt; **Configure exchange rate providers**.</span></span> |
| <span data-ttu-id="ead30-145">FiscalEstablishment\_BR.ConsumerEFDocCsc</span><span class="sxs-lookup"><span data-stu-id="ead30-145">FiscalEstablishment\_BR.ConsumerEFDocCsc</span></span>                 | <span data-ttu-id="ead30-146">**組織管理** &gt; **会計機関** &gt; **会計機関** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ead30-146">Select **Organization administration** &gt; **Fiscal establishments** &gt; **Fiscal establishments**.</span></span> |
| <span data-ttu-id="ead30-147">FiscalEstablishmentStaging.CSC</span><span class="sxs-lookup"><span data-stu-id="ead30-147">FiscalEstablishmentStaging.CSC</span></span>                           | <span data-ttu-id="ead30-148">このフィールドは、データ インポート/エクスポート フレームワーク (DIXF) によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-148">This field is used by the Data Import/Export Framework (DIXF).</span></span> |
| <span data-ttu-id="ead30-149">HcmPersonIdentificationNumber.PersonIdentificationNumber</span><span class="sxs-lookup"><span data-stu-id="ead30-149">HcmPersonIdentificationNumber.PersonIdentificationNumber</span></span> | <span data-ttu-id="ead30-150">**人事管理** &gt; **作業者** &gt; **作業者** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-150">Select **Human resources** &gt; **Workers** &gt; **Workers**.</span></span> <span data-ttu-id="ead30-151">**ワーカー**タブの、**個人情報**グループで、**ID 番号**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-151">On the **Worker** tab, in the **Personal information** group, select **Identification numbers**.</span></span> |
| <span data-ttu-id="ead30-152">HcmWorkerActionHire.PersonIdentificationNumber</span><span class="sxs-lookup"><span data-stu-id="ead30-152">HcmWorkerActionHire.PersonIdentificationNumber</span></span>           | <span data-ttu-id="ead30-153">このフィールドは、Microsoft Dynamics AX 7.0 以降 (2016 年 2 月) に廃止されました。</span><span class="sxs-lookup"><span data-stu-id="ead30-153">This field has been obsolete since Microsoft Dynamics AX 7.0 (February 2016).</span></span> <span data-ttu-id="ead30-154">これは以前、**すべての作業者アクション** フォーム (**人事管理** &gt; **作業者** &gt; **アクション** &gt; **すべての作業者アクション**) でした。</span><span class="sxs-lookup"><span data-stu-id="ead30-154">It was previously in the **All worker actions** form (**Human resources** &gt; **Workers** &gt; **Actions** &gt; **All worker actions**).</span></span> |
| <span data-ttu-id="ead30-155">SysEmailSMPTPassword.Password</span><span class="sxs-lookup"><span data-stu-id="ead30-155">SysEmailSMPTPassword.Password</span></span>                            | <span data-ttu-id="ead30-156">**システム管理** &gt; **電子メール** &gt; **電子メール パラメーター** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-156">Select **System administration** &gt; **Email** &gt; **Email parameters**.</span></span> |
| <span data-ttu-id="ead30-157">SysOAuthUserTokens.EncryptedAccessToken</span><span class="sxs-lookup"><span data-stu-id="ead30-157">SysOAuthUserTokens.EncryptedAccessToken</span></span>                  | <span data-ttu-id="ead30-158">このフィールドは、AOS で内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-158">This field is used internally by AOS.</span></span> <span data-ttu-id="ead30-159">これは無視できます。</span><span class="sxs-lookup"><span data-stu-id="ead30-159">It can be ignored.</span></span> |
| <span data-ttu-id="ead30-160">SysOAuthUserTokens.EncryptedRefreshToken</span><span class="sxs-lookup"><span data-stu-id="ead30-160">SysOAuthUserTokens.EncryptedRefreshToken</span></span>                 | <span data-ttu-id="ead30-161">このフィールドは、AOS で内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-161">This field is used internally by AOS.</span></span> <span data-ttu-id="ead30-162">これは無視できます。</span><span class="sxs-lookup"><span data-stu-id="ead30-162">It can be ignored.</span></span> |

### <a name="if-youre-running-retail-components-document-encrypted-and-environment-specific-values"></a><span data-ttu-id="ead30-163">小売コンポーネントを実行している場合は、暗号化された、環境固有の値を文書化します。</span><span class="sxs-lookup"><span data-stu-id="ead30-163">If you're running Retail components, document encrypted and environment-specific values</span></span>

<span data-ttu-id="ead30-164">次のページの値は、環境固有またはデータベースで暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="ead30-164">The values on the following pages are either environment-specific or encrypted in the database.</span></span> <span data-ttu-id="ead30-165">したがって、インポートされた値はすべて正しくありません。</span><span class="sxs-lookup"><span data-stu-id="ead30-165">Therefore, all the imported values will be incorrect.</span></span>

- <span data-ttu-id="ead30-166">支払サービス (**売掛金勘定** &gt; **支払設定** &gt; **支払サービス**) に移動します。</span><span class="sxs-lookup"><span data-stu-id="ead30-166">Payments services (**Accounts receivable** &gt; **Payments setup** &gt; **Payments services**)</span></span>
- <span data-ttu-id="ead30-167">ハードウェア プロファイル (**小売りとコマース** &gt; **チャネル設定** &gt; **POS 設定** &gt; **POS プロファイル** &gt; **ハードウェア プロファイル**)</span><span class="sxs-lookup"><span data-stu-id="ead30-167">Hardware profiles (**Retail and commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profiles** &gt; **Hardware profiles**)</span></span>

## <a name="create-a-copy-of-the-source-database"></a><span data-ttu-id="ead30-168">ソース データベースのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ead30-168">Create a copy of the source database</span></span>

<span data-ttu-id="ead30-169">ソース Azure SQL データベースをエクスポートする前に、変更追跡をオフにしてデータベース ユーザーを削除する必要があるため、そのデータベースのコピーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="ead30-169">Because you must turn off change tracking and delete database users before you can export the source Azure SQL database, you should create a copy of that database.</span></span> <span data-ttu-id="ead30-170">元のデータベースから情報を削除する代わりに、コピーで作業することができます。</span><span class="sxs-lookup"><span data-stu-id="ead30-170">You can then work with the copy instead of deleting information from the original database.</span></span> <span data-ttu-id="ead30-171">次の SQL ステートメントは、axdb\_mySourceDatabaseToCopy データベースのコピーを作成し、**MyNewCopy** という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="ead30-171">The following SQL statement creates a copy of the axdb\_mySourceDatabaseToCopy database and names it **MyNewCopy**.</span></span> <span data-ttu-id="ead30-172">データベースの名前を使用するように、このスクリプトを編集します。</span><span class="sxs-lookup"><span data-stu-id="ead30-172">Edit this script so that it uses the names of your databases.</span></span>

```
CREATE DATABASE MyNewCopy AS COPY OF axdb_mySourceDatabaseToCopy
```

<span data-ttu-id="ead30-173">この SQL ステートメントは、非同期で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-173">This SQL statement runs asynchronously.</span></span> <span data-ttu-id="ead30-174">つまり、1 分後に完了するように見えますが、実際はバックグラウンドで実行しています。</span><span class="sxs-lookup"><span data-stu-id="ead30-174">In other words, although it appears to be completed after one minute, it actually continues to run in the background.</span></span> <span data-ttu-id="ead30-175">詳細については、[データベースの作成 (Azure SQL データベース)](https://msdn.microsoft.com/en-us/library/dn268335.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ead30-175">For more information, see [CREATE DATABASE (Azure SQL Database)](https://msdn.microsoft.com/en-us/library/dn268335.aspx).</span></span> <span data-ttu-id="ead30-176">コピー操作の進行状況を監視するには、同じインスタンス内の MASTER データベースに対して次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="ead30-176">To monitor the progress of the copy operation, run the following query against the MASTER database in the same instance.</span></span>

```
SELECT * FROM sys.dm_database_copies
```

> [!WARNING] 
> <span data-ttu-id="ead30-177">どの Finance and Operations 環境でも、長期間にわたってデータベースのコピーを保持することはできません。</span><span class="sxs-lookup"><span data-stu-id="ead30-177">Retaining copies of the database for an extended period is not allowed in any Finance and Operations environment.</span></span> <span data-ttu-id="ead30-178">Microsoft は、事前に通知することなく、7 日を超える古いデータベースのコピーを削除する権限を保有します。</span><span class="sxs-lookup"><span data-stu-id="ead30-178">Microsoft reserves the right to delete any copies of the database older than 7 days without any prior notice.</span></span> 

## <a name="prepare-the-database"></a><span data-ttu-id="ead30-179">データベースの準備</span><span class="sxs-lookup"><span data-stu-id="ead30-179">Prepare the database</span></span>

<span data-ttu-id="ead30-180">データベースのコピーに対して次のスクリプトを実行して変更追跡を停止し、SQL データベース ユーザーとシステム ビューを削除します。</span><span class="sxs-lookup"><span data-stu-id="ead30-180">Run the following script against the copy of the database to turn off change tracking, and to remove SQL Database users and a system view.</span></span> <span data-ttu-id="ead30-181">また、スクリプトはシステムフラグを修正し、以前の環境への参照を削除し、バッチを保留し、電子メールの設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="ead30-181">The script also corrects system flags, removes references to the previous environment, withholds batches, and removes email configuration.</span></span> <span data-ttu-id="ead30-182">これらの変更はデータベースのエクスポートとインポートが正常に行われるために必要です。</span><span class="sxs-lookup"><span data-stu-id="ead30-182">All these changes are required for a successful export and import of the database.</span></span> <span data-ttu-id="ead30-183">これらの変更では、起動すると、AOS コンピューターが対象となる環境で開始されると、何も自動的に実行を保証できます。</span><span class="sxs-lookup"><span data-stu-id="ead30-183">These changes also help guarantee that, when the AOS computer is started in the target environment, nothing automatically starts to run.</span></span>

> [!NOTE]
> <span data-ttu-id="ead30-184">データベースのコピーの名前を使用できるように、次の **データベースの変更** コマンドを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-184">You must edit the following **ALTER DATABASE** command so that it uses the name of your database copy.</span></span>

```
--Prepare a database in Azure SQL Database for export to SQL Server.
--Disable change tracking on tables where it is enabled.
declare
@SQL varchar(1000)
set quoted_identifier off
declare changeTrackingCursor CURSOR for
select 'ALTER TABLE ' + t.name + ' DISABLE CHANGE_TRACKING'
from sys.change_tracking_tables c, sys.tables t
where t.object_id = c.object_id
OPEN changeTrackingCursor
FETCH changeTrackingCursor into @SQL
WHILE @@Fetch_Status = 0
BEGIN
exec(@SQL)
FETCH changeTrackingCursor into @SQL
END
CLOSE changeTrackingCursor
DEALLOCATE changeTrackingCursor

--Disable change tracking on the database itself.
ALTER DATABASE
-- SET THE NAME OF YOUR DATABASE BELOW
MyNewCopy
set CHANGE_TRACKING = OFF
--Remove the database level users from the database
--these will be recreated after importing in SQL Server.
declare
@userSQL varchar(1000)
set quoted_identifier off
declare userCursor CURSOR for
select 'DROP USER ' + name
from sys.sysusers
where issqlrole = 0 and hasdbaccess = 1 and name <> 'dbo'
OPEN userCursor
FETCH userCursor into @userSQL
WHILE @@Fetch_Status = 0
BEGIN
exec(@userSQL)
FETCH userCursor into @userSQL
END
CLOSE userCursor
DEALLOCATE userCursor
--Delete the SYSSQLRESOURCESTATSVIEW view as it has an Azure-specific definition in it.
--We will run db synch later to recreate the correct view for SQL Server.
if(1=(select 1 from sys.views where name = 'SYSSQLRESOURCESTATSVIEW'))
DROP VIEW SYSSQLRESOURCESTATSVIEW
--Next, set system parameters ready for being a SQL Server Database.
update sysglobalconfiguration
set value = 'SQLSERVER'
where name = 'BACKENDDB'
update sysglobalconfiguration
set value = 0
where name = 'TEMPTABLEINAXDB'
--Clean up the batch server configuration, server sessions, and printers from the previous environment.
TRUNCATE TABLE SYSSERVERCONFIG
TRUNCATE TABLE SYSSERVERSESSIONS
TRUNCATE TABLE SYSCORPNETPRINTERS
--Remove records which could lead to accidentally sending an email externally.
UPDATE SysEmailParameters
SET SMTPRELAYSERVERNAME = ''
GO
UPDATE LogisticsElectronicAddress
SET LOCATOR = ''
WHERE Locator LIKE '%@%'
GO
TRUNCATE TABLE PrintMgmtSettings
TRUNCATE TABLE PrintMgmtDocInstance
--Set any waiting, executing, ready, or canceling batches to withhold.
UPDATE BatchJob
SET STATUS = 0
WHERE STATUS IN (1,2,5,7)
GO
```

## <a name="export-the-database"></a><span data-ttu-id="ead30-185">データベースをエキスポート</span><span class="sxs-lookup"><span data-stu-id="ead30-185">Export the database</span></span>

<span data-ttu-id="ead30-186">**コマンド プロンプト** ウィンドウを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ead30-186">Open a **Command Prompt** window and run the following commands.</span></span>

```
cd C:\Program Files (x86)\Microsoft SQL Server\140\DAC\bin

SqlPackage.exe /a:export /ssn:<server>.database.windows.net /sdn:<database to export> /tf:D:\Exportedbacpac\my.bacpac /p:CommandTimeout=1200 /p:VerifyFullTextDocumentTypesSupported=false /sp:<SQL password> /su:<sql user>
```

<span data-ttu-id="ead30-187">パラメータの説明を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="ead30-187">Here is an explanation of the parameters:</span></span>

- <span data-ttu-id="ead30-188">**ssn(ソース サーバー名)** – エクスポートする Azure SQL データベース サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="ead30-188">**ssn (source server name)** – The name of the Azure SQL Database server to export from.</span></span>
- <span data-ttu-id="ead30-189">**sdn(ソース データベース名)** – エクスポートするデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="ead30-189">**sdn (source database name)** – The name of the database to export.</span></span>
- <span data-ttu-id="ead30-190">**tf(ターゲット ファイル)** – エクスポートするファイルのパスと名前。</span><span class="sxs-lookup"><span data-stu-id="ead30-190">**tf (target file)** – The path and name of the file to export to.</span></span>
- <span data-ttu-id="ead30-191">**sp(ソース パスワード)** – ソース SQL Server の SQL パスワード。</span><span class="sxs-lookup"><span data-stu-id="ead30-191">**sp (source password)** – The SQL password for the source SQL Server.</span></span>
- <span data-ttu-id="ead30-192">**su(ソース ユーザー)** – ソース SQL Server の SQL ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="ead30-192">**su (source user)** – The SQL user name for the source SQL Server.</span></span> <span data-ttu-id="ead30-193">**sqladmin** ユーザーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ead30-193">We recommend that you use the **sqladmin** user.</span></span> <span data-ttu-id="ead30-194">このユーザーは、展開中に Finance and Operations のすべての SQLインスタンスで作成されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-194">This user is created on every Finance and Operations SQL instance during deployment.</span></span> <span data-ttu-id="ead30-195">このユーザーのパスワードは、Microsoft Dynamics Lifecycle Services (LCS) 内のプロジェクトから取得することができます。</span><span class="sxs-lookup"><span data-stu-id="ead30-195">You can retrieve the password for this user from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="ead30-196">エクスポートが完了すると、次のコマンドを実行してデータベース コピーを削除します。</span><span class="sxs-lookup"><span data-stu-id="ead30-196">After the export is completed, run the following command to delete the database copy.</span></span>

```
DROP DATABASE [MyNewCopy]
```

## <a name="import-the-database"></a><span data-ttu-id="ead30-197">データベースのインポート</span><span class="sxs-lookup"><span data-stu-id="ead30-197">Import the database</span></span>

<span data-ttu-id="ead30-198">データベースをインポートするときは、これらのガイドラインに従うことお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ead30-198">When you import the database, we recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="ead30-199">必要な場合は、後で戻すことができるように、既存の AxDB データベースのコピーを保持します。</span><span class="sxs-lookup"><span data-stu-id="ead30-199">Retain a copy of the existing AxDB database, so that you can revert to it later if you must.</span></span>
- <span data-ttu-id="ead30-200">**AxDB\_fromProd** などの新しい名前の下に新しいデータベースをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ead30-200">Import the new database under a new name, such as **AxDB\_fromProd**.</span></span>

<span data-ttu-id="ead30-201">最高のパフォーマンスを保証するには、\*.bacpac ファイルをインポート元のローカル コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ead30-201">To help guarantee the best performance, copy the \*.bacpac file to the local computer that you're importing from.</span></span> <span data-ttu-id="ead30-202">**コマンド プロンプト** ウィンドウを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ead30-202">Open a **Command Prompt** window and run the following commands.</span></span>

```
cd C:\Program Files (x86)\Microsoft SQL Server\140\DAC\bin

SqlPackage.exe /a:import /sf:D:\Exportedbacpac\my.bacpac /tsn:localhost /tdn:<target database name> /p:CommandTimeout=1200
```

<span data-ttu-id="ead30-203">パラメータの説明を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="ead30-203">Here is an explanation of the parameters:</span></span>

- <span data-ttu-id="ead30-204">**tsn(ターゲット サーバー名)** – インポートする SQL Server の名前。</span><span class="sxs-lookup"><span data-stu-id="ead30-204">**tsn (target server name)** – The name of the SQL Server to import into.</span></span>
- <span data-ttu-id="ead30-205">**tdn(ターゲット データベース名)** – インポートするデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="ead30-205">**tdn (target database name)** – The name of the database to import into.</span></span> <span data-ttu-id="ead30-206">データベースが既に存在していては**いけません**。</span><span class="sxs-lookup"><span data-stu-id="ead30-206">The database should **not** already exist.</span></span>
- <span data-ttu-id="ead30-207">**sf(ソース ファイル)** – インポートするファイルのパスと名前。</span><span class="sxs-lookup"><span data-stu-id="ead30-207">**sf (source file)** – The path and name of the file to import from.</span></span>

> [!NOTE]
> <span data-ttu-id="ead30-208">インポート中に、ユーザー名およびパスワードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ead30-208">During import, the user name and password aren't required.</span></span> <span data-ttu-id="ead30-209">既定では、SQL Server は現在サインインしているユーザーに対して Microsoft Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="ead30-209">By default, SQL Server uses Microsoft Windows authentication for the user who is currently signed in.</span></span>

## <a name="update-the-database"></a><span data-ttu-id="ead30-210">データベースの更新</span><span class="sxs-lookup"><span data-stu-id="ead30-210">Update the database</span></span>

<span data-ttu-id="ead30-211">インポートされたデータベースに対して、次の SQL スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ead30-211">Run the following SQL script against the imported database.</span></span> <span data-ttu-id="ead30-212">このスクリプトは、ソース データベースから削除したユーザーを追加し、この SQL インスタンスの SQL のログインに正しくリンクします。</span><span class="sxs-lookup"><span data-stu-id="ead30-212">This script adds back the users that you deleted from the source database and correctly links them to the SQL logins for this SQL instance.</span></span> <span data-ttu-id="ead30-213">スクリプトはまた、変更の追跡を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="ead30-213">The script also turns change tracking back on.</span></span> <span data-ttu-id="ead30-214">必ず、データベースの名前を使用できるように、最後の **ALTER DATABASE** ステートメントを編集してください。</span><span class="sxs-lookup"><span data-stu-id="ead30-214">Remember to edit the final **ALTER DATABASE** statement so that it uses the name of your database.</span></span>

```
CREATE USER axdeployuser FROM LOGIN axdeployuser
EXEC sp_addrolemember 'db_owner', 'axdeployuser'

CREATE USER axdbadmin FROM LOGIN axdbadmin
EXEC sp_addrolemember 'db_owner', 'axdbadmin'

CREATE USER axmrruntimeuser FROM LOGIN axmrruntimeuser
EXEC sp_addrolemember 'db_datareader', 'axmrruntimeuser'
EXEC sp_addrolemember 'db_datawriter', 'axmrruntimeuser'

CREATE USER axretaildatasyncuser FROM LOGIN axretaildatasyncuser
EXEC sp_addrolemember 'DataSyncUsersRole', 'axretaildatasyncuser'

CREATE USER axretailruntimeuser FROM LOGIN axretailruntimeuser
EXEC sp_addrolemember 'UsersRole', 'axretailruntimeuser'
EXEC sp_addrolemember 'ReportUsersRole', 'axretailruntimeuser'

CREATE USER axdeployextuser WITH PASSWORD = '<password from LCS>'
EXEC sp_addrolemember 'DeployExtensibilityRole', 'axdeployextuser'

CREATE USER [NT AUTHORITY\NETWORK SERVICE] FROM LOGIN [NT AUTHORITY\NETWORK SERVICE]
EXEC sp_addrolemember 'db_owner', 'NT AUTHORITY\NETWORK SERVICE'

UPDATE T1
SET T1.storageproviderid = 0
    , T1.accessinformation = ''
    , T1.modifiedby = 'Admin'
    , T1.modifieddatetime = getdate()
FROM docuvalue T1
WHERE T1.storageproviderid = 1 --Azure storage

ALTER DATABASE [<your AX database name>] SET CHANGE_TRACKING = ON (CHANGE_RETENTION = 6 DAYS, AUTO_CLEANUP = ON)
GO
-- Begin Refresh Retail FullText Catalogs
DECLARE @RFTXNAME NVARCHAR(MAX);
DECLARE @RFTXSQL NVARCHAR(MAX);
DECLARE retail_ftx CURSOR FOR
SELECT OBJECT_SCHEMA_NAME(object_id) + '.' + OBJECT_NAME(object_id) fullname FROM SYS.FULLTEXT_INDEXES
    WHERE FULLTEXT_CATALOG_ID = (SELECT TOP 1 FULLTEXT_CATALOG_ID FROM SYS.FULLTEXT_CATALOGS WHERE NAME = 'COMMERCEFULLTEXTCATALOG');
OPEN retail_ftx;
FETCH NEXT FROM retail_ftx INTO @RFTXNAME;

BEGIN TRY
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        PRINT 'Refreshing Full Text Index ' + @RFTXNAME;
        EXEC SP_FULLTEXT_TABLE @RFTXNAME, 'activate';
        SET @RFTXSQL = 'ALTER FULLTEXT INDEX ON ' + @RFTXNAME + ' START FULL POPULATION';
        EXEC SP_EXECUTESQL @RFTXSQL;
        FETCH NEXT FROM retail_ftx INTO @RFTXNAME;
    END
END TRY
BEGIN CATCH
    PRINT error_message()
END CATCH

CLOSE retail_ftx;  
DEALLOCATE retail_ftx; 
-- End Refresh Retail FullText Catalogs
```

### <a name="re-provision-the-target-environment"></a><span data-ttu-id="ead30-215">対象の環境を再プロビジョニング</span><span class="sxs-lookup"><span data-stu-id="ead30-215">Re-provision the target environment</span></span>

[!include [environment-reprovision](../includes/environment-reprovision.md)]

### <a name="reset-the-financial-reporting-database"></a><span data-ttu-id="ead30-216">財務報告データベースのリセット</span><span class="sxs-lookup"><span data-stu-id="ead30-216">Reset the Financial Reporting database</span></span>

<span data-ttu-id="ead30-217">Management Reporter という以前の名前を持った財務報告を使用する場合は、[データベースを復元した後の財務報告のデータ マートのリセット](../analytics/reset-financial-reporting-datamart-after-restore.md)の手順に従って、財務報告データベースをリセットする必要があります</span><span class="sxs-lookup"><span data-stu-id="ead30-217">If you're using Financial Reporting, which was previously named Management Reporter, you must reset the Financial Reporting database by following the steps in [Resetting the financial reporting data mart after restoring a database](../analytics/reset-financial-reporting-datamart-after-restore.md).</span></span>

## <a name="start-to-use-the-new-database"></a><span data-ttu-id="ead30-218">新しいデータベースの使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="ead30-218">Start to use the new database</span></span>

<span data-ttu-id="ead30-219">環境を切り替えて新しいデータベースを使用するには、最初に次のサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="ead30-219">To switch the environment and use the new database, first stop the following services:</span></span>

- <span data-ttu-id="ead30-220">World Wide Web 公開サービス</span><span class="sxs-lookup"><span data-stu-id="ead30-220">World wide web publishing service</span></span>
- <span data-ttu-id="ead30-221">Finance and Operations バッチ管理サービス</span><span class="sxs-lookup"><span data-stu-id="ead30-221">Finance and Operations Batch Management service</span></span>
- <span data-ttu-id="ead30-222">Management Reporter 2012 処理サービス</span><span class="sxs-lookup"><span data-stu-id="ead30-222">Management Reporter 2012 Process service</span></span>

<span data-ttu-id="ead30-223">サービスが停止した後、AxDB データベース **AxDB\_orig** の名前を変更し、新しくインポートしたデータベース **AxDB** の名前を変更し、そして 3 つのサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ead30-223">After the services have been stopped, rename the AxDB database **AxDB\_orig**, rename your newly imported database **AxDB**, and then restart the three services.</span></span>

<span data-ttu-id="ead30-224">元のデータベースに戻すには、このプロセスを逆にします。</span><span class="sxs-lookup"><span data-stu-id="ead30-224">To switch back to the original database, reverse this process.</span></span> <span data-ttu-id="ead30-225">つまり、サービスを停止し、データベースの名前を変更してから、サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ead30-225">In other words, stop the services, rename the databases, and then restart the services.</span></span>

## <a name="re-enter-data-from-encrypted-and-environment-specific-fields-in-the-target-database"></a><span data-ttu-id="ead30-226">ターゲット データベースの暗号化された環境固有のフィールドからデータを再入力</span><span class="sxs-lookup"><span data-stu-id="ead30-226">Re-enter data from encrypted and environment-specific fields in the target database</span></span>

<span data-ttu-id="ead30-227">Finance and Operations クライアントでは、暗号化された環境固有のフィールドに記録した値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ead30-227">In the Finance and Operations client, enter the values that you documented for the encrypted and environment-specific fields.</span></span> <span data-ttu-id="ead30-228">次のフィールドが影響されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-228">The following fields are affected.</span></span> <span data-ttu-id="ead30-229">フィールド名は Table.Field 形式で指定されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-229">The field names are given in Table.Field format.</span></span>

| <span data-ttu-id="ead30-230">フィールド名</span><span class="sxs-lookup"><span data-stu-id="ead30-230">Field name</span></span>                                               | <span data-ttu-id="ead30-231">値を設定する場所</span><span class="sxs-lookup"><span data-stu-id="ead30-231">Where to set the value</span></span> |
|----------------------------------------------------------|------------------------|
| <span data-ttu-id="ead30-232">CreditCardAccountSetup.SecureMerchantProperties</span><span class="sxs-lookup"><span data-stu-id="ead30-232">CreditCardAccountSetup.SecureMerchantProperties</span></span>          | <span data-ttu-id="ead30-233">**売掛金勘定** &gt; **支払設定** &gt; **支払サービス** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-233">Select **Accounts receivable** &gt; **Payments setup** &gt; **Payment services**.</span></span> |
| <span data-ttu-id="ead30-234">ExchangeRateProviderConfigurationDetails.Value</span><span class="sxs-lookup"><span data-stu-id="ead30-234">ExchangeRateProviderConfigurationDetails.Value</span></span>           | <span data-ttu-id="ead30-235">**総勘定元帳** &gt; **通貨** &gt; **為替レート プロバイダーを構成する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-235">Select **General ledger** &gt; **Currencies** &gt; **Configure exchange rate providers**.</span></span> |
| <span data-ttu-id="ead30-236">FiscalEstablishment\_BR.ConsumerEFDocCsc</span><span class="sxs-lookup"><span data-stu-id="ead30-236">FiscalEstablishment\_BR.ConsumerEFDocCsc</span></span>                 | <span data-ttu-id="ead30-237">**組織管理** &gt; **会計機関** &gt; **会計機関** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ead30-237">Select **Organization administration** &gt; **Fiscal establishments** &gt; **Fiscal establishments**.</span></span> |
| <span data-ttu-id="ead30-238">FiscalEstablishmentStaging.CSC</span><span class="sxs-lookup"><span data-stu-id="ead30-238">FiscalEstablishmentStaging.CSC</span></span>                           | <span data-ttu-id="ead30-239">このフィールドは DIXF で使用されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-239">This field is used by DIXF.</span></span> |
| <span data-ttu-id="ead30-240">HcmPersonIdentificationNumber.PersonIdentificationNumber</span><span class="sxs-lookup"><span data-stu-id="ead30-240">HcmPersonIdentificationNumber.PersonIdentificationNumber</span></span> | <span data-ttu-id="ead30-241">**人事管理** &gt; **作業者** &gt; **作業者** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-241">Select **Human resources** &gt; **Workers** &gt; **Workers**.</span></span> <span data-ttu-id="ead30-242">**ワーカー**タブの、**個人情報**グループで、**ID 番号**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-242">On the **Worker** tab, in the **Personal information** group, select **Identification numbers**.</span></span> |
| <span data-ttu-id="ead30-243">HcmWorkerActionHire.PersonIdentificationNumber</span><span class="sxs-lookup"><span data-stu-id="ead30-243">HcmWorkerActionHire.PersonIdentificationNumber</span></span>           | <span data-ttu-id="ead30-244">このフィールドは、AX 7.0 以降 (2016 年 2 月) に廃止されました。</span><span class="sxs-lookup"><span data-stu-id="ead30-244">This field has been obsolete since AX 7.0 (February 2016).</span></span> <span data-ttu-id="ead30-245">これは以前、**すべての作業者アクション** フォーム (**人事管理** &gt; **作業者** &gt; **アクション** &gt; **すべての作業者アクション**) でした。</span><span class="sxs-lookup"><span data-stu-id="ead30-245">It was previously in the **All worker actions** form (**Human resources** &gt; **Workers** &gt; **Actions** &gt; **All worker actions**).</span></span> |
| <span data-ttu-id="ead30-246">SysEmailSMPTPassword.Password</span><span class="sxs-lookup"><span data-stu-id="ead30-246">SysEmailSMPTPassword.Password</span></span>                            | <span data-ttu-id="ead30-247">**システム管理** &gt; **電子メール** &gt; **電子メール パラメーター** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-247">Select **System administration** &gt; **Email** &gt; **Email parameters**.</span></span> |
| <span data-ttu-id="ead30-248">SysOAuthUserTokens.EncryptedAccessToken</span><span class="sxs-lookup"><span data-stu-id="ead30-248">SysOAuthUserTokens.EncryptedAccessToken</span></span>                  | <span data-ttu-id="ead30-249">このフィールドは、AOS で内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-249">This field is used internally by AOS.</span></span> <span data-ttu-id="ead30-250">これは無視できます。</span><span class="sxs-lookup"><span data-stu-id="ead30-250">It can be ignored.</span></span> |
| <span data-ttu-id="ead30-251">SysOAuthUserTokens.EncryptedRefreshToken</span><span class="sxs-lookup"><span data-stu-id="ead30-251">SysOAuthUserTokens.EncryptedRefreshToken</span></span>                 | <span data-ttu-id="ead30-252">このフィールドは、AOS で内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-252">This field is used internally by AOS.</span></span> <span data-ttu-id="ead30-253">これは無視できます。</span><span class="sxs-lookup"><span data-stu-id="ead30-253">It can be ignored.</span></span> |

## <a name="known-issues"></a><span data-ttu-id="ead30-254">既知の問題</span><span class="sxs-lookup"><span data-stu-id="ead30-254">Known issues</span></span>

### <a name="i-cant-drop-users-in-source-database"></a><span data-ttu-id="ead30-255">ソース データベースにユーザーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="ead30-255">I can't drop users in source database</span></span>

<span data-ttu-id="ead30-256">ソース データベース内のユーザーを削除するとき、axdbadmin または axdeployuser ユーザーが削除されないことがあります。それは、そのユーザーがフルテキスト カタログの現在の所有者であるためです。</span><span class="sxs-lookup"><span data-stu-id="ead30-256">When you drop users in the source database, the axdbadmin or axdeployuser user might not be deleted, because that user is the current owner of the full-text catalog.</span></span> <span data-ttu-id="ead30-257">この問題は、データベースが元々 Dynamics AX 7 (Finance and Operations) の CTP7 または CTP8 用に作成された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="ead30-257">This issue occurs if the database was originally created for CTP7 or CTP8 of Dynamics AX 7 (Finance and Operations).</span></span> <span data-ttu-id="ead30-258">この問題を解決するには、次の Transact-SQL (T-SQL) コマンドを実行して、所有者を **dbo** ユーザーに変更します。</span><span class="sxs-lookup"><span data-stu-id="ead30-258">To resolve the issue, run the following Transact-SQL (T-SQL) command to change the owner to the **dbo** user.</span></span>

```
ALTER AUTHORIZATION ON Fulltext Catalog:: TO [dbo]; 
```

<span data-ttu-id="ead30-259">コマンドの詳細については、[代替認証](https://msdn.microsoft.com/en-us/library/ms187359.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ead30-259">For more information about this command, see [ALTER AUTHORIZATION](https://msdn.microsoft.com/en-us/library/ms187359.aspx).</span></span>

### <a name="i-cant-download-management-studio-installation-files"></a><span data-ttu-id="ead30-260">Management Studio インストール ファイルをダウンロードできません</span><span class="sxs-lookup"><span data-stu-id="ead30-260">I can't download Management Studio installation files</span></span>

<span data-ttu-id="ead30-261">Management Studio インストーラーをダウンロードしようとすると、次のエラー メッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-261">When you try to download the Management Studio installer, you might receive the following error message:</span></span>

> <span data-ttu-id="ead30-262">現在のセキュリティ設定では、このファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ead30-262">Your current security settings do not allow this file to be downloaded.</span></span>

<span data-ttu-id="ead30-263">この問題を回避するには、次の手順を実行してファイルのダウンロードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ead30-263">To work around this issue, follow these steps to enable file downloads.</span></span>

1. <span data-ttu-id="ead30-264">Web ブラウザーで**インターネット オプション**を開きます。</span><span class="sxs-lookup"><span data-stu-id="ead30-264">In your web browser, open **Internet options**.</span></span>
2. <span data-ttu-id="ead30-265">**セキュリティ**タブで、**インターネット**ゾーンを選択し、**レベルのカスタマイズ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-265">On the **Security** tab, select the **Internet** zone, and then select **Custom level**.</span></span>
3. <span data-ttu-id="ead30-266">**ダウンロード** までスクロールし、**ファイルのダウンロード** で **有効にする** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ead30-266">Scroll to **Downloads**, and then, under **File download**, select the **Enable** option.</span></span>

### <a name="database-synchronization-fails"></a><span data-ttu-id="ead30-267">データベース同期の失敗</span><span class="sxs-lookup"><span data-stu-id="ead30-267">Database synchronization fails</span></span>

<span data-ttu-id="ead30-268">データベースを Microsoft Visual Studio から新しくインポートされたデータベースと同期させると、その同期は失敗することがあり、次のエラー メッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-268">When you synchronize the database against the newly imported database from Microsoft Visual Studio, the synchronization might fail, and you might receive the following error message:</span></span>

> <span data-ttu-id="ead30-269">コード 1 で終了した SQL connection syncengine.exe のオープンに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="ead30-269">Failed to open SQL connection syncengine.exe exited with code -1.</span></span>

<span data-ttu-id="ead30-270">この場合、次のメッセージも Windows アプリケーション ログのイベント ID 140 で記録されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-270">In this case, the following message is also logged under event ID 140 in the Windows application log:</span></span>

> <span data-ttu-id="ead30-271">オブジェクト サーバー データベース シンクロナイザー: データベースに格納されている内部システム テーブル バージョン番号が、カーネル (141/138) でサポートされているバージョンよりも大きくなっています。</span><span class="sxs-lookup"><span data-stu-id="ead30-271">Object Server Database Synchronizer: The internal system table version number stored in the database is higher than the version supported by the kernel (141/138).</span></span> <span data-ttu-id="ead30-272">新しい Microsoft Dynamics カーネルを使用するか、-REPAIR コマンドライン パラメーターを使用して Microsoft Dynamics を起動し、同期を強制します。</span><span class="sxs-lookup"><span data-stu-id="ead30-272">Use a newer Microsoft Dynamics kernel, or start Microsoft Dynamics using the -REPAIR command line parameter to enforce synchronization.</span></span>

<span data-ttu-id="ead30-273">この問題は、現在の環境のプラットフォーム ビルド番号がソース環境のプラットフォーム ビルド番号よりも低い場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ead30-273">This issue can occur when the platform build number of the current environment is lower than the platform build number of the source environment.</span></span> <span data-ttu-id="ead30-274">状況に応じて、LCS **環境**ページの**更新**タイルを使用して、現在の環境のプラットフォームをソース環境のプラットフォームと一致するようにアップグレードするか、次のクエリを実行してデータベースの必要なバージョンを調整します。</span><span class="sxs-lookup"><span data-stu-id="ead30-274">Depending on your circumstances, either use the **Updates** tiles on the LCS **Environment** page to upgrade the platform in the current environment so that it matches the platform in the source environment, or run the following query to adjust the expected version in the database.</span></span>

```
UPDATE SQLSYSTEMVARIABLES

SET VALUE = 138

WHERE PARM = 'SYSTABVERSION'
```

> [!NOTE]
> <span data-ttu-id="ead30-275">前のクエリの値 **138** は、この特定の環境でバージョン 138 が予想されるイベント ログ メッセージから取得されます。</span><span class="sxs-lookup"><span data-stu-id="ead30-275">The value **138** in the preceding query is taken from the event log message, where version 138 was expected in this particular environment.</span></span>

### <a name="performance"></a><span data-ttu-id="ead30-276">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="ead30-276">Performance</span></span>

<span data-ttu-id="ead30-277">次のガイドラインは、最適なパフォーマンスを達成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ead30-277">The following guidelines can help you achieve optimal performance:</span></span>

- <span data-ttu-id="ead30-278">常に Azure SQL データベースと同じ Azure データ センター内にある仮想マシン (VM) からデータベースをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ead30-278">Always export a database from a virtual machine (VM) that is in the same Azure datacenter as the Azure SQL database.</span></span> <span data-ttu-id="ead30-279">サンドボックス データベースのコピーをエクスポートする場合は、サンド ボックス AOS コンピューターからエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ead30-279">If you're exporting a copy of your sandbox database, export it from the sandbox AOS computer.</span></span>
- <span data-ttu-id="ead30-280">常に .bacpac ファイルを SQL Server インスタンスを実行するコンピューターにローカルでインポートします。</span><span class="sxs-lookup"><span data-stu-id="ead30-280">Always import the .bacpac file locally on the computer that runs the SQL Server instance.</span></span> <span data-ttu-id="ead30-281">リモート マシンで Management Studio からインポートしないでください。</span><span class="sxs-lookup"><span data-stu-id="ead30-281">Don't import it from Management Studio on a remote machine.</span></span>
- <span data-ttu-id="ead30-282">Azure でホストされている Finance and Operations 1 ボックス環境では、インポートするときに D ドライブに .bacpac ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="ead30-282">In a Finance and Operations one-box environment that is hosted in Azure, put the .bacpac file on drive D when you import it.</span></span> <span data-ttu-id="ead30-283">(ワンボックス環境はレベル 1 環境とも呼ばれます。) Azure Vm 上でのテンポラリー ドライブに関する詳細については、[Windows Azure 仮想マシンのテンポラリー ドライブを理解する](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/) ブログ投稿を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ead30-283">(A one-box environment is also known as a Tier 1 environment.) For more information about the temporary drive on Azure VMs, see the [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/) blog post.</span></span>
- <span data-ttu-id="ead30-284">SQL Server Windows サービス [インスタンス ファイルの初期化](https://msdn.microsoft.com/en-us/library/ms175935.aspx) を実行するアカウントに権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="ead30-284">Grant the account that runs the SQL Server Windows service [Instance File Initialization](https://msdn.microsoft.com/en-us/library/ms175935.aspx) rights.</span></span> <span data-ttu-id="ead30-285">この方法で、インポート処理の速度および \*.bak ファイルからの復元の速度を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="ead30-285">In this way, you can help improve the speed of the import process and the speed of a restore from a \*.bak file.</span></span> <span data-ttu-id="ead30-286">開発者環境では、axlocaladmin アカウントとして実行する SQL Server を設定することにより、SQL Server サービスを実行するアカウントがこれらの権限を持っていることを簡単に確認することができます。</span><span class="sxs-lookup"><span data-stu-id="ead30-286">For a developer environment, you can easily make sure that the account that runs the SQL Server service has these rights by setting SQL Server to run as the axlocaladmin account.</span></span>
- <span data-ttu-id="ead30-287">大きなデータベースのメモリ制限が存在する場合があるので、Azure SQLデータベースから、**Management Studio でデータ層アプリケーションのエクスポート**を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="ead30-287">From Azure SQL Database, don't select **Export data tier application in Management Studio**, because there can be a memory limitation for larger databases.</span></span>
