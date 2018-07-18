---
title: "AX 2012 R3 用データのインポート/エクスポート フレームワークのインストール"
description: "このトピックでは、Microsoft Dynamics AX 2012 R3 のデータ インポート/エクスポート フレームワークをインストールする方法について説明します。"
author: kfend
manager: AnnBe
ms.date: 11/13/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: 
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: AX 2012
ms.custom: 96693
ms.assetid: d8ba7c2e-2a57-4e34-84fb-ba5f6289e781
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 9aaa96ac3b038bf29e087d8d2610e1a20d58244c
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="install-the-data-importexport-framework-for-ax-2012-r3"></a><span data-ttu-id="c4104-103">AX 2012 R3 用データのインポート/エクスポート フレームワークのインストール</span><span class="sxs-lookup"><span data-stu-id="c4104-103">Install the Data import/export framework for AX 2012 R3</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c4104-104">このトピックでは、Microsoft Dynamics AX 2012 R3 のデータ インポート/エクスポート フレームワークをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4104-104">This topic describes how to install the Data Import/Export Framework for Microsoft Dynamics AX 2012 R3.</span></span> 

<span data-ttu-id="c4104-105">開始する前に、環境には次のコンポーネントが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4104-105">Before you begin, your environment must include the following components:</span></span>

-   <span data-ttu-id="c4104-106">業務に合わせてコンフィギュレーションされた実行中の AX 2012 R3 のバージョン。</span><span class="sxs-lookup"><span data-stu-id="c4104-106">A running version of AX 2012 R3 that has been configured for your business.</span></span> <span data-ttu-id="c4104-107">AX 2012 R3 をインストールする方法の詳細については、[Microsoft Dynamics AX 2012 のインストール](https://technet.microsoft.com/en-us/library/dd362138.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4104-107">For more information about how to install AX 2012 R3, see [Install Microsoft Dynamics AX 2012](https://technet.microsoft.com/en-us/library/dd362138.aspx).</span></span>
-   <span data-ttu-id="c4104-108">実行中の Microsoft SQL Server Integration Services インスタンス。</span><span class="sxs-lookup"><span data-stu-id="c4104-108">A running instance of Microsoft SQL Server Integration Services.</span></span> <span data-ttu-id="c4104-109">SQL Server のバージョンは、Microsoft Dynamics AX ビジネス データベースおよびモデル ストア データベースをホストするバージョンと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4104-109">The version of SQL Server must be the same as the version that hosts the Microsoft Dynamics AX business and model store databases.</span></span> <span data-ttu-id="c4104-110">サポートされているバージョンは、SQL Server 2008 R2、SQL Server 2012、SQL Server 2014 です。</span><span class="sxs-lookup"><span data-stu-id="c4104-110">The supported versions are SQL Server 2008 R2, SQL Server 2012, and SQL Server 2014.</span></span> <span data-ttu-id="c4104-111">SQL Server Integration Services をインストールする方法の詳細については、[統合サービスのインストール](http://go.microsoft.com/fwlink/?LinkID=394975&clcid=0x409) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4104-111">For more information about how to install SQL Server Integration Services, see [Install Integration Services](http://go.microsoft.com/fwlink/?LinkID=394975&clcid=0x409).</span></span>

<span data-ttu-id="c4104-112">**注記:** InformationSource からデータのインポート/エクスポート フレームワークを以前にインストールした場合は、それを完全にアンインストールしてから、AX 2012 R3 用に再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4104-112">**Note:** If you have previously installed the Data Import/Export Framework from InformationSource, you must fully uninstall it and then reinstall it for AX 2012 R3.</span></span> <span data-ttu-id="c4104-113">アンインストールの一環として、**プログラムの追加と削除**を使用してすべてのバイナリ ファイルを削除する必要があります。また、データのインポート/エクスポート フレームワーク モデルもアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4104-113">As part of the uninstallation, you must remove all binary files by using **Add/Remove Programs**, and you must also uninstall the Data Import/Export Framework model.</span></span> <span data-ttu-id="c4104-114">詳細については、「Microsoft Dynamics AX のアンインストール」および「[方法: モデル情報を削除 (アンインストール)](https://technet.microsoft.com/en-us/library/hh433514.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4104-114">For more information, see Uninstall Microsoft Dynamics AX and [How to: Remove (Uninstall) a Model](https://technet.microsoft.com/en-us/library/hh433514.aspx).</span></span>

## <a name="install-the-version-of-the-data-importexport-framework-that-is-available-in-ax-2012-r3"></a><span data-ttu-id="c4104-115">AX 2012 R3 で利用できるデータのインポート/エクスポート フレームワークのバージョンをインストールする</span><span class="sxs-lookup"><span data-stu-id="c4104-115">Install the version of the Data Import/Export Framework that is available in AX 2012 R3</span></span>
<span data-ttu-id="c4104-116">データのインポート/エクスポート フレームワークのコンポーネントを次のようにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4104-116">Components of the Data Import/Export Framework must be installed as follows:</span></span>

-   <span data-ttu-id="c4104-117">データのインポート/エクスポート フレームワーク サービスは、SQL Server Integration Services を実行するコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4104-117">The Data Import/Export Framework service must be installed on a computer that is running SQL Server Integration Services.</span></span>
-   <span data-ttu-id="c4104-118">データのインポート/エクスポート フレームワーク サーバーは、Microsoft Dynamics AX Application Object Server (AOS) のインスタンスを実行しているコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4104-118">The Data Import/Export Framework server must be installed on a computer that is running an instance of Microsoft Dynamics AX Application Object Server (AOS).</span></span>
-   <span data-ttu-id="c4104-119">データのインポート/エクスポート フレームワーク クライアントは、Microsoft Dynamics AX クライアントを実行しているコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4104-119">The Data Import/Export Framework client must be installed on a computer that is running the Microsoft Dynamics AX client.</span></span>

<span data-ttu-id="c4104-120">これらのコンポーネントは、同じコンピューターまたは別のコンピューターのいずれかにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c4104-120">These components can be on either the same computer or different computers.</span></span> <span data-ttu-id="c4104-121">インストーラーは、各コンピューターにローカルで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4104-121">You must run the installer locally on each computer.</span></span>

1.  <span data-ttu-id="c4104-122">**Microsoft Dynamics AX セットアップ**を開始します。</span><span class="sxs-lookup"><span data-stu-id="c4104-122">Start **Microsoft Dynamics AX Setup**.</span></span> <span data-ttu-id="c4104-123">**インストール** で、**Microsoft Dynamics AX コンポーネント** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4104-123">Under **Install**, select **Microsoft Dynamics AX components**.</span></span>
2.  <span data-ttu-id="c4104-124">最初のウィザード ページに進みます。</span><span class="sxs-lookup"><span data-stu-id="c4104-124">Advance through the first wizard pages.</span></span> <span data-ttu-id="c4104-125">各ページの**次へ**をクリックして、既定の設定を承認します。</span><span class="sxs-lookup"><span data-stu-id="c4104-125">Click **Next** on each page to accept the default settings.</span></span>
3.  <span data-ttu-id="c4104-126">**セットアップ サポート ファイル**がコンピューターにインストールされていない場合、**ファイルの場所を選択**ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4104-126">If the **Setup Support files** have not yet been installed on the computer, the **Select a file location** page is displayed.</span></span> <span data-ttu-id="c4104-127">**セットアップ サポート ファイル** はインストールに必要です。</span><span class="sxs-lookup"><span data-stu-id="c4104-127">The **Setup Support files** are required for installation.</span></span> <span data-ttu-id="c4104-128">ファイルの場所を入力するか、または既定の場所を受け入れ、**次**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4104-128">Enter a file location or accept the default location, and then click **Next**.</span></span>
4.  <span data-ttu-id="c4104-129">**コンポーネントの選択**ページで、インストールするコンピューターの適切なコンポーネントを選択し、**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4104-129">On the **Select components** page, select the appropriate component for the computer that you are installing to, and then click **Next**:</span></span>
    -   <span data-ttu-id="c4104-130">SQL Server Integration Services を実行するコンピューターで、**データのインポート/エクスポート フレームワーク (DIXF) サービス**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4104-130">On the computer that is running SQL Server Integration Services, select **Data Import/Export Framework (DIXF) service**.</span></span>
    -   <span data-ttu-id="c4104-131">AOS インスタンスで、AOS コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="c4104-131">On the AOS instance, select AOS component.</span></span> <span data-ttu-id="c4104-132">インストールの一部として AOS サービスの再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="c4104-132">A restart of the AOS service is required as part of the installation.</span></span>
    -   <span data-ttu-id="c4104-133">クライアント コンピューターで、**クライアント コンポーネント**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4104-133">On the client computer, select **Client component**.</span></span>

5.  <span data-ttu-id="c4104-134">前提条件の検証チェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4104-134">A prerequisite validation check runs.</span></span> <span data-ttu-id="c4104-135">前提条件の確認がインストーラーの外部に検出された問題に対処して、検証確認を再起動します。</span><span class="sxs-lookup"><span data-stu-id="c4104-135">Address any issues that the prerequisite check finds outside the installer, and then restart the validation check.</span></span> <span data-ttu-id="c4104-136">すべての前提条件が満たされたとき、**次へ** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4104-136">When all prerequisites have been found, click **Next**.</span></span>
6.  <span data-ttu-id="c4104-137">ウィザードに**データのインポート/エクスポート フレームワーク サービスの構成**ページが表示されている場合、サービス アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4104-137">If the wizard displays the **Configure the Data Import/Export Framework service** page, specify a service account.</span></span> <span data-ttu-id="c4104-138">AOS サービス用に使用したサービス アカウントと同じサービス アカウントを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c4104-138">We recommend that you use the same service account as that used for the AOS service.</span></span> <span data-ttu-id="c4104-139">**次へ** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4104-139">Click **Next**.</span></span>
7.  <span data-ttu-id="c4104-140">ウィザードに**データのインポート/エクスポート フレームワーク サービス拡張機能の構成**ページが表示されている場合、データのインポート/エクスポート フレームワーク サービスを実行するサーバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4104-140">If the wizard displays the **Configure the Data Import/Export Framework extensions** page, specify the name of the server that runs the Data Import/Export Framework service.</span></span> <span data-ttu-id="c4104-141">**次へ** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4104-141">Click **Next**.</span></span>
8.  <span data-ttu-id="c4104-142">もう 1 つの前提条件の検証チェックが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c4104-142">Another prerequisite validation check might run.</span></span> <span data-ttu-id="c4104-143">前提条件の確認がインストーラーの外部に検出された問題に対処して、検証確認を再起動します。</span><span class="sxs-lookup"><span data-stu-id="c4104-143">Address any issues that the prerequisite check finds outside the installer, and then restart the validation check.</span></span> <span data-ttu-id="c4104-144">すべての前提条件が満たされたとき、**次へ** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4104-144">When all prerequisites have been found, click **Next**.</span></span>
9.  <span data-ttu-id="c4104-145">**インストールの準備ができました**ページで、**インストール**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4104-145">On the **Ready to install** page, click **Install**.</span></span>
10. <span data-ttu-id="c4104-146">**セットアップが正常に完了**ページで、**完了**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4104-146">On the **Setup was completed successfully** page, click **Finish**.</span></span>

## <a name="configure-the-data-importexport-framework"></a><span data-ttu-id="c4104-147">データのインポート/エクスポート フレームワークのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="c4104-147">Configure the Data Import/Export Framework</span></span>
<span data-ttu-id="c4104-148">データ インポート/エクスポート フレームワークのインストールが終了したら、以下の手順に従ってそれを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4104-148">When you have finished installing the Data Import/Export Framework, follow these steps to configure it.</span></span>

1.  <span data-ttu-id="c4104-149">データのインポート/エクスポート フレームワーク サービスを実行しているコンピューターの **Microsoft Dynamics AX のデータのインポート エクスポート フレームワーク サービス ユーザー** ローカル グループに、データのインポート/エクスポート フレームワーク サービス アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c4104-149">Add the Data Import/Export Framework service account to the **Microsoft Dynamics AX Data Import Export Framework Service Users** local group on the computer that is running the Data Import/Export Framework service.</span></span> <span data-ttu-id="c4104-150">その後、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c4104-150">Then restart that computer.</span></span> <span data-ttu-id="c4104-151">**注:** サービス アカウントをグループに追加する方法の詳細については、[ローカル グループにメンバーを追加](http://go.microsoft.com/fwlink/?LinkID=394060&clcid=0x409) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4104-151">**Note: ** For more information about how to add a service account to a group, see [Add a member to a local group](http://go.microsoft.com/fwlink/?LinkID=394060&clcid=0x409).</span></span>
2.  <span data-ttu-id="c4104-152">AOS インスタンスを実行しているコンピューターの **Microsoft Dynamics AX のデータのインポート エクスポート フレームワーク サービス ユーザー** ローカル グループに AOS サービス アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c4104-152">Add the AOS service account to the **Microsoft Dynamics AX Data Import Export Framework Service Users** local group on the computer that is running the AOS instance.</span></span> <span data-ttu-id="c4104-153">その後、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c4104-153">Then restart that computer.</span></span>
3.  <span data-ttu-id="c4104-154">データのインポート/エクスポート フレームワークのパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="c4104-154">Set the Data Import/Export Framework parameters.</span></span> <span data-ttu-id="c4104-155">データのインポート/エクスポート フレームワークには、データのインポート/エクスポート フレームワーク サービス アカウントが読み取りアクセス権を必要とする共有ディレクトリが必要です。</span><span class="sxs-lookup"><span data-stu-id="c4104-155">The Data Import/Export Framework requires a shared directory that the Data Import/Export Framework service account must have read access to.</span></span> <span data-ttu-id="c4104-156">AOS サービス アカウントには、ディレクトリへの読み書きアクセス権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="c4104-156">The AOS service account must have read and write access to the directory.</span></span> <span data-ttu-id="c4104-157">AOS サービスでは、データのインポート/エクスポート フレームワークが SQL Server 統合サービスを使用してデータを読み込むことができるように、データを共有ディレクトリに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c4104-157">The AOS service writes data to the shared directory, so that the Data Import/Export Framework can use SQL Server Integration Services to read the data.</span></span> <span data-ttu-id="c4104-158">パフォーマンス上の理由から、ディレクトリが SQL Server Integration Services として同じサーバーに配置されることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c4104-158">For performance reasons, we recommend that the directory be located on the same server as SQL Server Integration Services.</span></span> <span data-ttu-id="c4104-159">**セキュリティ上の注意:** 共有ディレクトリには、インポートおよびエクスポートする内容に応じて、機密データが含まれている可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c4104-159">**Security Note:** Be aware that the shared directory may contain sensitive data, depending on what you are importing and exporting.</span></span> <span data-ttu-id="c4104-160">出来る限りの少数のユーザーが、AOS サービス アカウントおよびデータのインポート/エクスポート フレームワーク サービス アカウントに加えて、その場所にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c4104-160">Ensure that as few users as possible have access to the location, in addition to the AOS service account and the Data Import/Export Framework service account.</span></span>
    1.  <span data-ttu-id="c4104-161">AX 2012 R3 クライアントで、**データのインポート/エクスポート フレームワーク** &gt; **設定** &gt; **データのインポート/エクスポート フレームワークのパラメーター**に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4104-161">In an AX 2012 R3 client, go to **Data Import/Export Framework** &gt; **Setup** &gt; **Data Import/Export Framework parameters**.</span></span>
    2.  <span data-ttu-id="c4104-162">**共有作業ディレクトリ** フィールドで、共有ディレクトリを入力してから**検証**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4104-162">In the **Shared working directory** field, enter a shared directory, and then click **Validate**.</span></span> <span data-ttu-id="c4104-163">このステップでは、AOS アカウントが場所に書き込むことができ、データ インポート/エクスポート フレームワークがその場所から読み取ることができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c4104-163">This step verifies that the AOS account can write to the location, and that the Data Import/Export Framework can read from the location.</span></span> <span data-ttu-id="c4104-164">これらの両方の条件が true である場合、検証アイコンが緑色になります。</span><span class="sxs-lookup"><span data-stu-id="c4104-164">If both these conditions are true, the validation icon turns green.</span></span>
    3.  <span data-ttu-id="c4104-165">データの処理時にエラーが含まれる行をスキップする場合、**エラーを無視**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4104-165">If you want to skip rows that contain errors when data is processed, select **Ignore error**.</span></span> <span data-ttu-id="c4104-166">**エラーを無視**を選択した場合、**エラー ファイルの作成**も選択し、エラーをファイルに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c4104-166">If you select **Ignore error**, you can also select **Create error file** to write any errors to a file.</span></span>
    4.  <span data-ttu-id="c4104-167">**データ アクセス モード** フィールドを使用すると、SQL Server Integration Services がデータの読み込みに使用するメソッドをコントロールすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4104-167">You can use the **Data access mode** field to control the method that SQL Server Integration Services uses to load data.</span></span> <span data-ttu-id="c4104-168">また、**最大挿入コミット サイズ** フィールドを使用して、読み込まれるバッチのサイズをコントロールすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4104-168">You can also use the **Maximum insert commit size** field to control the size of the batches that are loaded.</span></span>

## <a name="configure-the-data-importexport-framework-for-use-by-external-services-such-as-lifecycle-services"></a><span data-ttu-id="c4104-169">Lifecycle Services などの外部サービスで使用するためのデータのインポート/エクスポート フレームワークのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="c4104-169">Configure the Data Import/Export Framework for use by external services, such as Lifecycle Services</span></span>
<span data-ttu-id="c4104-170">Lifecycle Services などの外部サービスからデータのインポート/エクスポート フレームワークに接続するために、**DMFEntityExecutionService** および **DMFService** のサービス グループを配置して有効にし、受信ポートを提示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4104-170">In order to connect to the Data Import/Export Framework from an external service, such as Lifecycle Services, the **DMFEntityExecutionService** and **DMFService** service groups must be deployed and enabled to provide inbound ports.</span></span>
1.  <span data-ttu-id="c4104-171">AX 2012 R3 クライアントで、開発ワークスペースを開きます。</span><span class="sxs-lookup"><span data-stu-id="c4104-171">In an AX 2012 R3 client, open a development workspace.</span></span>
2.  <span data-ttu-id="c4104-172">**Service Groups** の下で、次の 2 つのサービス グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="c4104-172">Under **Service Groups**, deploy the following two service groups:</span></span>
    -   <span data-ttu-id="c4104-173">**DMFEntityExecutionService**</span><span class="sxs-lookup"><span data-stu-id="c4104-173">**DMFEntityExecutionService**</span></span>
    -   <span data-ttu-id="c4104-174">**DMFService**</span><span class="sxs-lookup"><span data-stu-id="c4104-174">**DMFService**</span></span>





