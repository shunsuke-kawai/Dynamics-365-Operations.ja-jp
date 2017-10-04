--- 
title: "コンフィギュレーション可能な製品の属性ベースの価格決定の設定"
description: "この手順では、属性ベースの価格を設定する方法を示します。"
author: YuyuScheller
manager: AnnBe
ms.date: 10/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: 88402bef6fd5dad38a74795cd31a4046085d6db7
ms.contentlocale: ja-jp
ms.lasthandoff: 09/14/2017

---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="15c4d-103">コンフィギュレーション可能な製品の属性ベースの価格決定の設定</span><span class="sxs-lookup"><span data-stu-id="15c4d-103">Set up attribute-based pricing for configurable products</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="15c4d-104">この手順では、属性ベースの価格を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-104">This procedure shows how to set up attribute-based pricing.</span></span> <span data-ttu-id="15c4d-105">前提条件として、1 つ以上のコンポーネントと属性を持つ製品コンフィギュレーション モデルが必要です。</span><span class="sxs-lookup"><span data-stu-id="15c4d-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="15c4d-106">この例では、デモ データの会社 USMF のハイエンド スピーカーの製品モデルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="15c4d-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="15c4d-107">通常、製品マネージャーがこの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="15c4d-108">新しい価格モデルの作成</span><span class="sxs-lookup"><span data-stu-id="15c4d-108">Create a new price model</span></span>
1. <span data-ttu-id="15c4d-109">[製品バリアント モデルの定義] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15c4d-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="15c4d-110">[製品コンフィギュレーション モデル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15c4d-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="15c4d-111">リストで、名前のリンクをクリックせずにハイエンド スピーカーの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-111">In the list, select the High End Speaker line, but don’t click the link for the name.</span></span>
4. <span data-ttu-id="15c4d-112">[アクション] ウィンドウで、[モデル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15c4d-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="15c4d-113">[価格モデル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15c4d-113">Click Price models.</span></span>
6. <span data-ttu-id="15c4d-114">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15c4d-114">Click New.</span></span>
7. <span data-ttu-id="15c4d-115">[価格モデル名] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-115">In the Price model name field, type a value.</span></span>
    * <span data-ttu-id="15c4d-116">容易にモデルを識別できる名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="15c4d-117">[説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-117">In the Description field, type a value.</span></span>
9. <span data-ttu-id="15c4d-118">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15c4d-118">Click Save.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="15c4d-119">価格要素の追加</span><span class="sxs-lookup"><span data-stu-id="15c4d-119">Add price elements</span></span>
1. <span data-ttu-id="15c4d-120">[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15c4d-120">Click Edit.</span></span>
    * <span data-ttu-id="15c4d-121">製品モデルの各コンポーネントごとに、価格の式のルールの基準価格要素および任意の数字を設定できます。</span><span class="sxs-lookup"><span data-stu-id="15c4d-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="15c4d-122">異なる通貨でも価格を追加できます。</span><span class="sxs-lookup"><span data-stu-id="15c4d-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="15c4d-123">[基準価格の式] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-123">In the Base price expression field, type a value.</span></span>
    * <span data-ttu-id="15c4d-124">たとえば、「100」と入力します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-124">For example, type 100.</span></span>   <span data-ttu-id="15c4d-125">基準価格の式は、数値あるいは 1 つ以上の属性を含む算術計算で構成できます。</span><span class="sxs-lookup"><span data-stu-id="15c4d-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="15c4d-126">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15c4d-126">Click Add.</span></span>
4. <span data-ttu-id="15c4d-127">[名前] フィールドに、「シタン」と入力します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-127">In the Name field, type ‘Rosewood’.</span></span>
    * <span data-ttu-id="15c4d-128">価格の式の名前は、価格要素が表す内容を識別する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="15c4d-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="15c4d-129">この例では、シタンのスピーカー キャビネットの仕上げオプションに対する価格要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="15c4d-130">[条件の編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15c4d-130">Click Edit condition.</span></span>
    * <span data-ttu-id="15c4d-131">価格の条件によって、属性の特定の組み合わせがある場合にのみ、価格の式の要素を確実に販売価格に含められます。</span><span class="sxs-lookup"><span data-stu-id="15c4d-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="15c4d-132">[ConstraintBody] フィールドで、「CabinetFinish=="シタン"」と入力します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-132">In the ConstraintBody field, enter 'CabinetFinish=="Rosewood"'.</span></span>
7. <span data-ttu-id="15c4d-133">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15c4d-133">Click OK.</span></span>
8. <span data-ttu-id="15c4d-134">[式フィールド] に値を入力します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-134">In the Expression field, type a value.</span></span>
    * <span data-ttu-id="15c4d-135">たとえば、「50」と入力します。</span><span class="sxs-lookup"><span data-stu-id="15c4d-135">For example, type 50.</span></span>  
9. <span data-ttu-id="15c4d-136">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="15c4d-136">Close the page.</span></span>
10. <span data-ttu-id="15c4d-137">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="15c4d-137">Close the page.</span></span>

