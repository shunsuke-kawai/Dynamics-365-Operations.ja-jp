--- 
title: "機械学習を利用する製品の推奨事項のコンフィギュレーション"
description: "この手順では、製品の推奨項目を促進する機械学習システムが使用するエンティティストアが更新され、その後製品の推奨項目がPOSクライアントで有効になります。"
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: c51c5f82efb50db1e238f4046506920975f33218
ms.contentlocale: ja-jp
ms.lasthandoff: 07/28/2017

---
# <a name="configure-machine-learning-powered-product-recommendations"></a>機械学習を利用する製品の推奨事項のコンフィギュレーション

[!include[task guide banner](../includes/task-guide-banner.md)]

この手順では、製品の推奨項目を促進する機械学習システムが使用するエンティティストアが更新され、その後製品の推奨項目がPOSクライアントで有効になります。 この手順では、デモ データの会社 USRT を使用します。

1. [システム管理] > [設定] > [エンティティストア] の順に移動します。
2. リストで、記録のRetailSalesを検索、選択します。
3. [更新] をクリックします。
4. [OK] をクリックします。
5. ページを閉じます。
6. [小売りとコマース] > [本社の設定] > [パラメーター] > [小売パラメーター] に移動します。
7. 機械学習のタブをクリックします。
8. [製品の推薦項目を有効化] フィールドで [はい] を選択します。
    * 「推奨モデルが取得できませんでした」というメッセージが表示された場合は、それはエンティティ・ストアが最近更新され、システムが新しいデータとの同化を終了していないことが原因です。 待機時間は2～3時間です。再度お試しください。  
9. [保存] をクリックします。
10. ページを閉じます。

