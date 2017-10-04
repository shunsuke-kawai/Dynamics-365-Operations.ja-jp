--- 
title: "付帯サービス請求金額としての燃料インデックスの配送業者への関連付け"
description: "このガイドでは、付帯サービスの割り当て、配送業者付帯サービス請求金額、燃料割増金の付帯サービス マスターの作成方法、および配送業者の燃料インデックスの配送業者への割り当て方法を示します。"
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a2b8534231c5fa50b1e0f709e09d318bb8202a43
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a><span data-ttu-id="547d3-103">付帯サービス請求金額としての燃料インデックスの配送業者への関連付け</span><span class="sxs-lookup"><span data-stu-id="547d3-103">Associate a fuel index with a carrier as an accessorial charge</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="547d3-104">このガイドでは、付帯サービスの割り当て、配送業者付帯サービス請求金額、燃料割増金の付帯サービス マスターの作成方法、および配送業者の燃料インデックスの配送業者への割り当て方法を示します。</span><span class="sxs-lookup"><span data-stu-id="547d3-104">This guide shows how to create an accessorial assignment, carrier accessorial charge, accessorial master for fuel surcharge, and associate a carrier fuel index with a carrier.</span></span> <span data-ttu-id="547d3-105">このガイドを実行する前に、配送業者の燃料インデックスを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="547d3-105">You need to have set up a carrier fuel index before you run this guide.</span></span> <span data-ttu-id="547d3-106">これを行うには、「配送業者の燃料インデックスの設定」ガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="547d3-106">You can use the “Set up a carrier fuel index” guide to do this.</span></span> <span data-ttu-id="547d3-107">これらの設定タスクは、通常、物流マネージャーが実行します。</span><span class="sxs-lookup"><span data-stu-id="547d3-107">These setup tasks are typically done by a Logistics manager.</span></span> <span data-ttu-id="547d3-108">この手順の作成に使用されたデモ データの会社は、USMF です。</span><span class="sxs-lookup"><span data-stu-id="547d3-108">The demo data used to create this procedure is USMF.</span></span>


## <a name="create-an-accessorial-master"></a><span data-ttu-id="547d3-109">付帯サービス マスターの作成</span><span class="sxs-lookup"><span data-stu-id="547d3-109">Create an accessorial master</span></span>
1. <span data-ttu-id="547d3-110">[輸送管理] > [設定] > [評価] > [付帯サービス マスター] に移動します。</span><span class="sxs-lookup"><span data-stu-id="547d3-110">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="547d3-111">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-111">Click New.</span></span>
3. <span data-ttu-id="547d3-112">[配送付帯サービス マスター] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="547d3-112">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="547d3-113">[名前] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="547d3-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="547d3-114">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-114">Click Save.</span></span>

## <a name="create-a-carrier-accessorial-charge"></a><span data-ttu-id="547d3-115">配送業者付帯サービス請求金額の作成</span><span class="sxs-lookup"><span data-stu-id="547d3-115">Create a carrier accessorial charge</span></span>
1. <span data-ttu-id="547d3-116">[輸送管理] > [設定] > [評価] > [輸送業者の付帯サービス請求金額] に移動します。</span><span class="sxs-lookup"><span data-stu-id="547d3-116">Go to Transportation management > Setup > Rating > Carrier accessorial charges.</span></span>
2. <span data-ttu-id="547d3-117">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-117">Click New.</span></span>
3. <span data-ttu-id="547d3-118">[配送付帯サービス ID] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="547d3-118">In the Carrier accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="547d3-119">[出荷の配送業者] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="547d3-119">In the Shipping carrier field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="547d3-120">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="547d3-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="547d3-121">この例では、トラックの配送業者を選択します。</span><span class="sxs-lookup"><span data-stu-id="547d3-121">In this example, choose Truck Carrier.</span></span>  
6. <span data-ttu-id="547d3-122">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="547d3-123">[配送サービス] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="547d3-123">In the Carrier service field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="547d3-124">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-124">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="547d3-125">[配送付帯サービス マスター] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="547d3-125">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="547d3-126">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="547d3-126">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="547d3-127">この例では、新しく作成された配送付帯サービス マスターを選択します。</span><span class="sxs-lookup"><span data-stu-id="547d3-127">In this example, choose the newly created Accessorial master.</span></span>  
11. <span data-ttu-id="547d3-128">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-128">Click Save.</span></span>

