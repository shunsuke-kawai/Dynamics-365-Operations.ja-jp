<span data-ttu-id="2c7da-101">環境間でデータベースをコピーするとき、コピーされたデータベースが完全に機能するには、その前に環境の再プロビジョニング ツールを実行して、すべての Retail コンポーネントを確実に最新にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c7da-101">When copying a database between environments, you will need to run the environment re-provisioning tool before the copied database is fully functional, to ensure that all Retail components are up-to-date.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c7da-102">小売機能はすべての環境に含まれているため、Retail コンポーネントを使用しているかどうかに関係なく、このプロシージャを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2c7da-102">We recommend that you run this procedure whether you are using Retail components or not, because Retail functionality is included in all environments.</span></span> 

<span data-ttu-id="2c7da-103">続行する前に、次の前提条件が満たされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c7da-103">Before you continue, you must make sure that the following prerequisites are met:</span></span>
1. <span data-ttu-id="2c7da-104">2017 年 7 月リリース (7.2 とも呼ばれる) 7.2.11792.56024 にアップグレードする場合は、移行先環境にアプリケーション X++ 修正プログラムを適用してから、その環境内でデータのアップグレードを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c7da-104">If you are upgrading to the July 2017 release (also known as 7.2) 7.2.11792.56024, apply the following application X++ hotfixes in the destination environment before running the data upgrade in that environment.</span></span> <span data-ttu-id="2c7da-105">これにより、データ アップグレード中の各種エラーの発生を防止します。</span><span class="sxs-lookup"><span data-stu-id="2c7da-105">These will prevent various errors occuring during the data upgrade:</span></span>

    - <span data-ttu-id="2c7da-106">KB 4036156 - Retail マイナー バージョン アップグレード - 'バリアント番号順序が設定されていません。'</span><span class="sxs-lookup"><span data-stu-id="2c7da-106">KB 4036156 - Retail minor version upgrade - 'Variant number sequence is not set.'</span></span> <span data-ttu-id="2c7da-107">この修正プログラム パッケージには、KB 4035399 および KB 4035751 も含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c7da-107">This fix package also includes KB 4035399 and KB 4035751.</span></span> <span data-ttu-id="2c7da-108">このパッケージを使用するには、最低でも Platform Update 9 が必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c7da-108">Note that you must have a minimum of Platform Update 9 to use this package.</span></span> <span data-ttu-id="2c7da-109">確信が持てない場合は、最新のバイナリをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="2c7da-109">If you are unsure, install the latest binaries.</span></span>
    
2. <span data-ttu-id="2c7da-110">Microsoft Dynamics AX 2012 からアップグレードする場合は、データ アップグレードを実行する前に、移行先の環境に次のアプリケーション X++ 修正プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2c7da-110">If you are upgrading from Microsoft Dynamics AX 2012, install the following application X++ fixes in the destination environment before you run the data upgrade:</span></span>
    - <span data-ttu-id="2c7da-111">KB 4033183 - Dynamics AX 2012 R2 または Dynamics AX 2012 R3 Pre-CU8 non-retail アップグレードは、dbo.RETAILTILLLAYOUTZONE のオブジェクトが存在しないため失敗しました。</span><span class="sxs-lookup"><span data-stu-id="2c7da-111">KB 4033183 - Dynamics AX 2012 R2 or Dynamics AX 2012 R3 Pre-CU8 non-retail upgrade fails with Object not found for dbo.RETAILTILLLAYOUTZONE.</span></span>
    - <span data-ttu-id="2c7da-112">KB 4040692 - Microsoft Dynamics 365 for Operations 7.2 への Dynamics AX 2012 R3 のアップグレードは、SalesLineIdx に RetailSalesLine の重複インデックスが存在するため失敗しました。</span><span class="sxs-lookup"><span data-stu-id="2c7da-112">KB 4040692 - Dynamics AX 2012 R3 to Microsoft Dynamics 365 for Operations 7.2 upgrade fails on RetailSalesLine duplicate index on SalesLineIdx.</span></span>
    - <span data-ttu-id="2c7da-113">KB 4035490 - GeneralJournalAccountEntry MainAccount フィールドのアップグレード スクリプトに関するパフォーマンスの問題。</span><span class="sxs-lookup"><span data-stu-id="2c7da-113">KB 4035490 - Performance issue with GeneralJournalAccountEntry MainAccount field upgrade script.</span></span>


<span data-ttu-id="2c7da-114">以下の手順に従って、環境再プロビジョニング ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c7da-114">Follow these steps to run the Environment reprovisioning tool.</span></span>

1. <span data-ttu-id="2c7da-115">共有アセット ライブラリで、**ソフトウェア配置可能なパッケージ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c7da-115">In the Shared asset library, select **Software deployable package**.</span></span>
2. <span data-ttu-id="2c7da-116">環境再プロビジョニング ツールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2c7da-116">Download the Environment reprovisioning tool.</span></span>
3. <span data-ttu-id="2c7da-117">自身のプロジェクトのアセット ライブラリで、**ソフトウェア配置可能パッケージ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c7da-117">In the asset library for your project, select **Software deployable package**.</span></span>
4. <span data-ttu-id="2c7da-118">**新規作成** コマンドを選択して、新しいパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2c7da-118">Select **New** to create a new package.</span></span>
5. <span data-ttu-id="2c7da-119">パッケージの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="2c7da-119">Enter a name and description for the package.</span></span> <span data-ttu-id="2c7da-120">**環境再プロビジョニング ツール** をパッケージ名として使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c7da-120">You can use **Environment reprovisioning tool** as the package name.</span></span>
6. <span data-ttu-id="2c7da-121">先ほどダウンロードしたパッケージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="2c7da-121">Upload the package that you downloaded earlier.</span></span>
7. <span data-ttu-id="2c7da-122">ターゲット環境の **環境の詳細** ページで、**管理** > **更新プログラムを適用** を順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2c7da-122">On the **Environment details** page for your target environment, select **Maintain** > **Apply updates**.</span></span>
8. <span data-ttu-id="2c7da-123">先ほどアップロードした環境再プロビジョニング ツールを選択し、**適用** を選択してパッケージを適用します。</span><span class="sxs-lookup"><span data-stu-id="2c7da-123">Select the Environment reprovisioning tool that you uploaded earlier, and then select **Apply** to apply the package.</span></span>
9. <span data-ttu-id="2c7da-124">パッケージの配置の進捗を監視します。</span><span class="sxs-lookup"><span data-stu-id="2c7da-124">Monitor the progress of the package deployment.</span></span> 

<span data-ttu-id="2c7da-125">配置可能パッケージを適用する方法の詳細については、[配置可能パッケージの適用](../deployment/create-apply-deployable-package.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c7da-125">For more information about how to apply a deployable package, see [Apply a deployable package](../deployment/create-apply-deployable-package.md).</span></span> <span data-ttu-id="2c7da-126">配置可能パッケージを手動で適用する方法の詳細については、[配置可能パッケージのインストール](../deployment/install-deployable-package.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c7da-126">For more information about how to manually apply a deployable package, see [Install a deployable package](../deployment/install-deployable-package.md).</span></span>