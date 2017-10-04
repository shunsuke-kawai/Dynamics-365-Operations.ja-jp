---
title: "店舗パフォーマンスの分析"
description: "この記事では、Microsoft Dynamics 365 for Retail データに基づいて、店舗パフォーマンスにアクセスし、それを検討し見抜くために、メモリ内およびリアルタイム分析を使用する方法について説明します。"
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 57811
ms.assetid: 495a66f0-491a-4688-842d-51c33c37676f
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 5cb5881cdb9c769bfc4272da85bc1c886a36705b
ms.contentlocale: ja-jp
ms.lasthandoff: 08/29/2017

---

# <a name="analyze-store-performance"></a><span data-ttu-id="f3f5e-103">店舗のパフォーマンスの分析</span><span class="sxs-lookup"><span data-stu-id="f3f5e-103">Analyze store performance</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="f3f5e-104">この記事では、Microsoft Dynamics 365 for Retail データに基づいて、店舗パフォーマンスにアクセスし、それを検討し見抜くために、メモリ内およびリアルタイム分析を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3f5e-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about store performance, based on your Microsoft Dynamics 365 for Retail data.</span></span> 

<span data-ttu-id="f3f5e-105">Microsoft Dynamics 365 for Retail の一部として、次の場所のいずれかから最初から用意されている [**チャンネル概要**] レポートを開くことにより、選択した期間における組織階層のさまざまなレベルでリアルタイムに店舗パフォーマンスを調査できます。</span><span class="sxs-lookup"><span data-stu-id="f3f5e-105">As part of Dynamics 365 for Retail, users can study store performance in real time across different levels of the organization hierarchy over a selected period by opening the out-of-box **Channel summary** report from any of the following locations:</span></span>

-   <span data-ttu-id="f3f5e-106">[**小売店舗管理**] ワークスペース &gt; [**小売**] &gt; [**チャンネル**] &gt; [**小売店舗管理**] &gt; [**レポート**] &gt; [**チャンネルの集計レポート**]</span><span class="sxs-lookup"><span data-stu-id="f3f5e-106">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Channel summary report**</span></span>
-   <span data-ttu-id="f3f5e-107">[**小売店舗の財務**] ワークスペース &gt; [**小売**] &gt; [**チャンネル**] &gt; [**小売店舗の財務**] &gt; [**レポート**] &gt; [**チャンネルの集計レポート**]</span><span class="sxs-lookup"><span data-stu-id="f3f5e-107">**Retail store financials** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store financials** &gt; **Reports** &gt; **Channel summary report**</span></span>
-   <span data-ttu-id="f3f5e-108">[**照会とレポート**] セクション &gt; [**小売**] &gt; [**照会とレポート**] &gt; [**売上レポート**] &gt; [**チャネル集計レポート**]</span><span class="sxs-lookup"><span data-stu-id="f3f5e-108">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Channel summary report**</span></span>

<span data-ttu-id="f3f5e-109">このレポートは、店舗パフォーマンスの一部として次のスナップショットの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="f3f5e-109">This report provides a snapshot of following summaries as part of store performance:</span></span>

-   <span data-ttu-id="f3f5e-110">総売上集計</span><span class="sxs-lookup"><span data-stu-id="f3f5e-110">Gross sales summary</span></span>
-   <span data-ttu-id="f3f5e-111">支払/入金タイプ集計</span><span class="sxs-lookup"><span data-stu-id="f3f5e-111">Tender type summary</span></span>
-   <span data-ttu-id="f3f5e-112">税集計</span><span class="sxs-lookup"><span data-stu-id="f3f5e-112">Tax summary</span></span>
-   <span data-ttu-id="f3f5e-113">価格変更の概要</span><span class="sxs-lookup"><span data-stu-id="f3f5e-113">Price overrides summary</span></span>
-   <span data-ttu-id="f3f5e-114">割引概要</span><span class="sxs-lookup"><span data-stu-id="f3f5e-114">Discounts summary</span></span>


