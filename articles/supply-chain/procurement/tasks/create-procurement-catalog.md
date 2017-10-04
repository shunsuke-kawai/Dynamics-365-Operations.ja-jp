--- 
title: "調達カタログの作成"
description: "このガイドでは、調達カタログを作成する方法を示します。"
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
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
ms.openlocfilehash: df844ba3834972441daa61899294b3e95cac96c1
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-procurement-catalog"></a><span data-ttu-id="c04f2-103">調達カタログの作成</span><span class="sxs-lookup"><span data-stu-id="c04f2-103">Create a procurement catalog</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c04f2-104">このガイドでは、調達カタログを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-104">This guide shows you how to create a procurement catalog.</span></span> <span data-ttu-id="c04f2-105">通常、このタスクを実行するのは、調達担当者です。</span><span class="sxs-lookup"><span data-stu-id="c04f2-105">This task would typically be carried out by a procurement professional.</span></span> <span data-ttu-id="c04f2-106">さらに従業員が要求を作成する際にカタログを使用する方法も参照できます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-106">You will also learn how employees can use the catalog when they create a requisition.</span></span> <span data-ttu-id="c04f2-107">カタログを作成する前に、システム内に調達カテゴリ階層が必要です。</span><span class="sxs-lookup"><span data-stu-id="c04f2-107">Before you can create a catalog, there must be a procurement category hierarchy in your system.</span></span> <span data-ttu-id="c04f2-108">階層は、階層にあるすべての製品とともに、新しいカタログによって継承されます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-108">The hierarchy is inherited by the new catalog, along with all the products that are in the hierarchy.</span></span> <span data-ttu-id="c04f2-109">調達カテゴリ階層を使用する場合、さらに手順ステップで使用される例にも、このガイドをデモ データ会社 USMF で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-109">You can use this guide in demo data company USMF where the procurement category hierarchy is available, as well as the examples used in the procedure steps.</span></span>


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a><span data-ttu-id="c04f2-110">調達カテゴリ階層が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-110">Ensure that a procurement category hierarchy exists</span></span>
1. <span data-ttu-id="c04f2-111">[調達] > [調達カテゴリ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-111">Go to Procurement and sourcing > Procurement categories.</span></span>
    * <span data-ttu-id="c04f2-112">調達カテゴリ階層は USMF のデモ データ会社内で使用でき、製品は [オフィス機器/コンピュータ] カテゴリに追加されました。</span><span class="sxs-lookup"><span data-stu-id="c04f2-112">A procurement category hierarchy is available in the USMF demo data company and products have been added to the Office machines/Computers category.</span></span> <span data-ttu-id="c04f2-113">この手順をタスク ガイドとして実行している場合は、カテゴリを参照するときガイドのロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c04f2-113">If you’re running this procedure as a task guide, you’ll need to unlock the guide if you want to browse through the category.</span></span> <span data-ttu-id="c04f2-114">階層を使用できない場合は、[新規] をクリックして階層を作成します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-114">If a hierarchy was not available, you’d create it by clicking New.</span></span> <span data-ttu-id="c04f2-115">これが実行可能な回数は一度だけです。</span><span class="sxs-lookup"><span data-stu-id="c04f2-115">This can only be done once.</span></span>  
2. <span data-ttu-id="c04f2-116">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-116">Close the page.</span></span>

## <a name="create-a-catalog"></a><span data-ttu-id="c04f2-117">カタログの作成</span><span class="sxs-lookup"><span data-stu-id="c04f2-117">Create a catalog</span></span>
1. <span data-ttu-id="c04f2-118">[調達] > [カタログ] > [調達カタログ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-118">Go to Procurement and sourcing > Catalogs > Procurement catalogs.</span></span>
2. <span data-ttu-id="c04f2-119">[新しい調達カタログ] をクリックすると、ドロップ ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-119">Click New procurement catalog to open the drop dialog.</span></span>
3. <span data-ttu-id="c04f2-120">[名前] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-120">In the Name field, type a value.</span></span>
4. <span data-ttu-id="c04f2-121">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-121">Click OK.</span></span>
5. <span data-ttu-id="c04f2-122">ツリーで、「CORP PROCUREMENT CATEGORIES」を展開します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-122">In the tree, expand 'CORP PROCUREMENT CATEGORIES'.</span></span>
6. <span data-ttu-id="c04f2-123">ツリーで、「OFFICE MACHINES」を展開します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-123">In the tree, expand 'OFFICE MACHINES'.</span></span>
7. <span data-ttu-id="c04f2-124">ツリーで、[コンピューター] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-124">In the tree, select 'Computers'.</span></span>
    * <span data-ttu-id="c04f2-125">調達カテゴリからの製品が一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-125">The products from the procurement category are displayed in the list.</span></span> <span data-ttu-id="c04f2-126">製品をカテゴリに追加する場合は、調達カテゴリ階層のページまたは品目の詳細ページで追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c04f2-126">If you want to add a product to the category you need to do this on the Procurement category hierarchy page or on the Item details page.</span></span>  
    * <span data-ttu-id="c04f2-127">既定の更新タイプは、調達カテゴリ階層に追加された新しい製品をすぐにカタログに表示するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-127">The Default update type determines whether new products that have been added to the procurement category hierarchy are immediately visible in the catalog.</span></span> <span data-ttu-id="c04f2-128">更新タイプが [動的] に設定されている場合、変更はすぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-128">If the update type is set to Dynamic, changes are visible immediately.</span></span> <span data-ttu-id="c04f2-129">更新タイプが [静的] の場合、新しい製品は、カタログが再公開された後にカタログを使用している従業員にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-129">If the update type is Static, new products are only visible to people using the catalog after the catalog has been re-published.</span></span> <span data-ttu-id="c04f2-130">公開アクションはページ上部のアクション ウィンドウで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-130">The Publish action is available on the Action Pane at the top of the page.</span></span> <span data-ttu-id="c04f2-131">製品が調達カテゴリ階層から削除されると、既定の更新タイプ フィールドの値に関係なく、変更はすぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-131">If products are removed from the procurement category hierarchy, the change is immediately visible, regardless of the value in the Default update type field.</span></span>  
8. <span data-ttu-id="c04f2-132">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-132">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="c04f2-133">[非表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-133">Click Hide.</span></span>
10. <span data-ttu-id="c04f2-134">アクション ウィンドウで、[カテゴリ ナビゲーション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-134">On the Action Pane, click Category navigation.</span></span>
11. <span data-ttu-id="c04f2-135">[無効化] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-135">Click Disable.</span></span>
12. <span data-ttu-id="c04f2-136">アクション ウィンドウで、[カテゴリ ナビゲーション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-136">On the Action Pane, click Category navigation.</span></span>
13. <span data-ttu-id="c04f2-137">[有効化] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-137">Click Enable.</span></span>
14. <span data-ttu-id="c04f2-138">[カタログの有効化] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-138">Click Activate catalog.</span></span>
15. <span data-ttu-id="c04f2-139">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-139">Close the page.</span></span>

## <a name="make-the-catalog-visible"></a><span data-ttu-id="c04f2-140">カタログを表示します</span><span class="sxs-lookup"><span data-stu-id="c04f2-140">Make the catalog visible</span></span>
1. <span data-ttu-id="c04f2-141">[調達] > [設定] > [ポリシー] > [購入ポリシー] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-141">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="c04f2-142">調達ポリシー USMF を選択します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-142">Select Procurement Policy USMF.</span></span>
    * <span data-ttu-id="c04f2-143">作業者がユーザー プロファイルに接続して製品を注文することができるよう、法人の購入ポリシーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c04f2-143">You need to select the purchasing policy for the legal entity that the worker connected to your user profile is allowed to order products in.</span></span> <span data-ttu-id="c04f2-144">USMF のデモ データでは、管理者ユーザーはジュリア ファンダーバークと呼ばれる作業者に接続され、既定の USMF で製品を注文します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-144">In the USMF demo data, the Admin user is connected to the worker called Julia Funderburk, and she orders products in USMF by default.</span></span>  
3. <span data-ttu-id="c04f2-145">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-145">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c04f2-146">作成したばかりのカタログを選択します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-146">Select the catalog that you’ve just created.</span></span>
5. <span data-ttu-id="c04f2-147">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-147">Click OK.</span></span>
6. <span data-ttu-id="c04f2-148">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-148">Close the page.</span></span>
7. <span data-ttu-id="c04f2-149">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-149">Close the page.</span></span>

## <a name="use-the-catalog"></a><span data-ttu-id="c04f2-150">カタログを使用します</span><span class="sxs-lookup"><span data-stu-id="c04f2-150">Use the catalog</span></span>
1. <span data-ttu-id="c04f2-151">[調達] > [購買要求] > [すべての購買要求] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-151">Go to Procurement and sourcing > Purchase requisitions > All purchase requisitions.</span></span>
2. <span data-ttu-id="c04f2-152">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-152">Click New.</span></span>
3. <span data-ttu-id="c04f2-153">[名前] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-153">In the Name field, type a value.</span></span>
4. <span data-ttu-id="c04f2-154">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-154">Click OK.</span></span>
5. <span data-ttu-id="c04f2-155">[製品の追加]をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-155">Click Add products.</span></span>
6. <span data-ttu-id="c04f2-156">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c04f2-157">左のカテゴリ階層またはリストの先頭にあるフィルターを使用して、製品をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="c04f2-157">You can use the category hierarchy on the left or the filter at the top of the list to filter the products.</span></span>  
7. <span data-ttu-id="c04f2-158">[明細行に追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-158">Click Add to lines.</span></span>
8. <span data-ttu-id="c04f2-159">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="c04f2-159">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="c04f2-160">[明細行に追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-160">Click Add to lines.</span></span>
10. <span data-ttu-id="c04f2-161">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c04f2-161">Click OK.</span></span>

