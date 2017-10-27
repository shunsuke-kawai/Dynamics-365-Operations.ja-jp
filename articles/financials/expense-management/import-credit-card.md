---
title: "クレジット カード トランザクションのインポートおよび管理"
description: "このトピックでは、インポートおよび経費に関連するクレジット カード トランザクションを管理する方法について説明します。 定期スケジュールで自動的にインポートされるようこれらのトランザクションを設定したり、または必要に応じて手動でトランザクションをインポートすることができます。"
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations, UnifiedOperations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 3379e2f850653cb99231d4ab030b64beb72b626a
ms.contentlocale: ja-jp
ms.lasthandoff: 09/29/2017

---

# <a name="import-and-maintain-credit-card-transactions"></a>クレジット カード トランザクションのインポートおよび管理

[!include[banner](../includes/banner.md)]

経費に関連するクレジット カード トランザクションは、定期的なスケジュールで自動的にインポートされるように設定できます。 または、必要に応じて手動でトランザクションをインポートすることができます。 クレジット カード トランザクションは、クレジット カード トランザクション データ エンティティを通じてインポートされます。

データ エンティティに関する詳細については、「[データ エンティティ](../../dev-itpro/data-entities/data-entities.md)」を参照してください。

## <a name="import-credit-card-transactions"></a>クレジット カード トランザクションをインポートします

1. [**クレジット カード トランザクション**] ページで、[**トランザクションのインポート**] をします。 データ管理を初めて開く場合、続行する前に、システムはデータ エンティティの一覧を更新する必要があります。
2. [**名前**] フィールドに、インポート ジョブの固有の説明を入力します。
3. [**ソース データ形式**] フィールドに、インポートするクレジット カード トランザクションを含むファイルの形式を選択します。
4. [**アップロード**] を選択し、インポートするファイルを見つけ、選択します。
5. ファイルをアップロードした後、タイルの [**マップの表示**] リンクを選択することにより、クレジット カード トランザクション ファイルのマッピングおよびクレジット カード トランザクション データ エンティティの列を検証します。 マッピング エラーがある場合、またはマッピングを変更する必要がある場合は、[**マッピングの視覚化**] タブまたは [**マッピング詳細**] タブのいずれかからマッピング変更を行います。
6. クレジット カード トランザクションを自動化するには、[**定期的なデータ ジョブの作成**] を選択します。 どのくらいの頻度でクレジット カード トランザクションをインポートする必要があるかを定義する、定期的なアイテムを設定することができます。 完了したら、[**OK**] を選択します。
7. 今すぐ選択したファイルをインポートするには、[**インポート**] を選択します。
8. インポート中にエラーが発生した場合は、修正する必要があるエラーを表示しインポートの成功を保証するために、実行ログまたはステージング データを表示できます。

> [!NOTE]
> 1 つ以上のファイル形式をインポートする必要がある場合、形式タイプごとに個別のインポート ジョブを作成する必要があります。

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a>離職した従業員用のクレジット カード トランザクションの再割り当て

従業員レコードが終了すると、従業員の Active Directory Domain Services (AD DS) の勘定は無効になります。 ただし、経費で処理され、および払い戻しされなければならない、有効なクレジット カード トランザクションがあります。 [**クレジット カード トランザクション**] ページから、関連する従業員が離職した場合にすべてのクレジット カード トランザクションの従業員を再度割り当てることができます。

1 つまたは複数のクレジット カード トランザクションを選択し、[**トランザクションの再割り当て**] を選択します。 クレジット カード トランザクションを割り当てる別の従業員を選択できます。 クレジット カード トランザクションを再度割り当てられた後、トランザクションは経費精算書用に選択され、経費精算書払い戻しの通常プロセスで支払うことができます。
