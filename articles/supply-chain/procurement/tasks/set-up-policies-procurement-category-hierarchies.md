--- 
title: "調達カテゴリ階層に対するポリシーの設定"
description: "カテゴリの製品を発注するルールを設定するには、この手順を使用します。"
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 50764f99be04d27e04047824f870e724336cb452
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a><span data-ttu-id="e174b-103">調達カテゴリ階層に対するポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="e174b-103">Set up policies for procurement category hierarchies</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e174b-104">カテゴリの製品を発注するルールを設定するには、この手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e174b-104">Use this procedure to set up rules for ordering products in a category.</span></span> <span data-ttu-id="e174b-105">ルールは特定の購入ポリシーに定義されます。</span><span class="sxs-lookup"><span data-stu-id="e174b-105">The rules are defined for a specific purchasing policy.</span></span> <span data-ttu-id="e174b-106">カテゴリ アクセス ルールは、従業員が要求を作成したときにどの調達カテゴリにアクセス許可があるかを管理します。</span><span class="sxs-lookup"><span data-stu-id="e174b-106">The category access rule controls which procurement categories employees have access to when they create a requisition.</span></span> <span data-ttu-id="e174b-107">要求が作成されると、購入ポリシーおよびカテゴリ アクセス ルールは、従業員が属している法人および業務単位によって適用され決定されます。</span><span class="sxs-lookup"><span data-stu-id="e174b-107">When a requisition is being created, the purchasing policy and category access rule that should be applied are determined by the legal entity and the operational unit that the employee belongs to.</span></span> <span data-ttu-id="e174b-108">デモ データの会社 USMF でこの手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e174b-108">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="e174b-109">通常、このタスクを実施するのは、購買マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="e174b-109">This task would typically be carried out by a purchasing manager.</span></span>


## <a name="find-the-procurement-policy"></a><span data-ttu-id="e174b-110">調達ポリシーを検索します。</span><span class="sxs-lookup"><span data-stu-id="e174b-110">Find the procurement policy</span></span>
1. <span data-ttu-id="e174b-111">[調達] > [設定] > [ポリシー] > [購入ポリシー] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e174b-111">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="e174b-112">調達ポリシー USMF ポリシーのリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e174b-112">Click the link on the Procurement Policy USMF policy.</span></span>
    * <span data-ttu-id="e174b-113">これは、ルールを追加するポリシーです。</span><span class="sxs-lookup"><span data-stu-id="e174b-113">This is the policy that you’ll add a rule to.</span></span> <span data-ttu-id="e174b-114">これは有効なポリシーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e174b-114">It must be an Active policy.</span></span>  

