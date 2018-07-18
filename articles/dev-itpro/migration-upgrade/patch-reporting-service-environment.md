---
title: "1 ボックス環境の SQL Server Reporting Services への修正プログラムの適用"
description: "SSRS 修正プログラムをワンボックス開発環境に適用します。"
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 23661
ms.assetid: 744bd1dc-d109-40df-a5dd-9db8982523a6
ms.search.region: Global
ms.author: shailesn
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 8f6b5c5899c13fc7ff2de60ac9c5ccca65edb919
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="patch-sql-server-reporting-services-in-a-one-box-environment"></a><span data-ttu-id="208bf-103">1 ボックス環境の SQL Server Reporting Services への修正プログラムの適用</span><span class="sxs-lookup"><span data-stu-id="208bf-103">Patch SQL Server Reporting Services in a one-box environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="208bf-104">次の手順は、1 ボックス開発環境のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="208bf-104">The following procedure is for one-box development environments only.</span></span>

## <a name="patch-the-reporting-service"></a><span data-ttu-id="208bf-105">Reporting Service のパッチ適用</span><span class="sxs-lookup"><span data-stu-id="208bf-105">Patch the Reporting Service</span></span>

<span data-ttu-id="208bf-106">次の手順は、1 ボックス開発環境のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="208bf-106">The following procedure is for one-box development environments only.</span></span>

-   <span data-ttu-id="208bf-107">パッチ .zip file を Lifecycle Services (LCS) からダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="208bf-107">Download the patch .zip file from Lifecycle Services (LCS).</span></span>
-   <span data-ttu-id="208bf-108">レポート サービスの修正プログラムのデータのフォルダーにフォント ファイルがある場合は、SQL Server Reporting Services (SSRS) が実行されているコンピューターにこれらをインストールします。</span><span class="sxs-lookup"><span data-stu-id="208bf-108">If there are any font files in the Reporting Service patch’s data folder, install these to the machine where SQL Server Reporting Services (SSRS) is running.</span></span> <span data-ttu-id="208bf-109">Windows でのフォントのインストールの詳細については、「<http://www.microsoft.com/en-us/Typography/TrueTypeInstall.aspx>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="208bf-109">For more information about installing fonts on windows, see <http://www.microsoft.com/en-us/Typography/TrueTypeInstall.aspx>.</span></span>  <span data-ttu-id="208bf-110">既にインストールされているフォントは再度インストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="208bf-110">Any fonts that have already been installed do not need to be installed again.</span></span>
-   <span data-ttu-id="208bf-111">Reporting Services のパッチ スクリプト フォルダーのファイルを C:\\Packages\\Plugins\\AxReportVmRoleStartupTask の下にあるレポート プラグイン フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="208bf-111">Copy the files in the Reporting Services patch scripts folder to the Report plug-in folder located under C:\\Packages\\Plugins\\AxReportVmRoleStartupTask.</span></span>
-   <span data-ttu-id="208bf-112">ディレクトリを、スクリプト ファイルを格納したレポート プラグイン フォルダに変更します。</span><span class="sxs-lookup"><span data-stu-id="208bf-112">Change the directory to the Report plug-in folder where you stored the script files.</span></span>
-   <span data-ttu-id="208bf-113">以下に示すメソッドのいずれかを使用して、レポート拡張機能の古いインスタンスを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="208bf-113">Using one of the methods listed below, replace the old instance of reporting extensions.</span></span>
    -   <span data-ttu-id="208bf-114">レポート拡張機能を削除/再インストールします。</span><span class="sxs-lookup"><span data-stu-id="208bf-114">Remove/reinstall the reporting extension.</span></span> <span data-ttu-id="208bf-115">削除/再インストール オプションでは、インストールが完了した後にすべてのレポートを再配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="208bf-115">The remove/reinstall option requires that redeploy all reports after you have finished the reinstallation..</span></span>
    -   <span data-ttu-id="208bf-116">SQL Server バイナリ フォルダーに手動でバイナリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="208bf-116">Manually copy binaries to the sql server binary folder.</span></span> <span data-ttu-id="208bf-117">手動でファイルをコピーする場合は、レポートを再展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="208bf-117">If you choose to manually copy the files, then you do not need to redeploy reports.</span></span>

### <a name="removereinstall-the-reporting-extension"></a><span data-ttu-id="208bf-118">レポート拡張機能を削除/再インストール</span><span class="sxs-lookup"><span data-stu-id="208bf-118">Remove/reinstall the reporting extension</span></span>
<span data-ttu-id="208bf-119">SSRS が実行されているマシンの管理者グループのユーザーとして、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="208bf-119">Complete the following procedure as a user in the administrator group for the machine where SSRS is running.</span></span>

