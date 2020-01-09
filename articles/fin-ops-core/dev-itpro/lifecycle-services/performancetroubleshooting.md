---
title: Lifecycle Services (LCS) 内のツールを使用した、パフォーマンスのトラブルシューティング
description: このトピックでは、Microsoft Dynamics Lifecycle Services (LCS) がサンドボックスと生産環境でのパフォーマンスの問題を診断して緩和できるようにするために提供するさまざまなツールについて説明します。
author: manalidongre
manager: AnnBe
ms.date: 03/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 267184
ms.assetid: eb056816-ccf4-43a5-aed3-cf72543353de
ms.search.region: Global
ms.author: manado
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 830d5242c436a18b29a9dcbb64e8157fd44a581d
ms.sourcegitcommit: dd960cf07d8be791fd27c7bb72e6baa2d63ccd51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2019
ms.locfileid: "2578303"
---
# <a name="performance-troubleshooting-using-tools-in-lifecycle-services-lcs"></a>Lifecycle Services (LCS) 内のツールを使用した、パフォーマンスのトラブルシューティング

[!include [banner](../includes/banner.md)]

このトピックでは、Microsoft Dynamics Lifecycle Services (LCS) で使用可能なツールを使用してパフォーマンスの問題をトラブルシューティングおよび緩和する方法について説明します。

## <a name="overview"></a>概要

顧客およびパートナーからよくあるフィードバックは、LCS のツールを使用してパフォーマンスの問題を正常に診断することができないというものでした。 要求時にパフォーマンス測定基準を収集する信頼性の高い方法を作成することで、このフィードバックに対処しました。 これにより、顧客やパートナーは、サンドボックスまたは生産環境での問題を軽減するために使用できる事前に定義された一連のアクションを実行できます。 この機能は、直接 SQL Server を照会するため、ほぼリアルタイムでクエリ ストア指標が取得されます。 アクションが実行されたときにアクションを実行したユーザーを容易に判断できるように、実行されるアクションに監査証跡も追加しました。

## <a name="details"></a>詳細情報

LCS のすべての SQL パフォーマンス ツールは、特定の環境の **環境の監視** ページにある **SQL インサイト** タブから使用できます。 次のタブがあります。

- **ライブ ビュー** – 現在の DTU、実行中のステートメント、ブロックしているステートメントを示しています。 パフォーマンスの問題を示す現在の **SQL Now** ページは、**ライブ ビュー**に置き換えられます。

    [![ライブ ビュー](./media/LiveView.jpg)](./media/LiveView.jpg)

- **クエリ** – 必要に応じてメトリックを取得するために使用される定義済みのクエリの一覧を表示します。 クエリの例には、現在のブロック ツリー、有効な計画ガイドのリスト、および最も高価なクエリの一覧が含まれています。

    [![クエリ](./media/Queries.jpg)](./media/Queries.jpg)
 
    > [!IMPORTANT]
    > クエリ結果が即座に返されることを保証するために、ほとんどのクエリは同期的に実行されます。 ただし、パフォーマンスに問題が発生している場合は、同期クエリの実行によってタイム アウト エラーが発生する可能性があります。 この問題に対処するために、新しい **高速クエリの使用** オプションが追加されました。 既定で、ほとんどのクエリでこのオプションが有効になっています。 クエリの実行後にタイム アウト エラーが発生する場合は、**高速クエリの使用** オプションをオフにして再度クエリの実行を試みます。 クエリは非同期に実行されます。

- **アクション** – サンド ボックスと製造環境での問題を緩和するために実行する必要がある定義済みアクションの一覧を表示します。 アクションの例としては、インデックスの追加または削除、テーブルでの統計の更新、インデックスの再構築、ブロック ステートメントの終了があります。 アクションを実行するといつでも、環境の環境履歴に実行されるアクションの記録が表示されます。 履歴レコードは、クエリの実行時ではなく、アクションにのみ作成されます。 

    [![アクション](./media/Actions.jpg)](./media/Actions.jpg)

