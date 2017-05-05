---
title: "Retail 周辺機器シミュレーター"
description: "このトピックでは、Microsoft Dynamics 365 for Operations - Retail で提供される周辺シミュレーター ツールについて説明します。"
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 266544
ms.assetid: 16f31e70-15fc-441e-9727-e6a31c3a48f5
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 42dc414ff2bb6359b47d89c3bd3c510e4258f816
ms.openlocfilehash: b2229466040351d8c2b9494b30b4c928651820b8
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripheral-simulator"></a>Retail 周辺機器シミュレーター

[!include[banner](includes/banner.md)]


このトピックでは、Microsoft Dynamics 365 for Operations - Retail で提供される周辺シミュレーター ツールについて説明します。

<a name="overview"></a>概要
--------

Microsoft Dynamics 365 for Operations - Retail 周辺シミュレーターは、小売環境で使用される周辺機器を設定、テスト、およびトラブルシューティングを支援するツールです。 Retail 周辺機器のテストを簡素化したり、正しくない設定または障害が発生しているデバイス ドライバーによって生じた問題を分離する場合に周辺シミュレーターを使用できます。 周辺機器シミュレータには、Dynamics 365 for Operations - Retail がサポートする仮想バージョンのデバイスを搭載したデスクトップ プログラムが含まれています。 個々の仮想デバイスのセクションでは、デバイスと販売時点管理 (POS) の間の相互作用を示します。 また、さまざまな POS シナリオに有効な入力を提供するために使用することもできます。 周辺シミュレーターは、POS と次の仮想デバイス間の相互作用をサポートします:

-   **プリンタ** – 周辺シミュレーターは POS プリンターに対して設定されている入庫を表示できます。
-   **ライン ディスプレイ** – 現物ライン ディスプレイの活動を示す場合は、仮想ライン ディスプレイを設定できます。
-   **磁気ストライプ リーダー (MSR)** – 周辺シミュレーターから POS にシミュレートされた磁気ストライプのイベントを送信できます。
-   **ドロワー** – 現物キャッシュ ドロワーをシミュレーションできます。
-   **ドロワー 2** – 周辺シミュレーターに 2 番目のキャッシュ ドロワーを設定することにより、2 つのアクティブなシフトを持つ 1 つの POS レジスターを含むシナリオをシミュレートできます。
-   **スキャナ** – 周辺シミュレーターがサポートする仮想バーコード スキャナーは、バーコード スキャン イベントを発行することができます。
-   **スケール** – A の仮想スケールは POS と計量品目との相互作用をシミュレーションすることができます。
-   **個人識別番号 (PIN) パッド** – PIN パッドの操作をシミュレーションできます。 **注記:** 支払コネクタによる現物の PIN パッドのサポートを実行する必要があります。
-   **署名のキャプチャ** – 周辺機器シミュレーターには、顧客アカウントの支払いなど、一部の入札に必要な署名を求めるプロンプトが表示されるように設定できる仮想署名キャプチャ デバイスが含まれています。

周辺機器シミュレータを使用して、バーコード スキャナと MSR から発生するキーボード ウェッジのイベントをシミュレートすることもできます。 仮想周辺機器のシミュレーターは、Retail POS 用 Object linking and embedding (OPOS) をサポートします。

## <a name="key-scenarios"></a>重要なシナリオ
### <a name="troubleshooting"></a>トラブルシューティング

周辺シミュレーターを使用し、デバイスの設定をトラブルシューティングできます。 周辺機器シミュレーターまたは同じクラスのセカンド デバイスがない場合、どこで問題が発生したかを特定することが困難になる可能性があります。 ただし、周辺シミュレーターがある場合は、仮想デバイスを設定でき、物理デバイスに使用する同じコード パスとビジネス ロジックを実行できます。 周辺機器シミュレーター側からの仮想デバイスと物理デバイス間の主な違いは、サービス オブジェクト、またはデバイス ドライバです。 物理デバイスの場合は、サービス オブジェクトはデバイス メーカーによって提供されます。 それに対して、周辺機器シミューレーターの場合は、周辺機器シミュレーターの一部としてサービス オブジェクトが提供されます。 周辺機器シミューレーターが正常に機能している場合、ハードウェア プロファイルのデバイス名を実際のデバイスの名前に変更した後にデバイスが正常に機能しない場合は、メーカーが提出したサービス オブジェクトに問題があると想定できます。

### <a name="training"></a>トレーニング