-   <span data-ttu-id="208bf-120">Windows PowerShell を使用して、次のスクリプトを実行することで、Dynamics SSRS 拡張機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="208bf-120">Using Windows PowerShell, remove the Dynamics SSRS extension by running the following script:</span></span>
    -   <span data-ttu-id="208bf-121">PowerShell .\\DeploySsrsExtension.ps1 –UninstallOnly</span><span class="sxs-lookup"><span data-stu-id="208bf-121">PowerShell .\\DeploySsrsExtension.ps1 –UninstallOnly</span></span>
-   <span data-ttu-id="208bf-122">PowerShell では、次のスクリプトを実行することで Dynamics SSRS 拡張機能を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="208bf-122">In PowerShell, reinstall the Dynamics SSRS extension by running the following script:</span></span>
    -   <span data-ttu-id="208bf-123">PowerShell .\\DeploySsrsExtension.ps1</span><span class="sxs-lookup"><span data-stu-id="208bf-123">PowerShell .\\DeploySsrsExtension.ps1</span></span>
-   <span data-ttu-id="208bf-124">レポートの拡張機能を削除すると、すべてのレポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="208bf-124">Removing the reporting extension removes all the reports.</span></span> <span data-ttu-id="208bf-125">レポート拡張機能を削除してから再インストールした場合は、次のスクリプトを実行してレポートを再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="208bf-125">If you have removed and then reinstalled the reporting extension, it is necessary to re-deploy the reports by running the following script:</span></span>
    -   <span data-ttu-id="208bf-126">Powershell .\\DeployAllReportsToSsrs.ps1</span><span class="sxs-lookup"><span data-stu-id="208bf-126">Powershell .\\DeployAllReportsToSsrs.ps1</span></span>
-   <span data-ttu-id="208bf-127">このタスクは、完了までに 20 ~ 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="208bf-127">This task will take 20 to 30 minutes to complete.</span></span>

### <a name="manually-copy-binaries-to-the-sql-server-binary-folder"></a><span data-ttu-id="208bf-128">SQL Server バイナリ フォルダーへの手動でのバイナリのコピー</span><span class="sxs-lookup"><span data-stu-id="208bf-128">Manually copy binaries to the SQL Server binary folder</span></span>
1.  <span data-ttu-id="208bf-129">SQL Server Reporting Services を停止します。</span><span class="sxs-lookup"><span data-stu-id="208bf-129">Stop SQL Server Reporting Services.</span></span> <span data-ttu-id="208bf-130">これは、**サービス管理コンソール**または **Reporting Services 構成マネージャー**から実行できます。</span><span class="sxs-lookup"><span data-stu-id="208bf-130">This can be done either from the **Services management** console or from the **Reporting Services Configuration Manager**.</span></span> <span data-ttu-id="208bf-131">[![Configuration\_RSHotfix](./media/configuration_rshotfix.png)](./media/configuration_rshotfix.png)</span><span class="sxs-lookup"><span data-stu-id="208bf-131">[![Configuration\_RSHotfix](./media/configuration_rshotfix.png)](./media/configuration_rshotfix.png)</span></span>
2.  <span data-ttu-id="208bf-132">SQL Server Reporting Services バイナリ フォルダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="208bf-132">Find the SQL Server Reporting Services binary folder.</span></span> <span data-ttu-id="208bf-133">このフォルダーは、通常、C:\\ プログラム ファイル \\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\bin にあります。</span><span class="sxs-lookup"><span data-stu-id="208bf-133">This folder is usually located at C:\\Program Files\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\bin.</span></span>
3.  <span data-ttu-id="208bf-134">次のファイルのいずれかがパッチにある場合は、それらのファイルを SQL Server Reporting Services Bin フォルダーにコピーします。* *</span><span class="sxs-lookup"><span data-stu-id="208bf-134">If any of the following files are in the patch, copy them to the SQL Server Reporting Services bin folder.* *</span></span>

<span data-ttu-id="208bf-135">**注記:** パッチは、サービスによって使用されるすべてのファイルを含む完全なパッチ、または変更されたファイルのみを含む増分パッチのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="208bf-135">**Note:** Patches can either be full patches, which would contain all of the files used by the service, or incremental patches, which contain only the files that have changed.</span></span> <span data-ttu-id="208bf-136">差分の修正プログラムを使用する場合は、一部のファイルが含まれない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="208bf-136">If you have an incremental patch, then some files may not be included.</span></span> <span data-ttu-id="208bf-137">パッチに含まれていないファイルは、置き換える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="208bf-137">Files not included in the patch do not need to be replaced.</span></span>

