--- 
title: "元帳発生トランザクションの作成"
description: "このタスク ガイドでは、発生主義スキーマに基づく元帳計上トランザクションの生成について説明します。"
author: aprilolson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 368614ff447ae9f5cb6e74274558b92a0873ec7a
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="create-ledger-accrual-transactions"></a><span data-ttu-id="f2158-103">元帳発生トランザクションの作成</span><span class="sxs-lookup"><span data-stu-id="f2158-103">Create ledger accrual transactions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f2158-104">このタスク ガイドでは、発生主義スキーマに基づく元帳計上トランザクションの生成について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2158-104">This task guide steps through generating ledger accrual transactions that are based on accrual schemes</span></span>

1. <span data-ttu-id="f2158-105">[総勘定元帳] > [総勘定元帳] > [仕訳入力] > [一般仕訳帳] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f2158-105">Go to General ledger > Journal entries > General journals.</span></span>
2. <span data-ttu-id="f2158-106">一覧で、目的の仕訳帳を検索し選択するか、新しい仕訳帳を作成します。</span><span class="sxs-lookup"><span data-stu-id="f2158-106">In the list, find and select the desired journal or create a new one.</span></span>
3. <span data-ttu-id="f2158-107">[仕訳帳バッチ番号] フィールドをクリックしてリンク先を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2158-107">Click to follow the link in the Journal batch number field.</span></span>
4. <span data-ttu-id="f2158-108">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="f2158-108">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="f2158-109">[勘定] フィールドで、任意の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2158-109">In the Account field, specify the desired values.</span></span>
    * <span data-ttu-id="f2158-110">この例では、保険の経費を定義します。</span><span class="sxs-lookup"><span data-stu-id="f2158-110">In this example, we are defining the expense for the insurance.</span></span> <span data-ttu-id="f2158-111">これは定期的経費の金額になります。</span><span class="sxs-lookup"><span data-stu-id="f2158-111">It will be come periodic expense amount.</span></span>  
6. <span data-ttu-id="f2158-112">[説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2158-112">In the Description field, type a value.</span></span>
7. <span data-ttu-id="f2158-113">[借方] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2158-113">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="f2158-114">[相殺勘定] フィールドで、任意の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2158-114">In the Offset account field, specify the desired values.</span></span>
9. <span data-ttu-id="f2158-115">[機能] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2158-115">Click Functions.</span></span>
10. <span data-ttu-id="f2158-116">[元帳計上] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2158-116">Click Ledger accruals.</span></span>
11. <span data-ttu-id="f2158-117">[発生主義スキーマ ID] フィールドで、ドロップダウン ボタンをクリックしてルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2158-117">In the Accrual identification field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="f2158-118">一覧で、適用する発生主義スキーマを検索し選択します。</span><span class="sxs-lookup"><span data-stu-id="f2158-118">In the list, find and select the accural scheme you want to apply.</span></span>
13. <span data-ttu-id="f2158-119">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2158-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="f2158-120">[開始日] フィールドに日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2158-120">In the Start date field, enter a date.</span></span>
15. <span data-ttu-id="f2158-121">[トランザクション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2158-121">Click Transactions.</span></span>
16. <span data-ttu-id="f2158-122">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f2158-122">Close the page.</span></span>
17. <span data-ttu-id="f2158-123">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2158-123">Click OK.</span></span>
18. <span data-ttu-id="f2158-124">[転記] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2158-124">Click Post.</span></span>

