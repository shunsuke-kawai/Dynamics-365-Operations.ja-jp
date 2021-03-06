---
title: オフライン販売時点管理 (POS) の機能
description: この記事では、小売サーバーが利用できない場合にチャンネルのデータベースからオフライン データベースに POS デバイスが自動的に切り替わる、Retail Modern POS のオフライン モードについて説明します。 また、この記事ではオフライン モードの一般的な設定情報も含まれ、オフライン データベースとチャンネルのデータベース間で発生するデータ同期についても説明します。
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 27041
ms.assetid: 20b51874-8912-40cf-9296-864df707315a
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 056dd028410a4b3f7e8e1e22370f304d0c17263f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545089"
---
# <a name="offline-point-of-sale-pos-functionality"></a>オフライン販売時点管理 (POS) の機能

[!include [banner](includes/banner.md)]

この記事では、小売サーバーが利用できない場合にチャンネルのデータベースからオフライン データベースに POS デバイスが自動的に切り替わる、Retail Modern POS のオフライン モードについて説明します。 また、この記事ではオフライン モードの一般的な設定情報も含まれ、オフライン データベースとチャンネルのデータベース間で発生するデータ同期についても説明します。

## <a name="overview"></a>概要

Retail Modern POS では、小売サーバーが利用できないときはいつでも 販売時点管理 (POS) デバイスがオフライン モードになります。 したがって、小売サーバーとの接続が失われると、Retail Modern POS はオフライン データベースに自動的に切り替わります。 販売トランザクション中に、オフライン プロファイルでコンフィギュレーションされたタイムアウトの間隔内でデータの要求が成功しなかった場合、Retail Modern POS は自動的にオフライン データベースに切り替わり、販売トランザクションを続行します。 POS デバイスがオフライン モードの間に、Retail Modern POS はオフライン プロファイルでコンフィギュレーションされた再接続試行間隔の後に再接続を試みます。 この再接続試行は、トランザクションの先頭でのみ実行されます。

### <a name="determining-the-connection-mode-of-retail-modern-pos"></a>Retail Modern POS の接続モードを決定する

Retail Modern POS のステータス ヘッダーは現在の接続ステータスを表示し、**接続ステータス** ウィンドウはオフライン データベースと同期する最後の試行のステータスを表示します。

[![接続ステータス](./media/status.png)](./media/status.png)

### <a name="creating-a-button-to-manually-switch-between-online-and-offline-modes"></a>手動でオンラインとオフライン モードを切り替えるためのボタンを作成

Retail Modern POS にオンラインとオフライン モードを手動で切り替えるボタンを追加できます。 POS 操作 **917 – データベース接続ステータス**のボタンを作成します。 このボタンの名前は、Retail Modern POS が小売サーバーに接続されている場合は**接続解除**となり、接続解除されている場合は**接続**となります。 このボタンは接続の表示、小売サーバーとの接続解除および接続に使用できます。

[![Retail Modern POS の接続解除ボタン](./media/details-1024x537.png)](./media/details.png)

## <a name="setup"></a>セットアップ

POS のデバイス (登録) のオフライン サポートを有効にするには、**登録** ページで、**オフラインのサポート** オプションを **はい** に設定します。 新しいチャンネル データベース エンティティが作成され、店舗のチャンネル データ グループに追加されます。 その後、オフライン データベースのデータ パッケージを生成するためにすべての配送スケジュールを実行します。 次に、Retail Modern POS のオフライン バージョンをインストールします。 インストール プロセスでは、オフライン データベースが作成されます。 さらに、必要な場合は、Microsoft SQL Server 2014 Express をインストールします。 Retail Modern POS への最初のサインイン後にオフライン データの同期が開始されます。

## <a name="data-synchronization"></a>データ同期

小売用スケジューラはオフライン データベースにマスター データを送信するのに使用されます。 既定では、配送スケジュールの実行時に、データの変更がチャンネルのデータベースとオフライン データベースの両方に送信されます。 Retail Modern POS には、使用可能なすべてのデータ パッケージをダウンロードし、オフライン データベースに挿入する async sync ライブラリが含まれます。 トランザクションがオフラインで作成された場合、Retail Modern POS はそれらをチャンネル データベースに挿入するためにアップロードします。 オフラインのデータ同期は、Retail Modern POS の実行時にのみ実行できます。

[![オフライン同期](./media/offline-sync-1024x521.png)](./media/offline-sync.png)
