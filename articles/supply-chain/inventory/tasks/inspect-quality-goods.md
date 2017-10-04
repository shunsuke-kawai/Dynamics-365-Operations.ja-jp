---
title: "商品の品質の調査"
description: "この手順では、品質指示を処理する方法を説明します。"
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: aeed7eab750c606ea0009fa7c51baf96e2f9de51
ms.contentlocale: ja-jp
ms.lasthandoff: 09/12/2017

---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="9a4a9-103">商品の品質の調査</span><span class="sxs-lookup"><span data-stu-id="9a4a9-103">Inspect the quality of goods</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9a4a9-104">この手順では、品質指示を処理する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-104">This procedure shows you how to process a quality order.</span></span> <span data-ttu-id="9a4a9-105">デモ データの会社 USMF でこのガイドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="9a4a9-106">このサンプル手順を開始する前に、発注書「000016」を確認し、製品受領書を転記する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="9a4a9-107">これにより、品質指示が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-107">This will automatically create a quality order.</span></span> <span data-ttu-id="9a4a9-108">品質検査は、通常、品質検査の担当者により実行されます。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="9a4a9-109">品質指示の選択</span><span class="sxs-lookup"><span data-stu-id="9a4a9-109">Select a quality order</span></span>
1. <span data-ttu-id="9a4a9-110">[在庫管理] > [定期処理タスク] > [品質管理] > [品質指示] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-110">Go to Inventory management > Periodic tasks > Quality management > Quality orders.</span></span>
2. <span data-ttu-id="9a4a9-111">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9a4a9-112">この手順を開始する前に作成された品質指示を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-112">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="9a4a9-113">テスト結果の記録</span><span class="sxs-lookup"><span data-stu-id="9a4a9-113">Record test results</span></span>
1. <span data-ttu-id="9a4a9-114">[結果] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-114">Click Results.</span></span>
2. <span data-ttu-id="9a4a9-115">[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-115">Click Edit.</span></span>
3. <span data-ttu-id="9a4a9-116">[結果量] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-116">In the Result quantity field, enter a number.</span></span>
4. <span data-ttu-id="9a4a9-117">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-117">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="9a4a9-118">[結果] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-118">In the Outcome field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="9a4a9-119">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9a4a9-120">この例では、結果は定義済の結果に基づいています。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-120">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="9a4a9-121">通常、サイズまたは他の分析コードなどより詳細なテスト結果を記録します。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-121">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
7. <span data-ttu-id="9a4a9-122">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="9a4a9-123">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-123">Click Save.</span></span>
9. <span data-ttu-id="9a4a9-124">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-124">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="9a4a9-125">品質指示を検証する</span><span class="sxs-lookup"><span data-stu-id="9a4a9-125">Validate the quality order</span></span>
1. <span data-ttu-id="9a4a9-126">[検証] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-126">Click Validate.</span></span>
2. <span data-ttu-id="9a4a9-127">[検証者] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-127">In the Validated by field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9a4a9-128">検査を実行するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-128">Select the user performing the inspection.</span></span>  
3. <span data-ttu-id="9a4a9-129">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-129">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="9a4a9-130">[選択] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-130">Click Select.</span></span>
5. <span data-ttu-id="9a4a9-131">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-131">Click OK.</span></span>
6. <span data-ttu-id="9a4a9-132">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9a4a9-132">Close the page.</span></span>
