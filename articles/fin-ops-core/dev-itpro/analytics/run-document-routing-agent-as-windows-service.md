---
title: ドキュメント回覧エージェントを Windows サービスとして実行する
description: ドキュメント回覧エージェントは、デスクトップ アプリケーションまたは Microsoft Windows サービスのいずれかとして実行できます。 このトピックでは、正しく実行モードを選択するのに役立つ重要な情報を提供します。
author: TJVass
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 191133
ms.assetid: 7adc7228-4360-4a54-8a3e-4d916e727dd2
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: df65e86e33dbfab158ca10701f2781955c1fd487
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772452"
---
# <a name="run-the-document-routing-agent-as-a-windows-service"></a>ドキュメント回覧エージェントを Windows サービスとして実行する

[!include [banner](../includes/banner.md)]

ドキュメント回覧エージェントには、実行モードを選択できるオプションが含まれています。 このプロセスは、デスクトップ アプリケーションまたは Microsoft Windows サービスのいずれかとして実行できます。 アプリケーションは、Windows サービスとして実行されるとき、コンピューターの再起動後に自動的に起動することができます。 また、特定のユーザー アカウントのセキュリティ コンテキストで実行するように構成することもできます。 この機能拡張により、顧客はネットワーク プリント サーバーなどのセキュリティで保護されたドメイン リソースでドキュメント ルート指定エージェントをホストできます。

このトピックでは、正しく実行モードを選択するのに役立つ重要な情報を提供します。

## <a name="service-applications"></a>サービス アプリケーション
アプリケーションはユーザーがデスクトップ上で連携するプログラムです。 サービスは、バックグラウンドで実行され、アクティブなウィンドウを持たないプロセスです。 ドキュメント回覧エージェントは現在、両方の実行モードをサポートしています。 他方ではなくそのモードを選択する理由、およびサービスとしてのプロセスの実行に関連するステップを理解しておくことが重要です。 Windows サービスの詳細については、[Windows サービス アプリケーションの概要](/dotnet/framework/windows-services/introduction-to-windows-service-applications) を参照してください。 バックグラウンド サービスとしてドキュメント回覧エージェントを実行する主な利点を次に示します。

- コンピューターを再起動すると自動的にサービスが開始されるように設定できます。 ユーザー操作は必要ありません。
- サービスは、バックグラウンドで実行されます。 通知領域で実行される有効なアプリケーションはありません。
- このサービスは、ユーザーがキャッシュされた資格情報を使用してサインインせずに、ドキュメントをルーティングできます。

ドキュメント回覧エージェントを Windows サービスとして実行することには多くの利点がありますが、制限もあります。 次のセクションでは、カスタムのページ マージンを必要とする小切手などのドキュメント レポートの処理に影響する問題について説明します。

## <a name="documents-that-require-custom-margins"></a>カスタム マージンを要求するドキュメント
ドキュメント回覧エージェントが Windows サービスとして実行されるときは、ユーザー設定の余白を必要とする小切手などのドキュメント レポートをネットワーク プリンターに直接印刷することはできません。 代わりに、このドキュメント回覧エージェントは自動的にこれらのドキュメントをターゲット フォルダーに転送します。 アプリケーションの**設定**ダイアログ ボックスにある新しいコンフィギュレーション プロパティで、カスタム マージンを必要とするドキュメント レポートの対象となる場所を定義できます。

ドキュメント回覧エージェントは、デスクトップ アプリケーションとして実行されるときは、Adobe Reader の活用する続行して、Finance and Operations で選択されている共有プリンター デバイスにドキュメントをスプールします。 カスタムの余白を設定したドキュメントを印刷する必要があるシナリオを処理するには、ドキュメント ルーティング エージェントを複数の場所にインストールすることをお勧めします。 デスクトップ アプリケーション モードで実行されるドキュメント ルーティング エージェントでのみ、これらのドキュメントを処理するプリンターをインストールします。 または、実行後のプロセスを使用してターゲット ディレクトリ内のファイルを取得し適切な方法でそれらを指示します。

## <a name="install-the-latest-build"></a>最新ビルドのインストール
1. 現在のドキュメント回覧エージェント構成ファイルのコピーを保存します。 このファイルは、C:\\Users\\&lt;UserID&gt;\\AppData\\Local\\Microsoft\\Microsoft Dynamics 365 for Finance and Operations Document Routing\\Microsoft.Dynamics.AX.Framework.DocumentRouting.config にあります。このパスでは、&lt;UserID&gt;は、ドキュメント ルーティング エージェントがインストールされた Active Directory Domain Services (AD DS) のユーザー名です。
2. ドキュメント回覧エージェントの現在のバージョンをアンインストールします。
3. [ネットワーク印刷を有効にするためにドキュメント回覧エージェントをインストールする](install-document-routing-agent.md)の手順に従って、ドキュメント回覧エージェントの最新バージョンをインストールします。

    > [!NOTE]
    > この時点でアプリケーションをインストールしますが、まだ実行しないでください。

