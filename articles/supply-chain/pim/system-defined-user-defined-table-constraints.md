---
title: "システム定義およびユーザー定義のテーブル制約"
description: "この記事では、製品コンフィギュレーション モデルのコンポーネントの 2 つのタイプのテーブル制約について説明します。ユーザー定義とシステム定義です。 テーブルの制約は、テーブルの各行が設定可能な各属性値の定義を表す許可された属性の組み合わせのマトリックスを表します。"
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: b59452496f0ad47f1fe2ff034895a082a205dda9
ms.contentlocale: ja-jp
ms.lasthandoff: 09/14/2017

---

# <a name="system-defined-and-user-defined-table-constraints"></a><span data-ttu-id="9f198-104">システム定義およびユーザー定義のテーブル制約</span><span class="sxs-lookup"><span data-stu-id="9f198-104">System-defined and user-defined table constraints</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9f198-105">この記事では、製品コンフィギュレーション モデルのコンポーネントの 2 つのタイプのテーブル制約について説明します。ユーザー定義とシステム定義です。</span><span class="sxs-lookup"><span data-stu-id="9f198-105">This article explains the two types of table constraints for components in a product configuration model -  user-defined and system-defined.</span></span> <span data-ttu-id="9f198-106">テーブルの制約は、テーブルの各行が設定可能な各属性値の定義を表す許可された属性の組み合わせのマトリックスを表します。</span><span class="sxs-lookup"><span data-stu-id="9f198-106">Table constraints represent matrices of the allowed attribute combinations, where each row defines one set of possible attribute values.</span></span>

<span data-ttu-id="9f198-107">テーブルの制約は、製品コンフィギュレーション モデルのコンポーネントに許可されている属性の組み合わせマトリックスを表します。</span><span class="sxs-lookup"><span data-stu-id="9f198-107">Table constraints represent matrices of the combinations of attributes that are allowed for components in a product configuration model.</span></span> <span data-ttu-id="9f198-108">テーブルの各行は、設定可能な各属性値の定義になります。</span><span class="sxs-lookup"><span data-stu-id="9f198-108">Each row in the table defines one set of possible attribute values.</span></span> <span data-ttu-id="9f198-109">製品コンフィギュレーション モデルで 2 つの制約タイプを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="9f198-109">You can declare two types of constraints in a product configuration model:</span></span>

-   <span data-ttu-id="9f198-110">**式の制約** – 式の制約を使用すると、属性間の関係を表し、互換性がある値だけを製品のコンフィギュレーション時に選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9f198-110">**Expression constraint** – Create an expression that defines relations between attributes to guarantee that only compatible values can be selected during product configuration.</span></span>
-   <span data-ttu-id="9f198-111">**テーブルの制約** – 指定された一連の属性に対して許可されるすべての組み合わせを定義するテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f198-111">**Table constraint** – Create a table that defines all the combinations that are allowed for a specified set of attributes.</span></span> <span data-ttu-id="9f198-112">2 つのタイプのテーブルの制約を使用できます。それは、ユーザー定義のテーブル制約とシステム定義のテーブル制約です。</span><span class="sxs-lookup"><span data-stu-id="9f198-112">Two types of table constraints are available: user-defined table constraints and system-defined table constraints.</span></span>

<span data-ttu-id="9f198-113">この記事では、製品コンフィギュレーション モデルのコンポーネントのユーザー定義とシステム定義のテーブル制約について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f198-113">This article describes user-defined and system-defined table constraints for components in a product configuration model.</span></span>

## <a name="user-defined-table-constraints"></a><span data-ttu-id="9f198-114">ユーザー定義のテーブル制約</span><span class="sxs-lookup"><span data-stu-id="9f198-114">User-defined table constraints</span></span>
<span data-ttu-id="9f198-115">ユーザー定義のテーブル制約は、属性タイプによって定義される属性値の組み合わせの説明に使用されるマトリックス タイプです。</span><span class="sxs-lookup"><span data-stu-id="9f198-115">A user-defined table constraint is a type of matrix that is used to describe the combinations of attribute values that are defined by attribute types.</span></span> <span data-ttu-id="9f198-116">たとえば、スピーカーを生産する場合、キャビネットの仕上げと前グリルの列を、ユーザー定義のテーブル制約に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9f198-116">For example, if you produce speakers, you can include columns for the cabinet finish and the front grill in the user-defined table constraint.</span></span> <span data-ttu-id="9f198-117">キャビネットの仕上げの属性タイプには 4 つの値、前グリルの属性タイプには 3 つの値があります。</span><span class="sxs-lookup"><span data-stu-id="9f198-117">The attribute type for the cabinet finish has four values, and the attribute type for the front grill has three values.</span></span> <span data-ttu-id="9f198-118">したがって、制約を使用しない場合、4 × 3 = 12 が可能な組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="9f198-118">Therefore, if constraints aren't used, there are 4 × 3 = 12 possible combinations.</span></span> <span data-ttu-id="9f198-119">ただし、この例では、次の表に示すように 6 つの組み合わせのみ許可するようにします。</span><span class="sxs-lookup"><span data-stu-id="9f198-119">However, in this example, only six combinations are allowed, as shown in the following table.</span></span> <span data-ttu-id="9f198-120">この情報は、**テーブル制約の編集**ページの**許可済み組み合わせ**タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f198-120">This information is displayed on the **Allowed combinations** tab on the **Edit table constraint** page.</span></span>