-   <span data-ttu-id="208bf-138">Microsoft.Dynamics.AX.Framework.Services.Platform.Client.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-138">Microsoft.Dynamics.AX.Framework.Services.Platform.Client.dll</span></span>
-   <span data-ttu-id="208bf-139">Microsoft.Dynamics.Framework.ReportsExtensions.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-139">Microsoft.Dynamics.Framework.ReportsExtensions.dll</span></span>
-   <span data-ttu-id="208bf-140">Microsoft.Dynamics.Framework.Reports.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-140">Microsoft.Dynamics.Framework.Reports.dll</span></span>
-   <span data-ttu-id="208bf-141">Microsoft.Dynamics.ApplicationPlatform.SSRSReportRuntime.Instrumentation.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-141">Microsoft.Dynamics.ApplicationPlatform.SSRSReportRuntime.Instrumentation.dll</span></span>
-   <span data-ttu-id="208bf-142">Microsoft.Dynamics.ApplicationPlatform.SSRSReportRuntime.man</span><span class="sxs-lookup"><span data-stu-id="208bf-142">Microsoft.Dynamics.ApplicationPlatform.SSRSReportRuntime.man</span></span>
-   <span data-ttu-id="208bf-143">Microsoft.Dynamics.Platform.Integration.ClientSdk.Abstraction.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-143">Microsoft.Dynamics.Platform.Integration.ClientSdk.Abstraction.dll</span></span>
-   <span data-ttu-id="208bf-144">Microsoft.Dynamics.AX.Framework.Reports.Shared.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-144">Microsoft.Dynamics.AX.Framework.Reports.Shared.dll</span></span>
-   <span data-ttu-id="208bf-145">Microsoft.Dynamics.AX.Framework.EncryptionEngine.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-145">Microsoft.Dynamics.AX.Framework.EncryptionEngine.dll</span></span>
-   <span data-ttu-id="208bf-146">Microsoft.Dynamics.AX.Framework.Utilities.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-146">Microsoft.Dynamics.AX.Framework.Utilities.dll</span></span>
-   <span data-ttu-id="208bf-147">Microsoft.Dynamics.ApplicationSuite.Reporting.BusinessLogic.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-147">Microsoft.Dynamics.ApplicationSuite.Reporting.BusinessLogic.dll</span></span>
-   <span data-ttu-id="208bf-148">Microsoft.Dynamics.ApplicationPlatform.Environment.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-148">Microsoft.Dynamics.ApplicationPlatform.Environment.dll</span></span>
-   <span data-ttu-id="208bf-149">Microsoft.Dynamics.AX.ReportConfiguration.axc</span><span class="sxs-lookup"><span data-stu-id="208bf-149">Microsoft.Dynamics.AX.ReportConfiguration.axc</span></span>
-   <span data-ttu-id="208bf-150">Microsoft.WindowsAzure.ServiceRuntime.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-150">Microsoft.WindowsAzure.ServiceRuntime.dll</span></span>
-   <span data-ttu-id="208bf-151">Microsoft.IdentityModel.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-151">Microsoft.IdentityModel.dll</span></span>
-   <span data-ttu-id="208bf-152">msshrtmi.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-152">msshrtmi.dll</span></span>

<span data-ttu-id="208bf-153">SQL Server Reporting Services を再起動します。</span><span class="sxs-lookup"><span data-stu-id="208bf-153">Restart SQL Server Reporting Services.</span></span>

### <a name="reporting-service-installation"></a><span data-ttu-id="208bf-154">Reporting Services インストール</span><span class="sxs-lookup"><span data-stu-id="208bf-154">Reporting service installation</span></span>
<span data-ttu-id="208bf-155">レポート サービスのインストールでは、以下の変更が行われます。以下のファイルは、レポート サービスの bin フォルダー (C:\\Program Files\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\bin) にコピーされ、対応する SSRS 設定ファイルが更新され、SSRS は拡張機能を認識します。</span><span class="sxs-lookup"><span data-stu-id="208bf-155">The following changes are made with the reporting service installation: The following files will be copied into Reporting service bin folder (C:\\Program Files\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\bin), and the corresponding SSRS config files will be updated so that SSRS is aware of the extension.</span></span>

