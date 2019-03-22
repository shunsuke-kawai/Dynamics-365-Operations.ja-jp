---
title: Lifecycle Services (LCS) によるサービスの更新の構成
description: このトピックでは、環境の最新のサービスを受け取る方法とタイミングを指定する方法について説明します。
author: manalidongre
manager: AnnBe
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: manado
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 35a710d210d99b5d28f7eea1b331a9c0b75bc830
ms.sourcegitcommit: 0bd0215d0735ed47b1b8af93a80bcdbf7ca2cc49
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "790312"
---
# <a name="configure-service-updates-through-lifecycle-services-lcs"></a>Lifecycle Services (LCS) によるサービスの更新の構成

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/coming-soon.md)]

Microsoft Dynamics Lifecycle Services (LCS) では、Microsoft Dynamics 365 for Finance and Operations 環境のサービス更新を Microsoft から受け取る方法とタイミングを指定できます。

> [!IMPORTANT]
> この機能は **Microsoft Dynamics 365 for Finance and Operations バージョン 8.1 (2018 年 10 月) 以降** を使用していて[最初のリリース](../../fin-and-ops/get-started/public-preview-releases.md) プログラムの一部で **ない** 顧客だけが利用できます。 Microsoft はこの機能を最初のリリースのお客様、および古いバージョンの製品を使用しているお客様もご利用いただけるよう努めています。 

LCS で **プロジェクト所有者** ロールが割り当てられているユーザー (顧客またはパートナー) のみが更新を構成できます。 さらに、更新は **実装プロジェクト** に対してのみ構成できます。

構成設定を変更するには、これらの手順を実行します。

> [!NOTE]
> これらの設定は、サービス更新にのみ適用されます。 毎月、環境に適用されているオペレーティング システム レベルのセキュリティ更新には影響がありません。

1. 実装プロジェクトの LCS で **プロジェクト設定** ページを開きます。

    このページには **更新プログラムの設定** という名前の新しいタブがあります。

2. **更新設定** タブで、必要に応じて、次のコンフィギュレーション オプションを設定します。

    - **更新環境**: 生産更新の前に更新する代替サンドボックス環境を選択します。

        既定では、マイクロソフトは、まず基本サービスに含まれる第 2 層標準受け入れテスト (サンドボックス) 環境を更新します。 次に、更新プログラムを実稼働環境に適用します。 第 2 層以上のサンドボックス アドオン環境を購入し、別のサンド ボックスを更新する場合は、代替環境に既定の環境を変更するためにこのフィールドを使用できます。

        > [!IMPORTANT]
        > ここで選択した環境は、実稼働環境に選択されている更新頻度の 7 暦日前に更新されます。

    - **製造環境更新頻度**: 実稼働環境への定期更新の頻度を選択します。 **環境の更新** フィールドで選択したサンドボックス環境は、選択されている頻度の 7 暦日前に更新されます。 次のオプションを使用できます。

        - **頻度を選択**: 月の第 1 週、第 2 週、第 3 週に更新を受け取るかどうかを選択します。
        - **3つのタイム ゾーンのいずれかを選択**: 実稼働環境を更新するタイム ゾーンを選択します: 東部標準時 (UTC - 5)、香港時 (UTC + 8)、またはグリニッジ標準時 (UTC + 0)。
        - **曜日を選択:** 更新を受信する曜日を選択します。
        - **時間帯を選択:** 更新プログラムを受信する時間帯を選択します。

        > [!NOTE]
        > 現時点では、曜日および時間帯オプションはいくつかのオプションのみ使用できます。 Microsoft は、顧客の平日など、他のオプションもすぐに追加します。

 3. コンフィギュレーション オプションの設定が完了したら **保存** を選択します。
 
更新環境および更新頻度を設定したら、Microsoft は、今後6か月の更新カレンダーを生成します。 このカレンダーは、コンフィギュレーション済のサンド ボックスと生産環境がいつ更新されるを正確に表示します。 したがって、各更新の予想される時期を特定できます。 カレンダーを表示するには、**実稼働環境の更新頻度** オプションで **更新カレンダーを表示** リンクを選択します。

> [!IMPORTANT]
> 設定を保存した後いつでも変更できます。 ただし、進行中の展開がある場合、新しい設定は、既存の展開タイミングを更新するために使用されません。 代わりに、次の展開で使用され始めます。 進行中の展開は、サンド ボックス環境の更新に関する電子メール通知が送信された日付から、実稼働環境の更新時の日付までの14日間の期間によって定義されます。

構成されたサンドボックス環境および実稼働環境への更新を一時停止する方法の詳細は、[Lifecycle Services (LCS) によるサービスの更新の一時停止](pause-service-updates.md) を参照してください。

1 つのバージョンおよび Microsoft が管理するサービスの更新の詳細は、[1 つのバージョンのサービス更新に関するよく寄せられる質問](../../fin-and-ops/get-started/one-version.md) を参照してください。