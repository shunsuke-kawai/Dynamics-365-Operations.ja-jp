---
title: 倉庫の作業ポリシーの設定 (申請、2016 年 5 月)
description: 倉庫のプロセスは倉庫作業を常に含みません。
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy, WMSLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 23ad33a2f070a33e4e658870561406c4604f4dce
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847066"
---
# <a name="set-up-warehouse-work-policies-application-may-2016"></a>倉庫の作業ポリシーの設定 (申請、2016 年 5 月)

[!include [task guide banner](../../includes/task-guide-banner.md)]

倉庫のプロセスは倉庫作業を常に含みません。 作業ポリシーを定義して、原材料のピッキングの作業の作成、および特定の場所での一連の製品に対する完成品のプット アウェイを防ぐことができます。 デモ データの会社 USMF がこの記録の作成に使用されました。 このタスク ガイドでは、Dynamics AX アプリケーション 7.0.1 以降が必要です。

1. [倉庫管理] > [設定] > [作業] > [作業ポリシー] の順に移動します。
2. [新規] をクリックします。
3. [作業ポリシー名] フィールドに、「プット アウェイ作業なし」と入力します。
4. [保存] をクリックします。
5. [追加] をクリックします。
6. 一覧で、選択された行をマークします。
7. [ワーク オーダー タイプ] フィールドで、[完成品のプット アウェイ] を選択します。
8. [追加] をクリックします。
9. 一覧で、選択された行をマークします。
10. [ワーク オーダー タイプ] フィールドで、[連産物と副産物のプット アウェイ] を選択します。
11. [在庫場所] セクションを展開します。
12. [追加] をクリックします。
13. 一覧で、選択された行をマークします。
14. 倉庫の一覧で、「51」を入力します。
15. [場所] フィールドで「001」を入力または選択します。
16. [製品] セクションを展開します。
17. [製品の選択] フィールドで、[選択済] を選択します。
18. [追加] をクリックします。
19. 一覧で、選択された行をマークします。
20. [品目番号] フィールドで、「L0101」を入力または選択します。
21. [保存] をクリックします。

