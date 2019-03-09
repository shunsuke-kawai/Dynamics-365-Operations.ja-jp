---
title: 移動オーダー用の倉庫の設定
description: このトピックでは、移動オーダーの倉庫を設定する方法について説明します。
author: Mirzaab
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 8111601cb2948c66097b0f5b2f261b7462b279f9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "337466"
---
# <a name="set-up-warehouses-for-transfer-orders"></a><span data-ttu-id="d289c-103">移動オーダー用の倉庫の設定</span><span class="sxs-lookup"><span data-stu-id="d289c-103">Set up warehouses for transfer orders</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d289c-104">倉庫レベルを使用して倉庫間の移動オーダーをサポートする階層を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d289c-104">You can use warehouse levels to create a hierarchy that supports transfer orders between warehouses.</span></span> <span data-ttu-id="d289c-105">この設定に基づいて、マスタ スケジューリングは個々の倉庫レベルにおける在庫品目要求を計算し、割り当てられたソース倉庫から計画移動オーダーを生成してそれらの要求を満たします。</span><span class="sxs-lookup"><span data-stu-id="d289c-105">Based on this setup, master scheduling calculates item requirements at the individual warehouse level and generates planned transfer orders from an assigned source warehouse to fulfill them.</span></span>

1.  <span data-ttu-id="d289c-106">**在庫管理 > 設定 > 在庫詳細 > 倉庫** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d289c-106">Click **Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>

2.  <span data-ttu-id="d289c-107">補充する倉庫を選択します。</span><span class="sxs-lookup"><span data-stu-id="d289c-107">Select the warehouse that you want to refill.</span></span>

3.  <span data-ttu-id="d289c-108">**マスター プラン** クイック タブで、**補充**チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d289c-108">On the **Master planning** FastTab, select the **Refilling** check box.</span></span>

4.  <span data-ttu-id="d289c-109">**主要倉庫**フィールドで、補充倉庫として割り当てる倉庫を選択します。</span><span class="sxs-lookup"><span data-stu-id="d289c-109">In the **Main warehouse** field, select the warehouse that you want to assign as the refilling warehouse.</span></span> <span data-ttu-id="d289c-110">マスタ スケジューリングは選択した倉庫の移動要求を計算し、割り当てられた**主要倉庫**から計画移動オーダーを生成します。</span><span class="sxs-lookup"><span data-stu-id="d289c-110">Master scheduling calculates a transfer requirement for the selected warehouse and generates a planned transfer order from the assigned **Main warehouse**.</span></span>
   
    > [!NOTE]
    > <P><span data-ttu-id="d289c-111"><STRONG>補充</STRONG>チェックボックスをオフにすると、<STRONG>主要倉庫</STRONG>に関連する倉庫レベルが選択した倉庫に割り当てられますが、<STRONG>主要倉庫</STRONG>は補充倉庫として設定されません。</span><span class="sxs-lookup"><span data-stu-id="d289c-111">If you clear the <STRONG>Refilling</STRONG> check box, the selected warehouse is assigned a warehouse level in regard to the <STRONG>Main warehouse</STRONG>, but the <STRONG>Main warehouse</STRONG> is not set up as a refilling warehouse.</span></span></P>

5.  <span data-ttu-id="d289c-112">ページを閉じて、新しい設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="d289c-112">Close the page to apply the new setup.</span></span>


> [!TIP]
> <P><span data-ttu-id="d289c-113">補充用の倉庫を割り当てる場合は、倉庫を<STRONG>保管分析コード グループ</STRONG>ページの保管分析コードとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d289c-113">If you want to assign a warehouse for refilling, you must first set up the warehouse as a storage dimension on the <STRONG>Storage dimension groups</STRONG> page.</span></span> <span data-ttu-id="d289c-114">このページで、倉庫に対する<STRONG>有効</STRONG>フィールドおよび<STRONG>分析コード別補充計画</STRONG>フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="d289c-114">On this page, select the <STRONG>Active</STRONG> field and the <STRONG>Coverage plan by dimension</STRONG> field for the warehouse.</span></span></P>

## <a name="set-up-transport-lead-time"></a><span data-ttu-id="d289c-115">配送のリード タイムの設定</span><span class="sxs-lookup"><span data-stu-id="d289c-115">Set up transport lead time</span></span>

<span data-ttu-id="d289c-116">**配送日数**ページの倉庫間で配送のリード タイムを設定することも必要です。</span><span class="sxs-lookup"><span data-stu-id="d289c-116">You must also set up the transport lead time between the warehouses on the **Transport days** page.</span></span> 
1. <span data-ttu-id="d289c-117">**在庫管理 > 設定 > 配分 > 配送日数**に移動します。</span><span class="sxs-lookup"><span data-stu-id="d289c-117">Go to **Inventory management > Setup > Distribution > Transport days**.</span></span>
2. <span data-ttu-id="d289c-118">**入荷場所**フィールドで、**倉庫**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d289c-118">In the **Receiving point** field, select **warehouse**.</span></span>
3. <span data-ttu-id="d289c-119">**出荷倉庫**、**入荷倉庫**、および**配送日数**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d289c-119">Select the **Shipping warehouse**, **Receiving warehouse**, and **Transport days**.</span></span> 
4. <span data-ttu-id="d289c-120">(オプション) 荷渡方法によっては、**荷渡方法ごとの配送日数**タブで配送時間を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d289c-120">(Optional) You can also set transport time, depending on the mode of delivery, under the **Transport days per mode of delivery** tab.</span></span>