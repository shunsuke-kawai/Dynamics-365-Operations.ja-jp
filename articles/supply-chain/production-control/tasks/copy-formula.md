--- 
title: "フォーミュラのコピー"
description: "多少の違いはあっても、既存のフォーミュラと同じ構成要素を含んでいるフォーミュラを作成することに焦点を当てています。"
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 036bd9f592ca584afad9d4b9b7a49a9787076056
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="copy-a-formula"></a><span data-ttu-id="22a01-103">フォーミュラのコピー</span><span class="sxs-lookup"><span data-stu-id="22a01-103">Copy a formula</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="22a01-104">多少の違いはあっても、既存のフォーミュラと同じ構成要素を含んでいるフォーミュラを作成することに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="22a01-104">This procedure focuses on creating a formula that includes the same ingredients as an existing formula, but with minor differences.</span></span> <span data-ttu-id="22a01-105">式明細行を作成するため、[コピー] 機能を使用して必要な構成要素のほとんどを持つ既存の式をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="22a01-105">To create the formula lines, you can use the Copy function to copy an existing formula that has most of the ingredients that you need.</span></span> <span data-ttu-id="22a01-106">次に、新しいバージョンの個々の行に必要な変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="22a01-106">You can then make any necessary changes to the individual lines in the new version.</span></span> <span data-ttu-id="22a01-107">[コピー] 機能を使用すると、ほぼ同一である複数の式を作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="22a01-107">By using the Copy function, you do not have to create multiple formulas that are almost identical.</span></span> <span data-ttu-id="22a01-108">このタスクの作成に使用するデモ データの会社は USP2 です。</span><span class="sxs-lookup"><span data-stu-id="22a01-108">The demo data company used to create this task is USP2.</span></span>


## <a name="create-a-formula"></a><span data-ttu-id="22a01-109">フォーミュラの作成</span><span class="sxs-lookup"><span data-stu-id="22a01-109">Create a formula</span></span>
1. <span data-ttu-id="22a01-110">[製品情報管理] > [部品表およびフォーミュラ] > [フォーミュラ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="22a01-110">Go to Product information management > Bills of materials and formulas > Formulas.</span></span>
2. <span data-ttu-id="22a01-111">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-111">Click New.</span></span>
3. <span data-ttu-id="22a01-112">[フォーミュラ] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="22a01-112">In the Formula field, type a value.</span></span>
4. <span data-ttu-id="22a01-113">[名前] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="22a01-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="22a01-114">意味のあるフォーミュラ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="22a01-114">Type a meaningful name for the formula.</span></span>  
5. <span data-ttu-id="22a01-115">[サイト] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="22a01-115">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="22a01-116">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="22a01-117">[品目グループ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="22a01-117">In the Item group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="22a01-118">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="22a01-118">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="22a01-119">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-119">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="22a01-120">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-120">Click Save.</span></span>

## <a name="copy-formula-lines"></a><span data-ttu-id="22a01-121">フォーミュラ明細行のコピー</span><span class="sxs-lookup"><span data-stu-id="22a01-121">Copy formula lines</span></span>
1. <span data-ttu-id="22a01-122">アクション ウィンドウで、[フォーミュラ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-122">On the Action Pane, click Formula.</span></span>
2. <span data-ttu-id="22a01-123">[コピー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-123">Click Copy.</span></span>
3. <span data-ttu-id="22a01-124">[品目番号] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="22a01-124">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="22a01-125">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="22a01-126">[フォーミュラバージョン] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="22a01-126">In the Formula version field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="22a01-127">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-127">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="22a01-128">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-128">Click OK.</span></span>

## <a name="adjust-copied-formula-lines"></a><span data-ttu-id="22a01-129">コピーしたフォーミュラ明細行の調整</span><span class="sxs-lookup"><span data-stu-id="22a01-129">Adjust copied formula lines</span></span>
1. <span data-ttu-id="22a01-130">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="22a01-130">In the list, mark the selected row.</span></span>
2. <span data-ttu-id="22a01-131">[削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-131">Click Delete.</span></span>
3. <span data-ttu-id="22a01-132">[はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-132">Click Yes.</span></span>

## <a name="approve-formula"></a><span data-ttu-id="22a01-133">フォーミュラを承認</span><span class="sxs-lookup"><span data-stu-id="22a01-133">Approve formula</span></span>
1. <span data-ttu-id="22a01-134">アクション ウィンドウで、[フォーミュラ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-134">On the Action Pane, click Formula.</span></span>
2. <span data-ttu-id="22a01-135">[フォーミュラを承認] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-135">Click Approve formula.</span></span>
3. <span data-ttu-id="22a01-136">[承認者] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="22a01-136">In the Approved by field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="22a01-137">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="22a01-138">[選択] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-138">Click Select.</span></span>
6. <span data-ttu-id="22a01-139">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a01-139">Click OK.</span></span>

