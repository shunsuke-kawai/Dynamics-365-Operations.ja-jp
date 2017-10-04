---
title: "製品のコンフィギュレーションの再利用"
description: "製品の既存のコンフィギュレーションを自動的に再利用することを指定できます。 次にユーザーがコンフィギュレーション セッションを完了すると、ユーザーの選択と一致するコンフィギュレーションが既に存在するかどうかが確認されます。 一致するコンフィギュレーションが見つかった場合は、コンフィギュレーション ID、対応する部品表 (BOM)、および工順が再利用されます。"
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: b4d61c869577a3e18d1ac951f32dae286937a51c
ms.contentlocale: ja-jp
ms.lasthandoff: 09/14/2017

---

# <a name="reuse-product-configurations"></a><span data-ttu-id="b7108-105">製品のコンフィギュレーションの再利用</span><span class="sxs-lookup"><span data-stu-id="b7108-105">Reuse product configurations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b7108-106">製品の既存のコンフィギュレーションを自動的に再利用することを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b7108-106">You can specify that you want to automatically reuse an existing configuration for a product.</span></span> <span data-ttu-id="b7108-107">次にユーザーがコンフィギュレーション セッションを完了すると、ユーザーの選択と一致するコンフィギュレーションが既に存在するかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="b7108-107">Then, when a user has completed a configuration session, the system verifies whether a configuration that matches the user’s selections already exists.</span></span> <span data-ttu-id="b7108-108">一致するコンフィギュレーションが見つかった場合は、コンフィギュレーション ID、対応する部品表 (BOM)、および工順が再利用されます。</span><span class="sxs-lookup"><span data-stu-id="b7108-108">If a matching configuration is found, the configuration ID, corresponding bill of materials (BOM), and route are reused.</span></span>

<a name="requirements-for-reusing-configurations"></a><span data-ttu-id="b7108-109">コンフィギュレーションを再利用するための条件</span><span class="sxs-lookup"><span data-stu-id="b7108-109">Requirements for reusing configurations</span></span>
---------------------------------------

<span data-ttu-id="b7108-110">コンフィギュレーションの再利用を有効にするには、[**製品コンフィギュレーション モデルの詳細**] ページで、コンポーネントと属性の次の情報を指定する必要があります:</span><span class="sxs-lookup"><span data-stu-id="b7108-110">To enable configurations to be reused, you must specify the following information for the components and attributes on the **Product configuration model details** page:</span></span>

-   <span data-ttu-id="b7108-111">[**コンポーネントおよびサブコンポーネント**] – [**一般**] クイック タブ、[**コンフィギュレーションの再利用**] フィールドで [**有**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7108-111">**Components and subcomponents** – On the **General** FastTab, in the **Reuse configurations** field, select **Yes**.</span></span>
-   <span data-ttu-id="b7108-112">[**属性**] – [**属性**] クイック タブで、[**再利用に含める**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b7108-112">**Attributes** – On the **Attributes** FastTab, select the **Include in reuse** option.</span></span> <span data-ttu-id="b7108-113">このオプションは、関連するコンポーネントの再利用が有効になっている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7108-113">This option appears only when the related component is enabled for reuse.</span></span> <span data-ttu-id="b7108-114">再利用の属性を選択しない場合、コンフィギュレーション セッション中のユーザーの選択に関係なく、コンフィギュレーションは常に再利用されます。</span><span class="sxs-lookup"><span data-stu-id="b7108-114">If you don't select any attributes for reuse, the configuration is always reused, regardless of the user’s selections during a configuration session.</span></span> <span data-ttu-id="b7108-115">既存のコンフィギュレーションの属性値はユーザーの選択と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7108-115">The attribute values in the existing configuration must match the user’s selections.</span></span> <span data-ttu-id="b7108-116">たとえば、ユーザーがコンフィギュレーション セッション中、色に [**青**] を選択すると、システムはコンポーネントの既存のコンフィギュレーションに青い色があるかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="b7108-116">For example, if the user selects **Blue** as the color during a configuration session, the system verifies whether an existing configuration of the component has the color blue.</span></span>

## <a name="resetting-configuration-reuse"></a><span data-ttu-id="b7108-117">コンフィギュレーション再利用をリセットします</span><span class="sxs-lookup"><span data-stu-id="b7108-117">Resetting configuration reuse</span></span>
<span data-ttu-id="b7108-118">コンフィギュレーションの再利用をリセットする場合、以前に作成したコンフィギュレーションは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="b7108-118">When you reset configuration reuse, previously created configurations are no longer considered.</span></span> <span data-ttu-id="b7108-119">BOM または工順が変更され、コンフィギュレーションの再利用をリセットしたい場合でも、関連する属性は変更されません。</span><span class="sxs-lookup"><span data-stu-id="b7108-119">You might want to reset configuration reuse if the BOM or route was changed, but no related attributes were changed.</span></span> <span data-ttu-id="b7108-120">コンポーネントの [**一般**] クイック タブで、コンフィギュレーションの再利用をリセットします。</span><span class="sxs-lookup"><span data-stu-id="b7108-120">You reset configuration reuse on the **General** FastTab for the component.</span></span>



