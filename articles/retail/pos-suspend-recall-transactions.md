---
title: "販売時点管理 (POS) で トランザクションを中断し再開する"
description: "このトピックでは、Microsoft Dynamics 365 for Retail を使用して、ユーザーが進行中のトランザクションを中断して後で再開する、または別のレジスターで再開する方法について説明します。"
author: jblucher
manager: AnnBe
ms.date: 11/27/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: ffb04609318c7de4b9ef729a8e03a7f9395806b8
ms.contentlocale: ja-jp
ms.lasthandoff: 01/04/2019

---

# <a name="suspend-and-resume-transactions-in-the-point-of-sale-pos"></a><span data-ttu-id="b97ee-103">販売時点管理 (POS) で トランザクションを中断し再開する</span><span class="sxs-lookup"><span data-stu-id="b97ee-103">Suspend and resume transactions in the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="b97ee-104">販売時点管理 (POS) ユーザーは、進行中のトランザクションを中断して後で再開するか、または別のレジスターで再開できます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-104">Point of sale (POS) users can suspend in-progress transactions, and then resume them later or on a different register.</span></span> <span data-ttu-id="b97ee-105">現在のトランザクションを処理しながら、別のタスクのため素早くレジスターを確保するために、トランザクションはしばしば中断されます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-105">Transactions are often suspended to quickly free up a register for a different task without losing any progress on the current transaction.</span></span> <span data-ttu-id="b97ee-106">たとえば、店舗スタッフは、モバイル デバイスで顧客のトランザクションを処理を始めても、キャッシュ ドロワーのあるレジスターで処理を終えねばなりません。</span><span class="sxs-lookup"><span data-stu-id="b97ee-106">For example, a store associate starts to process a customer's transaction on a mobile device but must complete it on a register that has a cash drawer.</span></span> <span data-ttu-id="b97ee-107">この場合、店舗スタッフはモバイル デバイス上でのトランザクションを中断して、レジスターでそれを呼び出して再開することができます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-107">In this case, the store associate can suspend the transaction on the mobile device, and then recall and resume it on a register.</span></span>

## <a name="configure-suspend-and-resume-functionality"></a><span data-ttu-id="b97ee-108">中断と再開機能のコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="b97ee-108">Configure suspend and resume functionality</span></span>

### <a name="pos-operations"></a><span data-ttu-id="b97ee-109">POS 操作</span><span class="sxs-lookup"><span data-stu-id="b97ee-109">POS operations</span></span>

<span data-ttu-id="b97ee-110">2 つの [POS 操作](pos-operations.md)は、POS サポートを中断し、シナリオを再開します。</span><span class="sxs-lookup"><span data-stu-id="b97ee-110">Two [POS operations](pos-operations.md) let the POS support suspend and resume scenarios.</span></span> <span data-ttu-id="b97ee-111">これらの工程を、トランザクション ページまたはウェルカム ページにある[ボタン グリッド](pos-screen-layouts.md)に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-111">You can assign these operations to [button grids](pos-screen-layouts.md) on the transaction page or the welcome page.</span></span>

- <span data-ttu-id="b97ee-112">503: トランザクションの中断</span><span class="sxs-lookup"><span data-stu-id="b97ee-112">503: Suspend transaction</span></span>
- <span data-ttu-id="b97ee-113">504: トランザクションの呼び出し</span><span class="sxs-lookup"><span data-stu-id="b97ee-113">504: Recall transaction</span></span>

### <a name="receipt-template"></a><span data-ttu-id="b97ee-114">入庫のテンプレート</span><span class="sxs-lookup"><span data-stu-id="b97ee-114">Receipt template</span></span>

<span data-ttu-id="b97ee-115">トランザクションが中断された場合、印刷された伝票を生成するために、POS をコンフィギュレーションすることができます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-115">The POS can be configured to generate a printed slip when a transaction is suspended.</span></span> <span data-ttu-id="b97ee-116">その伝票は、後でトランザクションをすばやく識別し呼び出したりするのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-116">That slip can then be used to quickly identify and recall the transaction later.</span></span>

