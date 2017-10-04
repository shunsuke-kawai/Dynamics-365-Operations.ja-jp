--- 
title: "自動運賃調整の設定"
description: "この手順では、自動運賃調整のデータ設定方法を示します。"
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
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
ms.openlocfilehash: 97f0c4d8fe06ab2fc252b9543cb688306214c79f
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-automatic-freight-reconciliation"></a><span data-ttu-id="c9a8b-103">自動運賃調整の設定</span><span class="sxs-lookup"><span data-stu-id="c9a8b-103">Set up automatic freight reconciliation</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c9a8b-104">この手順では、自動運賃調整のデータ設定方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-104">This procedure shows how to set up data for automatic freight reconciliation.</span></span> <span data-ttu-id="c9a8b-105">これは、通常、倉庫マネージャーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-105">This is typically done by a warehouse manager.</span></span> <span data-ttu-id="c9a8b-106">デモ データの会社 USMF でこの手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-106">You can use this procedure in demo data company USMF.</span></span>


## <a name="set-up-the-freight-bill-type"></a><span data-ttu-id="c9a8b-107">運賃請求書タイプの設定</span><span class="sxs-lookup"><span data-stu-id="c9a8b-107">Set up the freight bill type</span></span>
1. <span data-ttu-id="c9a8b-108">[輸送管理] > [設定] > [運賃の調整] > [運賃請求書タイプ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-108">Go to Transportation management > Setup > Freight reconciliation > Freight bill type.</span></span>
    * <span data-ttu-id="c9a8b-109">運賃請求書タイプは、運賃請求書と配送業者の請求書をどのようにして照合するべきかを定義します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-109">The freight bill type defines how freight bills and carrier invoices  should be matched.</span></span>  
2. <span data-ttu-id="c9a8b-110">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-110">Click New.</span></span>
3. <span data-ttu-id="c9a8b-111">[運賃請求書タイプ] フィールドで値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-111">In the Freight bill type field, type a value.</span></span>
4. <span data-ttu-id="c9a8b-112">[エンジン アセンブリ] フィールドで、「Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-112">In the Engine assembly field, type 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'.</span></span>
    * <span data-ttu-id="c9a8b-113">これは標準の輸送管理照合エンジン コード ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-113">This is the standard Transportation management matching engine code library.</span></span>  
5. <span data-ttu-id="c9a8b-114">[エンジン クラス] フィールドで、「Microsoft.Dynamics.Ax.Tms.dll」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-114">In the Engine class field, type 'Microsoft.Dynamics.Ax.Tms.dll'.</span></span>
    * <span data-ttu-id="c9a8b-115">これは標準の輸送管理照合エンジン クラスです。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-115">This is the standard Transportation management matching engine class.</span></span>  
6. <span data-ttu-id="c9a8b-116">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-116">Click New.</span></span>
7. <span data-ttu-id="c9a8b-117">[説明] フィールドで、運賃請求書と配送業者の請求書で照合する必要のある値を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-117">In the Description field, choose the value that should match on the freight bill and the carrier invoice.</span></span>  
8. <span data-ttu-id="c9a8b-118">[照合が必要] フィールドで、[はい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-118">In the Match required field, select 'Yes'.</span></span>
    * <span data-ttu-id="c9a8b-119">このフィールドで [はい] を設定すると、説明フィールドで選択された値が、運賃請求書と配送業者の請求書の両方で照合する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-119">If you set this field to Yes this means that the value selected in the Description field needs to match on both the freight bill and the carrier invoice.</span></span> <span data-ttu-id="c9a8b-120">[いいえ] に設定する場合、このフィールドをいずれかで空白にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-120">If you set it to No, the field can be blank on one of these.</span></span>  
9. <span data-ttu-id="c9a8b-121">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-121">Click Save.</span></span>

## <a name="set-up-the-freight-bill-type-assignment"></a><span data-ttu-id="c9a8b-122">運賃請求書タイプの割り当ての設定</span><span class="sxs-lookup"><span data-stu-id="c9a8b-122">Set up the freight bill type assignment</span></span>
1. <span data-ttu-id="c9a8b-123">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-123">Close the page.</span></span>
2. <span data-ttu-id="c9a8b-124">[輸送管理] > [設定] > [運賃の調整] > [運賃請求書タイプの割り当て] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-124">Go to Transportation management > Setup > Freight reconciliation > Freight bill type assignments.</span></span>
    * <span data-ttu-id="c9a8b-125">運賃請求書タイプの割り当てを使用して、特定の配送業者に使用する運賃請求書タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-125">The freight bill type assignment is used to specify which freight bill type is used for a particular carrier.</span></span>   
3. <span data-ttu-id="c9a8b-126">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-126">Click New.</span></span>
4. <span data-ttu-id="c9a8b-127">[モード] フィールドで値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-127">In the Mode field, enter or select a value.</span></span>
5. <span data-ttu-id="c9a8b-128">[出荷の配送業者] フィールドで値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-128">In the Shipping carrier field, enter or select a value.</span></span>
6. <span data-ttu-id="c9a8b-129">[運賃請求書タイプ] フィールドで、先に作成した運賃請求書タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-129">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
7. <span data-ttu-id="c9a8b-130">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-130">Close the page.</span></span>

## <a name="set-up-the-audit-master"></a><span data-ttu-id="c9a8b-131">監査マスターの設定</span><span class="sxs-lookup"><span data-stu-id="c9a8b-131">Set up the audit master</span></span>
1. <span data-ttu-id="c9a8b-132">[輸送管理] > [設定] > [運賃の調整] > [監査マスター] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-132">Go to Transportation management > Setup > Freight reconciliation > Audit master.</span></span>
    * <span data-ttu-id="c9a8b-133">監査マスターは、自動運賃調整の許容制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-133">The audit master defines the tolerance limits for automatic freight reconciliation.</span></span> <span data-ttu-id="c9a8b-134">これは、運賃請求書と配送業者の請求書の金額の差と調整できる金額で指定します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-134">It specifies by how much the monetary amounts on the freight bill and the carrier invoice can differ and still allow reconciliation to occur.</span></span> <span data-ttu-id="c9a8b-135">また、不一致の処理方法も定義します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-135">It also defines how to handle discrepancies.</span></span>  
2. <span data-ttu-id="c9a8b-136">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-136">Click New.</span></span>
3. <span data-ttu-id="c9a8b-137">[監査マスター ID] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-137">In the Audit master ID field, type a value.</span></span>
4. <span data-ttu-id="c9a8b-138">[出荷の配送業者] フィールドで、先で使用した同じ出荷の配送業者を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-138">In the Shipping carrier  field, select the same shipping carrier as you did earlier.</span></span>
5. <span data-ttu-id="c9a8b-139">[運賃請求書タイプ] フィールドで、先に作成した運賃請求書タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-139">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
6. <span data-ttu-id="c9a8b-140">[許容範囲] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-140">Expand the Tolerance section.</span></span>
7. <span data-ttu-id="c9a8b-141">[最小許容範囲レベル] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-141">In the Minimum tolerance level field, enter a number.</span></span>
8. <span data-ttu-id="c9a8b-142">[最大許容範囲レベル] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-142">In the Maximum tolerance level field, enter a number.</span></span>
9. <span data-ttu-id="c9a8b-143">[結果] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-143">Expand the Result section.</span></span>
10. <span data-ttu-id="c9a8b-144">[過剰支払の理由コード] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-144">In the Overpayment reason code field, enter or select a value.</span></span>
    * <span data-ttu-id="c9a8b-145">金額が運賃請求書と配送業者の請求書で異なる場合、差異が許容範囲レベル内であれば、超過/不足支払の理由コードに応じて差額を登録する必要のある勘定が指定されます。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-145">If the monetary amounts differ on the freight bill and the carrier invoice, the overpayment and underpayment reason codes specify the accounts that the difference should be registered on, as long as the difference is within the tolerance levels.</span></span>  
11. <span data-ttu-id="c9a8b-146">[過少支払の理由コード] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-146">In the Underpayment reason code field, enter or select a value.</span></span>
12. <span data-ttu-id="c9a8b-147">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c9a8b-147">Close the page.</span></span>

