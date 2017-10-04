---
title: "リーン組織のモデリング"
description: "この記事は、リーン組織のモデリングにおける重要な概念に関する情報を提供します。"
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow, PlanActivity
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53141
ms.assetid: 4f272f2f-ec2c-4b0d-a652-00a63b719b9e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e5f96b3eb0df3e35486a08e55439fb59e3479fac
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="modeling-a-lean-organization"></a><span data-ttu-id="f98e4-103">リーン組織のモデリング</span><span class="sxs-lookup"><span data-stu-id="f98e4-103">Modeling a lean organization</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f98e4-104">この記事は、リーン組織のモデリングにおける重要な概念に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f98e4-104">The article provides information about the key concepts in modeling a lean organization.</span></span> 

<span data-ttu-id="f98e4-105">通常、リーン生産のシナリオは、単なる無関係なかんばんルールや材料の供給ポリシーの寄せ集めではありません。</span><span class="sxs-lookup"><span data-stu-id="f98e4-105">Typically, a lean manufacturing scenario is more than just a collection of unrelated kanban rules or material supply policies.</span></span> <span data-ttu-id="f98e4-106">特定の生産シナリオや供給シナリオに関する作業セルや場所での材料や製品の流れは、プロセスや転送活動のシーケンスまたは小さいネットワークとして表すことができます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-106">The flow of material and products throughout work cells and locations for a specific production or supply scenario can be described as a sequence or small network of process or transfer activities.</span></span> <span data-ttu-id="f98e4-107">このシーケンスやネットワークは、生産フローと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-107">This sequence or network is known as a production flow.</span></span>

## <a name="production-flows-in-lean-manufacturing"></a><span data-ttu-id="f98e4-108">リーン生産の生産フロー</span><span class="sxs-lookup"><span data-stu-id="f98e4-108">Production flows in lean manufacturing</span></span>
<span data-ttu-id="f98e4-109">製造オーダーに基づいた生産のシナリオでは、材料は、特定の製造オーダーに発行されます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-109">In production scenarios that are based on production orders, material is issued to a specific production order.</span></span> <span data-ttu-id="f98e4-110">部品表 (BOM) と工順に基づいた一連の工程の間に、製品は供給場所で生産され、最終的に受け取られます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-110">During a sequence of operations that is based on a bill of materials (BOM) and routes, products are created and are finally received at the supplied location.</span></span> <span data-ttu-id="f98e4-111">製造オーダーのスループットの時間は、分から週までと異なります。</span><span class="sxs-lookup"><span data-stu-id="f98e4-111">The throughput time of production orders varies from minutes to weeks.</span></span> <span data-ttu-id="f98e4-112">すべての関連する原価、材料、労務は、製造オーダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-112">All related cost, material, and labor are accumulated on the production order.</span></span> 

<span data-ttu-id="f98e4-113">バッチ製造が原因で発生するワークセンター間の出荷のリードタイムと過剰な在庫を減らすために、リーン生産は、製造と倉庫の補充において、かんばん補充およびかんばんスーパーマーケットを導入します。</span><span class="sxs-lookup"><span data-stu-id="f98e4-113">To reduce the delivery lead times and excess inventory between work centers that batch production causes, lean manufacturing introduces kanban replenishment and supermarkets in manufacturing and warehouse replenishment.</span></span> <span data-ttu-id="f98e4-114">通常、これらの機能は部分的に独立したかんばんサイクルの生産を阻みます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-114">Typically, these features disrupt the production of partially independent kanban cycles.</span></span> <span data-ttu-id="f98e4-115">半完成品のかんばんの補充は、もはや完成品の発注によっては行われません。</span><span class="sxs-lookup"><span data-stu-id="f98e4-115">The replenishment of a kanban for a semi-finished product is no longer triggered by an order for a finished product.</span></span> 

<span data-ttu-id="f98e4-116">Microsoft Dynamics 365 for Finance and Operations、Enterprise edition で提案されるさまざまなかんばんのシナリオの生産とコストのコンテキストを再構築するために、活動ベースの生産フローが、リーン生産のバックボーンとして導入されました。</span><span class="sxs-lookup"><span data-stu-id="f98e4-116">To re-establish a production and cost context for the various kanban scenarios that are proposed in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, activity-based production flows have been introduced as the backbone of lean manufacturing.</span></span> <span data-ttu-id="f98e4-117">すべてのかんばんルールは、この定義された構造によります。</span><span class="sxs-lookup"><span data-stu-id="f98e4-117">All kanban rules refer to this predefined structure.</span></span> <span data-ttu-id="f98e4-118">活動ベースのモデルでは、Dynamics AX のリーン生産の以前のバージョンがサポートしていたものより広範囲のシナリオの設定にサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f98e4-118">The activity-based model supports the setup of a wider range of scenarios than previous versions of Lean manufacturing for Dynamics AX supported.</span></span> <span data-ttu-id="f98e4-119">ただし、このモデルでは、すべてのシナリオが同じ活動ベースのユーザー インターフェイスを使用するため、作業現場の作業がより複雑になることはありません。</span><span class="sxs-lookup"><span data-stu-id="f98e4-119">However, this model doesn't add complexity for the shop floor workers, because all scenarios use the same activity-based user interface.</span></span>