<span data-ttu-id="b97ee-117">伝票印刷のために POS を有効にするには、**中断されたトランザクション**の受領書フォーマットを店舗のレシート プロファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b97ee-117">To enable the POS to print a slip, you must add the **Suspended transaction** receipt format to the store's receipt profile.</span></span> <span data-ttu-id="b97ee-118">トランザクションに関する特定の詳細を含める、もしくは除外するように、受領書フォーマットをデザインすることができます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-118">You can design the receipt format so that it includes or excludes specific details about the transaction.</span></span> <span data-ttu-id="b97ee-119">たとえば、フォーマットには、スキャンをサポートするためのバーコードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-119">For example, the format can include a barcode to support scanning.</span></span>

### <a name="receipt-numbering"></a><span data-ttu-id="b97ee-120">レシート番号</span><span class="sxs-lookup"><span data-stu-id="b97ee-120">Receipt numbering</span></span>

<span data-ttu-id="b97ee-121">印刷されたレシートを生成する他の POS トランザクション タイプに関しては、店舗機能プロファイルの**レシート番号**セクションで中断されたトランザクションの番号順序を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-121">As for other POS transaction types that generate a printed receipt, you can define a number sequence for suspended transactions in the **Receipt numbering** section of the store's functionality profile.</span></span>

### <a name="void-when-closing-shift"></a><span data-ttu-id="b97ee-122">シフトのクローズ時は無効となります</span><span class="sxs-lookup"><span data-stu-id="b97ee-122">Void when closing shift</span></span>

<span data-ttu-id="b97ee-123">**シフトのクローズ時に無効**オプションを使用して、ユーザーがシフトをクローズする前に、中断されたトランザクションを完了または無効にすることを要求できます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-123">You can use the **Void when closing shift** option to require that users either complete or void any suspended transactions before they close their shift.</span></span> <span data-ttu-id="b97ee-124">**シフトのクローズ**操作中に、POS は未処理の中断されたトランザクションを表示または無効にするようユーザーに要求します。</span><span class="sxs-lookup"><span data-stu-id="b97ee-124">During the **Close shift** operation, the POS will prompt users to either view or void any outstanding suspended transactions.</span></span>

## <a name="suspend-and-resume-a-transaction"></a><span data-ttu-id="b97ee-125">トランザクションの中断および再開</span><span class="sxs-lookup"><span data-stu-id="b97ee-125">Suspend and resume a transaction</span></span>

### <a name="suspend-a-transaction"></a><span data-ttu-id="b97ee-126">トランザクションの中断</span><span class="sxs-lookup"><span data-stu-id="b97ee-126">Suspend a transaction</span></span>

<span data-ttu-id="b97ee-127">十分な権限があり、**トランザクションの中断**操作を含む画面レイアウトを持つユーザーは、後でまたは別のレジスターに呼び戻すことができるように、トランザクションを中断することができます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-127">Users who have sufficient privileges, and who have a screen layout that includes the **Suspend transaction** operation, can suspend a transaction so that it can be recalled later or on a different register.</span></span>

<span data-ttu-id="b97ee-128">トランザクションが以下のタイプの行を含んで**いない**場合にのみ、トランザクションを中断することができます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-128">Transactions can be suspended only if they do **not** contain the following types of lines:</span></span>

- <span data-ttu-id="b97ee-129">有効な支払明細行</span><span class="sxs-lookup"><span data-stu-id="b97ee-129">Active payment lines</span></span>
- <span data-ttu-id="b97ee-130">ギフト カード明細行 (ギフト カードを発行するか、ギフト カードの残高に追加する)</span><span class="sxs-lookup"><span data-stu-id="b97ee-130">Gift card lines (either to issue a gift card or to add to the gift card balance)</span></span>

