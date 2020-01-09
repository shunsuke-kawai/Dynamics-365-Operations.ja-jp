---
title: 係数減価償却
description: この記事は、係数償却方法の減価償却の概要を示します。
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5c36441e926cd5a82c802a350adf6b2ed6d6387
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178640"
---
# <a name="factor-depreciation"></a>係数減価償却

[!include [banner](../includes/banner.md)]

この記事は、係数償却方法の減価償却の概要を示します。

係数は、資産の減価償却に使用される比率です。 固定資産減価償却プロファイルを設定し、**減価償却プロファイル** ページの**方法**フィールドで**係数**を選択すると、累進的減価償却、累減的減価償却、または定額減価償却を設定できます。

-   累進的減価償却では、減価償却期間ごとに減価償却金額は増加します。
-   累減的減価償却では、期間ごとの減価償却金額はしだいに減少します。
-   定額法では、各期間の減価償却金額は同じになります。

次のルールと例は、減価償却の各タイプに対して、係数をどのように設定できるかを示します。 

> [!NOTE] 
> **方法**フィールドで**係数**を選択すると、**係数**フィールドおよび**間隔**フィールドが表示されます。

## <a name="progressive-depreciation"></a>累進的減価償却
**係数**フィールドの値は **50** より大きくなります。

### <a name="example"></a>例

取得価格は 100,000、係数は 70、耐用年数は 10 年、および減価償却は 1 月 1 日から開始します。 減価償却金額と正味簿価額の金額は、耐用年数の最初 6 年間のみ表示されます。

| 年 | 期間      | 減価償却金額 | 正味簿価金額 |
|------|-------------|---------------------|-----------------------|
| 1    | 12 月 31 日 | 307.69              | 99,692.31             |
| 2    | 12 月 31 日 | 1,447.21            | 98,245.10             |
| 3    | 12 月 31 日 | 3,104.50            | 95,140.60             |
| 4    | 12 月 31 日 | 5,150.21            | 89,990.39             |
| 5    | 12 月 31 日 | 7,522.95            | 82,467.44             |
| 6    | 12 月 31 日 | 10,184.06           | 72,283.38             |

## <a name="digressive-depreciation"></a>累減的減価償却
**係数**フィールドの値は **50** より小さくなります。

### <a name="example"></a>例

取得価格は 100,000、係数は 20、耐用年数は 10 年、および減価償却は 1 月 1 日から開始します。 減価償却金額と正味簿価額の金額は、耐用年数の最初 6 年間のみ表示されます。

| 年 | 期間      | 減価償却金額 | 正味簿価金額 |
|------|-------------|---------------------|-----------------------|
| 1    | 12 月 31 日 | 56,080.43           | 43,919.57             |
| 2    | 12 月 31 日 | 10,665.70           | 33,253.87             |
| 3    | 12 月 31 日 | 7,156.22            | 26,097.65             |
| 4    | 12 月 31 日 | 5,538.06            | 20,559.59             |
| 5    | 12 月 31 日 | 4,579.89            | 15,979.70             |
| 6    | 12 月 31 日 | 3,937.36            | 12,042.34             |

## <a name="straight-line-depreciation"></a>定額減価償却
**係数**フィールドの値は、**50** に等しくなります。 この場合、各期間の減価償却額は同じになり、「[耐用年数定額減価償却](straight-line-service-life-depreciation.md)」での説明に従って、他のフィールドでの選択の関連について考慮する必要があります。