## <a name="semi-finished-products-non-bom-levels"></a><span data-ttu-id="f98e4-120">半完成品 (非 BOM レベル)</span><span class="sxs-lookup"><span data-stu-id="f98e4-120">Semi-finished products (non-BOM levels)</span></span>
<span data-ttu-id="f98e4-121">Dynamics AX のリーン生産は、在庫製品と半完成品のかんばんを 1 つのフレームワークに統合し、すべてのケースにおいて同一のユーザー エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f98e4-121">Lean manufacturing for Dynamics AX integrates kanbans for inventoried products and semi-finished products in a single framework, and therefore offers a unified user experience for all cases.</span></span> <span data-ttu-id="f98e4-122">この構造のため、かんばんを半完成品に使用できるようにするために追加の BOM レベルを導入する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f98e4-122">Because of this architecture, additional BOM levels no longer have to be introduced to enable kanbans to be used for semi-finished products.</span></span> <span data-ttu-id="f98e4-123">また、この構造は在庫トランザクションを最小限にします。</span><span class="sxs-lookup"><span data-stu-id="f98e4-123">This architecture also helps reduce inventory transactions to a minimum.</span></span>

## <a name="products-and-material-in-work-in-progress"></a><span data-ttu-id="f98e4-124">進行中の作業の製品および材料</span><span class="sxs-lookup"><span data-stu-id="f98e4-124">Products and material in work in progress</span></span>
<span data-ttu-id="f98e4-125">リーン生産において、バッチ サイズを単一のフローの最適な状態に下げることにより、各ピッキング プロセスやかんばんの登録が消費品目のトランザクションを起こす場合、在庫トランザクションが劇的に増加する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f98e4-125">The reduction of batch sizes to the ideal state of a single piece flow in lean manufacturing can cause a dramatic increase in inventory transactions if each picking process or kanban registration causes transactions for the consumed items.</span></span> <span data-ttu-id="f98e4-126">この生産フロー構造により、倉庫または配送処理単位サイズでの引き取りかんばんで、生産フローに対する材料の移動ができます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-126">The production flow architecture allows for the transfer of material to the production flow, together with the withdrawal kanbans in storage or transport handling unit sizes.</span></span> <span data-ttu-id="f98e4-127">払出された材料の額は、生産フローに関連した仕掛品 (WIP) 勘定に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-127">The value of the issued material is added to the work in progress (WIP) account that is related to the production flow.</span></span> <span data-ttu-id="f98e4-128">この動作は、製造オーダーに発行される材料の動作に類似しています。</span><span class="sxs-lookup"><span data-stu-id="f98e4-128">This behavior resembles the behavior for material that is issued to a production order.</span></span> <span data-ttu-id="f98e4-129">同じ原則は、製品および半完成品に適用できます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-129">The same principle can be applied to products and semi-finished products.</span></span> <span data-ttu-id="f98e4-130">これらの製品が生産フロー内で作成、転送、または消費されていない場合、在庫トランザクションはオプションです。</span><span class="sxs-lookup"><span data-stu-id="f98e4-130">Unless these products are created, transferred, or consumed within a production flow, inventory transactions are optional.</span></span> <span data-ttu-id="f98e4-131">製品が在庫に転記されると、生産フローの仕掛品勘定は、関連する標準コストにより減算されます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-131">After the products are posted to inventory, the WIP account for the production flow is reduced by deducting by the related standard cost.</span></span>

## <a name="value-streams-and-value-stream-mapping"></a><span data-ttu-id="f98e4-132">バリュー ストリームとバリュー ストリームのマッピング</span><span class="sxs-lookup"><span data-stu-id="f98e4-132">Value streams and value stream mapping</span></span>
<span data-ttu-id="f98e4-133">Dynamics AX のリーン生産構造は、ウォーマックとジョーンズが定めた 5 つのリーン原則に基づいています。すなわち、顧客の価値、バリュー ストリーム、フロー、プル、そして完成度です。</span><span class="sxs-lookup"><span data-stu-id="f98e4-133">The architecture of Lean manufacturing for Dynamics AX is inspired by the five Lean principles that were formulated by Womack and Jones: Customer value, Value stream, flow, pull, and perfection.</span></span> <span data-ttu-id="f98e4-134">実際の製造業においてリーン生産のソリューションを導入するためのよい方法は、バリュー ストリーム マッピング (VSM) です。</span><span class="sxs-lookup"><span data-stu-id="f98e4-134">One approved method for implementing lean manufacturing solutions in the physical world of manufacturing is value stream mapping (VSM).</span></span> <span data-ttu-id="f98e4-135">この方法は、リーン生産研究所でロザーとシュークにより発行された「Learning to See」の中で紹介されました。</span><span class="sxs-lookup"><span data-stu-id="f98e4-135">This method was introduced by Rother and Shook in their publication “Learning to See” at the Lean Manufacturing Institute.</span></span> 

