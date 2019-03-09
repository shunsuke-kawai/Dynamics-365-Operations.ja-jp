---
title: 小売価格レポート
description: このトピックでは、さまざまな製品の今後の価格変更を表示するために使用できる価格レポート機能の概要を提供します。
author: shajain
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 6db6d1c6b6eb1d69b40fe75d97eeb71564986707
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "353060"
---
# <a name="retail-price-reports"></a><span data-ttu-id="a789d-103">小売価格レポート</span><span class="sxs-lookup"><span data-stu-id="a789d-103">Retail price reports</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]


<span data-ttu-id="a789d-104">顧客に競争力のある価格を提供するために、小売業者はしばしば製品の価格を変更します。</span><span class="sxs-lookup"><span data-stu-id="a789d-104">In order to provide competitive prices to their customers, retailers often change prices of products.</span></span> <span data-ttu-id="a789d-105">店舗マネージャーは、店舗の棚に表示されている価格を更新するために必要なリソースを計画できるように、最新または今後の価格変更に簡単にアクセスできる機能を求めています。</span><span class="sxs-lookup"><span data-stu-id="a789d-105">Store managers want the ability to easily access recent or upcoming price changes so that they can plan for the required resources to update the price labels displayed on the store shelves.</span></span> <span data-ttu-id="a789d-106">Dynamics 365 for Retail リリース 10.0 で店舗マネージャーが**価格**レポートを開くには、**すべての小売店舗 \> 店舗 \> 価格レポート**に移動し、その店舗に関連する製品の更新された価格を表示します。</span><span class="sxs-lookup"><span data-stu-id="a789d-106">With release 10.0 of Dynamics 365 for Retail, a store manager can open the **Price** report by navigating to **All retail stores \> Store \> Price report** and viewing the updated prices for the products associated to the store.</span></span> 

<span data-ttu-id="a789d-107">価格レポートを有効にするには、**小売店舗の価格レポートを有効にする**パラメーターをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a789d-107">To enable the price report, the **Enable price report for Retail store** parameter must be turned on.</span></span> <span data-ttu-id="a789d-108">このパラメーターは、**小売パラメーター\>割引\> その他**タブにあります。**価格レポート**ページを開くと、さまざまな構成のダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a789d-108">This parameter is located on the **Retail parameters \> Discounts \> Miscellaneous** tab. Opening the **Price report** page displays a dialog box with various configurations.</span></span> <span data-ttu-id="a789d-109">使用可能な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a789d-109">The available configurations are listed below.</span></span>

| <span data-ttu-id="a789d-110">構成</span><span class="sxs-lookup"><span data-stu-id="a789d-110">Configuration</span></span> | <span data-ttu-id="a789d-111">説明</span><span class="sxs-lookup"><span data-stu-id="a789d-111">Description</span></span> |
|---|---|
| <span data-ttu-id="a789d-112">開始日 / 終了日</span><span class="sxs-lookup"><span data-stu-id="a789d-112">From date / To date</span></span>| <span data-ttu-id="a789d-113">価格レポートが生成される日付範囲。</span><span class="sxs-lookup"><span data-stu-id="a789d-113">The date range for which the price report should be generated.</span></span> <span data-ttu-id="a789d-114">期間は現在 7 日間に制限されています。</span><span class="sxs-lookup"><span data-stu-id="a789d-114">The duration is currently limited to 7 days.</span></span> |
| <span data-ttu-id="a789d-115">チャネル</span><span class="sxs-lookup"><span data-stu-id="a789d-115">Channel</span></span>| <span data-ttu-id="a789d-116">価格レポートが生成される小売店舗。</span><span class="sxs-lookup"><span data-stu-id="a789d-116">The retail store for which the price report should be generated.</span></span> |
| <span data-ttu-id="a789d-117">使用可能な在庫がある製品を表示</span><span class="sxs-lookup"><span data-stu-id="a789d-117">Display products with available inventory</span></span>| <span data-ttu-id="a789d-118">これを**はい**に設定すると、現在店舗に現物在庫がある製品のみの価格が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a789d-118">Setting this to **Yes** will show the prices for only those products which currently have physical inventory available in the store.</span></span> |
| <span data-ttu-id="a789d-119">バリアントの価格を表示</span><span class="sxs-lookup"><span data-stu-id="a789d-119">Display prices for variants</span></span> | <span data-ttu-id="a789d-120">これを**はい**に設定すると、製品マスターと共にバリアントの価格が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a789d-120">Setting this to **Yes** will display the prices of the variants along with the product masters.</span></span> <span data-ttu-id="a789d-121">行数が非常に増加するために、バリアント固有の価格がある場合はこれを**オン**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a789d-121">This should only be turned **On** if you have variant-specific prices, because the number of rows grows very large.</span></span> <span data-ttu-id="a789d-122">将来のリリースでは、分析コードに基づく価格を有効にし、店舗マネージャーが表示する価格の分析コードを選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a789d-122">In future releases, we will enable the dimensions-based prices so that the store manager can choose the dimensions for which the prices should be displayed.</span></span> |
| <span data-ttu-id="a789d-123">価格変更のある製品の表示</span><span class="sxs-lookup"><span data-stu-id="a789d-123">Display products with price changes</span></span> | <span data-ttu-id="a789d-124">これを**はい**設定すると、価格が変更された日付のみの価格が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a789d-124">Setting this to **Yes** will display the prices for only those dates on which the price has been changed.</span></span> <span data-ttu-id="a789d-125">選択した**開始日**から*1 日前*の価格が常に表示され、それにより店舗マネージャーは選択した期間に価格変更がない製品を簡単に識別でき、また現在の価格も確認できます。</span><span class="sxs-lookup"><span data-stu-id="a789d-125">The price for *one day before* the selected **From date** will always be displayed, so that the store manager can easily identity the products which have not changed prices for the entire selected duration, and can also view the current price.</span></span> |

<span data-ttu-id="a789d-126">レポートが生成された後、追加のフィルタリング ニーズに合わせて Excel ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="a789d-126">After the report is generated, the Excel file can be downloaded for any additional filtering needs.</span></span> <span data-ttu-id="a789d-127">価格レポートを使用して、過去の日付の製品の価格履歴を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="a789d-127">The price report can also be used to check the historical prices of products for past dates.</span></span>