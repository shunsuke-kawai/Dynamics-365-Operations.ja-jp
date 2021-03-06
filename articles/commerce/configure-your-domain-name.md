---
title: ドメイン名のコンフィギュレーション
description: このトピックでは、Microsoft Dynamics 365 E コマース サイトのドメイン名をコンフィギュレーションする方法について説明します。
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7a988f533757cc3f8555fcf4fb724a22a5b014f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770461"
---
# <a name="configure-your-domain-name"></a>ドメイン名のコンフィギュレーション

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

このトピックでは、Microsoft Dynamics 365 E コマース サイトのドメイン名をコンフィギュレーションする方法について説明します。 

## <a name="add-domains-during-e-commerce-initialization"></a>E-コマースの初期化中にドメインを追加する

ドメインを E コマース環境に関連付けるには、[新しい E コマース サイトの配置](deploy-ecommerce-site.md) に記載され E コマースを初期化します。 初期化中、E コマース環境のプロビジョニングに使用する情報を提供するように求められます。 **サポートされるホスト名**フィールドに、この環境で使用する予定のすべてのドメインを追加します。 複数のドメインはセミコロンで区切る必要があります。 この方法で、全ての必要な E コーマース コンポーネントでドメインがコンフィギュレーションされ、それらは、コンテンツ配信ネットワーク (CDN) または Web サーバーからのトラフィックを切り替えて、それを E コマース フロント エンドにポイントする際に使用することができます。

## <a name="add-domains-after-e-commerce-initialization"></a>E-コマースの初期化後にドメインを追加する

E コマースの初期化後に新しいドメインを E コマース環境に関連付けるには、サービス要求を送信する必要があります。

## <a name="additional-resources"></a>追加リソース

[オンライン ストアの概要](online-store-overview.md)

[E コマース サイトの作成](create-ecommerce-site.md)

[新しい E コマース サイトの配置](deploy-ecommerce-site.md)

[チャンネルとオンライン サイトの関連付け](associate-site-online-store.md)

[コンテンツ配信ネットワーク (CDN) のサポートの追加](add-cdn-support.md)

[場所に基づく店舗検出の有効化](enable-store-detection.md)

[ユーザー ログイン用のカスタム ページの設定](custom-pages-user-logins.md)