| <span data-ttu-id="9f198-121">キャビネットの仕上げ</span><span class="sxs-lookup"><span data-stu-id="9f198-121">Cabinet finish</span></span> | <span data-ttu-id="9f198-122">前グリル</span><span class="sxs-lookup"><span data-stu-id="9f198-122">Front grill</span></span> |
|----------------|-------------|
| <span data-ttu-id="9f198-123">黒</span><span class="sxs-lookup"><span data-stu-id="9f198-123">Black</span></span>          | <span data-ttu-id="9f198-124">黒</span><span class="sxs-lookup"><span data-stu-id="9f198-124">Black</span></span>       |
| <span data-ttu-id="9f198-125">黒</span><span class="sxs-lookup"><span data-stu-id="9f198-125">Black</span></span>          | <span data-ttu-id="9f198-126">メタル</span><span class="sxs-lookup"><span data-stu-id="9f198-126">Metal</span></span>       |
| <span data-ttu-id="9f198-127">カシ</span><span class="sxs-lookup"><span data-stu-id="9f198-127">Oak</span></span>            | <span data-ttu-id="9f198-128">黒</span><span class="sxs-lookup"><span data-stu-id="9f198-128">Black</span></span>       |
| <span data-ttu-id="9f198-129">シタン</span><span class="sxs-lookup"><span data-stu-id="9f198-129">Rosewood</span></span>       | <span data-ttu-id="9f198-130">白</span><span class="sxs-lookup"><span data-stu-id="9f198-130">White</span></span>       |
| <span data-ttu-id="9f198-131">白</span><span class="sxs-lookup"><span data-stu-id="9f198-131">White</span></span>          | <span data-ttu-id="9f198-132">黒</span><span class="sxs-lookup"><span data-stu-id="9f198-132">Black</span></span>       |
| <span data-ttu-id="9f198-133">白</span><span class="sxs-lookup"><span data-stu-id="9f198-133">White</span></span>          | <span data-ttu-id="9f198-134">白</span><span class="sxs-lookup"><span data-stu-id="9f198-134">White</span></span>       |

<span data-ttu-id="9f198-135">ユーザー定義のテーブル制約は、式の制約と同じように機能する静的なテーブル入力によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="9f198-135">User-defined table constraints are defined by static table input that works the same way as an expression constraint.</span></span> <span data-ttu-id="9f198-136">ユーザー定義のテーブル制約を使用するとき、利点として、長い式の制約よりも、テーブルの作成、理解、および管理が容易になります。</span><span class="sxs-lookup"><span data-stu-id="9f198-136">When you use a user-defined table constraint, the advantage is that tables are often easier to create, understand, and maintain than long expression constraints.</span></span>

## <a name="system-defined-table-constraints"></a><span data-ttu-id="9f198-137">システム定義のテーブル制約</span><span class="sxs-lookup"><span data-stu-id="9f198-137">System-defined table constraints</span></span>
<span data-ttu-id="9f198-138">システム定義のテーブル制約は、属性タイプとテーブルのフィールドとの間の動的マッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f198-138">A system-defined table constraint creates a dynamic mapping between an attribute type and a field in a table.</span></span> <span data-ttu-id="9f198-139">システム定義のテーブル制約が製品コンフィギュレーション モデルに含まれている場合、マッピングを使用することで、属性タイプの値の代わりにテーブルのデータが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="9f198-139">When a system-defined table constraint is included in a product configuration model, the mapping guarantees that the data in the table is shown instead of the values of the attribute type.</span></span> <span data-ttu-id="9f198-140">その結果は動的制約です。それは、テーブルの内容が他のモジュールなどによって変更されるからです。</span><span class="sxs-lookup"><span data-stu-id="9f198-140">The result is a dynamic constraint, because the table contents can be modified (for example, by other modules).</span></span>  

<span data-ttu-id="9f198-141">システム定義のテーブル制約を作成するとき、テーブルを選択し、オプションで使用するクエリを定義し、選択したテーブルのフィールドに属性タイプを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="9f198-141">When you create a system-defined table constraint, you select a table, optionally define the query to use, and then associate attribute types to the fields in the selected table.</span></span> <span data-ttu-id="9f198-142">フィールドのタイプは、属性タイプのタイプと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f198-142">The types of fields must match the types of attribute types.</span></span>  

<span data-ttu-id="9f198-143">テーブルの制約を製品コンフィギュレーション モデルで有効にするには、モデルのコンポーネントの 1 つの制約にテーブルの制約を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f198-143">Before a table constraint can take effect on a product configuration model, the table constraint must be included in a constraint on one of the model's components.</span></span> <span data-ttu-id="9f198-144">手順としては、新しい制約を作成し、テーブルの制約タイプを選択し、それから使用するテーブルの制約定義を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f198-144">The procedure is to create a new constraint, select the table constraint type, and then select the table constraint definition to use.</span></span> <span data-ttu-id="9f198-145">最後に、テーブルの制約のすべてのフィールドを、製品コンフィギュレーション モデルの属性にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f198-145">Finally, all fields in the table constraint must be mapped to attributes in the product configuration model.</span></span>

<a name="see-also"></a><span data-ttu-id="9f198-146">参照</span><span class="sxs-lookup"><span data-stu-id="9f198-146">See also</span></span>
--------

[<span data-ttu-id="9f198-147">製品コンフィギュレーション モデルの重要な概念</span><span class="sxs-lookup"><span data-stu-id="9f198-147">Key concepts in product configuration models</span></span>](product-configuration-models.md)



