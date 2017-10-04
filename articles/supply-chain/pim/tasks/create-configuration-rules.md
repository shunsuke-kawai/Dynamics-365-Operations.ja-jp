--- 
title: "コンフィギュレーション ルールの作成"
description: "この手順は、分析コード ベースのコンフィギュレーションを使用して BOM 明細行の特定の組み合わせを使用または禁止できるコンフィギュレーション ルールを作成します。"
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
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
ms.openlocfilehash: 71f429d3aba1b5c51b35b0d08337f69094d0b135
ms.contentlocale: ja-jp
ms.lasthandoff: 09/14/2017

---
# <a name="create-configuration-rules"></a><span data-ttu-id="55d96-103">コンフィギュレーション ルールの作成</span><span class="sxs-lookup"><span data-stu-id="55d96-103">Create configuration rules</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="55d96-104">この手順は、分析コード ベースのコンフィギュレーションを使用して BOM 明細行の特定の組み合わせを使用または禁止できるコンフィギュレーション ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="55d96-104">This procedure creates configuration rules that can be used for dimension-based configuration to enforce or prevent certain combinations of BOM lines.</span></span> <span data-ttu-id="55d96-105">この手順の作成に使用するデモ データの会社は USMF です。</span><span class="sxs-lookup"><span data-stu-id="55d96-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="55d96-106">これは、分析コード ベースのコンフィギュレーションでの組み合わせの作成方法を説明する 8 つの手順の 7 番目です。</span><span class="sxs-lookup"><span data-stu-id="55d96-106">This is the seventh procedure out of eight that explains how to build combinations for dimension-based configuration.</span></span>

1. <span data-ttu-id="55d96-107">[製品情報管理] > [部品表およびフォーミュラ] > [部品表] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="55d96-107">Go to Product information management > Bills of materials and formulas > Bills of materials.</span></span>
2. <span data-ttu-id="55d96-108">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="55d96-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="55d96-109">[分析コードベースのコンフィギュレーションの BOM] を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="55d96-109">Find and select the BOM for the dimension-based configuration.</span></span>  
3. <span data-ttu-id="55d96-110">[アクション] ウィンドウで、[オプション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55d96-110">On the Action Pane, click Options.</span></span>
4. <span data-ttu-id="55d96-111">[ビューの変更] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55d96-111">Click Change view.</span></span>
5. <span data-ttu-id="55d96-112">[ヘッダーの表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55d96-112">Click Header view.</span></span>
    * <span data-ttu-id="55d96-113">[コンフィギュレーション ルート] クイック タブにアクセスするヘッダー表示を開きます。</span><span class="sxs-lookup"><span data-stu-id="55d96-113">Open the header view to access the Configuration route FastTab.</span></span>  
6. <span data-ttu-id="55d96-114">[コンフィギュレーション ルート] セクションを展開または折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="55d96-114">Expand or collapse the Configuration route section.</span></span>
    * <span data-ttu-id="55d96-115">[コンフィギュレーション ルート] クイック タブを展開モードにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55d96-115">The Configuration route FastTab must be in the expanded mode.</span></span>  
7. <span data-ttu-id="55d96-116">[コンフィギュレーション ルール] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55d96-116">Click Configuration rules.</span></span>
8. <span data-ttu-id="55d96-117">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55d96-117">Click New.</span></span>
9. <span data-ttu-id="55d96-118">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="55d96-118">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="55d96-119">[品目番号] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="55d96-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="55d96-120">現在のコンフィギュレーション グループの品目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55d96-120">The items in the current configuration group are displayed.</span></span> <span data-ttu-id="55d96-121">ルールの条件を表す 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="55d96-121">Select the one that represents the condition in the rule.</span></span>  
11. <span data-ttu-id="55d96-122">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="55d96-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="55d96-123">[方法] フィールドで、オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="55d96-123">In the Method field, select an option.</span></span>
    * <span data-ttu-id="55d96-124">別のコンフィギュレーション グループの品目の選択または選択解除を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="55d96-124">It is possible to enforce either a selection or a deselection of an item from another configuration group.</span></span>  
13. <span data-ttu-id="55d96-125">[派生グループ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="55d96-125">In the Derived group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="55d96-126">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="55d96-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="55d96-127">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="55d96-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="55d96-128">目的のコンフィギュレーション グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="55d96-128">Select the desired configuration group.</span></span>  
16. <span data-ttu-id="55d96-129">[派生品目番号] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="55d96-129">In the Derived item number field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="55d96-130">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="55d96-130">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="55d96-131">選択された方法によって選択または選択解除となる品目番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="55d96-131">Select the item number that will be either selected or deselected depending on the chosen method.</span></span>  
18. <span data-ttu-id="55d96-132">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="55d96-132">Close the page.</span></span>