## <a name="create-a-category-access-rule"></a><span data-ttu-id="e174b-115">カテゴリにアクセスするルールを作成する</span><span class="sxs-lookup"><span data-stu-id="e174b-115">Create a category access rule</span></span>
1. <span data-ttu-id="e174b-116">[カテゴリ アクセス ポリシー ルール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e174b-116">Select the Category access policy rule.</span></span>
    * <span data-ttu-id="e174b-117">[ポリシー ルールの作成] ボタンがグレー表示の場合は、既にカテゴリ アクセスの有効なポリシー ルールが存在するためです。</span><span class="sxs-lookup"><span data-stu-id="e174b-117">If the Create policy rule button is dimmed, it’s because there’s already an active policy rule for Category access.</span></span> <span data-ttu-id="e174b-118">[有効日および有効期限] フィールドを確認し特定した後、それを選択し、[ポリシー ルールの破棄] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e174b-118">Check the Effective and Expiration date fields to determine which it is, then select it, and click Retire policy rule.</span></span> <span data-ttu-id="e174b-119">[ポリシー ルールの作成] ボタンが使用できる場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e174b-119">If the Create policy rule button is available, you don’t need to do anything.</span></span>  
2. <span data-ttu-id="e174b-120">[ポリシー ルールの作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e174b-120">Click Create policy rule.</span></span>
3. <span data-ttu-id="e174b-121">[有効日] フィールドに日時を入力します。</span><span class="sxs-lookup"><span data-stu-id="e174b-121">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="e174b-122">すでに有効な別のルールと、時間を重複させることはできません。</span><span class="sxs-lookup"><span data-stu-id="e174b-122">The time must not overlap with another rule that’s already active.</span></span>  
    * <span data-ttu-id="e174b-123">ルールが適用されるカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="e174b-123">Select a category that the rule will apply to.</span></span> <span data-ttu-id="e174b-124">これがどのカテゴリであるかメモを作成します。これは後で必要になります。</span><span class="sxs-lookup"><span data-stu-id="e174b-124">Make a note of which category this is – you’ll need it later.</span></span> <span data-ttu-id="e174b-125">カテゴリを選択すると、その親カテゴリまたはカテゴリも選択したカテゴリ リストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e174b-125">When you select a category, its parent category or categories will also be added to the Selected categories list.</span></span>  
    * <span data-ttu-id="e174b-126">選択したカテゴリのすべてのサブカテゴリにルールを適用する場合は、[サブカテゴリを含める] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e174b-126">If you want the rule to apply to all subcategories of the selected category, select the Include subcategories check box.</span></span>  
4. <span data-ttu-id="e174b-127">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e174b-127">Click Add.</span></span>
    * <span data-ttu-id="e174b-128">[親ルールを含める] オプションを [はい] に設定する場合、どのポリシー ルールも子カテゴリに対して定義されていないなら、その親カテゴリに対して定義するポリシー ルールはその子カテゴリにも割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e174b-128">If you set the Include parent rule option to Yes, the policy rule that you define for a parent category is also assigned to its child categories, if no policy rule has been defined for the child categories.</span></span>  
5. <span data-ttu-id="e174b-129">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e174b-129">Click OK.</span></span>

## <a name="create-a-category-policy-rule"></a><span data-ttu-id="e174b-130">カテゴリのポリシー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="e174b-130">Create a category policy rule</span></span>
1. <span data-ttu-id="e174b-131">[カテゴリ ポリシー ルール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e174b-131">Select the Category policy rule</span></span>
    * <span data-ttu-id="e174b-132">[ポリシー ルールの作成] ボタンがグレー表示の場合は、有効なポリシー ルールを選択した後、[ポリシー ルールの破棄] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e174b-132">If the Create policy rule button is dimmed, select the active policy rule, and then click Retire policy rule.</span></span>  
2. <span data-ttu-id="e174b-133">[ポリシー ルールの作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e174b-133">Click Create policy rule.</span></span>
3. <span data-ttu-id="e174b-134">[有効日] フィールドに日時を入力します。</span><span class="sxs-lookup"><span data-stu-id="e174b-134">In the Effective date field, enter a date and time.</span></span>
4. <span data-ttu-id="e174b-135">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e174b-135">Click Add.</span></span>
5. <span data-ttu-id="e174b-136">カテゴリ アクセス ルールに使用した同じカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="e174b-136">Select the same category that you used for the Category access rule.</span></span>
6. <span data-ttu-id="e174b-137">[仕入先の選択] フィールドで、オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e174b-137">In the Vendor selection field, select an option.</span></span>
    * <span data-ttu-id="e174b-138">ルールを選択し、請求の作成時に、どのタイプの仕入先がカテゴリに対して選択できるかを管理します。</span><span class="sxs-lookup"><span data-stu-id="e174b-138">Select a rule to control which kind of vendors can be selected for the category when requisitions are created.</span></span>  
7. <span data-ttu-id="e174b-139">[閉じる] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e174b-139">Click Close.</span></span>
    * <span data-ttu-id="e174b-140">定義したポリシー ルールは消費タイプの要求に対応するものです。</span><span class="sxs-lookup"><span data-stu-id="e174b-140">The policy rules that you have defined have been for requisitions of type Consumption.</span></span> <span data-ttu-id="e174b-141">補充タイプの要求のポリシーを定義する場合は、「補充のカテゴリ アクセス ポリシー ルール」というポリシー ルール タイプのルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e174b-141">If you wanted to define policies for requisitions of type Replenishment, you would create a rule for the Policy rule type called “Replenishment category access policy rule”.</span></span>  