物理的なハードウェアの設定が利用できない場合、周辺機器シミュレーターを使用し、実際的なレイヤーをキャッシャー トレーニングに追加できます。 周辺機器シミュレーターがトレーニングのシナリオに含まれている場合、レジ担当者は、製品のバーコードのスキャンやギフト カードの読み取りなどのインプットを提供し、さらに特定のトランザクションに対してどの入庫が印刷されるかを確認することにより、より効果的に POS を操作できます。

### <a name="testing"></a>テスト

周辺機器シミュレーターを使用し、仮想環境の物理的なハードウェアを配置せずに、製品のバーコードや受領書フォーマットなどをテストできます。 物理的なハードウェアが必要とされず、ハードウェア ステーションまたは物理的なコンピューターの POS を配置する必要がないため、バック オフィスに行われた変更をより迅速にテストできます。

## <a name="set-up-the-peripheral-simulator"></a>周辺機器シミュレーターの設定
### <a name="set-up-a-hardware-profile"></a>ハードウェア プロファイルの設定

1.  周辺機器シミュレーターを設定するには、[**小売りとコマース**] &gt; [**チャネル設定**] &gt; [**POS 設定**] &gt; [**POS プロファイル**] &gt; [**ハードウェア プロファイル**] の順に移動します。
2.  新しいプロファイルを作成するには、[**新規**] をクリックします。
3.  **[プロファイル番号]** および **[説明]** フィールドに値を入力します。
4.  テストする必要がある仮想デバイスを設定するには、次の表を参照してください。 表の列の説明を次に示します。
    -   **デバイス** – この列はデバイスを設定するために展開する FastTab の名前を示します。
    -   **機器タイプ** – この列は、デバイスの名前のラベルが付いているフィールドで選択した値を提供します。
    -   **デバイス名** – この列はデバイス名に対して入力する正確な値を提供します。 **重要:** ハードウェア ステーションがこれらの特定の名前を使用し、デバイスに対処するため、ここで指定されたデバイスは必須です。 これらの特定の名前を使用しない場合、デバイスは使用できません。

    | デバイス            | デバイス タイプ | デバイス名              |
    |-------------------|-------------|--------------------------|
    | プリンター           | OPOS        | MockOPOSPrinter          |
    | ライン ディスプレイ      | OPOS        | MockOPOSLineDisplay      |
    | MSR               | OPOS        | MockOPOSMSR              |
    | 手形振出人            | OPOS        | MockOPOSDrawer1          |
    | Drawer2           | OPOS        | MockOPOSDrawers          |
    | スキャナー           | OPOS        | MockOPOSScanner          |
    | スケール             | OPOS        | MockOPOSScale            |
    | PIN パッド           | OPOS        | MockOPOSPinPad           |
    | 署名キャプチャ | OPOS        | MockOPOSSignatureCapture |

**注記:** バーコード スキャナーと MSR のキーボード ウェッジのイベントをシミュレーションするには、ハードウェア プロファイルでの特定の設定は必要ありません。

### <a name="assign-the-hardware-profile-to-a-register"></a>レジスターへのハードウェア プロファイルの割り当て

1.  ハードウェア プロファイルを作成した後に、チャンネルは、[**小売りとコマース**] &gt; [**チャネル設定**] &gt; [**POS の設定**] &gt; [**登録**] の順に移動します。
2.  [**POS レジスター**] リストでは、周辺機器シミュレーターを使用する必要があるレジスターに対して、[**レジスター番号**] フィールドにあるリンクをクリックします。
3.  [**編集**] をクリックします。
4.  [**プロファイル**] セクションの [**ハードウェア プロファイル**] フィールドでは、仮想周辺機器用に作成したハードウェア プロファイルを選択します。
5.  [**保存**] をクリックします。

### <a name="synchronize-changes-to-the-channel-database"></a>チャンネル データベースへの変更の同期

1.  [**小売りとコマース**] &gt; [**小売 IT**] &gt; [**配送スケジュール**] の順に移動します。
2.  [**1090**] 配送スケジュールを選択します。
3.  POS への変更を同期させるには、[**今すぐ実行**] をクリックします。

データが同期されると、新しいハードウェア プロファイルとレジスターへの変更は、チャンネル データベースで使用できます。