<span data-ttu-id="b97ee-131">中断されたトランザクションは、店舗の販売情報や使用可能な在庫情報には影響しません。</span><span class="sxs-lookup"><span data-stu-id="b97ee-131">A suspended transaction doesn't affect sales information or inventory availability information for the store.</span></span>

### <a name="resume-a-suspended-transaction"></a><span data-ttu-id="b97ee-132">中断されたトランザクションを再開する</span><span class="sxs-lookup"><span data-stu-id="b97ee-132">Resume a suspended transaction</span></span>

<span data-ttu-id="b97ee-133">十分な権限があり、**トランザクションの呼び出し**操作が含まれるレイアウトを持つユーザーであれば、どのユーザーでも同じ店舗で中断されたトランザクションを呼び出して再開することができます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-133">Suspended transactions can be recalled and resumed in the same store by any user who has sufficient privileges, and who also has a layout that includes the **Recall transaction** operation.</span></span>

<span data-ttu-id="b97ee-134">中断されたトランザクションをすばやく簡単に呼び出すには、**トランザクションの呼び出し**操作でトランザクションのリストを表示しながら、印刷された伝票のバーコードをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="b97ee-134">To quickly and easily recall a suspended transaction, scan the barcode on the printed slip while you're viewing the list of transactions from the **Recall transaction** operation.</span></span>

### <a name="considerations-for-offline-mode"></a><span data-ttu-id="b97ee-135">オフライン モードに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="b97ee-135">Considerations for offline mode</span></span>

- <span data-ttu-id="b97ee-136">データがオフライン データベースと同期されていないため、POS がオンライン モードの間に中断されたトランザクションはオフライン モードで再開できません。</span><span class="sxs-lookup"><span data-stu-id="b97ee-136">Any transaction that is suspended while the POS is in online mode can't be resumed in offline mode, because the data isn't synced to the offline database.</span></span>
- <span data-ttu-id="b97ee-137">POS がオフライン モードの時にトランザクションを中断した場合、トランザクションを中断してから POS がオンライン モードに戻っていなければ、オフライン モードで呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-137">If you suspend a transaction while the POS is in offline mode, you can recall it in offline mode, provided that the POS wasn't switched back to online mode at any time since you suspended the transaction.</span></span> <span data-ttu-id="b97ee-138">POS がオンライン モードに切り替えられた場合、中断されたトランザクションに関するデータはオンライン データベースに移動され、オフライン データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-138">When the POS is switched back to online mode, data about suspended transactions is moved to the online database and removed from the offline database.</span></span> <span data-ttu-id="b97ee-139">したがって、トランザクションは、オンライン モードでのみ再開できます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-139">Therefore, the transactions can be resumed only in online mode.</span></span> <span data-ttu-id="b97ee-140">POS をオフライン モードに切り替えた場合、中断されたトランザクションは既にオフライン データベースから削除されているため、再開することはできません。</span><span class="sxs-lookup"><span data-stu-id="b97ee-140">If you switch the POS back to offline mode, you won't be able to resume those suspended transaction, because they have already been removed from the offline database.</span></span>

### <a name="void-a-suspended-transaction"></a><span data-ttu-id="b97ee-141">中断されたトランザクションの無効化</span><span class="sxs-lookup"><span data-stu-id="b97ee-141">Void a suspended transaction</span></span>

<span data-ttu-id="b97ee-142">トランザクションを呼び出してから**トランザクションの無効化**操作を実行するか、**トランザクションの呼び出し**リストを選択してアプリ バーの**無効化**を選択することによって、中断されたトランザクションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-142">You can void suspended transactions either by recalling the transaction and then performing the **Void transaction** operation, or by selecting the transaction in the **Recall transaction** list and selecting **Void** on the app bar.</span></span> <span data-ttu-id="b97ee-143">または、ユーザーがシフトをクローズする時に中断されたトランザクションを無効にするように、店舗をコンフィギュレーションすることができます。</span><span class="sxs-lookup"><span data-stu-id="b97ee-143">Alternatively, the store can be configured to prompt users to void suspended transactions when they close their shift.</span></span>
