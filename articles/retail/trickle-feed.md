---
title: 小売店舗トランザクション用トリクル フィードベースの注文作成
description: このトピックでは、Microsoft Dynamics 365 Retail の小売店舗トランザクションに対するトリクル フィードベースの注文作成について説明します。
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: deb8399aa401af16b6fe123a433eb21864e178c6
ms.sourcegitcommit: 92322167f57b66d2accc134aaf862e6b9931ec94
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "2693092"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions-public-preview"></a>小売店舗トランザクション用トリクル フィードベースの注文作成 (パブリック プレビュー)

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

Dynamics 365 Retail バージョン 10.0.4 およびそれ以前のバージョンでは、小売明細書の転記は営業終了操作で、すべてのトランザクションは 1 日の終わりに帳簿に転記されます。 その後、限られた時間枠で大規模なトランザクションを処理する必要があります。その結果、負荷、ロック、明細書の転記エラーなどが発生する場合があります。 小売業者は、1 日をとおして帳簿にある収益や支払も識別できません。

Retail バージョン 10.0.5 に導入されたトリクル フィードベースの注文作成のパブリック プレビューを使用すると、トランザクションは 1 日をとおして処理されます。そして、支払/入金の財務調整およびその他の現金管理トランザクションのみが 1 日の最後に処理されます。 この機能により、1 日の販売注文、請求書、支払の作成の負荷が分割され、より的確な業績が得られると共に、帳簿の収益や支払をほぼリアルタイムで認識することができます。 


## <a name="how-to-use-trickle-feed-based-posting"></a>トリクル フィードベースの転記の使用方法
  
1. 小売トランザクションのトリクル フィードベースの転記を有効にするには、 **システム管理 > 設定 > ライセンス コンフィギュレーション** に移動し、**小売明細書** キーを無効にします。

2. 同じページで、**小売明細書 (トリクル フィード) – プレビュー** ライセンス キーを有効にします。 このキーを有効にした場合は、転記を待機している保留中の明細書がないかどうかを確認してください。 

> [!Important]
> **小売明細書 (トリクル フィード) – プレビュー** ライセンスキーを有効にする前に、転記を待機している保留中の明細書がないことを確認してください。

3. 現在の明細書ドキュメントは、2 つの異なるタイプ、トランザクション明細書と財務諸表に分割されます。

      - トランザクション明細書は、すべての転記されていない有効な小売トランザクションを取得し、販売注文、売上請求書、支払および割引仕訳帳、収入経費トランザクションを設定した頻度で作成します。 このプロセスを高頻度で実行できるようにコンフィギュレーションして、小売トランザクションが P-ジョブを介して Retail Headquarters にアップロードされる際にドキュメントが作成されるようにする必要があります。 販売注文と売上請求書が既に作成されているトランザクション明細書では、**在庫の転記** バッチ ジョブをコンフィギュレーションする必要はありません。 ただし、特定の業務要件を満たすために使用することはできます。  
      
     - 財務諸表は、その日の終わりに作成するように設計されており、**シフト** の決算方法のみをサポートしています。 この明細書は財務調整に限定され、他の現金管理トランザクションの仕訳帳と一緒に、異なる支払/入金の計算金額とトランザクション金額の差額が記載された仕訳帳のみが作成されます。   

4. トランザクション明細書を計算するには、**Retail > Retail IT > POS 転記 > バッチ内のトランザクション明細書の計算**へ移動します。 バッチ内のトランザクション明細書を転記するには、**Retail > Retail IT > POS 転記 > バッチ内のトランザクション明細書の転記**へ移動します。

5. 財務諸表を計算するには、**Retail > Retail IT > POS 転記 > バッチ内の財務諸表の計算**へ移動します。 バッチ内の財務諸表を転記するには、**Retail > Retail IT > POS 転記 > バッチ内の財務諸表の転記**へ移動します。

> [!NOTE]
> メニュー項目、**Ratail > Retail IT > POS転記 > バッチ内の明細書の計算** と **Retail > Retail IT > POS 転記** は、この新しい機能により無効になります。

トランザクション タイプおよび財務諸表タイプは、手動で作成することもできます。 **Retail > チャンネル > 小売店舗** に移動して、**小売明細書**をクリックします。 **新規** をクリックし、作成する明細書のタイプを選択します。 **小売明細書** ページのフィールドとそのページの **明細書グループ** にあるアクションは、選択した明細書タイプに基づいて、関連するデータおよびアクションを表示します。