## <a name="install-the-peripheral-simulator"></a>周辺機器シミュレーターのインストール
1.  [**小売りとコマース**] &gt; [**チャンネル設定**] &gt; [**POS 設定**] &gt; [**POS プロファイル**] &gt; [**ハードウェア プロファイル**] の順に移動します。
2.  **[ダウンロード]** をクリックし、[**PeripheralSimulator**] をクリックします。 **注記:** 周辺機器シミュレーターをダウンロードするには、ポップアップ ブロッカーをオフにする必要があります。
3.  ダウンロードが完了した後、[**ダウンロード**] フォルダーを開き、[**VirtualPeripherals.msi**] をダブルクリックすると、インストーラーが開始します。
4.  既定の設定を使用して周辺機器シミュレーターをインストールします。

周辺機器シミュレーターに加えて、Monroe Consulting Services からコモン コントロール オブジェクトをインストールする必要があります。 それ以外の方法では、周辺機器シミュレーターは正しく動作しません。 コモン コントロール オブジェクトをダウンロードするには、<http://monroecs.com/oposccos_current.htm> に移動します。

## <a name="using-the-peripheral-simulator"></a>周辺機器シミュレーターの使用
周辺機器シミュレーターを開始するには、コンピューターの [**開始**] をクリックし、[**Retail 周辺シミュレーター**] を入力してから、検索結果に表示されるアプリを選択します。 周辺シミュレーターが開始されたら、サポートされているデバイスを表示するデバイス名をクリックします。 これらのデバイスはウィンドウの左側のタブとしてリストされます。 特定のデバイスを表示するには、そのデバイスのタブをクリックします。

### <a name="line-display-capabilities"></a>ライン ディスプレイ機能

ライン ディスプレイは、周辺シミュレーターに表示される最初のデバイスです。 仮想ライン ディスプレイを設定すると、POS トランザクションでスキャンする際に、品目が表示されます。 明細行品目に加えて、支払 / 入金が POS で選択されている場合に支払われる合計を表示します。 また、支払/入金を入力すると、トランザクションに対してまだ支払がされていない金額が表示されます。 POS が使用されていない場合は、レジが終了したことを示すメッセージを表示できます。 ハードウェア プロファイルの **ライン ディスプレイ** FastTab のメッセージを設定する必要があります。

### <a name="cash-drawer-capabilities"></a>キャッシュ ドロワー機能

キャッシュ ドロワーは、周辺機器シミュレーターに表示されるセカンド デバイスです。 仮想キャッシュ ドロワーを使用できるようにハードウェア プロファイルを設定すると、POS は、支払/入金申告などのドロワー操作に応じて、有効なシフトのキャッシュ ドロワーを開き、レジ担当者は、標準のキャッシュ・アンド・キャリー トランザクション中に変更または預金できるようになります。 仮想キャッシュ ドロワーには **メイン ドロワー** および **セカンド ドロワー**のラベルがあります。 これらのラベルはハードウェア プロファイルにドロワーとドロワー 2 とそれぞれ表示されます。 ドロワーが閉まると、終了したキャッシュ ドロワーの画像が表示され、終了したキャッシュ ドロワーのボタンには **ドロワーを開く** というラベルが付きます。 このボタンをクリックすると、開いていることを示す開いているキャッシュ ドロワーの画像と置き換えられます。 開いているキャッシュ ドロワーのボタンには **ドロワーを閉める** というラベルが付きます。 POS の複数の操作により、キャッシュ ドロワーを開くことができます。 キャッシュ ドロワーが開いている間はほとんどの操作を続行できません。 一部の営業終了処理は例外となります。 POS ユーザーが、キャッシュ ドロワーが開いている間に操作を実行できないことを示すエラー メッセージが表示された場合は、ユーザーは仮想または現物キャッシュ ドロワーを閉じて操作を続行する必要があります。 キャッシュ ドロワーがハードウェア プロファイルで **共有** とマークされている場合、システムは、操作の前にドロワーが閉じられていることを確認しません。 キャッシュ ドロワーを開いていても、通常通りに操作が進みます。 この動作は、キャッシュ ドロワーが販売担当者間で共有され、販売担当者がキャッシュ ドロワーを使用する一方で、他の販売担当者が自分の POS デバイスの不適切なタスクを実行するシナリオをサポートします。 キャッシュ ドロワーにした変更は、現在のシフトを閉じ、新しいシフトを開けるまでは確認できません。

### <a name="msr-capabilities"></a>MSR 機能

