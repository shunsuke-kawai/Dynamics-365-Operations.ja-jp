--- 
title: "レジスターの作成と関連付け"
description: "この手順では、販売時点管理 (POS) レジスターを作成する方法を示します。"
author: rubencdelgado
manager: AnnBe
ms.date: 10/05/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6a95019e50bcc060165dab3e6aa2b3ca8a897bf3
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---
# <a name="create-and-associate-registers"></a><span data-ttu-id="bd22b-103">レジスターの作成と関連付け</span><span class="sxs-lookup"><span data-stu-id="bd22b-103">Create and associate registers</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="bd22b-104">この手順では、販売時点管理 (POS) レジスターを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bd22b-104">This procedure demonstrates how to create a point of sale (POS) register.</span></span> <span data-ttu-id="bd22b-105">この手順では、デモ データ会社 USRT を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd22b-105">This procedure uses the demo data company USRT.</span></span>

1. <span data-ttu-id="bd22b-106">[小売りとコマース] > [チャンネル設定] > [POS 設定] > [レジスター] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd22b-106">Go to Retail and commerce > Channel setup > POS setup > Registers.</span></span>
2. <span data-ttu-id="bd22b-107">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd22b-107">Click New.</span></span>
3. <span data-ttu-id="bd22b-108">[レジスター番号] フィールドに、新しいレジスターの ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd22b-108">In the Register number field, type an ID for the new register.</span></span>
    * <span data-ttu-id="bd22b-109">レジスター ID には、レジスターを所属する店舗とその店舗内の場所にマップするためのコードが通常含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd22b-109">The register ID typically includes codes that help map the register to the store to which it belongs, and the location within the store.</span></span>  
4. <span data-ttu-id="bd22b-110">[名前] フィールドに、レジスターの内容を説明する名前を入力します..</span><span class="sxs-lookup"><span data-stu-id="bd22b-110">In the Name field, type a descriptive name for the register..</span></span>
5. <span data-ttu-id="bd22b-111">[店舗番号] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="bd22b-111">In the Store number field, enter or select a value.</span></span>
6. <span data-ttu-id="bd22b-112">[ハードウェア プロファイル] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="bd22b-112">In the Hardware profile field, enter or select a value.</span></span>
    * <span data-ttu-id="bd22b-113">ハードウェア プロファイルはキャッシュ ドロワーやレシート プリンターなど、レジスターに接続される小売周辺機器を指定するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd22b-113">Hardware profiles are used to specify the retail peripherals that will be connected to the register, such as cash drawer and receipt printer.</span></span>  
7. <span data-ttu-id="bd22b-114">[ビジュアル プロファイル] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="bd22b-114">In the Visual profile field, enter or select a value.</span></span>
    * <span data-ttu-id="bd22b-115">視覚プロファイルは POS のバックグラウンド、ログイン ページ、および POS のテーマで使用されている画像を指定するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd22b-115">Visual profiles are used to specify the images used in the POS background and login page as well as themes for the POS.</span></span>  
8. <span data-ttu-id="bd22b-116">[EFT POS レジスター番号] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd22b-116">In the EFT POS register number field, type a value.</span></span>
    * <span data-ttu-id="bd22b-117">EFT POS レジスター番号はどの支払ターミナルが認証要求を送信しているかを支払処理担当者に通知するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd22b-117">The EFT POS register number is used to inform the payment processor which payment terminal is sending authorization requests.</span></span> <span data-ttu-id="bd22b-118">この値は、「ターミナル ID」、または「TID」と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="bd22b-118">This value is often called the "Terminal ID" or “TID”.</span></span> <span data-ttu-id="bd22b-119">TID は、支払デバイスのステッカーの明細行から見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="bd22b-119">The TID can generally be found on a sticker on the payment device.</span></span>  
9. <span data-ttu-id="bd22b-120">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd22b-120">Click Save.</span></span>

