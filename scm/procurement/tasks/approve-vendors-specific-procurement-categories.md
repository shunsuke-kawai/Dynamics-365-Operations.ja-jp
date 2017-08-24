--- 
title: "特定の調達カテゴリに対する仕入先の承認"
description: "購買要求が作成されると、承認仕入先または優先仕入先を選択する必要があり、それは購入ポリシーの設定方法によって異なります。"
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 75486202c3fdcaff78a5592389c624d8e21fa969
ms.contentlocale: ja-jp
ms.lasthandoff: 07/27/2017

---
# <a name="approve-vendors-for-specific-procurement-categories"></a>特定の調達カテゴリに対する仕入先の承認

[!include[task guide banner](../../includes/task-guide-banner.md)]

購買要求が作成されると、承認仕入先または優先仕入先を選択する必要があり、それは購入ポリシーの設定方法によって異なります。 この手順では、特定の調達カテゴリに対して仕入先が承認、または優先されるよう指定する方法を示します。 通常、このタスクを実行するのは、調達担当者です。 デモ データの会社 USMF でこの手順を使用できます。

1. [調達] > [仕入先] > [すべての仕入先] の順に移動します。
2. カテゴリで承認仕入先または優先仕入先として設定する仕入先を選択します。
3. アクション ウィンドウで、[一般] をクリックします。
4. [カテゴリ] をクリックします。
5. [カテゴリの追加] をクリックします。
6. カテゴリ フィールドで、オフィスとデスク アクセサリ (OFFICE AND DESK ACCESSORIES) を選択します。
7. [仕入先カテゴリ ステータス] フィールドで、「優先」を選択します。
    * カテゴリに複数の優先仕入先を指定することができます。  
8. [保存] をクリックします。
9. [調達] > [調達カテゴリ] の順に移動します。
10. ツリーで、「CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES」を選択します。
11. [仕入先] セクションを展開します。
    * 選択した仕入先がオフィスとデスク アクセサリ カテゴリの優先仕入先として表示されるかどうか確認します。 この手順をタスク ガイドとして実行する場合、仕入先の一覧にスクロールできるようにロック解除のボタンをクリックする必要があります。  このページに優先仕入先および承認済仕入先を追加することもできます。  
12. ツリーで、「OFFICE AND DESK ACCESSORIES」を展開します。
13. ツリーで、「シザーズ」を選択します。
14. 親カテゴリからの継承仕入先で [いいえ] を選択します。フィールド。
15. 親カテゴリからの継承仕入先で [はい] を選択します。フィールド。