周辺機器シミュレーターは、OPOS モードまたはキーボード ウェッジ モードで操作することにより、仮想 MSR 操作に対して堅牢なサポートを提供します。 OPOS モードでは OPOS デバイスとして機能するようにハードウェア プロファイルで MSR を設定する必要があります。 キーボード ウェッジ モードは Microsoft Windows に、キーボード ウェッジ データ イベントを送信するのみです。 設定が異なること以外にも、OPOS とキーボード ウェッジ モードは次の点において違います。

-   POS クライアントでは、ロイヤルティまたはギフト カードのエントリに対して磁気ストライプ データを有効にするシナリオなど、特定のシナリオに対して、OPOS MSR デバイスが有効になります。
-   キーボード ウェッジ モードでは、データが送信されると、周辺機器シミュレーターがキーボード ウェッジ データを有効なフィールドに送信します。 この動作は、データがキーボードにより入力された場合に実行される動作に似ています。 キーボード ウェッジとして MSR を使用するには、ユーザーはデータが正しいフィールド受信されるように、Retail Modern POS (MPOS) に切り替える必要があります。 したがって、データが正しいフィールドに送信されるかを確認できる時間をユーザーに与えるため、遅延を設定できます。

#### <a name="testing-gift-and-payment-card-swipes"></a>ギフト カードや支払カードの読み取りのテスト

周辺機器シミュレーターが提供する仮想 MSR はギフト カードや支払カードの読み取りにおけるシナリオをテストするために特定の MSR データを設定することもできます。 カードを作成するには、プラス記号 (**+**) タンをクリックし、カードのタイプを選択します。 その後、定義しているカードの有効期限の月と年を含め、カード番号を指定するか、または POS に送信する必要があるデータを追跡します。 [**カードの種類**] フィールドで選択した値は、カードにマップできるだけのラベルです。 このラベルにより、周辺機器シミュレーターでカードを読み取ると、カードを識別し易くなります。 画像の上の左矢印 (**&lt;**) および右矢印 (**&gt;**) ボタンを使用して、周辺機器シミュレーターで設定されたカードを選択できます。 プラス記号 (**+**) ボタンの隣にある [**編集**] および [**削除**] ボタンを使用することにより、カードを編集または削除できます。

### <a name="pin-pad"></a>PIN パッド

PIN パッドのシミュレーターを設定し、OPOS PIN パッドをシミュレートできます。 電子資金決済 (EFT) のトランザクションが POS で実行されると、PIN 入力が必要とされ、ハードウェア ステーションは、PIN デバイスに PIN 入力を要求するよう PIN デバイスを呼び出します。 これを実行する上で、周辺機器シミュレーターの PIN パッドから、EFT の支払コネクター サポートが要求されます。

### <a name="printer"></a>プリンター

仮想周辺機器のプリンタには、POS から印刷されると入庫が表示されます。 印刷工程で複数の入庫が作成される場合、入庫をスクロールできます。

#### <a name="configure-receipt-printing"></a>入庫印刷の構成

1.  [**小売りとコマース**] &gt; [**チャンネル設定**] &gt; [**POS 設定**] &gt; [**POS プロファイル**] &gt; [**ハードウェア プロファイル**] の順に移動します。
2.  仮想周辺機器用に作成したハードウェア プロファイルを選択します。
3.  [**プリンタ**] FastTab で、[**編集**] をクリックします。
4.  [**レシート プロファイル ID**] フィールドで、レシート プロファイルを選択します。
5.  [**保存**] をクリックします。

### <a name="scale"></a>スケール

スケールの製品が POS トランザクションに追加され、スケールが設定されると、POS によってスケールから重量を取得します。 仮想スケールと物理的スケールについては、製品がトランザクションに追加される前に製品と重量を指定する必要があります。 スケール製品をトランザクションに追加する前に、周辺機器シミュレーターに移動し、プラス記号 (**+**) およびマイナス記号 (**–**) ボタンを使用して、スケールがレポートする必要がある重量を調整します。 [**現在の値**] フィールドで目的の重量を入力することもできます。 プラス記号 (**+**)、[**編集**]、および [**削除**] ボタンを使用することにより、重量単位を調整できます。 これにより、単位は、重さを測る製品またはスケールを使用するロケールをベースに指定されます。

#### <a name="configure-a-scale-product"></a>スケール製品の設定

1.  [**小売りと****コマース**] &gt; [**製品とカテゴリ**] &gt; [**カテゴリ別リリース済製品**] に移動します。
2.  製品レコードを開きます。
3.  重さを測る製品を選択します。
4.  [**小売**] FastTab で [**スケール製品**] オプションを [**いいえ**] から [**はい**] に設定します。

