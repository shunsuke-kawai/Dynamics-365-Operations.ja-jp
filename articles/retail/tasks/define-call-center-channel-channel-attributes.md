--- 
title: "コール センター チャネルおよびチャネル属性の定義"
description: "この手順では、新しい小売チャネルを作成し、チャネル属性を定義する方法を説明します。"
author: mugunthanm
manager: AnnBe
ms.date: 05/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c3d2f6785b9054ede7ea96ebd48c5d1f23e510e7
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="define-call-center-channel-and-channel-attributes"></a><span data-ttu-id="bee52-103">コール センター チャネルおよびチャネル属性の定義</span><span class="sxs-lookup"><span data-stu-id="bee52-103">Define call center channel and channel attributes</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="bee52-104">この手順では、新しい小売チャネルを作成し、チャネル属性を定義する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="bee52-104">This procedure walks through creating a new retail channel and defining channel attributes.</span></span> <span data-ttu-id="bee52-105">このタスクの作成に使用するデモ データの会社は USRT です。</span><span class="sxs-lookup"><span data-stu-id="bee52-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="bee52-106">この手順は、「小売 IT」ロールを対象としています。</span><span class="sxs-lookup"><span data-stu-id="bee52-106">This procedure is intended for the Retail IT role.</span></span>


## <a name="create-new-store"></a><span data-ttu-id="bee52-107">新しい店舗の作成</span><span class="sxs-lookup"><span data-stu-id="bee52-107">Create new store</span></span>
1. <span data-ttu-id="bee52-108">[すべてのワークスペース] > [チャンネルの配置] に移動します。</span><span class="sxs-lookup"><span data-stu-id="bee52-108">Go to All workspaces > Channel deployment.</span></span>
2. <span data-ttu-id="bee52-109">[新しいチャネル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-109">Click New channel.</span></span>
3. <span data-ttu-id="bee52-110">[店舗] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-110">Click Store.</span></span>
4. <span data-ttu-id="bee52-111">[名前] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bee52-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="bee52-112">[店舗番号] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bee52-112">In the Store number field, type a value.</span></span>
6. <span data-ttu-id="bee52-113">[倉庫] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-113">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="bee52-114">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-114">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="bee52-115">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="bee52-116">[ストア タイムゾーン] フィールドで、オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-116">In the Store time zone field, select an option.</span></span>
10. <span data-ttu-id="bee52-117">[チャネル プロファイル] フィールドで、ドロップ ダウン ボタンをクリックしてルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-117">In the Channel profile field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="bee52-118">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="bee52-119">[言語] フィールドで、ドロップ ダウン ボタンをクリックしてルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-119">In the Language field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="bee52-120">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="bee52-121">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="bee52-122">[売上税グループ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-122">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="bee52-123">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="bee52-124">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="bee52-125">[顧客のアドレス帳] フィールドで、ドロップ ダウン ボタンをクリックしてルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-125">In the Customer address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="bee52-126">この店舗に顧客をリンクするために使用するアドレス帳を選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-126">Select the address book used to link customers to this store.</span></span>  
19. <span data-ttu-id="bee52-127">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-127">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="bee52-128">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-128">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="bee52-129">[選択] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-129">Click Select.</span></span>
22. <span data-ttu-id="bee52-130">[従業員のアドレス帳] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-130">In the Employee address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="bee52-131">このチャネルにレジ担当者をリンクするために使用するアドレス帳を選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-131">Select the address book used to link cashiers to this channel.</span></span>  
23. <span data-ttu-id="bee52-132">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-132">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="bee52-133">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-133">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="bee52-134">[選択] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-134">Click Select.</span></span>
26. <span data-ttu-id="bee52-135">[既定の顧客] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-135">In the Default customer field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="bee52-136">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-136">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="bee52-137">[画面レイアウト] セクションを展開または折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="bee52-137">Expand or collapse the Screen layout section.</span></span>
29. <span data-ttu-id="bee52-138">[画面レイアウト ID] フィールドで、ドロップ ダウン ボタンをクリックしてルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-138">In the Screen layout ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="bee52-139">この店舗の既定の POS の画面レイアウトを選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-139">Select the default POS screen layout for this store.</span></span>  
30. <span data-ttu-id="bee52-140">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-140">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="bee52-141">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="bee52-142">アクション ペインで、[設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-142">On the Action Pane, click Set up.</span></span>
33. <span data-ttu-id="bee52-143">[チャネル属性] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-143">Click Channel attributes.</span></span>
34. <span data-ttu-id="bee52-144">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-144">Click New.</span></span>
35. <span data-ttu-id="bee52-145">[名前] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-145">In the Name field, click the drop-down button to open the lookup.</span></span>
36. <span data-ttu-id="bee52-146">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-146">In the list, find and select the desired record.</span></span>
37. <span data-ttu-id="bee52-147">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-147">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="bee52-148">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-148">Click Save.</span></span>
39. <span data-ttu-id="bee52-149">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bee52-149">Close the page.</span></span>
40. <span data-ttu-id="bee52-150">アクション ペインで、[設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-150">On the Action Pane, click Set up.</span></span>
41. <span data-ttu-id="bee52-151">[支払方法] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-151">Click Payment methods.</span></span>
42. <span data-ttu-id="bee52-152">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-152">Click New.</span></span>
43. <span data-ttu-id="bee52-153">[支払方法] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-153">In the Payment method field, click the drop-down button to open the lookup.</span></span>
44. <span data-ttu-id="bee52-154">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-154">In the list, click the link in the selected row.</span></span>
45. <span data-ttu-id="bee52-155">[転記] セクションを展開または折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="bee52-155">Expand or collapse the Posting section.</span></span>
46. <span data-ttu-id="bee52-156">[口座番号] フィールドで、任意の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="bee52-156">In the Account number field, specify the desired values.</span></span>
47. <span data-ttu-id="bee52-157">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-157">Click Save.</span></span>
48. <span data-ttu-id="bee52-158">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bee52-158">Close the page.</span></span>
49. <span data-ttu-id="bee52-159">アクション ペインで、[設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-159">On the Action Pane, click Set up.</span></span>
50. <span data-ttu-id="bee52-160">[現金申告] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-160">Click Cash declaration.</span></span>
51. <span data-ttu-id="bee52-161">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-161">Click New.</span></span>
52. <span data-ttu-id="bee52-162">[トランザクション通貨の金額] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bee52-162">In the Amount in transaction currency field, enter a number.</span></span>
53. <span data-ttu-id="bee52-163">[通貨] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-163">In the Currency field, click the drop-down button to open the lookup.</span></span>
54. <span data-ttu-id="bee52-164">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-164">In the list, find and select the desired record.</span></span>
55. <span data-ttu-id="bee52-165">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-165">In the list, click the link in the selected row.</span></span>
56. <span data-ttu-id="bee52-166">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-166">Click Save.</span></span>
57. <span data-ttu-id="bee52-167">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bee52-167">Close the page.</span></span>
58. <span data-ttu-id="bee52-168">アクション ペインで、[設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-168">On the Action Pane, click Set up.</span></span>
59. <span data-ttu-id="bee52-169">[店舗ロケーター グループの割り当て] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-169">Click Store locator group assignment.</span></span>
60. <span data-ttu-id="bee52-170">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-170">Click New.</span></span>
61. <span data-ttu-id="bee52-171">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="bee52-171">In the list, mark the selected row.</span></span>
62. <span data-ttu-id="bee52-172">[ロケーター グループ] フィールドで、ドロップ ダウン ボタンをクリックしてルックアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee52-172">In the Locator group field, click the drop-down button to open the lookup.</span></span>
63. <span data-ttu-id="bee52-173">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="bee52-173">In the list, find and select the desired record.</span></span>
64. <span data-ttu-id="bee52-174">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-174">In the list, click the link in the selected row.</span></span>
65. <span data-ttu-id="bee52-175">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bee52-175">Click Save.</span></span>
66. <span data-ttu-id="bee52-176">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bee52-176">Close the page.</span></span>

