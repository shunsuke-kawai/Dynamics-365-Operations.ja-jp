---
title: ソース データの処理および追跡
description: すべてのデータ処理は、ジョブによって実行されます。
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a6e913f3630862ba07718592cdd039940c5d40b8
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187685"
---
# <a name="process-and-trace-source-data"></a>ソース データの処理および追跡

[!include [task guide banner](../../includes/task-guide-banner.md)]

すべてのデータ処理は、ジョブによって実行されます。 各ジョブおよびデータ プロバイダーの場合、プロセスが実行され、そのエントリは現在のジョブで処理されたことを記録するために、仕訳帳が作成されます。 この手順を使用して、データ ソースを設定し、特定のコスト エントリの発生元を追跡します。 この記録では、USP2 デモ データ会社 USP2 を使用します。 このタスクを完了する前に、次のタスク ガイドを再生し確認します。「原価会計元帳の作成」、「原価管理単位を定義」、および「原価会計元帳のデータ ソースを管理」。

1. [原価計算] > [元帳の設定] > [原価会計元帳] へ、移動します。
2. 一覧で、目的のレコードを見つけ、選択します。
    * 以前に作成した原価会計元帳を、選択します。  
3. [実際のバージョン] をクリックします。
4. [アクション ペイン] で、[ソース データの処理] をクリックします。
5. [一般会計エントリ振替仕訳帳] をクリックします。
6. 一覧で、目的のレコードを見つけ、選択します。
7. [仕訳入力] をクリックします。
8. 一覧で、選択された行をマークします。
9. [原価エントリ] をクリックします。
10. [ソース エントリ] をクリックします。
11. [アクション ペイン] で、[ソース データの処理] をクリックします。
12. [一般会計] をクリックします。
13. [会計カレンダー 期間] フィールドで、値を入力または選択します。
    * この例の場合、[会計 2017 期間 9] を選択します。  
14. [OK] をクリックします。

