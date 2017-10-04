---
title: "売掛金勘定の決算"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 59372
ms.assetid: c18d83e5-4adb-422a-91be-82a665d8288b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2b2e827df0c679855af9624f8a2fb36cb23f359a
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="close-accounts-receivable"></a><span data-ttu-id="b3753-102">売掛金勘定の決算</span><span class="sxs-lookup"><span data-stu-id="b3753-102">Close Accounts receivable</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="b3753-103">次の表に売掛金勘定の決算業務プロセスをサポートしているページの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="b3753-103">The following table lists the pages that support the close Accounts receivable business process.</span></span>

> [!NOTE] 
> <span data-ttu-id="b3753-104">次の表で一部のページを開くには、情報の入力またはパラメーター設定の指定が必要です。</span><span class="sxs-lookup"><span data-stu-id="b3753-104">To open some of the pages in the table, you must enter information or specify parameter settings.</span></span>

<span data-ttu-id="b3753-105">**業務プロセス コンポーネント タスク**</span><span class="sxs-lookup"><span data-stu-id="b3753-105">**Business process component task**</span></span>                   

<span data-ttu-id="b3753-106">一般会計の期間の閉鎖</span><span class="sxs-lookup"><span data-stu-id="b3753-106">Close periods in the general ledger</span></span>