- **パフォーマンス メトリックス** - 論理入出力、実行カウント、期間、CPU 時間、および待機数に基づいて、選択した期間にシステムで実行された最もコストのかかったクエリが表示されます。 このデータは SQL クエリ ストアからクエリされます。 データは 30 日間保持され、ツールは毎日、協定世界時 (UTC) の午後 10 時にデータ収集を実行します。 ツールを使用するには、過去 30 日間の期間を選択します。 クエリ結果が表示されたら、期間グラフ内のバーを選択して、クエリが他の基準に該当する場所を強調表示します。 **ステートメント**タブで、クエリを表示、またはクエリの実行計画をダウンロードします。

    [![パフォーマンス メトリックス](./media/perfmetrics.jpg)](./media/perfmetrics.jpg)

- **インデックス分析** – ユーザーのスキャン、ユーザーのシーク、ユーザーの更新プログラム、および行の数に基づいて、集計インデックスとテーブル情報が表示されます。 パフォーマンス測定基準と同様に、このツールは追加のテーブル メトリックスと共に選択したインデックスのトレンドを表示します。

    [![インデックス分析](./media/IndexAnalysis.jpg)](./media/IndexAnalysis.jpg)

- **クエリ** タブと **アクション** タブ – **クエリ** および **アクション** タブに表示されるクエリの詳細については、[クックブックの照会](querycookbook.md) を参照してください。

## <a name="how-do-i-use-this-feature"></a>この機能を使う方法

1. LCS でプロジェクトに移動し、環境の詳細ページを開きます。 **監視** セクションで **環境監視** リンクを選択します。。 **SQL インサイト** タブを選択してこの機能にアクセスします。
2. 各タブ (**ライブ ビュー**、**クエリ**、および**アクション**、**パフォーマンス メトリックス**、**インデックス**、**分析**) に移動し、詳細を表示またはクエリ実行できます。
3. クエリの実行による結果を検索したり、Excel にエクスポートしたりするオプションがあります。
4. パフォーマンスの問題の原因を絞り込んだら、事前に定義されたアクションを使用して問題を軽減できます。
5. アクションを実行すると、**環境履歴** ページにエントリが作成されます。アクションの詳細、渡されたパラメーター、タイムスタンプ、アクションをトリガーしたユーザーが表示されます。

## <a name="sample-flow"></a>サンプル フロー

**シナリオ**: ユーザーは、システムを使用する場合にパフォーマンスの低下を報告します。 1 つの問題はブロック ステートメントの可能性があります。 正常なシステムでは単独でブロックするのが通常であり、過剰になったり、営業活動に悪影響を及ぼし始めたときのみ問題となります。

1. **ライブ ビュー** タブに移動し、ブロック ステートメントがないか確認します。 ブロック ステートメントがある場合、ブロック クエリ ID をコピーします。
2. **クエリ** タブを開き、**現在のブロック ツリー** クエリを選択します。 SQL 操作をブロックしているルート ブロッカーが返されます。
3. 問題を解決するには、実行させて自然にクリアさせるか、リード ブロッカーのプロセスを終了して作業をロールバックすることができます。 一般に、自然にクリアしないとは思われる場合 (不適切なクエリ プランの場合など) や、重要なプロセスを実行できないためにすぐに完了する必要があるような状況でのみリード ブロッカーを終了する必要があります。
4. 現在実行されているステートメントを終了しても問題がないことを確認します。
5. **アクション** タブを開き、**SQL プロセスの終了** アクションを選択して、ルート ブロッカー クエリ ID を渡します。 これは、ブロック ステートメントを終了するために SQL データベースに対してクエリを実行します。
6. **クエリ** タブに移動し、**現在ブロックしているクエリ** を実行して、ブロック ステートメントが終了したかどうかを確認します。
7. **環境履歴** ページで、どのプロセスが終了したかの詳細を確認することもできます。
8. 将来この問題を避けるため、インデックスまたはプラン ガイドを使用したり、ロック エスカレーションをオフにしたり、各種レコードでの操作中にプロセスが互いにブロックしている場合はページ ロックを使用してください。 プロセスが同じレコードで動作している場合、ブロックを回避するには、同時に同じレコード上で動作しないよう、プロセスをリファクタリングまたは再スケジューリングする必要があります。