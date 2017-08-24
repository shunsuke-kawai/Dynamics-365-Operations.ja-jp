--- 
title: "需要予測の手動変更"
description: "この手順では、品目の予測を変更する方法を示します。"
author: YuyuScheller
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 26f667f51efd30bcc86242fce79226d356d99847
ms.contentlocale: ja-jp
ms.lasthandoff: 07/27/2017

---
# <a name="modify-a-demand-forecast-manually"></a>需要予測の手動変更

[!include[task guide banner](../../includes/task-guide-banner.md)]

この手順では、品目の予測を変更する方法を示します。 この手順の作成に使用するデモ データの会社は USMF です。 この記録は、生産計画担当者を対象としています。 


## <a name="modify-the-forecast-for-an-item"></a>品目の予測の変更
1. [製品情報管理] > [製品] > [リリースされた製品] の順に移動します。
2. 一覧で、目的のレコードを見つけ、選択します。
    * 予測を変更する品目を選択します。 たとえば、品目「D0001」を選択できます。  
3. アクション ウィンドウで、[計画] をクリックします。
4. [需要予測] をクリックします。
5. 一覧で、選択された行をマークします。
    * 予測明細行がない場合は、新しい行を作成するために、 アプリ バーで [新規] をクリックします。  
6. [販売数量] フィールドに数値を入力します。
    * この数値は、品目の予測数量を表わします。  
7. [保存] をクリックします。

## <a name="modify-the-forecast-in-excel"></a>Excel での予測の編集
1. [Microsoft Office で開く] をクリックします。
2. [Excel での需要予測の編集] をクリックします。
    * Excel では、需要予測明細行を追加、削除、および編集できます。 Excel でデータを参照できない場合、[サインインしたままにする] オプションを有効にして Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition にサインインし、そのデータ接続アプリを信頼する必要があります。  