| <span data-ttu-id="b3753-107">ページ名</span><span class="sxs-lookup"><span data-stu-id="b3753-107">Page name</span></span>                            | <span data-ttu-id="b3753-108">用途</span><span class="sxs-lookup"><span data-stu-id="b3753-108">Usage</span></span>                                                                                      |
|--------------------------------------|--------------------------------------------------------------------------------------------|
|<span data-ttu-id="b3753-109">バッチ ジョブ</span><span class="sxs-lookup"><span data-stu-id="b3753-109">Batch job</span></span>                             | <span data-ttu-id="b3753-110">バッチ ジョブを表示または作成します。</span><span class="sxs-lookup"><span data-stu-id="b3753-110">View or create batch jobs.</span></span> <span data-ttu-id="b3753-111">バッチ ジョブを完了できなかったため、すべての転記が完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3753-111">Batch jobs might not be completed, and you want make sure that all posting is completed.</span></span>                                                                                                               |
|<span data-ttu-id="b3753-112">販売注文の確認</span><span class="sxs-lookup"><span data-stu-id="b3753-112">Confirm sales order</span></span>                   | <span data-ttu-id="b3753-113">販売注文を更新します。</span><span class="sxs-lookup"><span data-stu-id="b3753-113">Update sales orders.</span></span>                                                                       |
|<span data-ttu-id="b3753-114">外貨再評価</span><span class="sxs-lookup"><span data-stu-id="b3753-114">Foreign currency revaluation</span></span>          | <span data-ttu-id="b3753-115">外貨で転記された未処理の顧客トランザクションの値を更新するトランザクションを生成します。</span><span class="sxs-lookup"><span data-stu-id="b3753-115">Generate transactions that update the value of open customer transactions in foreign currencies.</span></span>                                                                                                                         |
| <span data-ttu-id="b3753-116">仕訳帳</span><span class="sxs-lookup"><span data-stu-id="b3753-116">Journal</span></span>                              | <span data-ttu-id="b3753-117">請求書、支払、および約束手形を転記します。</span><span class="sxs-lookup"><span data-stu-id="b3753-117">Post invoices, payments, and promissory notes.</span></span>                                             |
| <span data-ttu-id="b3753-118">仕訳伝票</span><span class="sxs-lookup"><span data-stu-id="b3753-118">Journal voucher</span></span>                      |<ul><li><span data-ttu-id="b3753-119">**支払仕訳帳** : 支払を生成、処理、および転記します。</span><span class="sxs-lookup"><span data-stu-id="b3753-119">**Payment journal** – Generate, process, and post payments.</span></span></li><li><span data-ttu-id="b3753-120">**為替手形振出仕訳帳** : 為替手形を転記します。</span><span class="sxs-lookup"><span data-stu-id="b3753-120">**Draw bill of exchange journal** – Post bills of exchange.</span></span></li><li><span data-ttu-id="b3753-121">**為替手形受取拒否仕訳帳** : 受取拒否手形を転記します。</span><span class="sxs-lookup"><span data-stu-id="b3753-121">**Protest bill of exchange journal** – Post protested bills of exchange.</span></span></li><li><span data-ttu-id="b3753-122">**為替手形仕訳の振出** : 再振出済為替手形を転記します。</span><span class="sxs-lookup"><span data-stu-id="b3753-122">**Redraw bill of exchange journal** – Post redrawn bills of exchange.</span></span></li><li><span data-ttu-id="b3753-123">**送金仕訳帳** : 送金を転記します。</span><span class="sxs-lookup"><span data-stu-id="b3753-123">**Remittance journal** – Post remittances.</span></span></li><li><span data-ttu-id="b3753-124">**為替手形仕訳帳の決済** : 決済済為替手形を転記します</span><span class="sxs-lookup"><span data-stu-id="b3753-124">**Settle bill of exchange journal** – Post settled bills of exchange</span></span></li></ul>                   |
| <span data-ttu-id="b3753-125">梱包明細転記</span><span class="sxs-lookup"><span data-stu-id="b3753-125">Packing slip posting</span></span>                 | <span data-ttu-id="b3753-126">販売注文の梱包明細を更新します。</span><span class="sxs-lookup"><span data-stu-id="b3753-126">Update packing slips for sales orders.</span></span>                                                     |
| <span data-ttu-id="b3753-127">自由書式の請求書の転記</span><span class="sxs-lookup"><span data-stu-id="b3753-127">Post free text invoice</span></span>               | <span data-ttu-id="b3753-128">自由書式の請求書を転記します。</span><span class="sxs-lookup"><span data-stu-id="b3753-128">Post free text invoices.</span></span>                                                                   |
| <span data-ttu-id="b3753-129">請求の転記</span><span class="sxs-lookup"><span data-stu-id="b3753-129">Posting invoice</span></span>                      | <span data-ttu-id="b3753-130">販売注文の請求書を転記します。</span><span class="sxs-lookup"><span data-stu-id="b3753-130">Post invoices for sales orders.</span></span>                                                            |
| <span data-ttu-id="b3753-131">ピッキング リストの転記</span><span class="sxs-lookup"><span data-stu-id="b3753-131">Posting picking list</span></span>                 |<span data-ttu-id="b3753-132">販売注文のピッキング リストを更新します。</span><span class="sxs-lookup"><span data-stu-id="b3753-132">Update picking lists for sales orders.</span></span>                                                      |

<span data-ttu-id="b3753-133">**業務プロセス コンポーネント タスク**</span><span class="sxs-lookup"><span data-stu-id="b3753-133">**Business process component task**</span></span>   

<span data-ttu-id="b3753-134">EU 販売リストの作成および送信</span><span class="sxs-lookup"><span data-stu-id="b3753-134">Create and submit the EU sales list</span></span>

| <span data-ttu-id="b3753-135">ページ名</span><span class="sxs-lookup"><span data-stu-id="b3753-135">Page name</span></span>                            | <span data-ttu-id="b3753-136">用途</span><span class="sxs-lookup"><span data-stu-id="b3753-136">Usage</span></span>                                                                                      |
|--------------------------------------|--------------------------------------------------------------------------------------------|
|<span data-ttu-id="b3753-137">EU 販売リスト</span><span class="sxs-lookup"><span data-stu-id="b3753-137">EU sales list</span></span>                         | <span data-ttu-id="b3753-138">付加価値税 (VAT) 申告のための売上税所轄官庁への欧州連合 (EU) 販売のレポート。</span><span class="sxs-lookup"><span data-stu-id="b3753-138">Report on European Union (EU) sales to the tax authority for value-added tax (VAT) declaration purposes.</span></span>                                                                                                                           |






