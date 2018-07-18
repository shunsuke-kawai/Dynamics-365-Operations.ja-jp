---
title: PageState
description: "ページを配置できるさまざまな高レベルの状態を表します。"
author: shadykdc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: 
ms.search.region: Global
ms.author: kashea
ms.search.validFrom: 
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 8fde04b0a8962f1523dbb474e86a598f91bf0bd1
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="pagestate-enumeration"></a><span data-ttu-id="088f2-103">PageState 列挙</span><span class="sxs-lookup"><span data-stu-id="088f2-103">PageState Enumeration</span></span>

[!include [banner](../../../../includes/banner.md)]

<span data-ttu-id="088f2-104">ページを配置できるさまざまな高レベルの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="088f2-104">Represents the various high-level states the a page can be in.</span></span>

## <a name="index"></a><span data-ttu-id="088f2-105">指数</span><span class="sxs-lookup"><span data-stu-id="088f2-105">Index</span></span>

### <a name="enumeration-members"></a><span data-ttu-id="088f2-106">列挙型メンバー</span><span class="sxs-lookup"><span data-stu-id="088f2-106">Enumeration members</span></span>

* [<span data-ttu-id="088f2-107">エラー</span><span class="sxs-lookup"><span data-stu-id="088f2-107">error</span></span>](view-model-ipage-pagestate.md#error)
* [<span data-ttu-id="088f2-108">読み込み済み</span><span class="sxs-lookup"><span data-stu-id="088f2-108">loaded</span></span>](view-model-ipage-pagestate.md#loaded)
* [<span data-ttu-id="088f2-109">読み込み中</span><span class="sxs-lookup"><span data-stu-id="088f2-109">loading</span></span>](view-model-ipage-pagestate.md#loading)
* [<span data-ttu-id="088f2-110">オフライン</span><span class="sxs-lookup"><span data-stu-id="088f2-110">offline</span></span>](view-model-ipage-pagestate.md#offline)
* [<span data-ttu-id="088f2-111">更新中</span><span class="sxs-lookup"><span data-stu-id="088f2-111">refreshing</span></span>](view-model-ipage-pagestate.md#refreshing)

## <a name="enumeration-members"></a><span data-ttu-id="088f2-112">列挙型メンバー</span><span class="sxs-lookup"><span data-stu-id="088f2-112">Enumeration members</span></span>

### <a name="error"></a><span data-ttu-id="088f2-113">エラー</span><span class="sxs-lookup"><span data-stu-id="088f2-113">error</span></span>

<span data-ttu-id="088f2-114">エラー: 10 ページは現在、エラー状態にありますが、更新することでこの状態から抜け出すことができます。</span><span class="sxs-lookup"><span data-stu-id="088f2-114">error: 10 The page is currently in the error state, but can be refreshed in an attempt to get out of this state.</span></span>


### <a name="loaded"></a><span data-ttu-id="088f2-115">loaded</span><span class="sxs-lookup"><span data-stu-id="088f2-115">loaded</span></span>

<span data-ttu-id="088f2-116">loaded: 3 ページが完全に読み込まれ、更新可能であり、可能ならば送信できます。</span><span class="sxs-lookup"><span data-stu-id="088f2-116">loaded: 3 The page is fully loaded and can be refreshed and, if possible, submitted.</span></span>


### <a name="loading"></a><span data-ttu-id="088f2-117">loading</span><span class="sxs-lookup"><span data-stu-id="088f2-117">loading</span></span>

<span data-ttu-id="088f2-118">loading: 2 ページが現在読み込まれています。</span><span class="sxs-lookup"><span data-stu-id="088f2-118">loading: 2 The page is currently being loaded.</span></span>


### <a name="offline"></a><span data-ttu-id="088f2-119">オフライン</span><span class="sxs-lookup"><span data-stu-id="088f2-119">offline</span></span>

<span data-ttu-id="088f2-120">offline: 1 ページはオフライン モードで読み込まれたので更新できません。</span><span class="sxs-lookup"><span data-stu-id="088f2-120">offline: 1 The page was loaded in the offline mode, thus not refreshable.</span></span>


### <a name="refreshing"></a><span data-ttu-id="088f2-121">更新中</span><span class="sxs-lookup"><span data-stu-id="088f2-121">refreshing</span></span>

<span data-ttu-id="088f2-122">更新中: 4 ページは現在データを更新中です。</span><span class="sxs-lookup"><span data-stu-id="088f2-122">refreshing: 4 The page is currently refreshing its data.</span></span>


