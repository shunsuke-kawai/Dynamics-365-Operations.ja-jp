---
title: 製品コンフィギュレーション モデルの BOM の管理
description: この手順を実行するには、既存の製品コンフィギュレーション モデルが必要です。
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f663c28dfcbf6b365e3e88d3a4f6385ce2fcca9f
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844396"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>製品コンフィギュレーション モデルの BOM の管理

[!include [task guide banner](../../includes/task-guide-banner.md)]

この手順を実行するには、既存の製品コンフィギュレーション モデルが必要です。 この手順を作成するのに、デモ会社 USMF の [ハイエンド スピーカー] モデルが使用されています。


## <a name="add-a-bom-line"></a>BOM 明細行の追加
1. [製品バリアント モデルの定義] をクリックします。
2. [製品コンフィギュレーション モデル] をクリックします。
3. 一覧で、目的のレコードを見つけ、選択します。
    * この手順で [ハイエンド スピーカー] を選択します。  
4. 一覧で、選択された行のリンクをクリックします。
5. [BOM 明細行] セクションを展開します。
6. [追加] をクリックします。
7. [名前] フィールドに値を入力します。
8. [説明] フィールドに値を入力します。
9. [保存] をクリックします。

## <a name="add-bom-line-details"></a>BOM 明細行の詳細の追加
1. [BOM 明細行の詳細] をクリックします。
2. [品目番号] フィールドで、値を入力または選択します。
    * たとえば、品目 M0055 を選択できます。  
    * 各 BOM 明細行プロパティに、固定値をとるか、属性にマップさせるかを選択できます。  
3. [設定] チェック ボックスを選択します。
4. [計算] フィールドで、[はい] を選択します。
    * [計算] プロパティで [はい] を設定すると、原価計算に BOM 明細行 が含まれるようになります。  
5. [設定] タブをクリックします。
6. [設定] チェック ボックスを選択します。
7. [数量] フィールドに数値を入力します。
    * 数量フィールドは、BOM に含まれる品目の数量を決定します。 これは、属性のマッピングの明確な候補になる場合があります。  
8. [分析コード] タブをクリックします。
    * 製品分析コードのいずれかが有効であるかどうかを確認します。したがって、値または属性が割り当て済である必要があります。  
9. [OK] をクリックします。

