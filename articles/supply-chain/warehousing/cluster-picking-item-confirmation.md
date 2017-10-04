---
title: "クラスター ピッキングの製品の確認"
description: "このトピックでは、クラスタ ピッキングと共に品目検証を設定する方法について説明します。"
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
ms.openlocfilehash: 17f5761df4294abfea28e7cb8d50c86f1e3e136f
ms.contentlocale: ja-jp
ms.lasthandoff: 07/18/2017

---

[!include[banner](../includes/banner.md)]

# <a name="product-confirmation-for-cluster-picking"></a><span data-ttu-id="b8641-103">クラスター ピッキングの製品の確認</span><span class="sxs-lookup"><span data-stu-id="b8641-103">Product confirmation for cluster picking</span></span>
<span data-ttu-id="b8641-104">クラスタ ピッキングでは、複数の注文に対する品目のピッキングを同時にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b8641-104">Cluster picking allows you to pick items for several orders at the same time.</span></span> <span data-ttu-id="b8641-105">クラスタ ピッキングが適用される場合、クラスタに追加される品目を確認するための品目確認書は重要です。</span><span class="sxs-lookup"><span data-stu-id="b8641-105">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="b8641-106">クラスタ ピッキング プロセス中にクラスタ ピッキングの品目を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="b8641-106">You can verify items in cluster picking during the cluster picking process.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="b8641-107">該当する場合</span><span class="sxs-lookup"><span data-stu-id="b8641-107">Where it applies</span></span>
<span data-ttu-id="b8641-108">クラスタ ピッキングの品目の検証は、非クラスタ ピッキング プロセスで品目を確認する場合と同様に働きます。</span><span class="sxs-lookup"><span data-stu-id="b8641-108">Item verification for cluster picking works the same way as when you verify items in a non-cluster picking processes.</span></span> <span data-ttu-id="b8641-109">設定は、製品バー コード設定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="b8641-109">The setup is based on the product bar code setup.</span></span>

## <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="b8641-110">クラスタ ピッキングの品目の検証の設定</span><span class="sxs-lookup"><span data-stu-id="b8641-110">Set up item verification with cluster picking</span></span>
1.  <span data-ttu-id="b8641-111">モバイル デバイスのメニュー項目で、作業確認の設定フォームを開きます: [**倉庫管理**] > [**倉庫管理**] > [**設定**] > [**モバイル デバイス**] > [**モバイル デバイスのメニュー項目**] に進みます。</span><span class="sxs-lookup"><span data-stu-id="b8641-111">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span>
2.  <span data-ttu-id="b8641-112">モバイル デバイス メニュー品目から、[**作業確認の設定**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="b8641-112">From the mobile device menu item, open **Work confirmation setup**.</span></span>

| <span data-ttu-id="b8641-113">オプション</span><span class="sxs-lookup"><span data-stu-id="b8641-113">Option</span></span>        | <span data-ttu-id="b8641-114">説明</span><span class="sxs-lookup"><span data-stu-id="b8641-114">Description</span></span>   | 
| ------------- | ------------- |
|<span data-ttu-id="b8641-115">製品の確認</span><span class="sxs-lookup"><span data-stu-id="b8641-115">Product confirmation</span></span> | <span data-ttu-id="b8641-116">スキャンしたときに、モバイル デバイスから各在庫を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b8641-116">Allows you to verify each piece of inventory from the mobile device when scanned.</span></span>|