-   <span data-ttu-id="208bf-156">Dynamics.AX.Framework.Services.Platform.Client.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-156">Dynamics.AX.Framework.Services.Platform.Client.dll</span></span>
-   <span data-ttu-id="208bf-157">Dynamics.Framework.ReportsExtensions.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-157">Dynamics.Framework.ReportsExtensions.dll</span></span>
-   <span data-ttu-id="208bf-158">Dynamics.Framework.Reports.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-158">Dynamics.Framework.Reports.dll</span></span>
-   <span data-ttu-id="208bf-159">Dynamics.ApplicationPlatform.SSRSReportRuntime.Instrumentation.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-159">Dynamics.ApplicationPlatform.SSRSReportRuntime.Instrumentation.dll</span></span>
-   <span data-ttu-id="208bf-160">Dynamics.ApplicationPlatform.SSRSReportRuntime.man</span><span class="sxs-lookup"><span data-stu-id="208bf-160">Dynamics.ApplicationPlatform.SSRSReportRuntime.man</span></span>
-   <span data-ttu-id="208bf-161">Dynamics.Platform.Integration.ClientSdk.Abstraction.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-161">Dynamics.Platform.Integration.ClientSdk.Abstraction.dll</span></span>
-   <span data-ttu-id="208bf-162">Dynamics.AX.Framework.Reports.Shared.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-162">Dynamics.AX.Framework.Reports.Shared.dll</span></span>
-   <span data-ttu-id="208bf-163">Dynamics.AX.Framework.EncryptionEngine.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-163">Dynamics.AX.Framework.EncryptionEngine.dll</span></span>
-   <span data-ttu-id="208bf-164">Dynamics.AX.Framework.Utilities.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-164">Dynamics.AX.Framework.Utilities.dll</span></span>
-   <span data-ttu-id="208bf-165">Dynamics.ApplicationSuite.Reporting.BusinessLogic.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-165">Dynamics.ApplicationSuite.Reporting.BusinessLogic.dll</span></span>
-   <span data-ttu-id="208bf-166">Dynamics.ApplicationPlatform.Environment.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-166">Dynamics.ApplicationPlatform.Environment.dll</span></span>
-   <span data-ttu-id="208bf-167">Dynamics.AX.ReportConfiguration.axc</span><span class="sxs-lookup"><span data-stu-id="208bf-167">Dynamics.AX.ReportConfiguration.axc</span></span>
-   <span data-ttu-id="208bf-168">WindowsAzure.ServiceRuntime.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-168">WindowsAzure.ServiceRuntime.dll</span></span>
-   <span data-ttu-id="208bf-169">IdentityModel.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-169">IdentityModel.dll</span></span>
-   <span data-ttu-id="208bf-170">msshrtmi.dll</span><span class="sxs-lookup"><span data-stu-id="208bf-170">msshrtmi.dll</span></span>

<span data-ttu-id="208bf-171">SSRS サービス アカウントはローカル システムを使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="208bf-171">An SSRS service account will be updated to use the local system.</span></span> <span data-ttu-id="208bf-172">新しい SSRS カタログ データベースの DynamicsAxReportServer と、一時データベースの DynamicsAxReportServerTempDB データベースが作成され、SSRS は、これら 2 つのデータベースを使用するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="208bf-172">A new SSRS catalog database DynamicsAxReportServer and temp database DynamicsAxReportServerTempDB database will be created, and SSRS will be configured to use these two databases.</span></span> <span data-ttu-id="208bf-173">既定のカタログ データベース ReportServer と ReportServerTempDBstill は存在しますが、レポート サービスでは使用されないように設定されています。</span><span class="sxs-lookup"><span data-stu-id="208bf-173">The default catalog database ReportServer and ReportServerTempDBstill exist, but are set to not be used by reporting services.</span></span> <span data-ttu-id="208bf-174">SSRS サービスは、Windows 認証を使用するために更新されます。</span><span class="sxs-lookup"><span data-stu-id="208bf-174">The SSRS service will be updated to use Windows Authentication.</span></span> <span data-ttu-id="208bf-175">xml 構成ファイル ReportPVMConfiguration.xml はレポート実行時間の SSRS bin フォルダー内に作成されます。</span><span class="sxs-lookup"><span data-stu-id="208bf-175">An xml configuration file ReportPVMConfiguration.xml will be created in the SSRS bin folder for the report runtime.</span></span> <span data-ttu-id="208bf-176">**Dynamics** という名前のレポート ルート フォルダーと **DynamicsBrowser** という名前のセキュリティ ロールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="208bf-176">A report root folder named **Dynamics** and a new security role named **DynamicsBrowser** will be created.</span></span> <span data-ttu-id="208bf-177">このカスタム ロールには AOS Web アプリケーションの AppPool ID とバッチ サービス アカウントの両方が追加されます。</span><span class="sxs-lookup"><span data-stu-id="208bf-177">Both AOS Web application AppPool identity and batch service account will be added to this custom role.</span></span> <span data-ttu-id="208bf-178">配置中、レポート フォルダーは削除されてから再作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="208bf-178">Note that during deployment, the report folder will be deleted and then recreated.</span></span> <span data-ttu-id="208bf-179">したがって、以前に展開されたレポートはすべて SSRS サーバーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="208bf-179">Therefore all the previously deployed reports will be deleted from the SSRS server.</span></span>  <span data-ttu-id="208bf-180">レポート拡張機能を再インストールした後は、レポートを再配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="208bf-180">After you reinstall the reporting extension, you must redeploy the reports.</span></span>  