<span data-ttu-id="f98e4-136">Dynamics AX で、未来型のバリュー ストリームは、生産フロー バージョンとしてモデル化できます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-136">In Dynamics AX, the future-state value stream can be modeled as a production flow version.</span></span> <span data-ttu-id="f98e4-137">バリュー ストリームのすべてのプロセスがプロセス活動としてモデル化されます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-137">All processes of the value stream are modeled as process activities.</span></span> <span data-ttu-id="f98e4-138">転送ステータスを登録する必要があるか、または在庫ピッキングまたは連結出荷との統合が必要な場合は、移動や転送は転送活動としてモデル化できます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-138">Movements or transfers can be modeled as transfer activities if the transfer status must be registered, or if integration with inventory picking or consolidated shipments is required.</span></span> 

<span data-ttu-id="f98e4-139">バリュー ストリーム自体は、Dynamics AX の作業単位としてモデル化されます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-139">The value stream itself is modeled as an operating unit in Dynamics AX.</span></span> <span data-ttu-id="f98e4-140">したがって、バリュー ストリームは財務分析コードとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-140">Therefore, the value stream can be used as a financial dimension.</span></span>

## <a name="costing-for-lean-manufacturing-based-on-the-production-flow"></a><span data-ttu-id="f98e4-141">生産フローに基づいたリーン生産の原価計算</span><span class="sxs-lookup"><span data-stu-id="f98e4-141">Costing for lean manufacturing based on the production flow</span></span>
<span data-ttu-id="f98e4-142">生産フローの原価の定期的な連結により、関連する仕掛品勘定を修正し、生産フローによって供給される製品 の差異を決定できます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-142">The periodic consolidation of the cost for a production flow corrects the related WIP account and enables variances to be determined for the products that are supplied by the production flow.</span></span>

## <a name="continuous-improvement"></a><span data-ttu-id="f98e4-143">継続的な改善</span><span class="sxs-lookup"><span data-stu-id="f98e4-143">Continuous improvement</span></span>
<span data-ttu-id="f98e4-144">継続的な改善をよりよくサポートするために、生産フローは、時間が有効なバージョンになっています。</span><span class="sxs-lookup"><span data-stu-id="f98e4-144">To better support continuous improvement, the production flows are implemented in time-effective versions.</span></span> <span data-ttu-id="f98e4-145">したがって、既存の生産フロー バージョンは、関連するすべてのかんばんルールとともに生産フローの今後のバージョンにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-145">Therefore, an existing production flow version, together with all related kanban rules, can be copied to a future version of the production flow.</span></span> <span data-ttu-id="f98e4-146">また、未来型の生産フローは、生産のために検証して有効にする前にモデル化できます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-146">In addition, the future-state production flow can be modeled before it's validated and activated for production.</span></span> <span data-ttu-id="f98e4-147">移行日以降の材料のシームレスなフローを保証するため、古い生産フロー バージョンの既存のかんばんは自動的に新しいバージョンに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-147">To help guarantee a seamless material flow on the transition date and beyond, existing kanbans from old production flow versions are automatically related to the new version.</span></span>

## <a name="simplicity"></a><span data-ttu-id="f98e4-148">シンプルさ</span><span class="sxs-lookup"><span data-stu-id="f98e4-148">Simplicity</span></span>
<span data-ttu-id="f98e4-149">Dynamics AX のリーン生産の導入には、単一のスケーラブルな構造の中で、シンプルおよび複雑な生産シナリオのモデル化を可能にする生産フローおよび活動のアプローチを用意しています。</span><span class="sxs-lookup"><span data-stu-id="f98e4-149">For the implementation of Lean manufacturing for Dynamics AX, we choose a production flow and activity approach that enables simple and complex production scenarios to be modeled in a single scalable architecture.</span></span> <span data-ttu-id="f98e4-150">活動のコンセプトを詳しく調べると、作業現場およびロジスティクスの作業者などのユーザーが必要とする新たなシンプルさが見えてきます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-150">A closer look at the activity concept reveals a new simplicity for those users who require it: the shop floor and logistics workers.</span></span> <span data-ttu-id="f98e4-151">在庫トランザクションではなく活動ベースのジョブに関するレポートにより、複雑なビジネスの中で行われる様々な形態のリーン生産のすべてが、統一感のあるユーザー インターフェイスによってしかるべきところへ、つまりリーン生産のバックボーンとしての生産フローへと転送されます。</span><span class="sxs-lookup"><span data-stu-id="f98e4-151">By reporting against activity-based jobs instead of inventory transactions, a unified user interface for all lean manufacturing variants transfers the business complexity from the user interface to where it belongs: the production flow as the backbone of lean manufacturing.</span></span>



