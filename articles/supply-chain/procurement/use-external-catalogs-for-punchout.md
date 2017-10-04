---
title: "パンチアウト eProcurement の外部カタログの使用"
description: "このトピックでは、外部カタログを使用して要求を作成し送信する方法について説明します。"
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 035c5d15e5508c78dd66a349defd534bfecc96bb
ms.contentlocale: ja-jp
ms.lasthandoff: 07/18/2017

---

# <a name="use-external-catalogs-for-punchout-eprocurement"></a><span data-ttu-id="e32f0-103">パンチアウト eProcurement の外部カタログの使用</span><span class="sxs-lookup"><span data-stu-id="e32f0-103">Use external catalogs for PunchOut eProcurement</span></span>
<span data-ttu-id="e32f0-104">パンチアウト e-procurement の外部カタログを使用すると、自身のマスター データで仕入先の製品に関する情報を管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e32f0-104">By using external catalogs for PunchOut e-procurement, you don't have to maintain information about your vendors' products in your own master data.</span></span> <span data-ttu-id="e32f0-105">代わりに、仕入先の Web サイトのショッピング カートが正しい製品情報を持つ要求明細行に変換されます。</span><span class="sxs-lookup"><span data-stu-id="e32f0-105">Instead, the shopping cart on a vendor's website is converted to requisition lines that have the correct product information.</span></span> 

<span data-ttu-id="e32f0-106">自身のマスター データでは仕入先の製品の説明や価格を管理しないようにします。</span><span class="sxs-lookup"><span data-stu-id="e32f0-106">You should avoid maintaining the descriptions and prices of your vendors’ products in your own product master data.</span></span> <span data-ttu-id="e32f0-107">代わりに、パンチアウト e-procurement の外部カタログを使用します。</span><span class="sxs-lookup"><span data-stu-id="e32f0-107">Instead, use external catalogs for PunchOut e-procurement.</span></span> <span data-ttu-id="e32f0-108">その後、従業員は要求を作成するときに仕入先の外部カタログ サイトに「パンチアウト」できます (つまり、システムを離れて仕入先のサイトに移動します)。</span><span class="sxs-lookup"><span data-stu-id="e32f0-108">Then, when employees create requisitions, they can “punch out” to a vendor’s external catalog site (in other words, they leave your system and go to the vendor’s site).</span></span> <span data-ttu-id="e32f0-109">仕入先の Web サイトでショッピング カートに追加される製品は、要求明細行に変換できます。</span><span class="sxs-lookup"><span data-stu-id="e32f0-109">The products that are added to the shopping cart on the vendor’s website can then be converted to requisition lines.</span></span> <span data-ttu-id="e32f0-110">そのため、製品 ID、名前、価格などの正しい製品情報を取得することになります。</span><span class="sxs-lookup"><span data-stu-id="e32f0-110">Therefore, you get the correct product information: product ID, name, price, and so on.</span></span>

<span data-ttu-id="e32f0-111">外部カタログを使用するには、従業員は [**自分の購買要求**] ページで要求を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e32f0-111">To use external catalogs, an employee must create a requisition on the **My purchase requisitions** page.</span></span>

<span data-ttu-id="e32f0-112">要求を作成する従業員は、要求の作成者と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e32f0-112">The employee who creates a requisition is referred to as the preparer of the requisition.</span></span> <span data-ttu-id="e32f0-113">作成者として、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e32f0-113">As a preparer, you can complete the following tasks.</span></span>

<span data-ttu-id="e32f0-114">**外部カタログ** 明細行アクションを使用して、指定された要求者、購買組織、および受取作業単位に使用可能なすべての外部カタログを含むページを開きます。</span><span class="sxs-lookup"><span data-stu-id="e32f0-114">Use the **External catalogs** line action to open a page that includes all external catalogs that are available for the specified requester, buying legal entity, and receiving operating unit.</span></span>

<span data-ttu-id="e32f0-115">アクセス許可に応じて、要求者、購買組織、および受取作業単位を変更します。</span><span class="sxs-lookup"><span data-stu-id="e32f0-115">Depending on your permissions, change the requester, buying legal entity, and receiving operating unit.</span></span> <span data-ttu-id="e32f0-116">それらの値の変更により、要求者に使用可能な外部カタログのリストが変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e32f0-116">A change in those values might change the list of external catalogs that are available to a requester.</span></span> <span data-ttu-id="e32f0-117">使用可能な外部カタログは、購買組織あるいは受取作業単位の現在有効な購買ポリシーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e32f0-117">The external catalogs that are available depend on the current active purchasing policies for the buying legal entity or the receiving operating unit.</span></span> <span data-ttu-id="e32f0-118">これらのポリシーは、特定の調達カテゴリへのアクセスを許可したり禁止したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e32f0-118">These policies can allow or prevent access to specific procurement categories.</span></span> <span data-ttu-id="e32f0-119">したがって、これらの調達カテゴリにマップされている外部カタログのリストが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e32f0-119">Therefore, the list of external catalogs that are mapped to these procurement categories can be affected.</span></span>

<span data-ttu-id="e32f0-120">ポリシーの詳細については、「[購買ポリシー](../procurement/purchase-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e32f0-120">For more information about policies, see [Purchasing policies](../procurement/purchase-policies.md).</span></span>

- <span data-ttu-id="e32f0-121">特定の調達カテゴリの外部カタログを検索するには、カタログ検索フィールドにテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="e32f0-121">To find external catalogs for specific procurement categories, enter text in the catalog search field.</span></span>
- <span data-ttu-id="e32f0-122">仕入先の Web サイトで仕入先の外部カタログから製品を追加するには、その外部カタログをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e32f0-122">To add products from a vendor’s external catalog on the vendor’s website, click the external catalog.</span></span> <span data-ttu-id="e32f0-123">その後、製品をショッピング カートに追加し、チェックアウトします。</span><span class="sxs-lookup"><span data-stu-id="e32f0-123">Then add products to the shopping cart, and check out.</span></span> <span data-ttu-id="e32f0-124">ショッピング カート明細行が Microsoft Dynamics 365 に転送されます。</span><span class="sxs-lookup"><span data-stu-id="e32f0-124">The shopping cart lines will be transferred to Microsoft Dynamics 365.</span></span>

<span data-ttu-id="e32f0-125">調達カテゴリの複数のオプションがある場合は、要求に明細行を追加する前に、正しい調達カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="e32f0-125">If there are multiple options for procurement categories, select the correct procurement category before you add the lines to the requisition.</span></span>
<span data-ttu-id="e32f0-126">明細行が要求に追加されると、外部カタログを使用せずにさらに明細行を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e32f0-126">After lines have been added to a requisition, you can add more lines without using external catalogs.</span></span> <span data-ttu-id="e32f0-127">または、外部カタログを使用して明細行の追加を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="e32f0-127">Alternatively, you can continue to use external catalogs to add lines.</span></span>

<span data-ttu-id="e32f0-128">要求が準備できたら、[**ワークフロー**] > [**送信**] アクションを使用して承認のためにその要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="e32f0-128">When the requisition is ready, use the **Workflow** > **Submit** action to submit it for approval.</span></span>
