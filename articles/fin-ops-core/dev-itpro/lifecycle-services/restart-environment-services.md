---
title: 環境サービスの再開
description: このトピックでは、Microsoft Dynamics Lifecycle Services (LCS) を通じて展開される環境で個々のサービスを再起動する方法について説明します。こ
author: kfend
manager: AnnBe
ms.date: 03/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: manado
ms.search.validFrom: 2018-03-05
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: d59b4bd3f1b3289e10bf23a4733dd0ec212b39f6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183189"
---
# <a name="restart-environment-services"></a>環境サービスの再開

[!include [banner](../includes/banner.md)]

Microsoft Dynamics Lifecycle Services (LCS) のサービスの再開機能を使用すると、Microsoft サブスクリプションで展開された階層 2、階層 3、階層 4、または階層 5 の標準承認テスト (サンドボックス) 環境に関連付けられた個々のサービスを再開することができます。 この機能を使用すると、次のサービスを再起動することができます。

- IIS
- DIXF
- LCS 診断
- バッチ
- レポート サーバー

プロジェクト所有者、組織管理者、または環境マネージャーとして LCS プロジェクトに追加されたすべてのユーザーは、この機能を使用するアクセス許可を持っています。

## <a name="restart-a-specific-service"></a>特定のサービスを再起動する

展開された環境で特定のサービスを再起動するには、次の手順を実行します。

1. LCS で、適切なプロジェクトを開き、サービスを再起動する環境を選択します。
2. **環境の詳細**ページで、**メンテナンス** &gt; **サービスのリセット**を選択します。
3. **サービスを再起動します**ダイアログ ボックスで、再起動するサービスを選択してから **OK** を選択します。

    **環境状態** 値は、サービスが再起動されると更新されます。

4. 更新された状態を表示するには、ページを更新します。

    > [!NOTE]
    > サービスの再起動には数秒しかかからないため、**環境の状態**の値はすでに**配置済み**にリセットされている可能性があります。 再起動が完了すると、エントリが **履歴** ページに追加されます。
    
    
 ## <a name="stop-and-start-all-services"></a>すべてのサービスを再起動する
 
 **すべて** のサービスを再起動するには、環境の詳細 ページにて **停止** メニュー オプションを実行した後で、 **開始** オプションを実行します。
 
  > [!NOTE]
  > この機能は Tier-2+ Sandbox においてのみ利用可能となっています。プロダクション環境でがご利用いただけません。
