---
title: ハブ付帯サービス請求金額および付帯サービス マスターの設定
description: この手順は、ハブ付帯サービス マスターの作成方法と、ハブ付帯サービス請求金額を作成するためのマスターの使用方法を示します。
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9959c20f9a8fd07cbf0cfd76f7760b44d7b5cae1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560074"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>ハブ付帯サービス請求金額および付帯サービス マスターの設定

[!include [task guide banner](../../includes/task-guide-banner.md)]

この手順は、ハブ付帯サービス マスターの作成方法と、ハブ付帯サービス請求金額を作成するためのマスターの使用方法を示します。 この手順は、USMF データセットを使用します。 この設定は、通常、配送コーディネーターが実行します。


## <a name="set-up-a-hub-master"></a>ハブ マスターの設定
1. [輸送管理] > [設定] > [評価] > [付帯サービス マスター] に移動します。
2. [新規] をクリックします。
3. [配送付帯サービス マスター] フィールドに値を入力します。
4. [名前] フィールドに値を入力します。
5. [付帯サービス タイプ] フィールドで、「ハブ」を選択します。
6. [保存] をクリックします。
7. ページを閉じます。

## <a name="set-up-a-hub-accessorial-charge"></a>ハブ付帯サービス請求金額の設定
1. [輸送管理] > [設定] > [評価] > [ハブ付帯サービス請求金額] に移動します。
2. [新規] をクリックします。
3. [ハブ付帯サービス ID] フィールドに値を入力します。
4. [ハブ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
5. 一覧で、目的のレコードを見つけ、選択します。
6. [ハブの位置] フィールドで、オプションを選択します。
    * 集荷または配送として請求金額を作成できます。 選択内容に応じて、請求金額は、工順に対応する輸送区分に適用されます。  
7. [配送付帯サービス マスター] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
8. 一覧で、選択された行のリンクをクリックします。
    * 作成したマスターを選択します。  
9. [保存] をクリックします。
10. ページを閉じます。

