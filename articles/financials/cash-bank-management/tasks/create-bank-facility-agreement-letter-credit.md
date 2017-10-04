--- 
title: "信用状の銀行融資契約の作成"
description: "このタスクは、信用状を処理する銀行融資契約を作成する方法について説明します。"
author: ShylaThompson
manager: AnnBe
ms.date: 02/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ac3394a40bff3aaee6a76448633e4f36c4049612
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-bank-facility-agreement-for-a-letter-of-credit"></a><span data-ttu-id="1fedb-103">信用状の銀行融資契約の作成</span><span class="sxs-lookup"><span data-stu-id="1fedb-103">Create a bank facility agreement for a letter of credit</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1fedb-104">このタスクは、信用状を処理する銀行融資契約を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-104">This task walks through the creating a Bank facility agreement to process a Letter of credit.</span></span> <span data-ttu-id="1fedb-105">このタスクを始める前に、銀行融資および転記プロファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-105">You will want to set up bank facilities and posting profiles before this task.</span></span>  <span data-ttu-id="1fedb-106">このタスクでは、USMF というデモ会社を使用します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-106">This task uses the demo company 'USMF'.</span></span>  


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="1fedb-107">銀行融資契約の作成</span><span class="sxs-lookup"><span data-stu-id="1fedb-107">Create Bank facility agreement</span></span>
1. <span data-ttu-id="1fedb-108">[現金および銀行管理] > [信用状] > [銀行融資契約] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-108">Go to Cash and bank management > Letters of credit > Bank facility agreements.</span></span>
2. <span data-ttu-id="1fedb-109">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fedb-109">Click New.</span></span>
3. <span data-ttu-id="1fedb-110">[契約番号] フィールドに、銀行との契約にある契約番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-110">In the Agreement number field, enter the agreement number according to the agreement with the bank.</span></span>
4. <span data-ttu-id="1fedb-111">[銀行口座] フィールドで、発行した銀行の口座番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-111">In the Bank account field, enter the account number at the issuing bank.</span></span>
5. <span data-ttu-id="1fedb-112">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fedb-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="1fedb-113">[開始日] フィールドで、日付と時刻を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-113">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="1fedb-114">[終了日] フィールドで、日付と時刻を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-114">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="1fedb-115">[全般] セクションを展開または折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="1fedb-115">Expand or collapse the General section.</span></span>
9. <span data-ttu-id="1fedb-116">[行の追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fedb-116">Click Add line.</span></span>
10. <span data-ttu-id="1fedb-117">[融資タイプ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="1fedb-117">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="1fedb-118">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-118">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="1fedb-119">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fedb-119">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="1fedb-120">[限度] フィールドに、銀行との交渉に基づく融資金額を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-120">In the Limit field, enter the facility amount that was negotiated with the bank.</span></span>
14. <span data-ttu-id="1fedb-121">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fedb-121">Click Save.</span></span>
15. <span data-ttu-id="1fedb-122">[拡張] をクリックして、ドロップ ダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="1fedb-122">Click Extend to open the drop dialog.</span></span>
16. <span data-ttu-id="1fedb-123">[新しい契約番号] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-123">In the New agreement number field, type a value.</span></span>
17. <span data-ttu-id="1fedb-124">[終了日] フィールドで、日付と時刻を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fedb-124">In the End date field, enter a date and time.</span></span>
18. <span data-ttu-id="1fedb-125">[拡張] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fedb-125">Click Extend.</span></span>
19. <span data-ttu-id="1fedb-126">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1fedb-126">Close the page.</span></span>