#### <a name="synchronize-changes-to-the-channel-database"></a>チャンネル データベースへの変更の同期

1.  [**小売りとコマース**] &gt; [**小売 IT**] &gt; [**配送スケジュール**] の順に移動します。
2.  [**1040**] 配送スケジュールを選択します。
3.  POS への変更を同期させるには、[**今すぐ実行**] をクリックします。

データが同期されると、スケールの製品が POS トランザクションに追加され、POS は重量に対してスケールをチェックします。

### <a name="signature-capture"></a>署名キャプチャ

仮想署名のキャプチャ デバイスは、使用している支払/入金が署名を必要とする場合、仮想署名のキャプチャ パッドに署名を提供するようユーザーに要求します。 ユーザーが署名を承諾すると、POS に署名を表示できます。 そして、レジ担当者が署名を承諾できるようになります。 署名は支払/入金とともに保存され、バック オフィスに他のトランザクション データとともに同期されます。

#### <a name="set-up-a-tender-to-require-a-signature"></a>署名を要求するよう支払/入金を設定する

1.  [**小売とコマース**] &gt; [**チャンネル**] &gt; [**小売店舗**] &gt; [**すべての小売店舗**] の順に移動します。
2.  小売店舗を選択します。
3.  [**編集**] をクリックします。
4.  [**設定**] をクリックしてから、[**Set up**] セクションで、[**支払方法**] をクリックします。
5.  [**編集**] をクリックします。
6.  署名を要求する支払方法を選択します。
7.  [**一般l**] セクションの [**署名キャプチャ**] で [**署名キャプチャ デバイスの使用**] オプションを [**はい**] に設定します。
8.  [**署名キャプチャの最小額**] フィールドで、署名のキャプチャをトリガする必要がある最小額を入力します。

#### <a name="synchronize-changes-to-the-channel-database"></a>チャンネル データベースへの変更の同期

1.  [**小売りとコマース**] &gt; [**小売 IT**] &gt; [**配送スケジュール**] の順に移動します。
2.  [**1070**] 配送スケジュールを選択します。
3.  POS への変更を同期させるには、[**今すぐ実行**] をクリックします。

データが同期されると、署名を必要とする支払/入金が使用され、金額が署名のしきい値を満たす場合は、POS は仮想署名のキャプチャ デバイスで署名を要求します。

## <a name="additional-configuration"></a>追加設定
周辺機器シミュレーターのコンフィギュレーション ファイルを編集して、テストしているシナリオに対してさらに適切に取り組むことができます。 \\Program Files (x86) \\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config からコンフィギュレーション ファイルを検索できます。 コンフィギュレーション ファイルは、スケールのテストに使用できる単位、テストに使用できるカード タイプ、およびバーコード タイプを定義します。 たとえば、コンフィギュレーション ファイルのテキスト値の変更することによって、実行時に選択できる新しいカード タイプまたは測定単位を追加できます。 新しい値は、アプリケーションの再起動後に表示されます。

## <a name="troubleshooting"></a>トラブルシューティング
周辺機器シミュレーターの活動は、周辺機器シミュレーター内に記録されます。 \\Program Files (x86) \\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config からログを検索できます。 周辺シミュレーターは、[**アプリケーションとサービス ログ**] &gt; [**Microsoft**] &gt; [**DynamicsAX**] の順にアクセスできる Windows イベント ログに問題をレポートすることもできます。 MPOS または周辺機器シミュレーターを使用する場合に、ハードウェア プロファイルまたはその他の領域に加えた変更が明示的でない場合、チャンネルのデータベースにデータを同期する上で使用する配送スケジューラ ジョブを確認します。 変更が同期された後に、POS でまだ確認できない場合、POS クライアントを再起動します。 コンフィギュレーションされたキャッシュ ドロワーへの変更は、新しいシフトが作成されるまで有効になりません。 そのため、キャッシュ ドロワーに変更を加えた場合、新しいキャッシュ ドロワーの設定をテストするには、既存のシフトが常に閉まっているかを確認します。 メーカーのドライバがモンロー顧問サービスのコモン コントロール オブジェクトの後にインストールされている場合、ドライバが原因でコモン コントロール オブジェクトが正しく動作しなくなることがあります。 この場合、コモン コントロール オブジェクトを再インストールする必要があります。

<a name="see-also"></a>参照
--------

[小売周辺機器の概要](retail-peripherals-overview.md)



