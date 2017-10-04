---
title: "ピース ピッキング確認"
description: "このトピックでは、モバイル デバイスからピース ピッキングの確認を設定して適用する方法について説明します。"
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 62b637b81a522c353067248deea79cfbf98518e9
ms.contentlocale: ja-jp
ms.lasthandoff: 07/18/2017

---

# <a name="piece-picking-confirmation"></a><span data-ttu-id="05358-103">ピース ピッキング確認</span><span class="sxs-lookup"><span data-stu-id="05358-103">Piece picking confirmation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="05358-104">ピース ピッキングにより、モバイル デバイスでピッキング作業または棚卸作業を通して各在庫を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="05358-104">Piece picking allows you to confirm each piece of inventory through picking or counting work on a mobile device.</span></span> <span data-ttu-id="05358-105">ピッキングについては、ピッキングする作業に指定された数量まで、処理する作業量を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="05358-105">For picks, you can confirm the quantity of work to be processed up to the quantity that is specified on work to be picked.</span></span> <span data-ttu-id="05358-106">棚卸作業については、棚卸在庫をスキャンでき、合計金額を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="05358-106">For counting work, you can scan the inventory that you are counting and track the total amount.</span></span>

<span data-ttu-id="05358-107">ピース ピッキングを有効にすると、製品の確認書が自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="05358-107">When you enable piece picking, product confirmation is automatically selected.</span></span> <span data-ttu-id="05358-108">作業の種類の選択については、在庫の最大数が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="05358-108">For work-type picks, a maximum number of pieces is enabled.</span></span> <span data-ttu-id="05358-109">これにより、作業プロセス中に確定する必要がある在庫数数に最大値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="05358-109">This allows you to set a maximum to the number of pieces that must be confirmed during the work process.</span></span> <span data-ttu-id="05358-110">最大数量は、処理されている現在の作業単位に基づいています。</span><span class="sxs-lookup"><span data-stu-id="05358-110">The maximum quantity is based on the current work unit that is being processed.</span></span> <span data-ttu-id="05358-111">棚卸作業の種類には、最大値を設定できません。</span><span class="sxs-lookup"><span data-stu-id="05358-111">The counting work type does not allow a maximum.</span></span>

<span data-ttu-id="05358-112">スキャンされたバーコードに関連付けられた数量と測定単位 (UOM) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="05358-112">You can also use the quantity and unit of measure (UOM) that is associated with a scanned bar code.</span></span> <span data-ttu-id="05358-113">これにより、複数のライセンス番号の入荷、購買注文の品目、移動オーダーの品目および負荷品目を含む着信フローでの受領が実行されます。</span><span class="sxs-lookup"><span data-stu-id="05358-113">This will work for receiving on inbound flows including mixed license plate receiving, purchase order item, transfer order item, and load item.</span></span> <span data-ttu-id="05358-114">また、バーコードをスキャンすると、バーコード上の UOM と作業単位の間で変換された確認済みの在庫総数に数量が加算されます。</span><span class="sxs-lookup"><span data-stu-id="05358-114">It also works for piece picking where scanning the bar code will add the quantity to the total number of confirmed pieces converting between the UOM on the bar code and the work unit.</span></span> <span data-ttu-id="05358-115">バーコード上で UOM をカウントすると、その数量が順序グループでカウントできることが確認された場合、数量が合計カウントに加算されます。</span><span class="sxs-lookup"><span data-stu-id="05358-115">If, when counting the UOM on the bar code, it is confirmed that the quantity is allowed for counting on the sequence group, the quantity will be added to the total count.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="05358-116">該当する場合</span><span class="sxs-lookup"><span data-stu-id="05358-116">Where it applies</span></span>

<span data-ttu-id="05358-117">ピース ピッキングは、すべての棚卸作業と任意のタイプの作業における初期ピッキング作業に適しています。</span><span class="sxs-lookup"><span data-stu-id="05358-117">Piece picking works for all counting work and for the initial pick for any type of work.</span></span> <span data-ttu-id="05358-118">品目がシリアル番号で管理されている場合、またはナンバー プレート (LP) の場所から製品またはかんばんをピッキングしアイテムがステージングに設定されている場合、ピース ピッキングは適用されません。</span><span class="sxs-lookup"><span data-stu-id="05358-118">Piece picking does not apply if the item is controlled by serial numbers or if it is a production or kanban pick from a license plate (LP) location and the item is set to staging.</span></span>

## <a name="set-up-piece-picking"></a><span data-ttu-id="05358-119">ピッキング ピッキングの設定</span><span class="sxs-lookup"><span data-stu-id="05358-119">Set up piece picking</span></span>

1.  <span data-ttu-id="05358-120">モバイル デバイスのメニュー項目で、作業確認の設定フォームを開きます: [倉庫管理] > [**倉庫管理**] > [**設定**] > [**モバイル デバイス**] > [**モバイル デバイスのメニュー項目**] に進みます。</span><span class="sxs-lookup"><span data-stu-id="05358-120">On a mobile device menu item, open the setup form for work confirmation: Warehouse management > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span> 
2. <span data-ttu-id="05358-121">モバイル デバイス メニュー品目から、[作業確認の設定] を開きます。</span><span class="sxs-lookup"><span data-stu-id="05358-121">From the mobile device menu item, open Work confirmation setup.</span></span>

<span data-ttu-id="05358-122">作業タイプが選択または集計の場合、以下のオプションが選択可能になります。</span><span class="sxs-lookup"><span data-stu-id="05358-122">The following options become available for selection when the work type is pick or counting.</span></span>

| <span data-ttu-id="05358-123">オプション</span><span class="sxs-lookup"><span data-stu-id="05358-123">Option</span></span>        | <span data-ttu-id="05358-124">説明</span><span class="sxs-lookup"><span data-stu-id="05358-124">Description</span></span>   | 
| ------------- | ------------- |
| <span data-ttu-id="05358-125">ピース ピッキング確認</span><span class="sxs-lookup"><span data-stu-id="05358-125">Piece picking confirmation</span></span>   | <span data-ttu-id="05358-126">選択と棚卸作業タイプに使用できます。</span><span class="sxs-lookup"><span data-stu-id="05358-126">Available for pick and counting work types.</span></span> <span data-ttu-id="05358-127">製品の確認書が自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="05358-127">Product confirmation is automatically selected.</span></span> <span data-ttu-id="05358-128">モバイル デバイスから各在庫を確認できます。</span><span class="sxs-lookup"><span data-stu-id="05358-128">Allows you to confirm each piece of inventory from the mobile device.</span></span> | 
| <span data-ttu-id="05358-129">ピースの最大数</span><span class="sxs-lookup"><span data-stu-id="05358-129">Maximum number of pieces</span></span>     | <span data-ttu-id="05358-130">ピース ピッキングの確認が有効化された場合にピッキング作業に使用できます。</span><span class="sxs-lookup"><span data-stu-id="05358-130">Available for pick work if piece picking confirmation is enabled.</span></span> <span data-ttu-id="05358-131">確認する必要がある在庫数の制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="05358-131">Sets a limit to the number of pieces that you must confirm.</span></span> |  
