---
title: バッチ マネージャーのセキュリティ ロール
description: このトピックでは、バッチ ジョブの管理に使用されるバッチ管理者のセキュリティ ロールに関する情報を提供します。
author: hasaid
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62333
ms.assetid: 6135bcf7-bf8f-42ae-b2c6-458f6538e6a4
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2018-08-15
ms.dyn365.ops.version: Platform update 20
ms.openlocfilehash: 31afa018e84a92ef7f136fe13a24d27df6751a79
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191795"
---
# <a name="batch-manager-security-role"></a>バッチ マネージャーのセキュリティ ロール

[!include [banner](../includes/banner.md)]

プラットフォーム更新 20 より前では、バッチ ジョブを管理するシステム管理者や IT 管理者セキュリティ ロールにユーザーを割り当てる必要がありました。 プラットフォーム更新 20 のリリースには、より対象を絞り込んだロール、バッチ マネージャーがあります。 このセキュリティ ロールでは、ユーザーはバッチ ジョブをコピーする、ジョブを実行するユーザーを変更する、ジョブを実行できる時間範囲を指定するアクセス許可を持ちます。 バッチ管理セキュリティ特権は、バッチ管理者セキュリティ ロールの一部です。これによって、ユーザーはアド ホック バッチ ジョブを作成して、他のユーザーに権限を付与できます。

> [!NOTE]
> この機能は、Platform update 20 以降で利用できます。

## <a name="assign-the-batch-manager-role-to-a-user"></a>バッチ管理者ロールをユーザーに割り当てる
特定のユーザーにバッチ管理者のセキュリティ ロールを割り当てるには、次の手順を実行します。

1.  **システム管理** > **セキュリティ** > **ユーザーをロールに割り当てる** をクリックします。

![ロールへのユーザーの割り当て](./media/assign-batchmanager-role.png) 

2.  **バッチ ジョブ マネージャー** をクリックし、左ウィンドウで **ユーザーを手動で割り当てる/除外する** をクリックします。

![バッチ マネージャー ロール](./media/assign-batchmanager-role-2.png) 

3.  一覧からユーザーを選択し、**ロールに割り当て** をクリックします。
4.  ページを閉じます。 

## <a name="run-by-user"></a>実行者ユーザー

**実行者ユーザー**機能により、バッチ管理者は、バッチ ジョブを実行するユーザーを指定できます。 これは、現在ジョブの実行が割り当てられているユーザーを変更する場合、または別の会社にバッチ ジョブをコピーするときにユーザーをすばやく設定する場合に便利です。 この機能は、バッチ ジョブをコピーするのにも使用できます。

 ![実行者ユーザー](./media/runby-user.png)  
 
