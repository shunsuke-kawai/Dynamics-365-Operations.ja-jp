---
title: 事前定義された製品バリアントの製品番号の分類の作成
description: このトピックでは、事前定義済製品バリアントの製品番号の分類を設定する方法、および適切な製品分析コード グループに割り当てる方法を説明します。
author: ShylaThompson
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5cf0efeac2851e6ead6fc5e15a016370dfa620bc
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914910"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>事前定義された製品バリアントの製品番号の分類の作成

[!include [task guide banner](../../includes/task-guide-banner.md)]

このトピックでは、事前定義済製品バリアントの製品番号の分類を設定する方法、および適切な製品分析コード グループに割り当てる方法を説明します。 この手順の作成に使用するデモ データの会社は USMF です。 新しい製品番号に関する分類は、色やサイズの製品分析コード グループに割り当てられます。 このタスクは、通常、製品デザイナーが行います。


## <a name="create-a-product-number-nomenclature"></a>[製品番号の分類] を作成します。
1. **製品バリアント モデルの定義**を選択します。
2. **製品の分類**を選択します。
3. **新規** を選択します。
4. **名前**フィールドに、目標の製品分析コード グループ、たとえば、`ColorSize` を特定する用語の名前を入力します。
5. **説明**フィールドで、値を入力します。
6. **追加**を選択します。
7. **製品マスター**番号を選択します。
8. **追加**を選択します。
9. **テキスト定数**を選択します。
10. **テキスト** フィールドに値を入力します。
11. **追加**を選択します。
12. **色**を選択します。
13. **追加**を選択します。
14. **テキスト定数**を選択します。
15. **テキスト** フィールドに値を入力します。
16. **追加**を選択します。
17. **サイズ**を選択します。
18. ページを閉じます。

## <a name="assign-the-nomenclature-to-a-product-master"></a>製品マスターに用語を割り当て
1. **製品分析コード グループ**を選択します。
2. **SizeCol 製品分析コード** グループを選択します。
3. **編集**を選択します。
4. **分類の使用**フィールドで、**はい**を選択します。
5. **製品バリアント番号の分類**フィールドに、値を入力または選択します。
6. ページを閉じます。

