--- 
title: "元伝票の監査ポリシーの定義"
description: "この手順は、監査ポリシー ルールを設定および実行する方法を示します。"
author: ryansandness
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4b05f744120e940bfea3e92b8aac3e41fc8151d9
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="31746-103">元伝票の監査ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="31746-103">Define audit policies for source documents</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="31746-104">この手順は、監査ポリシー ルールを設定および実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="31746-104">This procedure shows how to set up and run audit policy rules.</span></span> <span data-ttu-id="31746-105">この例では、ホテル経費タイプの経費精算書を使用しています。</span><span class="sxs-lookup"><span data-stu-id="31746-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="31746-106">この手順では、USMF というデモ会社を使用します。</span><span class="sxs-lookup"><span data-stu-id="31746-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="31746-107">監査担当者ロールには、これらのタスクを実行する適切なアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="31746-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="31746-108">[監査ワークベンチ] > [設定] > [ポリシー ルール タイプ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="31746-108">Go to Audit workbench > Setup > Policy rule type.</span></span>
2. <span data-ttu-id="31746-109">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-109">Click New.</span></span>
3. <span data-ttu-id="31746-110">[ルール名] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="31746-110">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="31746-111">[説明] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="31746-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="31746-112">[クエリ名] フィールドで [経費精算書の明細行] を選択</span><span class="sxs-lookup"><span data-stu-id="31746-112">In the Query name field, select Expense report line</span></span>
6. <span data-ttu-id="31746-113">クエリ タイプ フィールドで [集計] を選択</span><span class="sxs-lookup"><span data-stu-id="31746-113">In the query type field, select Aggregate</span></span>
7. <span data-ttu-id="31746-114">[法人] フィールドで [法人] を選択</span><span class="sxs-lookup"><span data-stu-id="31746-114">In the Legal entity field, select Legal entity</span></span>
8. <span data-ttu-id="31746-115">[文書日付の参照] フィールドで [変更日時] を選択</span><span class="sxs-lookup"><span data-stu-id="31746-115">In the Document date reference field, select Modified date and time</span></span>
9. <span data-ttu-id="31746-116">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-116">Click Save.</span></span>
10. <span data-ttu-id="31746-117">[監査ワークベンチ] > [設定] > [監査ポリシー] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="31746-117">Go to Audit workbench > Setup > Audit policies.</span></span>
11. <span data-ttu-id="31746-118">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-118">Click New.</span></span>
12. <span data-ttu-id="31746-119">[名前] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="31746-119">In the Name field, type a value.</span></span>
13. <span data-ttu-id="31746-120">[ポリシーの組織] のセクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="31746-120">Expand the Policy organizations section.</span></span>
14. <span data-ttu-id="31746-121">ツリーで、「Contoso Entertainment System USA」を選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-121">In the tree, select 'Contoso Entertainment System USA'.</span></span>
15. <span data-ttu-id="31746-122">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-122">Click Add.</span></span>
16. <span data-ttu-id="31746-123">ツリーで、「Contoso Consulting USA」を選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-123">In the tree, select 'Contoso Consulting USA'.</span></span>
17. <span data-ttu-id="31746-124">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-124">Click Add.</span></span>
18. <span data-ttu-id="31746-125">ツリーで、「Contoso Retail USA」を選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-125">In the tree, select 'Contoso Retail USA'.</span></span>
19. <span data-ttu-id="31746-126">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-126">Click Add.</span></span>
20. <span data-ttu-id="31746-127">[ポリシーの組織] のセクションを折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="31746-127">Collapse the Policy organizations section.</span></span>
21. <span data-ttu-id="31746-128">[ポリシー ルール] のセクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="31746-128">Expand the Policy rules section.</span></span>
22. <span data-ttu-id="31746-129">一覧で、以前に作成したポリシー ルールを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-129">In the list, find and select the Policy Rule that was created previously.</span></span>
23. <span data-ttu-id="31746-130">[ポリシー ルールの作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-130">Click Create policy rule.</span></span>
24. <span data-ttu-id="31746-131">[有効日] フィールドに日時を入力します。</span><span class="sxs-lookup"><span data-stu-id="31746-131">In the Effective date field, enter a date and time.</span></span>
25. <span data-ttu-id="31746-132">[フィルター] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-132">Click Filter.</span></span>
26. <span data-ttu-id="31746-133">リストで、[経費カテゴリ] の行を選択し、詳細を [ホテル] に設定</span><span class="sxs-lookup"><span data-stu-id="31746-133">In the list, select the row for Expense category, and set the details to Hotel</span></span>
27. <span data-ttu-id="31746-134">[基準] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-134">In the Criteria field, enter or select a value.</span></span>
28. <span data-ttu-id="31746-135">[集計] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-135">Click the Aggregate tab.</span></span>
29. <span data-ttu-id="31746-136">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-136">Click Add.</span></span>
30. <span data-ttu-id="31746-137">リストで、トランザクション金額フィールドの値を選択</span><span class="sxs-lookup"><span data-stu-id="31746-137">In the list, select a field value of Transaction amount</span></span>
31. <span data-ttu-id="31746-138">[フィールド] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-138">In the Field field, enter or select a value.</span></span>
32. <span data-ttu-id="31746-139">集計関数のフィールドで、「合計」を選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-139">In the AggregateFunction field, select 'Sum'.</span></span>
33. <span data-ttu-id="31746-140">[グループ化] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-140">Click the Group by tab.</span></span>
34. <span data-ttu-id="31746-141">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-141">Click Add.</span></span>
35. <span data-ttu-id="31746-142">一覧で、[従業員] の値を選択</span><span class="sxs-lookup"><span data-stu-id="31746-142">In the list, select a value of Employee</span></span> 
36. <span data-ttu-id="31746-143">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-143">Click Add.</span></span>
37. <span data-ttu-id="31746-144">一覧で、[経費カテゴリ] の値を選択</span><span class="sxs-lookup"><span data-stu-id="31746-144">In the list, select a value of Expense category</span></span>
38. <span data-ttu-id="31746-145">[フィールド] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-145">In the Field field, enter or select a value.</span></span>
39. <span data-ttu-id="31746-146">[HAVING] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-146">Click the Having tab.</span></span>
40. <span data-ttu-id="31746-147">[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-147">Click Add.</span></span>
41. <span data-ttu-id="31746-148">[トランザクション金額] を選択</span><span class="sxs-lookup"><span data-stu-id="31746-148">Select Transaction amount</span></span>
42. <span data-ttu-id="31746-149">[フィールド] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-149">In the Field field, enter or select a value.</span></span>
43. <span data-ttu-id="31746-150">集計関数のフィールドで、「合計」を選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-150">In the AggregateFunction field, select 'Sum'.</span></span>
44. <span data-ttu-id="31746-151">[基準] フィールドで、「>2000」と入力します。</span><span class="sxs-lookup"><span data-stu-id="31746-151">In the Criteria field, type '>2000'.</span></span>
45. <span data-ttu-id="31746-152">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-152">Click OK.</span></span>
46. <span data-ttu-id="31746-153">[テスト] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-153">Click Test.</span></span>
47. <span data-ttu-id="31746-154">[ドキュメントの選択の開始日] フィールドで日時を入力します。</span><span class="sxs-lookup"><span data-stu-id="31746-154">In the Document selection starting date field, enter a date and time.</span></span>
48. <span data-ttu-id="31746-155">[ドキュメントの選択の終了日] フィールドで日時を入力します。</span><span class="sxs-lookup"><span data-stu-id="31746-155">In the Document selection ending date field, enter a date and time.</span></span>
49. <span data-ttu-id="31746-156">[テストの実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-156">Click Run test.</span></span>
50. <span data-ttu-id="31746-157">[アクション] ペインで、[監査ポリシー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-157">On the Action Pane, click Audit policy.</span></span>
51. <span data-ttu-id="31746-158">[追加のオプション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-158">Click Additional options.</span></span>
52. <span data-ttu-id="31746-159">[開始日] フィールドで、日付と時刻を入力します。</span><span class="sxs-lookup"><span data-stu-id="31746-159">In the Starting date field, enter a date and time.</span></span>
53. <span data-ttu-id="31746-160">[終了日] フィールドに日時を入力します。</span><span class="sxs-lookup"><span data-stu-id="31746-160">In the Ending date field, enter a date and time.</span></span>
54. <span data-ttu-id="31746-161">[バッチ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-161">Click Batch.</span></span>
55. <span data-ttu-id="31746-162">[バックグラウンドで実行] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="31746-162">Expand the Run in the background section.</span></span>
56. <span data-ttu-id="31746-163">[バッチ処理] フィールドで [はい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-163">Select Yes in the Batch processing field.</span></span>
57. <span data-ttu-id="31746-164">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-164">Click OK.</span></span>
58. <span data-ttu-id="31746-165">[監査ワークベンチ] > [監査ケース] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="31746-165">Go to Audit workbench > Audit cases.</span></span>
59. <span data-ttu-id="31746-166">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-166">In the list, find and select the desired record.</span></span>
60. <span data-ttu-id="31746-167">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-167">In the list, click the link in the selected row.</span></span>
61. <span data-ttu-id="31746-168">[関連] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="31746-168">Expand the Associations section.</span></span>
62. <span data-ttu-id="31746-169">一覧で、目的のレコードを見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="31746-169">In the list, find and select the desired record.</span></span>
63. <span data-ttu-id="31746-170">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="31746-170">In the list, click the link in the selected row.</span></span>

