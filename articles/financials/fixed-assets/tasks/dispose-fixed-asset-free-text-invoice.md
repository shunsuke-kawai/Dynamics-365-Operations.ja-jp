--- 
title: "自由書式の請求書を使用した固定資産の処分"
description: "この手順では、固定資産仕訳帳の取得提案を使用して固定資産の取得方法を示します。"
author: saraschi2
manager: AnnBe
ms.date: 10/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 24c7721a1e5467e98e6c4d245f1d8e24a973f5aa
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="dispose-of-a-fixed-asset-using-a-free-text-invoice"></a><span data-ttu-id="264e8-103">自由書式の請求書を使用した固定資産の処分</span><span class="sxs-lookup"><span data-stu-id="264e8-103">Dispose of a fixed asset using a free text invoice</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="264e8-104">この手順では、固定資産仕訳帳の取得提案を使用して固定資産の取得方法を示します。</span><span class="sxs-lookup"><span data-stu-id="264e8-104">This procedure shows how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="264e8-105">これは USMF の法人に対して経理担当ロールとデモ データを使用します。</span><span class="sxs-lookup"><span data-stu-id="264e8-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="264e8-106">[固定資産] > [仕訳入力] > [固定資産仕訳帳] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="264e8-106">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="264e8-107">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="264e8-107">Click New.</span></span>
3. <span data-ttu-id="264e8-108">[名前] フィールドで値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="264e8-108">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="264e8-109">[明細行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="264e8-109">Click Lines.</span></span>
5. <span data-ttu-id="264e8-110">[提案] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="264e8-110">Click Proposals.</span></span>
6. <span data-ttu-id="264e8-111">[取得提案] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="264e8-111">Click Acquisition proposal.</span></span>
7. <span data-ttu-id="264e8-112">[フィルター] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="264e8-112">Click Filter.</span></span>
8. <span data-ttu-id="264e8-113">[リセット] をクリックすると、前の値をクリアします。</span><span class="sxs-lookup"><span data-stu-id="264e8-113">Click Reset to clear out previous values.</span></span>
9. <span data-ttu-id="264e8-114">固定資産番号の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="264e8-114">Select the Fixed asset number row.</span></span>
10. <span data-ttu-id="264e8-115">[基準] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="264e8-115">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="264e8-116">この提案と一緒に取得したい固定資産の残余基準を設定します。</span><span class="sxs-lookup"><span data-stu-id="264e8-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
11. <span data-ttu-id="264e8-117">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="264e8-117">Click OK.</span></span>
12. <span data-ttu-id="264e8-118">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="264e8-118">Click OK.</span></span>
    * <span data-ttu-id="264e8-119">作成したトランザクション明細行を確認します。</span><span class="sxs-lookup"><span data-stu-id="264e8-119">Verify the transaction lines created.</span></span>  
    * <span data-ttu-id="264e8-120">帳簿で設定された取得日付と取得価格が付いている固定資産のみが取得提案に含まれます。</span><span class="sxs-lookup"><span data-stu-id="264e8-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
13. <span data-ttu-id="264e8-121">[帳簿] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="264e8-121">Click the Books tab.</span></span>
14. <span data-ttu-id="264e8-122">[転記] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="264e8-122">Click Post.</span></span>

