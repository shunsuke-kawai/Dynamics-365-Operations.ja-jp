---
title: "状態"
description: "すべてのコントロールの基準メソッドと属性を持つコントロール インターフェイス。 これは、コントロールのランタイムのインスタンスを表します。 プロパティの変更は、UI にすぐに反映されます。"
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
ms.openlocfilehash: c81cc4951f0b948717fc95833f740b8ca65feb65
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="control-type"></a><span data-ttu-id="83b55-105">コントロール タイプ</span><span class="sxs-lookup"><span data-stu-id="83b55-105">Control Type</span></span>

[!include [banner](../../../../includes/banner.md)]

<span data-ttu-id="83b55-106">すべてのコントロールの基準メソッドと属性を持つコントロール インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="83b55-106">Control interface with base methods and attributes for all controls.</span></span>
<span data-ttu-id="83b55-107">これは、コントロールのランタイムのインスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="83b55-107">This represents the runtime instance of a control.</span></span> <span data-ttu-id="83b55-108">プロパティの変更は、UI にすぐに反映されます。</span><span class="sxs-lookup"><span data-stu-id="83b55-108">Modifying the properties are immediately reflected in the UI.</span></span>

### <a name="hierarchy"></a><span data-ttu-id="83b55-109">階層</span><span class="sxs-lookup"><span data-stu-id="83b55-109">Hierarchy</span></span>

<span data-ttu-id="83b55-110">状態</span><span class="sxs-lookup"><span data-stu-id="83b55-110">Control</span></span> <br><span data-ttu-id="83b55-111">&nbsp;&nbsp;&nbsp;└─ [PageLink](view-model-control-pagelink-ipagelink-ipagelink.md)</span><span class="sxs-lookup"><span data-stu-id="83b55-111">&nbsp;&nbsp;&nbsp;└─ [PageLink](view-model-control-pagelink-ipagelink-ipagelink.md)</span></span> <br><span data-ttu-id="83b55-112">&nbsp;&nbsp;&nbsp;└─ [ContainerControl](view-model-control-container-icontainercontrol-icontainercontrol.md)</span><span class="sxs-lookup"><span data-stu-id="83b55-112">&nbsp;&nbsp;&nbsp;└─ [ContainerControl](view-model-control-container-icontainercontrol-icontainercontrol.md)</span></span> <br><span data-ttu-id="83b55-113">&nbsp;&nbsp;&nbsp;└─ [InputControl](view-model-control-basecontrol-iinputcontrol-iinputcontrol.md)</span><span class="sxs-lookup"><span data-stu-id="83b55-113">&nbsp;&nbsp;&nbsp;└─ [InputControl](view-model-control-basecontrol-iinputcontrol-iinputcontrol.md)</span></span> <br><span data-ttu-id="83b55-114">&nbsp;&nbsp;&nbsp;└─ [画像](view-model-control-image-iimage-iimage.md)</span><span class="sxs-lookup"><span data-stu-id="83b55-114">&nbsp;&nbsp;&nbsp;└─ [Image](view-model-control-image-iimage-iimage.md)</span></span> <br>

## <a name="index"></a><span data-ttu-id="83b55-115">指数</span><span class="sxs-lookup"><span data-stu-id="83b55-115">Index</span></span>

### <a name="properties"></a><span data-ttu-id="83b55-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83b55-116">Properties</span></span>

