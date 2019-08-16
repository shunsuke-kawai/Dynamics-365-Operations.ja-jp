---
title: RCS および ER のアプリケーション固有のメタデータを準備する
description: このトピックでは、Regulatory configuration service (RCS) および電子レポート (ER) のアプリケーション固有のメタデータを準備する方法について説明します。
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 289f901501a68319c9d85e993d8dfbfc3838a8eb
ms.sourcegitcommit: d940c7892b6caa6141b3bda8abf1c56e9df4687a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "1726435"
---
# <a name="prepare-application-specific-metadata-for-rcs"></a><span data-ttu-id="f5c5f-103">RCS のアプリケーション固有のメタデータを準備する</span><span class="sxs-lookup"><span data-stu-id="f5c5f-103">Prepare application-specific metadata for RCS</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f5c5f-104">このトピックでは、次のタスクの例について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-104">This topic walks you through examples of the following tasks:</span></span>

- [<span data-ttu-id="f5c5f-105">RCS で使用できるアプリケーション メタデータを準備する</span><span class="sxs-lookup"><span data-stu-id="f5c5f-105">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)
- [<span data-ttu-id="f5c5f-106">ER コンフィギュレーションを使用してアプリケーション メタデータにアクセスする</span><span class="sxs-lookup"><span data-stu-id="f5c5f-106">Access application metadata by using an ER configuration</span></span>](#access-application-metadata-by-using-an-er-configuration)
- [<span data-ttu-id="f5c5f-107">接続されているアプリケーションを使用してアプリケーション メタデータにアクセスする</span><span class="sxs-lookup"><span data-stu-id="f5c5f-107">Access application metadata by using connected applications</span></span>](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a><span data-ttu-id="f5c5f-108">RCS で使用できるアプリケーション メタデータを準備する</span><span class="sxs-lookup"><span data-stu-id="f5c5f-108">Prepare application metadata that can be used in RCS</span></span>

<span data-ttu-id="f5c5f-109">次の手順では、**システム管理者**または**電子報告開発者**のロールを持つ Finance and Operations のユーザーが、Regulatory Configuration Service (RCS) の ER モデル マッピング コンフィギュレーションを設計するための Microsoft Dynamics 365 for Finance and Operations アプリケーションのメタデータを含む、新しい電子レポート (ER) コンフィギュレーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-109">The following procedure shows how a user of Finance and Operations who has the **System Administrator** or **Electronic Reporting Developer** role can create an Electronic reporting (ER) configuration that contains metadata for the Microsoft Dynamics 365 for Finance and Operations application, and that is used to design ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="f5c5f-110">この例で作成されたサンプル ER モデル マッピング コンフィギュレーションは、対外貿易トランザクションにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-110">The sample ER model mapping configuration that is created in this example will be used to access foreign trade transactions.</span></span>

<span data-ttu-id="f5c5f-111">この例では、RCS を使用して、対外貿易ビジネスのドメインからの情報を含む電子ドキュメントを生成する Finance and Operations の ER ソリューションを設計します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-111">For this example, you want to use RCS to design an ER solution for Finance and Operations that will be used to generate electronic documents that contain information from the foreign trade business domain.</span></span> <span data-ttu-id="f5c5f-112">ER データ モデルと必要なデータ ソース間のマッピングを指定するには、RCS で Finance and Operations アプリケーションのメタデータにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-112">To specify the mapping between the ER data model and the sources of required data, you must have access to application metadata for Finance and Operations in RCS.</span></span> <span data-ttu-id="f5c5f-113">そのため、ER ソリューション設計プロセスの一部として、選択したビジネス ドメインに対する生成 ER レポートに現在必要とされるすべてのメタデータを含む、新しい ER メタデータ コンフィギュレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-113">Therefore, as part of the process of designing the ER solution, you must configure a new ER metadata configuration that contains all the metadata that is currently required in order to generate ER reports for the selected business domain.</span></span>

> [!NOTE]
> <span data-ttu-id="f5c5f-114">この例では、サンプル会社 Litware, Inc. のコンフィギュレーションを作成します。これらの手順はすべての会社で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-114">In this example, you will create a configuration for the sample company, Litware, Inc. These steps can be performed in any company.</span></span>

1. <span data-ttu-id="f5c5f-115">**組織管理  \> ワークスペース \> 電子申告** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-115">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="f5c5f-116">サンプル会社 Litware, Inc. のコンフィギュレーション プロバイダーが使用可能であり、**アクティブ**としてマークされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-116">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="f5c5f-117">このコンフィギュレーション プロバイダーが表示されない場合は、[コンフィギュレーション プロバイダーの作成および有効なプロバイダーとしてのマーク付け](tasks/er-configuration-provider-mark-it-active-2016-11.md)という手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-117">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="f5c5f-118">**メタデータ コンフィギュレーション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-118">Select **Metadata configurations**.</span></span>
4. <span data-ttu-id="f5c5f-119">**コンフィギュレーションの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-119">Select **Create configuration**.</span></span>
5. <span data-ttu-id="f5c5f-120">ドロップダウン ダイアログ ボックスの**名前**フィールドに名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-120">In the drop-down dialog box, in the **Name** field, enter a name.</span></span> <span data-ttu-id="f5c5f-121">この例では、**対外貿易メタデータ**と入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-121">For this example, enter **Foreign trade metadata**.</span></span>
6. <span data-ttu-id="f5c5f-122">**コンフィギュレーションの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-122">Select **Create configuration**.</span></span>
7. <span data-ttu-id="f5c5f-123">**デザイナー** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-123">Select **Designer**.</span></span>
8. <span data-ttu-id="f5c5f-124">**追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-124">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f5c5f-125">アプリケーション全体に対して、または選択したモデル、モジュールに対して、すべてのメタデータを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-125">You can select all metadata either for the whole application, or for selected models or modules.</span></span> <span data-ttu-id="f5c5f-126">どちらの場合も、レコードのテーブル、列挙体、および拡張データ型 (EDTs) のメタデータが自動的に追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-126">In both cases, be aware that the following metadata will be automatically added: tables of records, enumerations, and extended data types (EDTs).</span></span> <span data-ttu-id="f5c5f-127">メタデータの追加のタイプが必要な場合、手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-127">When additional types of metadata are required, they must be manually added.</span></span>

<span data-ttu-id="f5c5f-128">対外貿易トランザクションに関連付けられたメタデータをいくつか追加し、手動でメタデータ項目を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-128">You must add some metadata that is related to foreign trade transactions and manually select metadata items.</span></span>

9. <span data-ttu-id="f5c5f-129">**データソースを追加 \> テーブル レコード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-129">Select **Add data source \> Table records**.</span></span>
10. <span data-ttu-id="f5c5f-130">**名前**フィールドにある**イントラスタット**の値をフィルタ処理します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-130">Filter on a value of **Intrastat** in the **Name** field.</span></span>
11. <span data-ttu-id="f5c5f-131">**イントラスタット** テーブル レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-131">Select the **Intrastat** table record.</span></span>
12. <span data-ttu-id="f5c5f-132">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-132">Select **OK**.</span></span>

<span data-ttu-id="f5c5f-133">イントラスタットのレコード テーブルに関するメタデータ情報を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-133">You must add metadata information about the Intrastat table of records.</span></span>

13. <span data-ttu-id="f5c5f-134">ツリーで、**テーブル レコード イントラスタット\> \>リレーション \> イントラスタットコモディティ (テーブル レコード EcoResCategory)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-134">In the tree, select **Table records Intrastat \> \>Relations \> IntrastatCommodity (Table records EcoResCategory)**.</span></span>
14. <span data-ttu-id="f5c5f-135">**メタデータの追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-135">Select **Add metadata**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f5c5f-136">選択したレコード テーブルに必要な関係に関するメタデータは、手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-136">Metadata about required relations for the selected table of records must be added manually.</span></span>

15. <span data-ttu-id="f5c5f-137">**データソースの追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-137">Select **Add data source**.</span></span>
16. <span data-ttu-id="f5c5f-138">**列挙**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-138">Select **Enumeration**.</span></span>
17. <span data-ttu-id="f5c5f-139">**名前**フィールドにある **IntrastatDirection** の値をフィルタ処理します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-139">Filter on a value of **IntrastatDirection** in the **Name** field.</span></span>
18. <span data-ttu-id="f5c5f-140">**IntrastatDirection** の列挙レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-140">Select the **IntrastatDirection** enumeration record.</span></span>
19. <span data-ttu-id="f5c5f-141">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-141">Select **OK**.</span></span>
20. <span data-ttu-id="f5c5f-142">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-142">Select **Save**.</span></span>
21. <span data-ttu-id="f5c5f-143">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-143">Close the page.</span></span>
22. <span data-ttu-id="f5c5f-144">メタデータ コンフィギュレーションのドラフト バージョンの完了</span><span class="sxs-lookup"><span data-stu-id="f5c5f-144">Complete the draft version of the metadata configuration:</span></span>

    1. <span data-ttu-id="f5c5f-145">**ステータスの変更 \> 完了**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-145">Select **Change status \> Complete**.</span></span>
    2. <span data-ttu-id="f5c5f-146">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-146">Select **OK**.</span></span>
    3. <span data-ttu-id="f5c5f-147">完了したバージョン 1 を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-147">Select the completed version 1.</span></span>

23. <span data-ttu-id="f5c5f-148">完了したバージョンのメタデータ コンフィギュレーションをアプリケーションから XML ファイルとしてエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f5c5f-148">Export the completed version of the metadata configuration from the application as an XML file:</span></span>

    1. <span data-ttu-id="f5c5f-149">**交換 \> XML ファイルとしてエクスポート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-149">Select **Exchange \> Export as XML file**.</span></span>
    2. <span data-ttu-id="f5c5f-150">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-150">Select **OK**.</span></span>

<span data-ttu-id="f5c5f-151">作成した ER メタデータ コンフィギュレーションは、**対外貿易メタデータ .xml** ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-151">The ER metadata configuration that you created is saved as the **Foreign trade metadata.xml** file.</span></span> <span data-ttu-id="f5c5f-152">これをRCSにインポートすることで、Finance and Operations における対外貿易ビジネス ドメインのメタデータのソースとして使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-152">You can now import it into RCS, so that it can be used as the source of metadata for the foreign trade business domain in Finance and Operations.</span></span> <span data-ttu-id="f5c5f-153">この情報に基づいて、アプリケーション メタデータと ER データ モデルとの間のマッピングを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-153">Based on this information, you can specify the mapping between application metadata and the ER data model.</span></span>

## <a name="access-application-metadata-by-using-an-er-configuration"></a><span data-ttu-id="f5c5f-154">ER コンフィギュレーションを使用してアプリケーション メタデータにアクセスする</span><span class="sxs-lookup"><span data-stu-id="f5c5f-154">Access application metadata by using an ER configuration</span></span>

<span data-ttu-id="f5c5f-155">次の手順は、**システム管理者**または**電子レポート開発者**のロールを持つ RCS ユーザーが、Finance and Operations アプリケーションのメタデータを使用して新しい ER モデル マッピングをデザインする方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-155">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata from the Finance and Operations application.</span></span> <span data-ttu-id="f5c5f-156">アプリケーション メタデータには、対外貿易トランザクションにアクセスするためのサンプル メタデータ セットを含む ER メタデータ コンフィギュレーションを使用してアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-156">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span>

<span data-ttu-id="f5c5f-157">これを完了する前に、ます次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-157">Before you can complete this procedure, you must first complete the following procedures:</span></span>

- [<span data-ttu-id="f5c5f-158">コンフィギュレーション プロバイダーの作成および有効なプロバイダーとしてのマーク付け</span><span class="sxs-lookup"><span data-stu-id="f5c5f-158">Create a configuration provider and mark it as active</span></span>](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [<span data-ttu-id="f5c5f-159">RCS で使用できるアプリケーション メタデータを準備する</span><span class="sxs-lookup"><span data-stu-id="f5c5f-159">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)

1. <span data-ttu-id="f5c5f-160">**すべてのワークスペース \> 電子申告**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-160">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="f5c5f-161">サンプル会社 Litware, Inc. のコンフィギュレーション プロバイダーが使用可能であり、**アクティブ**としてマークされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-161">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="f5c5f-162">このコンフィギュレーション プロバイダーが表示されない場合は、[コンフィギュレーション プロバイダーの作成および有効なプロバイダーとしてのマーク付け](tasks/er-configuration-provider-mark-it-active-2016-11.md)という手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-162">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="f5c5f-163">Finance and Operations アプリケーションのメタデータを含む ER メタデータ コンフィギュレーションをインポートします。これは対外貿易ビジネス ドメインのための電子ドキュメントを生成するようコンフィギュレーションされています。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-163">Import the ER metadata configuration that contains metadata for the Finance and Operations application, and that is configured to generate electronic documents for the foreign trade business domain.</span></span> <span data-ttu-id="f5c5f-164">このトピックの前の部分 [RCS で使用できるアプリケーション メタデータを準備する](#prepare-application-metadata-that-can-be-used-in-rcs)の手順で ER メタデータ コンフィギュレーションを作成し、XML ファイルとしてエクスポートしました。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-164">You created this ER metadata configuration and exported it as an XML file in the [Prepare application metadata that can be used in RCS](#prepare-application-metadata-that-can-be-used-in-rcs) procedure earlier in this topic.</span></span>

    1. <span data-ttu-id="f5c5f-165">**メタデータ コンフィギュレーション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-165">Select **Metadata configurations**.</span></span>
    2. <span data-ttu-id="f5c5f-166">**交換**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-166">Select **Exchange**.</span></span>
    3. <span data-ttu-id="f5c5f-167">**XML ファイルから読み込む**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-167">Select **Load from XML file**.</span></span>
    4. <span data-ttu-id="f5c5f-168">参照し、**対外貿易メタデータ .xml** ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-168">Browse to select the **Foreign trade metadata.xml** file.</span></span>
    5. <span data-ttu-id="f5c5f-169">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-169">Select **OK**.</span></span>
    6. <span data-ttu-id="f5c5f-170">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-170">Close the page.</span></span>

4. <span data-ttu-id="f5c5f-171">データ モデル コンフィギュレーションの作成</span><span class="sxs-lookup"><span data-stu-id="f5c5f-171">Create a data model configuration:</span></span>

    1. <span data-ttu-id="f5c5f-172">**コンフィギュレーションをレポートする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-172">Select **Reporting configurations**.</span></span>
    2. <span data-ttu-id="f5c5f-173">**コンフィギュレーションの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-173">Select **Create configuration**.</span></span>
    3. <span data-ttu-id="f5c5f-174">ドロップ ダウン ダイアログ ボックスの**名前**フィールドに、**対外貿易モデル**と入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-174">In the drop-down dialog box, in the **Name** field, enter **Foreign trade model**.</span></span>
    4. <span data-ttu-id="f5c5f-175">**コンフィギュレーションの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-175">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="f5c5f-176">**デザイナー** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-176">Select **Designer**.</span></span>
    6. <span data-ttu-id="f5c5f-177">**新規**を選択すると、ドロップ ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-177">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="f5c5f-178">**名前**フィールドに、**ルート**と入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-178">In the **Name** field, type **Root**.</span></span>
        2. <span data-ttu-id="f5c5f-179">**追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-179">Select **Add**.</span></span>
    
    7. <span data-ttu-id="f5c5f-180">**新規**を選択すると、ドロップ ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-180">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="f5c5f-181">**名前**フィールドに、**トランザクション**と入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-181">In the **Name** field, type **Transaction**.</span></span>
        2. <span data-ttu-id="f5c5f-182">**品目タイプ** フィールドで、**レコード リスト**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-182">In the **Item type** field, select **Record list**.</span></span>
        3. <span data-ttu-id="f5c5f-183">**追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-183">Select **Add**.</span></span>
 
    8. <span data-ttu-id="f5c5f-184">**新規**を選択すると、ドロップ ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-184">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="f5c5f-185">**名前**フィールドに、**コモディティ コード**と入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-185">In the **Name** field, type **Commodity code**.</span></span>
        2. <span data-ttu-id="f5c5f-186">**品目タイプ**フィールドで、**文字列**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-186">In the **Item type** field, select **String**.</span></span>
        3. <span data-ttu-id="f5c5f-187">**追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-187">Select **Add**.</span></span>

    9. <span data-ttu-id="f5c5f-188">**新規**を選択すると、ドロップ ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-188">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="f5c5f-189">名前フィールドに、**請求金額**と入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-189">In the Name field, type **Invoiced amount**.</span></span>
        2. <span data-ttu-id="f5c5f-190">**品目タイプ** フィールドで、**実数**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-190">In the **Item type** field, select **Real**.</span></span>
        3. <span data-ttu-id="f5c5f-191">**追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-191">Select **Add**.</span></span>

    10. <span data-ttu-id="f5c5f-192">**新規**を選択すると、ドロップ ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-192">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="f5c5f-193">**名前**フィールドに、**日付**と入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-193">In the **Name** field, type **Date**.</span></span>
        2. <span data-ttu-id="f5c5f-194">**品目タイプ** フィールドで、**日付**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-194">In the **Item type** field, select **Date**.</span></span>
        3. <span data-ttu-id="f5c5f-195">**追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-195">Select **Add**.</span></span>
 
    11. <span data-ttu-id="f5c5f-196">**追加 \> ルート参照**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-196">Select **Add \> Root reference**.</span></span>
    12. <span data-ttu-id="f5c5f-197">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-197">Select **OK**.</span></span>
    13. <span data-ttu-id="f5c5f-198">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-198">Select **Save**.</span></span>
    14. <span data-ttu-id="f5c5f-199">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-199">Close the page.</span></span>
    15. <span data-ttu-id="f5c5f-200">**ステータスの変更 \> 完了**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-200">Select **Change status \> Complete**.</span></span>
    16. <span data-ttu-id="f5c5f-201">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-201">Select **OK**.</span></span>

5. <span data-ttu-id="f5c5f-202">モデル マッピング コンフィギュレーションの作成</span><span class="sxs-lookup"><span data-stu-id="f5c5f-202">Create a model mapping configuration:</span></span>

    1. <span data-ttu-id="f5c5f-203">**コンフィギュレーションの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-203">Select **Create configuration**.</span></span>
    2. <span data-ttu-id="f5c5f-204">ドロップ ダウン ダイアログ ボックスの**新規**フィールドに、**データ モデル対外貿易モデルに基づいたモデル マッピング**と入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-204">In the drop-down dialog box, in the **New** field, enter **Model Mapping based on data model Foreign trade model**.</span></span>
    3. <span data-ttu-id="f5c5f-205">**名前**フィールドに、**対外貿易マッピング**と入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-205">In the **Name** field, enter **Foreign trade mapping**.</span></span>
    4. <span data-ttu-id="f5c5f-206">**コンフィギュレーションの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-206">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="f5c5f-207">**必要条件**のクイック タブで、**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-207">On the **Prerequisites** FastTab, select **Edit**.</span></span>
    6. <span data-ttu-id="f5c5f-208">**新規** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-208">Select **New**.</span></span>
    7. <span data-ttu-id="f5c5f-209">**必要条件のコンポーネント タイプ** フィールドで、**コンフィギュレーション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-209">In the **Prerequisite component type** field, select **Configuration**.</span></span>
    8. <span data-ttu-id="f5c5f-210">**対外貿易メタデータ** コンフィギュレーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-210">Select the **Foreign trade metadata** configuration.</span></span>
    9. <span data-ttu-id="f5c5f-211">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-211">Select **Save**.</span></span> <span data-ttu-id="f5c5f-212">参照が**対外貿易メタデータ** コンフィギュレーションのバージョン 1 に追加されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-212">Notice that the reference is added to version 1 of the **Foreign trade metadata** configuration.</span></span> <span data-ttu-id="f5c5f-213">このコンフィギュレーションのアプリケーション メタデータは、このモデル マッピングをデザインするときに提供されます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-213">Application metadata from this configuration will be offered while the model mapping is designed.</span></span>
    10. <span data-ttu-id="f5c5f-214">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-214">Close the page.</span></span>
    11. <span data-ttu-id="f5c5f-215">**デザイナー** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-215">Select **Designer**.</span></span>
    12. <span data-ttu-id="f5c5f-216">**デザイナー** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-216">Select **Designer**.</span></span>
    13. <span data-ttu-id="f5c5f-217">ツリーで、**Dynamics 365 for Operations \> テーブル レコード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-217">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
    14. <span data-ttu-id="f5c5f-218">**ルートの追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-218">Select **Add root**.</span></span>
    15. <span data-ttu-id="f5c5f-219">**名前**フィールドに、**イントラスタット**と入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-219">In the **Name** field, enter **Intrastat**.</span></span>
    16. <span data-ttu-id="f5c5f-220">**イントラスタット** テーブル レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-220">Select **Intrastat** table records.</span></span>
    17. <span data-ttu-id="f5c5f-221">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-221">Select **OK**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f5c5f-222">現在使用されているメタデータ セットに追加されたテーブルは 2 つだけなので、2 つのテーブルのみが提供されています。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-222">Only two tables are offered, because only two tables were added to the set of metadata that is currently used.</span></span>

    18. <span data-ttu-id="f5c5f-223">**バインド**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-223">Select **Bind**.</span></span>
    19. <span data-ttu-id="f5c5f-224">ツリーで、**イントラスタット \> AmountMST** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-224">In the tree, select **Intrastat \> AmountMST**.</span></span>
    20. <span data-ttu-id="f5c5f-225">ツリーで、**トランザクション = イントラスタット \> 請求金額**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-225">In the tree, select **Transaction = Intrastat \> Invoiced amount**.</span></span>
    21. <span data-ttu-id="f5c5f-226">**バインド**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-226">Select **Bind**.</span></span>
    22. <span data-ttu-id="f5c5f-227">ツリーで、**イントラスタット \> TransDate** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-227">In the tree, select **Intrastat \> TransDate**.</span></span>
    23. <span data-ttu-id="f5c5f-228">ツリーで、**トランザクション = イントラスタット \> 日付**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-228">In the tree, select **Transaction = Intrastat \> Date**.</span></span>
    24. <span data-ttu-id="f5c5f-229">**バインド**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-229">Select **Bind**.</span></span>
    25. <span data-ttu-id="f5c5f-230">ツリーで、**イントラスタット \> \>リレーション \> イントラスタットコモディティ \> コード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-230">In the tree, select **Intrastat \> \>Relations \> IntrastatCommodity \> Code**.</span></span>
    26. <span data-ttu-id="f5c5f-231">ツリーで、**トランザクション = イントラスタット \> コモディティ コード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-231">In the tree, select **Transaction = Intrastat \> Commodity code**.</span></span>
    27. <span data-ttu-id="f5c5f-232">**バインド**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-232">Select **Bind**.</span></span>
    28. <span data-ttu-id="f5c5f-233">**検証**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-233">Select **Validate**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f5c5f-234">検証が完了した後、参照された ER メタデータ コンフィギュレーションのアプリケーション メタデータの詳細を使用して説明されているデータ ソース項目に、データ モデルの要素が正常にバインドされました。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-234">After validation is completed, you've successfully bound elements of the data model to items of the data sources that are described by using details of the application metadata from the referenced ER metadata configuration.</span></span>

    29. <span data-ttu-id="f5c5f-235">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-235">Select **Save**.</span></span>

<span data-ttu-id="f5c5f-236">必要に応じて、Finance and Operations で既存のメタデータ セットを拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-236">As you require, you can extend the existing set of metadata in Finance and Operations.</span></span> <span data-ttu-id="f5c5f-237">その後、Finance and Operations から新しい完了版の ER メタデータ コンフィギュレーションをエクスポートし、それを RCS にインポートして、インポートされたメタデータ コンフィギュレーションの新しいバージョンを参照してコンフィギュレーション済みモデル マッピングの前提条件を更新することができます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-237">You can then export the new completed version of the ER metadata configuration from Finance and Operations, import it into RCS, and update the prerequisites of the configured model mapping configuration to refer to a new version of the imported metadata configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="f5c5f-238">アプリケーション メタデータに関する情報を取得するこの方法は、ローカルに展開されたアプリケーションで利用できる唯一の方法です (ローカル ビジネス データ \[LBD\]、またはオンプレミスの場合、配置モデルは Finance and Operations に使用されます)。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-238">This method for getting information about application metadata is the only available method for applications that are locally deployed (that is, when a local business data \[LBD\], or on-premises, deployment model is used for Finance and Operations).</span></span>

## <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="f5c5f-239">接続されているアプリケーションを使用してアプリケーション メタデータにアクセスする</span><span class="sxs-lookup"><span data-stu-id="f5c5f-239">Access application metadata by using connected applications</span></span>

<span data-ttu-id="f5c5f-240">次の手順は、**システム管理者**または**電子レポート開発者**のロールを持つ RCS ユーザーが、Finance and Operations アプリケーションのメタデータを使用して新しい ER モデル マッピングをデザインする方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-240">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata of the Finance and Operations application.</span></span> <span data-ttu-id="f5c5f-241">アプリケーションのメタデータは、RCS 接続されたアプリケーションを使用してオンラインでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-241">Application metadata will be accessed online by using RCS connected application.</span></span> <span data-ttu-id="f5c5f-242">サンプル ER モデルマッピングは、対外貿易トランザクションにアクセスするようにコンフィギュレーションされます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-242">A sample ER model mapping will be configured to access foreign trade transactions.</span></span>

<span data-ttu-id="f5c5f-243">この手順を完了するには、まず RCS にある [コンフィギュレーション プロバイダーの作成および有効なプロバイダーとしてのマーク付け](tasks/er-configuration-provider-mark-it-active-2016-11.md)の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-243">To complete this procedure, you must first complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure in RCS.</span></span> <span data-ttu-id="f5c5f-244">このトピックの前の部分にある [ER コンフィギュレーションを使用してアプリケーション メタデータにアクセスする](#access-application-metadata-by-using-an-er-configuration)の手順をまだ完了していない場合は、[Dynamics 365 for Finance and Operations 8.1 電子レポート タスク ガイド](https://go.microsoft.com/fwlink/?linkid=2082739)のページに移動し、次の ER コンフィギュレーション ファイルを事前にダウンロードし、ローカルに保存してください : **対外貿易メタデータ .xml**、**対外貿易モデル .xml**、および**対外貿易マッピング .xml**</span><span class="sxs-lookup"><span data-stu-id="f5c5f-244">If you haven't yet completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, go to [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page to download the following ER configuration files in advance and save them locally: **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml**.</span></span>


### <a name="get-required-er-configurations"></a><span data-ttu-id="f5c5f-245">必要な ER コンフィギュレーションの取得</span><span class="sxs-lookup"><span data-stu-id="f5c5f-245">Get required ER configurations</span></span>

<span data-ttu-id="f5c5f-246">このトピックの前の部分にある [ER コンフィギュレーションを使用したアプリケーション メタデータへのアクセス](#access-application-metadata-by-using-an-er-configuration)手順を既に完了している場合、現在の RCS インスタンスに必要なすべての ER コンフィギュレーション (対外貿易メタデータ、モデルおよびマッピングのコンフィギュレーション) は、既に存在しています。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-246">If you've already completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, you already have all the required ER configurations (the foreign trade metadata, model, and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="f5c5f-247">その場合は、この手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-247">In that case, you can skip this procedure.</span></span>

1. <span data-ttu-id="f5c5f-248">**すべてのワークスペース \> 電子申告**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-248">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="f5c5f-249">**コンフィギュレーションをレポートする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-249">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="f5c5f-250">**対外貿易メタデータ .xml**、**対外貿易モデル .xml**、**対外貿易マッピング .xml** コンフィギュレーション ファイルを読み込み、それぞれについて、次の一連の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-250">Load the **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml** configuration files repeating the following chain of steps for each of them:</span></span>

    1. <span data-ttu-id="f5c5f-251">**交換**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-251">Select **Exchange**.</span></span>
    2. <span data-ttu-id="f5c5f-252">**XML ファイルから読み込む**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-252">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="f5c5f-253">**参照**を選択し、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-253">Select **Browse**, and select a file.</span></span>
    4. <span data-ttu-id="f5c5f-254">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-254">Select **OK**.</span></span>

### <a name="register-the-connection-with-finance-and-operations"></a><span data-ttu-id="f5c5f-255">接続を Finance and Operations に登録します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-255">Register the connection with Finance and Operations</span></span>

1. <span data-ttu-id="f5c5f-256">**すべてのワークスペース \> 電子申告**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-256">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="f5c5f-257">**接続アプリケーション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-257">Select **Connected applications**.</span></span>
3. <span data-ttu-id="f5c5f-258">コンフィギュレーションされたアプリケーションが Microsoft Azure に基づいており、RCS ユーザーが一般にアクセスできることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-258">Make sure that the configured application is based on Microsoft Azure, and that it is accessible in general to RCS users.</span></span> <span data-ttu-id="f5c5f-259">現在の RCS ユーザーが、選択されたアプリケーションにアクセスでき、アプリケーションのメタデータにアクセスするための権限を持つユーザーとして登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-259">The current RCS user must have access to the configured application being registered as a user of this application in a role that gives him or her privileges to access the application's metadata.</span></span>
4. <span data-ttu-id="f5c5f-260">**新規** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-260">Select **New**.</span></span>
5. <span data-ttu-id="f5c5f-261">**名前**フィールドに、接続されたアプリケーションの名前として **MyConnectedApp** と入力します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-261">In the **Name** field, enter **MyConnectedApp** as the name of the connected application.</span></span>
6. <span data-ttu-id="f5c5f-262">**アプリケーション** フィールドに、アプリケーションの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-262">In the **Application** field, specify the URL of the application.</span></span>
7. <span data-ttu-id="f5c5f-263">**テナント** フィールドに、アプリケーションのプロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-263">In the **Tenant** field, specify the provider of the application.</span></span>
8. <span data-ttu-id="f5c5f-264">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-264">Select **Save**.</span></span> 
9. <span data-ttu-id="f5c5f-265">コンフィギュレーションされたアプリケーションへの接続を確認するときは、**リモート アプリケーションへの接続**ページで、**ここを選択して、選択したリモート アプリケーションに接続する** のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-265">When you check the connection to the configured application, on the **Connect to remote application** page, select the **Select here to connect to selected remote application** link.</span></span> 
10. <span data-ttu-id="f5c5f-266">**接続の確認**を選択し、コンフィギュレーションされたアプリケーションへのアクセスを検証します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-266">Select **Check connection** to validate access to the configured application.</span></span>
11. <span data-ttu-id="f5c5f-267">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-267">Select **Close**.</span></span>

<span data-ttu-id="f5c5f-268">この手順を完了して接続検証に成功すると、コンフィギュレーションされたアプリケーションのバージョンとテナントの詳細が、現在のグリッドで更新されます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-268">After you complete this procedure and validation of the connection succeeds, the version and tenant details for the configured application will be updated in the current grid.</span></span>

### <a name="review-the-existing-model-mapping-configuration"></a><span data-ttu-id="f5c5f-269">既存のモデル マッピング コンフィギュレーションを確認する</span><span class="sxs-lookup"><span data-stu-id="f5c5f-269">Review the existing model mapping configuration</span></span>

1. <span data-ttu-id="f5c5f-270">**すべてのワークスペース \> 電子申告**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-270">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="f5c5f-271">**コンフィギュレーションをレポートする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-271">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="f5c5f-272">ツリーで、**対外貿易モデル \> 対外貿易マッピング**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-272">In the tree, select **Foreign trade model \> Foreign trade mapping**.</span></span>
4. <span data-ttu-id="f5c5f-273">**必要条件**のクイック タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-273">Select the **Prerequisites** FasTab.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f5c5f-274">現在、このマッピングはメタデータのコンフィギュレーションを参照しています。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-274">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="f5c5f-275">このコンフィギュレーションのアプリケーション メタデータは、このモデル マッピングをデザインするときに提供されます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-275">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

4. <span data-ttu-id="f5c5f-276">**デザイナー** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-276">Select **Designer**.</span></span>
5. <span data-ttu-id="f5c5f-277">**デザイナー** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-277">Select **Designer**.</span></span>
6. <span data-ttu-id="f5c5f-278">ツリーで、**Dynamics 365 for Operations \> テーブル レコード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-278">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
7. <span data-ttu-id="f5c5f-279">**ルートの追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-279">Select **Add root**.</span></span>
8. <span data-ttu-id="f5c5f-280">**テーブル** フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-280">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f5c5f-281">現在、このマッピングはメタデータのコンフィギュレーションを参照しています。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-281">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="f5c5f-282">このコンフィギュレーションのアプリケーション メタデータは、このモデル マッピングをデザインするときに提供されます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-282">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

9. <span data-ttu-id="f5c5f-283">**キャンセル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-283">Select **Cancel**.</span></span>

### <a name="assign-the-connected-application-to-a-model-mapping"></a><span data-ttu-id="f5c5f-284">接続されたアプリケーションをモデル マッピングに割り当てる</span><span class="sxs-lookup"><span data-stu-id="f5c5f-284">Assign the connected application to a model mapping</span></span>

1. <span data-ttu-id="f5c5f-285">**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-285">Select **Edit**.</span></span>
2. <span data-ttu-id="f5c5f-286">**接続されたアプリケーション フィールド**で、**MyConnectedApp** アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-286">In the **Connected application field**, select the **MyConnectedApp** application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f5c5f-287">このマッピングは、選択した接続アプリケーションのメタデータを参照します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-287">This mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="f5c5f-288">マッピングがメタデータ コンフィギュレーションと接続されたアプリケーションを同時に参照する場合、接続されたアプリケーションのメタデータが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-288">If a mapping refers to the metadata configuration and the connected application at the same time, the metadata of the connected application will be used.</span></span>

3. <span data-ttu-id="f5c5f-289">**デザイナー** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-289">Select **Designer**.</span></span>
4. <span data-ttu-id="f5c5f-290">**デザイナー** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-290">Select **Designer**.</span></span>
5. <span data-ttu-id="f5c5f-291">ツリーで、**Dynamics 365 for Operations \> テーブル レコード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-291">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
6. <span data-ttu-id="f5c5f-292">**ルートの追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-292">Select **Add root**.</span></span>
7. <span data-ttu-id="f5c5f-293">**テーブル** フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-293">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f5c5f-294">この時点で、マッピングは、割り当てられた接続アプリケーションのすべてのメタデータを使用するため、2 つ以上のアプリケーション テーブルが提供されました。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-294">At this point, more than two application tables are offered, because this mapping uses all the metadata of the connected application that has been assigned to it.</span></span>

8. <span data-ttu-id="f5c5f-295">**キャンセル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-295">Select **Cancel**.</span></span>
9. <span data-ttu-id="f5c5f-296">**検証**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-296">Select **Validate**.</span></span>

<span data-ttu-id="f5c5f-297">これで、このマッピングに割り当てられた接続アプリケーションのメタデータの詳細を使用して、説明されているデータ ソース項目にデータ モデルの要素が正常にバインドされました。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-297">You've now bound elements of the data model to items of the data sources that are described by using details of the metadata of the connected application that has been assigned to this mapping.</span></span>

<span data-ttu-id="f5c5f-298">異なるバージョンのアプリケーションのメタデータを使用してこのモデル マッピングを評価する必要がある場合は、接続されている別のアプリケーションを登録しモデル マッピングに割り当て、新しいメタデータに対してそれを検証します。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-298">When you must evaluate this model mapping by using the metadata of a different version of the application, register another connected application, assign it to this model mapping, and validate it against the new metadata.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f5c5f-299">追加リソース</span><span class="sxs-lookup"><span data-stu-id="f5c5f-299">Additional resources</span></span>

<span data-ttu-id="f5c5f-300">または、Finance and Operations の **RCS で使用できるアプリケーション メタデータを準備する**タスク ガイドを、**ER コンフィギュレーションを使用してアプリケーション メタデータにアクセスする**および RCS のタスク ガイド**接続されているアプリケーションを使用してアプリケーション メタデータにアクセスする**を再生することができます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-300">Alternatively, you can play the **Prepare application metadata that can be used in RCS** task guide in Finance and Operationsas as well as the **Access application metadata by using an ER configuration** and **Access application metadata by using connected applications** task guides in RCS.</span></span> <span data-ttu-id="f5c5f-301">これらのタスク ガイドは、[Dynamics 365 for Finance and Operations 8.1 電子レポート タスク ガイド](https://go.microsoft.com/fwlink/?linkid=2082739)のページからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f5c5f-301">These task guides can be downloaded from the [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page.</span></span>