## <a name="create-an-accessorial-assignment"></a><span data-ttu-id="547d3-129">付帯サービス割り当ての作成</span><span class="sxs-lookup"><span data-stu-id="547d3-129">Create an accessorial assignment</span></span>
1. <span data-ttu-id="547d3-130">[付帯サービス割り当て] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-130">Click Accessorial assignments.</span></span>
2. <span data-ttu-id="547d3-131">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-131">Click New.</span></span>
3. <span data-ttu-id="547d3-132">[名前] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="547d3-132">In the Name field, type a value.</span></span>
4. <span data-ttu-id="547d3-133">[基準] セクションの展開を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="547d3-133">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="547d3-134">基準では、燃料割増金を常に適用できます。また、この例の場合には、特定の地域内でのみ適用することができます。</span><span class="sxs-lookup"><span data-stu-id="547d3-134">In the criteria, you can choose to always apply the fuel surcharge or for this example choose that it only applies within a certain region.</span></span>  
5. <span data-ttu-id="547d3-135">[発送元郵便番号] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="547d3-135">In the ZIP/postal code from field, type a value.</span></span>
6. <span data-ttu-id="547d3-136">[配送先郵便番号] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="547d3-136">In the ZIP/postal code to field, type a value.</span></span>
7. <span data-ttu-id="547d3-137">[計算] セクションの展開を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="547d3-137">Toggle the expansion of the Calculation section.</span></span>
    * <span data-ttu-id="547d3-138">計算セクションでは、燃料割増金の計算方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="547d3-138">In the calculation section you can specify how to calculate the fuel surcharge.</span></span> <span data-ttu-id="547d3-139">この計算は、計算を基準として選択した付帯サービス単位によって異なります。</span><span class="sxs-lookup"><span data-stu-id="547d3-139">This calculation depends on the Accessorial unit that you chose as the base for your calculation.</span></span>  
8. <span data-ttu-id="547d3-140">[付帯サービス手数料タイプ] フィールドで、「燃料割増金」を選択します。</span><span class="sxs-lookup"><span data-stu-id="547d3-140">In the Accessorial fee type field, select 'Fuel surcharge'.</span></span>
9. <span data-ttu-id="547d3-141">[付帯サービス単位] フィールドで、「マイレージ」を選択します。</span><span class="sxs-lookup"><span data-stu-id="547d3-141">In the Accessorial unit field, select 'Mileage'.</span></span>
10. <span data-ttu-id="547d3-142">[地域] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="547d3-142">In the Region field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="547d3-143">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-143">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="547d3-144">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-144">Click Save.</span></span>

## <a name="update-the-carrier-rating-profile"></a><span data-ttu-id="547d3-145">配送業者の評価プロファイルの更新</span><span class="sxs-lookup"><span data-stu-id="547d3-145">Update the carrier rating profile</span></span>
1. <span data-ttu-id="547d3-146">[輸送管理] > [設定] > [配送業者] > [出荷の配送業者] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="547d3-146">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="547d3-147">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="547d3-147">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="547d3-148">[評価プロファイル] セクションの展開を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="547d3-148">Toggle the expansion of the Rating profiles section.</span></span>
4. <span data-ttu-id="547d3-149">[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-149">Click Edit.</span></span>
5. <span data-ttu-id="547d3-150">[配送業者の燃料インデックス] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="547d3-150">In the Carrier fuel index field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="547d3-151">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-151">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="547d3-152">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="547d3-152">Click Save.</span></span>

