---
title: 返品品目を検査に渡す
description: 返品品目を登録する場合、品目を在庫に戻すか、なんらかの手段で処分する前に、品目を検査に送ります。
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70aafb752b2c847d5d48236fd5d201a73e088c24
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556786"
---
# <a name="pass-returned-items-on-to-inspection"></a>返品品目を検査に渡す 

[!include [banner](../includes/banner.md)]


返品品目を登録する場合、品目を在庫に戻すか、なんらかの手段で処分する前に、品目を検査に送ることがあります。

1.  **在庫管理** \> **仕訳帳** \> **品目到着** \> **品目到着**の順にクリックします。
    
    \-または-
    
    **在庫管理** \> **仕訳帳** \> **品目到着** \> **生産入力**の順にクリックします。

2.  通常どおり、**在庫場所仕訳帳**フォームで、品目の受入を登録してください。
    

    > [!NOTE]
    > <P>返品品目の受入登録の詳細については、<A href="register-the-receipt-of-returned-items.md">返品品目の受取の登録</A>を参照してください。</P>



3.  **既定値**タブの、**取扱方法**領域で、**検査管理**ボックスをオンにします。

システムから検査指示が作成され、検査の担当者または担当部署が**検査指示**フォームを使ってこの指示に対応します。

## <a name="see-also"></a>参照

[検査による返却品目の受入](take-returned-items-through-inspection.md)

[返品品目の廃棄方法の指定](specify-how-to-dispose-of-returned-items.md)