* [<span data-ttu-id="83b55-117">コンテナー</span><span class="sxs-lookup"><span data-stu-id="83b55-117">container</span></span>](view-model-control-basecontrol-icontrol-icontrol.md#container)
* [<span data-ttu-id="83b55-118">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="83b55-118">generic</span></span>](view-model-control-basecontrol-icontrol-icontrol.md#generic)
* [<span data-ttu-id="83b55-119">getDataSource</span><span class="sxs-lookup"><span data-stu-id="83b55-119">getDataSource</span></span>](view-model-control-basecontrol-icontrol-icontrol.md#getdatasource)
* [<span data-ttu-id="83b55-120">非表示</span><span class="sxs-lookup"><span data-stu-id="83b55-120">hidden</span></span>](view-model-control-basecontrol-icontrol-icontrol.md#hidden)

### <a name="methods"></a><span data-ttu-id="83b55-121">メソッド</span><span class="sxs-lookup"><span data-stu-id="83b55-121">Methods</span></span>

* [<span data-ttu-id="83b55-122">applyDesign</span><span class="sxs-lookup"><span data-stu-id="83b55-122">applyDesign</span></span>](view-model-control-basecontrol-icontrol-icontrol.md#applydesign)
* [<span data-ttu-id="83b55-123">dataContext</span><span class="sxs-lookup"><span data-stu-id="83b55-123">dataContext</span></span>](view-model-control-basecontrol-icontrol-icontrol.md#datacontext)
* [<span data-ttu-id="83b55-124">getDesign</span><span class="sxs-lookup"><span data-stu-id="83b55-124">getDesign</span></span>](view-model-control-basecontrol-icontrol-icontrol.md#getdesign)
* [<span data-ttu-id="83b55-125">isEditable</span><span class="sxs-lookup"><span data-stu-id="83b55-125">isEditable</span></span>](view-model-control-basecontrol-icontrol-icontrol.md#iseditable)
* [<span data-ttu-id="83b55-126">メタデータ</span><span class="sxs-lookup"><span data-stu-id="83b55-126">metadata</span></span>](view-model-control-basecontrol-icontrol-icontrol.md#metadata)
* [<span data-ttu-id="83b55-127">親</span><span class="sxs-lookup"><span data-stu-id="83b55-127">parent</span></span>](view-model-control-basecontrol-icontrol-icontrol.md#parent)
* [<span data-ttu-id="83b55-128">ルート</span><span class="sxs-lookup"><span data-stu-id="83b55-128">root</span></span>](view-model-control-basecontrol-icontrol-icontrol.md#root)

## <a name="properties"></a><span data-ttu-id="83b55-129">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83b55-129">Properties</span></span>

### <a name="container"></a><span data-ttu-id="83b55-130">コンテナー</span><span class="sxs-lookup"><span data-stu-id="83b55-130">container</span></span>

<span data-ttu-id="83b55-131">container: ブール値 (省略可)</span><span class="sxs-lookup"><span data-stu-id="83b55-131">container: boolean (optional)</span></span> 

<span data-ttu-id="83b55-132">コントロールがコンテナーの場合は true です。</span><span class="sxs-lookup"><span data-stu-id="83b55-132">True if the control is a container.</span></span>


### <a name="generic"></a><span data-ttu-id="83b55-133">generic</span><span class="sxs-lookup"><span data-stu-id="83b55-133">generic</span></span>

<span data-ttu-id="83b55-134">generic: boolean (省略可)</span><span class="sxs-lookup"><span data-stu-id="83b55-134">generic: boolean (optional)</span></span> 




### <a name="getdatasource"></a><span data-ttu-id="83b55-135">getDataSource</span><span class="sxs-lookup"><span data-stu-id="83b55-135">getDataSource</span></span>

<span data-ttu-id="83b55-136">getDataSource: function(): any</span><span class="sxs-lookup"><span data-stu-id="83b55-136">getDataSource: function(): any</span></span>




### <a name="hidden"></a><span data-ttu-id="83b55-137">hidden</span><span class="sxs-lookup"><span data-stu-id="83b55-137">hidden</span></span>

<span data-ttu-id="83b55-138">hidden: boolean</span><span class="sxs-lookup"><span data-stu-id="83b55-138">hidden: boolean</span></span>

<span data-ttu-id="83b55-139">コントロールが非常時の場合は true です。</span><span class="sxs-lookup"><span data-stu-id="83b55-139">True if the control is hidden.</span></span>


## <a name="methods"></a><span data-ttu-id="83b55-140">メソッド</span><span class="sxs-lookup"><span data-stu-id="83b55-140">Methods</span></span>

### <a name="applydesign"></a><span data-ttu-id="83b55-141">applyDesign</span><span class="sxs-lookup"><span data-stu-id="83b55-141">applyDesign</span></span>


<span data-ttu-id="83b55-142">applyDesign(design: [Design](view-model-ipage-idesign.md)): void</span><span class="sxs-lookup"><span data-stu-id="83b55-142">applyDesign(design: [Design](view-model-ipage-idesign.md)): void</span></span>

<span data-ttu-id="83b55-143">付与されたデザインをコントロールのデザインに適用します。</span><span class="sxs-lookup"><span data-stu-id="83b55-143">Applies given design to the design on the control.</span></span>
<span data-ttu-id="83b55-144">デザインが既に存在する場合は、設計のプロトタイプ チェーンが保持されます。</span><span class="sxs-lookup"><span data-stu-id="83b55-144">If a design already exists, the prototype chain of the design will be preserved.</span></span>


#### <a name="parameters"></a><span data-ttu-id="83b55-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="83b55-145">Parameters</span></span>

| <span data-ttu-id="83b55-146">氏名</span><span class="sxs-lookup"><span data-stu-id="83b55-146">Name</span></span> | <span data-ttu-id="83b55-147">種類</span><span class="sxs-lookup"><span data-stu-id="83b55-147">Type</span></span> | <span data-ttu-id="83b55-148">説明</span><span class="sxs-lookup"><span data-stu-id="83b55-148">Description</span></span> |
| ---- | ---- | ----------- |
| <span data-ttu-id="83b55-149">design</span><span class="sxs-lookup"><span data-stu-id="83b55-149">design</span></span>|[<span data-ttu-id="83b55-150">Design</span><span class="sxs-lookup"><span data-stu-id="83b55-150">Design</span></span>](view-model-ipage-idesign.md)|<span data-ttu-id="83b55-151">デザイン プロパティをキーとして含むオブジェクト</span><span class="sxs-lookup"><span data-stu-id="83b55-151">object containing design properties as keys</span></span>|

#### <a name="returns-void"></a><span data-ttu-id="83b55-152">void を返します</span><span class="sxs-lookup"><span data-stu-id="83b55-152">Returns void</span></span>

### <a name="datacontext"></a><span data-ttu-id="83b55-153">dataContext</span><span class="sxs-lookup"><span data-stu-id="83b55-153">dataContext</span></span>


<span data-ttu-id="83b55-154">dataContext(): any</span><span class="sxs-lookup"><span data-stu-id="83b55-154">dataContext(): any</span></span>



#### <a name="returns-any"></a><span data-ttu-id="83b55-155">any を返します</span><span class="sxs-lookup"><span data-stu-id="83b55-155">Returns any</span></span>

### <a name="getdesign"></a><span data-ttu-id="83b55-156">getDesign</span><span class="sxs-lookup"><span data-stu-id="83b55-156">getDesign</span></span>


<span data-ttu-id="83b55-157">getDesign(): [Design](view-model-ipage-idesign.md)</span><span class="sxs-lookup"><span data-stu-id="83b55-157">getDesign(): [Design](view-model-ipage-idesign.md)</span></span>

<span data-ttu-id="83b55-158">このコントロールのデザイン オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="83b55-158">Returns the design object of this control.</span></span>

#### <a name="returns-designview-model-ipage-idesignmd"></a><span data-ttu-id="83b55-159">[Design](view-model-ipage-idesign.md) を返します</span><span class="sxs-lookup"><span data-stu-id="83b55-159">Returns [Design](view-model-ipage-idesign.md)</span></span>



### <a name="iseditable"></a><span data-ttu-id="83b55-160">isEditable</span><span class="sxs-lookup"><span data-stu-id="83b55-160">isEditable</span></span>


<span data-ttu-id="83b55-161">isEditable(): boolean</span><span class="sxs-lookup"><span data-stu-id="83b55-161">isEditable(): boolean</span></span>

<span data-ttu-id="83b55-162">コントロールが編集可能かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="83b55-162">Boolean indicating if the control is editable.</span></span>
<span data-ttu-id="83b55-163">コントロールまたはその親が編集可能でない場合は、false を返します。</span><span class="sxs-lookup"><span data-stu-id="83b55-163">Returns false when either the control or it's parent is not editable.</span></span>
<span data-ttu-id="83b55-164">コントロールとその親の両方が編集可能な場合、true を返します。</span><span class="sxs-lookup"><span data-stu-id="83b55-164">Returns true when both the control and it's parent are editable.</span></span>
<span data-ttu-id="83b55-165">コントロールまたはその親が編集可能で、もう一方が未定義の場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="83b55-165">Returns true when either the control or it's parent is editable and the other is undefined.</span></span>
<span data-ttu-id="83b55-166">コントロールの編集機能と親の編集機能の両方が未定義の場合は undefined を返します。</span><span class="sxs-lookup"><span data-stu-id="83b55-166">Returns undefined if both the control's edit-ability and it's parent's edit-ability is undefined.</span></span>

#### <a name="returns-boolean"></a><span data-ttu-id="83b55-167">ブール値を返します</span><span class="sxs-lookup"><span data-stu-id="83b55-167">Returns boolean</span></span>



### <a name="metadata"></a><span data-ttu-id="83b55-168">metadata</span><span class="sxs-lookup"><span data-stu-id="83b55-168">metadata</span></span>


<span data-ttu-id="83b55-169">metadata(): [ControlMetadata](view-model-control-basecontrol-icontrol-icontrolmetadata.md)</span><span class="sxs-lookup"><span data-stu-id="83b55-169">metadata(): [ControlMetadata](view-model-control-basecontrol-icontrol-icontrolmetadata.md)</span></span>

<span data-ttu-id="83b55-170">このコントロールのメタデータ オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="83b55-170">Returns the metadata object of this control.</span></span>

#### <a name="returns-controlmetadataview-model-control-basecontrol-icontrol-icontrolmetadatamd"></a><span data-ttu-id="83b55-171">[ControlMetadata](view-model-control-basecontrol-icontrol-icontrolmetadata.md) を返します</span><span class="sxs-lookup"><span data-stu-id="83b55-171">Returns [ControlMetadata](view-model-control-basecontrol-icontrol-icontrolmetadata.md)</span></span>



### <a name="parent"></a><span data-ttu-id="83b55-172">parent</span><span class="sxs-lookup"><span data-stu-id="83b55-172">parent</span></span>


<span data-ttu-id="83b55-173">parent(): [Control](view-model-control-basecontrol-icontrol-icontrol.md) &#124; [Page](view-model-ipage-ipage.md)</span><span class="sxs-lookup"><span data-stu-id="83b55-173">parent(): [Control](view-model-control-basecontrol-icontrol-icontrol.md) &#124; [Page](view-model-ipage-ipage.md)</span></span>

<span data-ttu-id="83b55-174">このコントロールの親 (コントロールまたはページ) を返します。</span><span class="sxs-lookup"><span data-stu-id="83b55-174">Returns the parent (control or page) of this control.</span></span>

#### <a name="returns-controlview-model-control-basecontrol-icontrol-icontrolmd-124-pageview-model-ipage-ipagemd"></a><span data-ttu-id="83b55-175">[Control](view-model-control-basecontrol-icontrol-icontrol.md) &#124; [Page](view-model-ipage-ipage.md) を返します</span><span class="sxs-lookup"><span data-stu-id="83b55-175">Returns [Control](view-model-control-basecontrol-icontrol-icontrol.md) &#124; [Page](view-model-ipage-ipage.md)</span></span>



### <a name="root"></a><span data-ttu-id="83b55-176">root</span><span class="sxs-lookup"><span data-stu-id="83b55-176">root</span></span>


<span data-ttu-id="83b55-177">root(): [Page](view-model-ipage-ipage.md)</span><span class="sxs-lookup"><span data-stu-id="83b55-177">root(): [Page](view-model-ipage-ipage.md)</span></span>

<span data-ttu-id="83b55-178">このコントロールのルート フォーム インスタンス (ページ) を返します。</span><span class="sxs-lookup"><span data-stu-id="83b55-178">Returns the root form instance (page) of this control.</span></span>

#### <a name="returns-pageview-model-ipage-ipagemd"></a><span data-ttu-id="83b55-179">[Page](view-model-ipage-ipage.md) を返します</span><span class="sxs-lookup"><span data-stu-id="83b55-179">Returns [Page](view-model-ipage-ipage.md)</span></span>