4. 手順1では、コンフィギュレーション ファイルをコピーし、次のディレクトリに貼り付けます。c:\\ProgramData\\Microsoft\\Microsoft Dynamics 365 for Finance and Operations Document Routing。 このステップにより、ドキュメント回覧エージェント アプリケーションの新しいバージョンに以前のすべての構成設定が使用されていることを保証できます。
5. ドキュメント回覧エージェントを実行します。
6. Microsoft Azure Active Directory (Azure AD) または Finance and Operations アプリの資格情報を使用してログインします。
7. 適切なメニュー項目をクリックして、設定およびプリンターを表示して確認します。

次のセクションでは、Windows サービスの実行モードを選択するための詳細な手順を説明します。

## <a name="change-the-default-execution-mode"></a>既定の実行モードの変更
既定では、ドキュメント回覧エージェントはデスクトップ アプリケーションとして実行されます。 プロセスを Windows サービスとして実行するには、[[ドキュメント ルーティング エージェントをインストールしてネットワーク プリンタ デバイスを有効にする](install-document-routing-agent.md)] のプロセスに精通していることを確認してください。 その後次のタスクをコンパイルします。

### <a name="update-the-execution-mode-for-the-document-routing-agent"></a>ドキュメント回覧エージェントの実行モードを更新
1. デスクトップ アイコンを使用してドキュメント回覧エージェントを起動します。
2. **サインイン** オプションを選択し、Azure AD 資格情報を使用してログインします。
3. リボンで、**設定**を選択します。
4. **Windows Service として実行**オプションを有効にします。
5. ユーザー設定の余白を持つドキュメントに生成される PDF ファイルの対象となるフォルダーを提供します。
6. **OK** を選択し、ドキュメント回覧エージェント ウィンドウを閉じます。

### <a name="configure-and-start-the-windows-service"></a>Windows サービスのコンフィギュレーションおよび開始
1. Windows で、Service Manager を開始します。
2. 一覧で、**Microsoft Dynamics 365 for Finance and Operations ドキュメント ルーティング サービス**を選択します。
3. 名前を右クリックし、**プロパティ** を選択します。
4. **ログオン**タブで、**この勘定**オプションを選択し、サービスを実行するために使用される AD DS 資格情報を入力します。

    > [!NOTE]
    > 選択したアカウントが共有ネットワーク デバイスにアクセスできることを確認します。

5. **OK**を選択します。
6. サービスを開始します。

ドキュメント回覧エージェントは現在 Windows サービス アプリケーションとして実行されています。

## <a name="troubleshooting-tips"></a>ヒントのトラブルシューティング
### <a name="verify-the-network-printer-connection"></a>ネットワーク プリンターの接続を確認します。
- 有効なアカウントにネットワーク プリンターへの十分なアクセス権があることを確認します。
- メモ帳または別のローカル アプリケーションを使用して、ユーザー アカウントがネットワーク デバイスに正常に印刷できることを確認します。

### <a name="verify-security-roles"></a>セキュリティ ロールの確認
- ドキュメント ルート指定クライアントのインストールに使用されるアプリケーション リンクにアクセスするには、ユーザーは**ドキュメント ルート指定クライアント**のセキュリティ ロールの一部である必要があります。

### <a name="review-the-service-accounts-access-rights"></a>サービス アカウントのアクセス権を確認します。
- ネットワーク デバイスにアクセスできるドメイン アカウントとして **DocumentRoutingService** サービスが実行されていることを確認します。

### <a name="refresh-the-azure-service-token"></a>Azure サービス トークンを更新
- ドキュメント回覧エージェントが Windows サービスとして実行されている間は Azure 認証トークンを **90 日おきに更新する**必要があります。 サービス トークンを更新するには、クライアントを起動し、メニュー項目を使用してサインアウトし、再びサインインします。

### <a name="disable-shared-printers-for-remote-access"></a>リモート アクセス用の共有プリンターを無効にします
- Microsoft リモート デスクトップを使用してホスト マシンに接続するときは、**ローカル リソース** タブの**ローカル デバイスとリソース** セクションで、 **プリンター** オプションがオフになっていることを確認します。

### <a name="review-the-event-logs"></a>イベント ログを確認
1. ホスト コンピューターで、イベント ビューアーを開始します。
2. **アプリケーションとサービス ログ** \> **Microsoft** \> **Dynamics** \> **AX-DocumentRouting** でログを確認します。
