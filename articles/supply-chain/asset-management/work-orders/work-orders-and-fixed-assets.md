---
title: 作業指示書と固定資産
description: このトピックでは、資産管理における固定資産と作業指示書について説明します。
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c87a2b94692e279a9c2f35dc38ac87bfd9bf7d27
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626227"
---
# <a name="work-orders-and-fixed-assets"></a>作業指示書と固定資産

[!include [banner](../../includes/banner.md)]


資産管理では、資産を固定資産に関連付けることができます。またこれらの資産の作業指示書を作成することもできます。 この機能を使用する場合、**プロジェクト管理および会計**モジュールと Microsoft Dynamics 365 for Finance and Operations の**固定資産**モジュールで、固定資産、関連する投資プロジェクトおよび投資プロジェクトに登録されている原価の概要を完全に取得できます。

>[!NOTE]
>**固定資産番号**フィールドは、作業指示書ジョブ プロジェクトでプロジェクト タイプとして**投資**が選択されている場合にのみ、作業指示書ジョブ プロジェクトに設定されます。

次の図は、**プロジェクト管理および会計**モジュールの投資プロジェクトと作業指示書ジョブ プロジェクトの関係を示しています。

![図 1](media/24-work-orders.png)

次の手順では、資産、作業指示書、作業指示書プロジェクト、および固定資産関連について説明します。

1. 固定資産に関連付ける資産を作成します。

![図 2](media/25-work-orders.png)

2. **作業指示書タイプ**ページ (**資産管理** > **設定** > **作業指示書** > **作業指示書タイプ**) で、作業指示書タイプを設定する場合は、投資を処理するための作業指示書タイプを作成します。 [作業指示書タイプ](../setup-for-work-orders/work-order-types.md) も参照してください。

![図 3](media/26-work-orders.png)

3. **作業指示書プロジェクトの設定**ページ (**資産管理** > **設定** > **作業指示書** > **プロジェクト設定**) の**プロジェクト グループ** タブで作業指示書プロジェクト グループを設定する場合は、投資のために使用される作業指示書と**プロジェクト管理および会計**モジュールの**プロジェクト グループ** ページ (**プロジェクト管理および会計** > **設定** > **転記** > **プロジェクト グループ**) で投資のために作成されたプロジェクト グループの関係を作成することができます。

![図 4](media/27-work-orders.png)

4. 固定資産に関連する作業指示書を作成する場合は、投資の処理に使用する**投資**などの作業指示書タイプを選択します。

5. 作業指示書が作成されると、関連する作業指示書タイプが**すべての作業指示書**ページで表示されます。

![図 5](media/28-work-orders.png)

6. 作業指示書が作成されると、作業指示書に関連付けられたプロジェクトが、**プロジェクト管理および会計**モジュールの**すべてのプロジェクト** ページ (**プロジェクト管理および会計** > **プロジェクト** > **すべてのプロジェクト**) に作成されます。 プロジェクトの関連情報を表示するには、**資産管理**モジュールの**すべての作業指示書**ページ (**資産管理** > **共通** > **作業指示書** > **すべての作業指示書**) の詳細ビューの、**行の詳細**クイック タブの**一般**タブで、**プロジェクト ID** フィールドのリンクを選択します。

![図 6](media/29-work-orders.png)

7. 固定資産に関連付けられているプロジェクトの概要を表示するには、**固定資産** > **固定資産** > **固定資産**を選択して、**固定資産番号**フィールドで、詳細ビューを開く固定資産のリンクを選択します。 ページの右側にある**関連情報**ウィンドウを展開し、**関連付けられたプロジェクト** クイック タブを選択します。
