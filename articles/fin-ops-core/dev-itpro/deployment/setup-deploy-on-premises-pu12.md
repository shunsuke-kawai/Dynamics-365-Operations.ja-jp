---
title: オンプレミス環境の設定と配置 (Platform update 12 以降)
description: このトピックでは、Dynamics 365 Finance + Operations (オンプレミス) プラットフォーム更新プログラム 12 以降を計画、設定、展開する方法について説明します。
author: sarvanisathish
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sarvanis
ms.search.validFrom: 2017-11-30
ms.dyn365.ops.version: Platform update 12
ms.openlocfilehash: d2326e0381779c0a4ab2261a2f30bc4fae300801
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770935"
---
# <a name="set-up-and-deploy-on-premises-environments-platform-update-12-and-later"></a>オンプレミス環境の設定と配置 (Platform update 12 以降)

[!include [banner](../includes/banner.md)]

このトピックでは、Dynamics 365 Finance + Operations (オンプレミス) プラットフォーム更新プログラム 12 以降を計画、設定、展開する方法について説明します。

> [!IMPORTANT]
> このトピックは、プラットフォーム更新プログラム 12 以降にオンプレミス環境を展開する場合にのみ適用されます。 プラットフォーム更新プログラム 8 および 11 のインストールへの配置方法については、[オンプレミス環境の設定と配置 (プラットフォーム更新プログラム 8 および 11)](setup-deploy-on-premises-pu8-pu11.md)を参照してください。 

[ローカル ビジネス データ Yammer グループ](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=13595809&view=all) が利用可能です。 オンプレミス展開に関する質問またはフィードバックをそこに投稿することができます。

このトピックの内容に関する質問やフィードバックがある場合は、このページ下の**コメント**セクションに転記してください。

## <a name="finance--operations-components"></a>Finance + Operations のコンポーネント

Finance + Operations アプリケーションは、次の 3 つの主要なコンポーネントで構成されています。

- Application Object Server (AOS)
- ビジネス インテリジェンス (BI)
- 財務レポート/管理レポーター

これらのコンポーネントは、次のシステム ソフトウェアによって異なります。

- Microsoft Windows Server 2016 (英語 OS のインストールのみがサポートされます)
- 以下の特徴を有する Microsoft SQL Server2016 SP1:
  - フルテキスト インデックス検索が有効にされている。
  - SQL Server Reporting Services (SSRS) - これは BI 仮想マシンに配置されます。
  - SQL Server Integration Services (SSIS) - これは AOS 仮想マシンに配置されます。

    > [!WARNING]
    > 完全なテキスト検索を有効にする必要があります。

- SQL Server Management Studio
- スタンドアロン Microsoft Azure Service Fabric
- Microsoft Windows PowerShell 5.0 以降
- Windows Server 2016 での Active Directory Federation Services (AD FS)
- ドメイン コントローラー

  > [!WARNING]
  > ドメイン コントローラは、Microsoft Windows Server 2012 R2 またはそれ以降であり、ドメイン機能レベルは 2012 R2 またはそれ以上である必要があります。    ドメイン機能レベルの詳細については、次のトピックを参照してください。
  >   - [Active Directory 機能レベルとは](https://technet.microsoft.com/library/cc787290(v=ws.10).aspx)
  >   - [Active Directory ドメイン サービス機能のレベルを理解する](https://technet.microsoft.com/library/understanding-active-directory-functional-levels(v=ws.10).aspx)

## <a name="lifecycle-services"></a>Lifecycle Services

Finance + Operations のビットは、Microsoft Dynamics Lifecycle Services (LCS) を通じて配布されます。 配置する前に、[エンタープライズ契約](https://www.microsoft.com/Licensing/licensing-programs/enterprise.aspx) チャンネルを通じてライセンス キーを購入し、LCS でオンプレミス プロジェクトを設定します。 LCS からのみ配置を開始することができます。 LCS でオンプレミス プロジェクトを設定する方法の詳細については、[Lifecycle Services (LCS) でのオンプレミス プロジェクトの設定](../lifecycle-services/lbd-create-lcs-on-prem-project.md) を参照してください。

## <a name="authentication"></a>認証

オンプレミス アプリケーションは AD FS で動作します。 LCS と対話するには、Azure Active Directory (AAD) も設定する必要があります。 配置を完了し、LCS ローカル エージェントを構成するには、AAD が必要です。 AAD テナントがまだない場合は、AAD によって提供されるオプションのいずれかを使用して無料のものを取得できます。 詳細については、[Azure Active Directory テナントを取得する方法](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant) を参照してください。

## <a name="standalone-service-fabric"></a>Standalone Service Fabric

Finance + Operations は スタンドアロン Service Fabric を使用します。 詳細については、[Service Fabric ドキュメント](/azure/service-fabric/) を参照してください。

Finance + Operations の設定は、Service Fabric (SF) 内に一連のアプリケーションを配置します。 展開中に、クラスター内の各ノードは、次のいずれかのノード タイプを持つように構成によって定義されます。

- **AOSNodeType** - アプリケーション オブジェクト サーバー (ビジネス ロジック) をホストします。
- **OrchestratorType** - Service Fabric のプライマリ ノードとして機能し、配置およびサービスロジックをホストします。
- **ReportServerType** - SSRS およびレポート ロジックをホストします。
- **MRType** - 管理レポート ロジックをホストします。

## <a name="infrastructure"></a>インフラストラクチャ

Finance + Operations には、非 Microsoft 仮想化プラットフォーム (具体的には VMWare) での操作に関する Microsoft の標準サポート ポリシーが適用されます。 詳細については、[Microsoft ソフトウェアのサポート ポリシー](https://support.microsoft.com/help/897615/support-policy-for-microsoft-software-that-runs-on-non-microsoft-hardw)を参照してください。 つまり、この環境では製品をサポートしますが、問題の調査を依頼された場合、仮想化プラットフォームのない状態または Microsoft 仮想化プラットフォームで問題を再現するようまずお客様に依頼する場合があります。

VMWare を使用している場合は、次の Web ページに記載されている修正プログラムを実装する必要があります。
- [仮想マシンをハードウェア バージョン 11 にアップグレード後、ネットワーク依存ワークロードのパフォーマンスが低下する (2129176)](https://kb.vmware.com/s/article/2129176)
- [vmxnet3 仮想アダプターのいくつかの問題](https://vinfrastructure.it/2016/05/several-issues-vmxnet3-virtual-adapter)

 > [!WARNING]
 > Dynamics 365 Finance + Operations (オンプレミス) は、Azure を含む、任意のパブリック クラウド インフラストラクチャでサポートされていません。

ハードウェア構成には、次のコンポーネントが含まれます。

- Windows Server 2016 仮想マシン (VM) に基づく Standalone Service Fabric Cluster
- Microsoft SQL Server (Clustered SQL と Always-On の両方がサポートされています)
- 認証のための AD FS
- ストレージ用の Server Message Block (SMB) バージョン 3 のファイル共有
- オプション: Microsoft Office Server 2017

詳細については、[オンプレミス展開のシステム要件](../../fin-ops/get-started/system-requirements-on-prem.md) を参照してください。

### <a name="hardware-layout"></a>ハードウェア レイアウト

[オンプレミス環境のハードウェア サイジング要件](../../fin-ops/get-started/hardware-sizing-on-premises-environments.md) で推奨されるサイジングに基づいて、インフラストラクチャと Service Fabric Cluster を計画します。 Service Fabric クラスターを計画する方法の詳細については、[Service Fabric のスタンドアロン クラスター展開の計画と準備](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) を参照してください。

次のテーブルは、ハードウェア レイアウトの例を示しています。 この例は、設定を説明するためにこのトピック全体で使用されています。 次の手順で指定されているマシン名と IP アドレスを、ご使用の環境のマシンの名前と IP アドレスに置き換える必要があります。

> [!NOTE]
> Service Fabric クラスターのプライマリ ノードには、少なくとも 3 つのノードが必要です。 この例では **OrchestratorType** を主要なノード タイプとして指定します。

| マシンの目的          | SF ノード タイプ     | コンピューター名    | IP アドレス    |
|--------------------------|------------------|-----------------|---------------|
| ドメイン コントローラー        |                  | DAX7SQLAODC1    | 10.179.108.2  |
| AD FS                    |                  | DAX7SQLAOADFS1  | 10.179.108.3  |
| ファイル サーバー              |                  | DAX7SQLAOFILE1  | 10.179.108.4  |
| SQL Always-On クラスター    |                  | DAX7SQLAOSQLA01 | 10.179.108.5  |
|                          |                  | DAX7SQLAOSQLA02 | 10.179.108.6  |
|                          |                  | DAX7SQLAOSQLA   | 10.179.108.9  |
| クライアント                   |                  | SQLAOCLIENT1    | 10.179.108.11 |
| AOS 1                    | AOSNodeType      | SQLAOSF1AOS1    | 10.179.108.12 |
| AOS 2                    | AOSNodeType      | SQLAOSF1AOS2    | 10.179.108.13 |
| AOS 3                    | AOSNodeType      | SQLAOSF1AOS3    | 10.179.108.14 |
| オーケストレータ 1           | OrchestratorType | SQLAOSF1ORCH1   | 10.179.108.15 |
| オーケストレータ 2           | OrchestratorType | SQLAOSF1ORCH2   | 10.179.108.16 |
| オーケストレータ 3           | OrchestratorType | SQLAOSF1ORCH3   | 10.179.108.17 |
| Management Reporter ノード | MRType           | SQLAOSMR1       | 10.179.108.18 |
| SSRS ノード                | ReportServerType | SQLAOSFBIN1     | 10.179.108.10 |

## <a name="setup"></a>段取り

### <a name="prerequisites"></a>前提条件

セットアップを開始する前に、次の前提条件が満たされている必要があります。 これらの前提条件の設定は、このドキュメントの範囲外です。

- Active Directory Domain Services (AD DS) は、ネットワークにインストールして構成する必要があります。
- AD FS は、展開する必要があります。
- SQL Server 2016 SP1 は SSRS コンピューターにインストールされている必要があります。
- SQL Server Reporting Services 2016 は、SSRS コンピューターに**ネイティブ** モードでインストールする必要があります。

次の必須ソフトウェアは、LCS からダウンロードされたインフラストラクチャ セットアップ スクリプトによって VM にインストールされます。

| ノード タイプ | コンポーネント | 詳細情報 |
|-----------|-----------|---------|
| AOS       | SNAC – ODBC ドライバー 13 | <https://www.microsoft.com/download/details.aspx?id=53339> |
| AOS       | SNAC – ODBC ドライバー 17 | このドライバーは、PU15 以上へのアップグレードに必要です。<https://www.microsoft.com/download/details.aspx?id=56567> |
| AOS       | Microsoft .NET Framework version 2.0–3.5 (CLR 2.0) | **Windows の機能:** NET-Framework-Features、NET-Framework-Core、NET-HTTP-Activation、NET-Non-HTTP-Activ |
| AOS       | Microsoft .NET Framework version 4.0–4.6 (CLR 4.0) | **Windows の機能:** NET-Framework-45-Features、NET-Framework-45-Core、NET-Framework-45-ASPNET、NET-WCF-Services45、NET-WCF-TCP-PortSharing45 |
| AOS       | インターネット インフォメーション サービス (IIS) | **Windows の機能:** WAS、WAS-Process-Model、WAS-NET-Environment、WAS-Config-APIs、Web-Server、Web-WebServer、Web-Security、Web-Filtering、Web-App-Dev、Web-Net-Ext、Web-Mgmt-Tools、Web-Mgmt-Console |
| AOS       | SQL Server Management Studio 17.2 | <https://go.microsoft.com/fwlink/?linkid=854085> |
| AOS       | Microsoft Visual Studio 2013 用 Microsoft Visual C++ 再頒布可能パッケージ | <https://support.microsoft.com/help/3179560> |
| AOS       | Microsoft Visual Studio 2017 用 Microsoft Visual C++ 再頒布可能パッケージ | <https://lcs.dynamics.com/V2/SharedAssetLibrary>> モデル > "VC ++ 17 再頒布可能" |
| AOS       | Microsoft Access データベース エンジン 2010 再頒布可能パッケージ | <https://www.microsoft.com/download/details.aspx?id=13255> |
| BI        | .NET Framework version 2.0–3.5 (CLR 2.0) | **Windows の機能:** NET-Framework-Features、NET-Framework-Core、NET-HTTP-Activation、NET-Non-HTTP-Activ |
| BI        | .NET Framework version 4.0–4.6 (CLR 4.0) | **Windows の機能:** NET-Framework-45-Features、NET-Framework-45-Core、NET-Framework-45-ASPNET、NET-WCF-Services45、NET-WCF-TCP-PortSharing45 |
| BI        | SQL Server Management Studio 17.2 | <https://go.microsoft.com/fwlink/?linkid=854085> |
| MR        | .NET Framework version 2.0–3.5 (CLR 2.0) | **Windows の機能:** NET-Framework-Features、NET-Framework-Core、NET-HTTP-Activation、NET-Non-HTTP-Activ |
| MR        | .NET Framework version 4.0–4.6 (CLR 4.0) | **Windows の機能:** NET-Framework-45-Features、NET-Framework-45-Core、NET-Framework-45-ASPNET、NET-WCF-Services45、NET-WCF-TCP-PortSharing45 |
| MR        | Visual Studio 2013 用 Visual C++ 再頒布可能パッケージ | <https://support.microsoft.com/help/3179560> |
| ORCH      | Microsoft .NET Framework version 4.0–4.8 (CLR 4.0) | <https://dotnet.microsoft.com/download/thank-you/net48-offline> |

### <a name="overview"></a>概要

Finance + Operations のインフラストラクチャを設定するには、以下の手順を完了する必要があります。 開始する前にすべての手順を読むと、セットアップを計画しやすくなります。

1. [ドメイン名と DNS ゾーンの計画](#plandomain)
2. [証明書の計画と取得](#plancert)
3. [ユーザーとサービス アカウントの計画](#plansvcacct)
4. [DNS ゾーンの作成と A レコードの追加](#createdns)
5. [VM のドメインへの参加](#joindomain)
6. [LCS からセットアップ スクリプトのダウンロード](#downloadscripts)
7. [コンフィギュレーションの記述](#describeconfig)
8. [証明書の構成](#configurecert)
9. [VM を設定する](#setupvms)
10. [スタンドアロン Service Fabric クラスターの設定](#setupsfcluster)
11. [テナント用 LCS 接続の構成](#configurelcs)
12. [ファイル ストレージの設定](#setupfile)
13. [SQL Server の設定](#setupsql)
14. [データベースを構成する](#configuredb)
15. [資格情報の暗号化](#encryptcred)
16. [資産除去債務 (SSIS) の設定](#setupssis)
17. [資産除去債務 (SSRS) の設定](#setupssrs)
18. [AD FS のコンフィギュレーション](#configureadfs)
19. [コネクタを構成し、オンプレミスのローカル エージェントをインストールする](#configureconnector)
20. [リモート処理が使用されたら、CredSSP を終了処理する](#teardowncredssp)
21. [LCS から Finance + Operations 環境を配置する](#deploy)
22. [Finance + Operations 環境への接続](#connect)

### <a name="plandomain"></a> 1. ドメイン名と DNS ゾーンの計画

AOS のプロダクション インストールには、公的に登録されたドメイン名を使用することをお勧めします。 このようにして、外部アクセスが必要な場合は、ネットワークの外部からインストールにアクセスできます。

たとえば、会社のドメインが contoso.com の場合、Finance + Operations は d365ffo.onprem.contoso.com であり、ホスト名は次のようになります。

- AOS の機械の場合 ax.d365ffo.onprem.contoso.com
- Service Fabric クラスターの場合 sf.d365ffo.onprem.contoso.com

### <a name="plancert"></a> 2. 証明書の計画と取得

Service Fabric クラスターと展開されているすべてのアプリケーションを保護するには、Secure Sockets Layer (SSL) 証明書が必要です。 プロダクションとサンドボックスのワークロードについては、[DigiCert](https://www.digicert.com/ssl-certificate/)、[Comodo](https://ssl.comodo.com/)、[Symantec](https://www.websecurity.symantec.com/ssl-certificate)、[GoDaddy](https://www.godaddy.com/web-security/ssl-certificate)、または [GlobalSign](https://www.globalsign.com/en/ssl/) などの認証局から証明書を取得することをお勧めします。 ドメインが [Active Directory 証明書サービス](https://technet.microsoft.com/library/cc772393(v=ws.10).aspx) (AD CS) で設定されている場合は、AD CS を介して証明書を作成します。 証明書ごとに、プライベート キーが作成されたキーの交換を含める必要があり、個人情報交換 (.pfx) ファイルにエクスポート可能な必要があります。

自己署名証明書は、テスト目的でのみ使用できます。 便宜上、LCS で提供されるセットアップ スクリプトには、自己署名証明書を生成およびエクスポートするスクリプトが含まれます。 自己署名スクリプトを使用している場合は、後の手順で作成スクリプトを実行するように指示されます。 先に述べたように、これらの証明書はテスト目的でのみ使用できます。

証明書の推奨設定は次のとおりです:
- 署名アルゴリズム: sha256RSA
- 署名ハッシュ アルゴリズム: sha256
- 公開キー: RSA (2048 ビット)
- Thumbprint アルゴリズム: sha1

| 目的                                      | 説明 | 追加条件 |
|----------------------------------------------|-------------|-------------------------|
| SQL Server SSL 証明書                   | この証明書は、ネットワーク上の SQL Server インスタンスとクライアント アプリケーションの間で転送されるデータを暗号化するために使用されます。 | <p>証明書の場合、ドメイン名は SQL Server のインスタンスまたはリスナーの完全修飾ドメイン名 (FQDN) と一致する必要があります。 たとえば、SQL のリスナーが DAX7SQLAOSQLA のコンピューターにホストされている場合、証明書の DNS 名は、DAX7SQLAOSQLA.contoso.com です。</p> <p>CN: DAX7SQLAOSQLA.contoso.com <br> DNS 名: DAX7SQLAOSQLA.contoso.com</p> |
| Service Fabric Server 証明書            | <p>この証明書を使用して、Service Fabric ノード間のノードからノードの通信を保護します。</p> <p> この証明書は、クラスターに接続するクライアントに提示されるサーバー証明書としても使用されます。</p> | <p>この証明書には、ドメインの SSL ワイルド カード証明書も使用できます。 たとえば、\*.contoso.com です。 これについて下の表で詳しく説明します。 それ以外の場合は、次の値を使用します:</p> <p>CN: sf.d365ffo.onprem.contoso.com <br> DNS 名: sf.d365ffo.onprem.contoso.com</p> |
| Service Fabric Client 証明書            | この証明書は、クライアントによって Service Fabric クラスターを表示および管理するために使用されます。 | CN: client.d365ffo.onprem.contoso.com <br> DNS 名: client.d365ffo.onprem.contoso.com |
| 証明書の暗号化                     | この証明書は、SQL Server パスワードとユーザー アカウントのパスワードなどの重要な情報を暗号化するために使用されます。 | <p> 証明書は、プロバイダー **Microsoft Enhanced Cryptographic Provider v1.0** を使用して作成する必要があります。 </p><p>証明書キーの使用にはデータ暗号化 (10) が含まれている必要があり、サーバー認証またはクライアント認証は含めないでください。</p><p>詳細については、[Service Fabric アプリケーションでの機密情報の管理](/azure/service-fabric/service-fabric-application-secret-management) を参照してください。</p> <p> CN: axdataenciphermentcert <br> DNS 名: axdataenciphermentcert </p> |
| AOS SSL 証明書                          | <p>この証明書は、AOS Web サイトに接続するクライアントに提示されるサーバー証明書としても使用されます。 また、WCF (Windows Communication Foundation) / SOAP (Simple Object Access Protocol) 証明書を有効にするためにも使用されます。</p> | <p>Service Fabric サーバー証明書として使用するのと同じワイルドカード証明書を使用することができます。 それ以外の場合は、次の値を使用します:</p> <p> CN: ax.d365ffo.onprem.contoso.com <br> DNS 名: ax.d365ffo.onprem.contoso.com </p> |
| セッション認証証明書           | この証明書は、AOS がユーザーのセッション情報を保護するために使用します。 | <p> この証明書は、LCS からの展開時に使用されるファイル共有証明書です。</p> <p> CN: SessionAuthentication <br> DNS 名: SessionAuthentication </p> |
| データの暗号化証明書                  | これらの証明書は、機密情報を暗号化するために AOS によって使用されます。  | <p>これはプロバイダー **Microsoft Enhanced RSA および AES Cryptographic Provider** を使用して作成する必要があります。 </p> <p> CN: DataEncryption <br> DNS 名: DataEncryption </p> |
| データ署名の証明書                     | これらの証明書は、機密情報を暗号化するために AOS によって使用されます。  | <p> これは、データ暗号化証明書とは別のもので、プロバイダー**Microsoft の拡張された RSA および AES 暗号化プロバイダー**を使用して作成する必要があります。 </p> <p> CN: DataSigning <br> DNS 名: DataSigning </p> |
| 財務報告クライアント証明書       | この証明書は、財務報告サービスと AOS 間の通信を保護するのに役立ちます。   この証明書を使用して、財務報告サービスと AOS 間の通信を保護します。 | <p>CN: FinancialReporting <br> DNS 名: FinancialReporting </p>  |
| 報告証明書                        | この証明書を使用して、SSRS と AOS 間の通信を保護します。| <p> **財務報告クライアント証明書を再利用しないでください。** </p> <p> CN: ReportingService <br> DNS 名: ReportingService </p> |
| オンプレミス ローカル エージェント証明書           | <p>この証明書は、オンプレミスと LCS でホストされているローカル エージェント間の通信を保護するのに役立ちます。</p><p>この証明書を使用すると、Azure AD テナントに代わってローカル エージェントが動作し、LCS と通信して配置を編成および監視することができます。</p><p>**注記:** テナントにはオンプレミス ローカル エージェント証明書が 1 つだけ必要です。</p> | <p> CN: OnPremLocalAgent <br> DNS 名: OnPremLocalAgent </p> |

ドメインの SSL ワイルド カード証明書を使用して、Service Fabric サーバー証明書と AOS SSL 証明書を結合できます。

以下は、AOS SSL 証明書と組み合わせた Service Fabric Server 証明書の例です。

#### <a name="subject-name"></a>件名

```
CN = *.d365ffo.onprem.contoso.com
```

#### <a name="subject-alternative-names"></a>件名の代替名

```
DNS Name=ax.d365ffo.onprem.contoso.com
DNS Name=sf.d365ffo.onprem.contoso.com
DNS Name=*.d365ffo.onprem.contoso.com
```

> [!NOTE]
> ワイルド カード証明書は、発行先となるドメインの最初のレベル サブドメインのみをセキュリティ保護できるようにします。

### <a name="plansvcacct"></a> 3. ユーザーとサービス アカウントの計画

Finance + Operations を機能させるために、いくつかのユーザー アカウントまたはサービス アカウントを作成する必要があります。 サービス アカウントの管理グループ (gMSAs)、ドメイン アカウント、および SQL アカウントの組み合わせを作成する必要があります。 次の表は、このトピックで使用されるユーザー アカウント、その目的、および名前の例を示しています。

| ユーザー アカウント                                            | 種類           | 目的 | ユーザー名 |
|---------------------------------------------------------|----------------|---------|-----------|
| 財務レポート アプリケーション サービス アカウント         | gMSA           |         | Contoso\\svc-FRAS$ |
| 財務レポート プロセス サービス アカウント             | gMSA           |         | Contoso\\svc-FRPS$ |
| 財務レポート クリック ワンス デザイナー サービス アカウント | gMSA           |         | Contoso\\svc-FRCO$ |
| AOS サービス アカウント                                     | gMSA           | このユーザーは、将来校正するために作成する必要があります。 今後のリリースでは、AOS を gMSA と連携させる予定です。 このユーザーを設定時に作成することで、gMSA へのシームレスな移行を確実にすることができます。 | Contoso\\svc-AXSF$ |
| AOS サービス アカウント                                     | ドメイン アカウント | AOS は、一般提供 (GA) リリースでこのユーザーを使用します。 | Contoso\\AXServiceUser |
| AOS SQL DB 管理者ユーザー                                   | SQL ユーザー       | Finance + Operations は、このユーザーを使用して SQL\* を認証します。 このユーザーも、今後のリリースで gMSA ユーザーに置き換えられます。 | AXDBAdmin |
| ローカル配置エージェント サービス アカウント                  | gMSA           | このアカウントは、ローカル エージェントによって、さまざまなノードでの展開を調整するために使用されます。 | Contoso\\Svc-LocalAgent$ |

\* SQL 認証の SQL ユーザー名とパスワードは、暗号化されてファイル共有に格納されているため、保護されています。

### <a name="createdns"></a> 4. DNS ゾーンの作成とレコードの追加

DNS は AD DS と統合されており、ネットワーク内のリソースを整理、管理、検索することができます。 次の指示では、AOS ホスト名と Service Fabric クラスターの DNS 前方参照ゾーンと A レコードを作成する手順を示します。 この設定例では、DNS ゾーン名は d365ffo.onprem.contoso.com で、A レコード/ホスト名は次のとおりです。

- AOS の機械の場合 **ax**.d365ffo.onprem.contoso.com
- Service Fabric クラスターの場合 **sf**.d365ffo.onprem.contoso.com

#### <a name="add-a-dns-zone"></a>DNS ゾーンの追加

DNS ゾーンを追加するには、次の手順を実行します。

1. ドメイン コントローラー コンピューターにログインして **スタート** を選択し、**dnsmgmt.msc** と入力して **dnsmgmt (DNS)** アプリケーションを選択することにより DNS マネージャーを起動します。
2. コンソール ツリーでドメイン コントローラー名を右クリックし、**新しいゾーン** \> **次へ** の順に選択します。
3. **プライマリ ゾーン** を選択します。
4. **Active Directory にゾーンを保存 (DNS サーバーが書き込み可能なドメイン コントローラーの場合にのみ使用可能)** のチェック ボックスが選択されたままの状態で、**次へ**を選択します。
5. **このドメイン (Contoso.com) のドメイン コントローラーで実行されているすべての DNS サーバーに対して** を選択し、**次へ** を選択します。
6. **前方参照ゾーン** を選択し、**次へ** を選択します。
7. 設定するゾーン名を入力し、**次へ**をクリックします。 たとえば、**d365ffo.onprem.contoso.com** と入力します。
8. **動的更新を許可しない** を選択し、**次へ** を選択します。
9. **完了** を選択します。

#### <a name="set-up-an-a-record-for-aos"></a>AOS の A レコードを設定する

新しい DNS ゾーンで、**AOSNodeType** タイプの Service Fabric クラスター ノード**ごと**に、**ax.d365ffo.onprem.contoso.com** という名前の 1 つの A レコードを作成します。 他のノード タイプの A レコードは作成しないでください。

1. DNS マネージャーの**前方参照ゾーン**フォルダーで、新しく作成したゾーンを検索します。
2. 新しいゾーンを右クリックして、**新しいホスト** を選択します。
3. Service Fabric ノードの 名前および IP アドレスを入力します。 (たとえば、**ax** を名前として入力し、**10.179.108.12** を IP アドレスとして入力します。) **ホストの追加**を選択します。
4. どのチェック ボックスもオンにしないでください。
5. 各 AOS ノードで手順 1 ～ 4 を繰り返します。

#### <a name="set-up-an-a-record-for-the-orchestrator"></a>Orchestrator の A レコードを設定する

新しい DNS ゾーンで、**OrchestratorType** タイプの Service Fabric クラスター ノード**ごと**に、**sf.d365ffo.onprem.contoso.com** という名前の 1 つの A レコードを作成します。 他のノード タイプの A レコードは作成しないでください。

1. 新しいゾーンを右クリックして、**新しいホスト** を選択します。
2. Service Fabric ノードの 名前および IP アドレスを入力します。 (たとえば、**sf** を名前としてを入力し、**10.179.108.15** を IP アドレスとして入力します。) **ホストの追加**を選択します。
3. どのチェック ボックスもオンにしないでください。
4. 各オーケストレータ ノードを繰り返します。

### <a name="joindomain"></a> 5. VM のドメインへの参加

各 VM をドメインに参加させるには、[コンピューターをドメインに参加させる](https://docs.microsoft.com/windows-server/identity/ad-fs/deployment/join-a-computer-to-a-domain)のドキュメントの手順を完了します。 または、次の Windows PowerShell スクリプトを使用します。

```powershell
$domainName = Read-Host -Prompt 'Specify domain name (ex: contoso.com)'
Add-Computer -DomainName $domainName -Credential (Get-Credential -Message 'Enter domain credential')
```

> [!IMPORTANT]
> ドメインにそれらを結合させた後、VM を再起動する必要があります。

### <a name="downloadscripts"></a> 6. LCS からのセットアップ スクリプトのダウンロード

セットアップ エクスペリエンスを向上させるためのスクリプトをいくつか紹介しています。 LCS からセットアップ スクリプトをダウンロードするには、次の手順に従います。

> [!IMPORTANT]
> スクリプトは、オンプレミス インフラストラクチャと同じドメイン内のコンピューターから実行する必要があります。

1. [LCS](https://lcs.dynamics.com/v2) にサインインします。
2. ダッシュボードで、**共有アセット ライブラリ**タイルを選択します。
3. **モデル**タブの、グリッドで、**Dynamics 365 for Operations オンプレミス - 配置スクリプト**行を選択します。
4. **バージョン** を選択し、スクリプトの zip ファイルの最新版をダウンロードします。
   >[!Note] 
   > プラットフォーム更新プログラム 8 またはプラットフォーム更新プログラム 11 の以前のバージョンが必要な場合は、バージョン 1 をダウンロードします。
5. zip ファイルを右クリックし、**プロパティ** を選択します。 ダイアログ ボックスで、**ブロック解除**チェック ボックスをオンにします。
6. ZIP ファイルをスクリプトの実行に使用するマシンにコピーします。
7. **infrastructure** という名前のフォルダーにファイルを解凍します。

> [!IMPORTANT]
> このフォルダーの ConfigTemplate.xml ファイルにすべての編集を加える必要があります。

### <a name="describeconfig"></a> 7. コンフィギュレーションの記述

インフラストラクチャの設定 スクリプトは、次のコンフィギュレーション ファイルを使用して設定を実行します。
- infrastructure\ConfigTemplate.xml
- infrastructure\D365FO-OP\NodeTopologyDefinition.xml
- infrastructure\D365FO-OP\DatabaseTopologyDefinition.xml

>[!NOTE]
>セットアップ スクリプトが正しく機能するには、環境に基づいてコンフィギュレーション ファイルを更新する必要があります。 これらのファイルは、設定に基づいて適切なコンピューター名、IP アドレス、サービス アカウントおよびドメインで更新してください。

**infrastructure\ConfigTemplate.xml** で説明します。
- アプリケーションが動作するために必要なサービス アカウント
- 通信を保護するために必要な証明書
- データベース コンフィギュレーション
- Service Fabric クラスター構成

    > [!IMPORTANT]
    > Service Fabric クラスタをコンフィギュレーションする際に OrchestratorType の 3 つのフォールト ドメインがあることを確認します。 Service Fabric クラスタをコンフィギュレーションする際、単一のマシンにノードの 1 つのタイプのみが配置されるよう確認します。

各 Service Fabric ノード タイプについて、**infrastructure\D365FO-OP\NodeTopologyDefinition.xml** で説明します。

- 各ノード タイプとアプリケーション、ドメインとサービス アカウント、および証明書間のマッピング。
- UAC を有効にするかどうか。
- Windows の機能とシステム ソフトウェアの前提条件。
- 厳密な名前の検証を有効にするかどうか。
- ファイアウォール ポートのリストを開く必要があります。

各データベースについて、**infrastructure\D365FO-OP\DatabaseTopologyDefinition.xml** で説明します。

- データベース設定。
- ユーザーとロール間のマッピング。

#### <a name="create-gmsa-and-domain-user-accounts"></a>gMSA およびドメイン ユーザー アカウントを作成する

1. **インフラストラクチャ** フォルダーに展開したインフラストラクチャ スクリプトがあるマシンに移動します。
2. **インフラストラクチャ**フォルダーをドメイン コントローラー マシンにコピーします。
3. 管理者特権モードで Windows PowerShell を起動し、ディレクトリを **infrastructure** フォルダーに変更して、次のコマンドを実行します。
    > [!IMPORTANT]
    > 次のスクリプトは、ドメイン ユーザー AxServiceUser を作成しません。 ユーザーが作成する必要があります。

    ```powershell
    Import-Module .\D365FO-OP\D365FO-OP.psd1
    New-D365FOGMSAAccounts -ConfigurationFilePath .\ConfigTemplate.xml
    ```
    


4. AOS サービス アカウントの **Contoso\svc-AXSF$** および **Contoso\AXServiceUser** をすべての AOS マシンのローカル 管理者グループへ追加します。 詳細については、「[ローカル グループへのメンバーの追加](https://technet.microsoft.com/library/cc772524(v=ws.11).aspx)」を参照してください。

5. アカウントまたはマシンを変更する必要がある場合は、元の **インフラストラクチャ** フォルダーの ConfigTemplate.xml ファイルを更新し、このマシンにコピーしてから次のスクリプトを実行します。

    ```powershell
    Update-D365FOGMSAAccounts -ConfigurationFilePath .\ConfigTemplate.xml
    ```

### <a name="configurecert"></a> 8. 証明書のコンフィギュレーション

1. **インフラストラクチャ** フォルダーがあるマシンに移動します。
2. 自己署名証明書を生成する必要がある場合は、次のコマンドを実行します。 スクリプトは証明書を作成し、それらをコンピューターの「CurrentUser\My certificate store」に格納し、XML ファイルのサムプリントを更新します。

    ```powershell
    # Create self-signed certs
    .\New-SelfSignedCertificates.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    証明書を再利用する必要があるため、証明書を生成する必要がない場合は、**generateSelfSignedCert** タグを **false** に設定します。

3. 既に生成されている SSL 証明書を使用している場合は、証明書生成をスキップし、configTemplate.xml ファイルの拇印を更新します。 証明書は CurrentUser\My ストアにインストールする必要があり、その秘密キーはエクスポート可能でなければなりません。

> [!WARNING]
> 存在する場合に特定するのが難しい先頭の印刷不可能な特殊文字のため、証明書マネージャーは拇印をコピーするために使用しないでください。 印刷できない特殊文字がある場合、**X509 証明書が無効です**というエラーが表示されます。 拇印を取得するには、PowerShell コマンドの結果を参照するか、PowerShell で次のコマンドを実行します。
> ```powershell
> dir cert:\CurrentUser\My
> dir cert:\LocalMachine\My
> dir cert:\LocalMachine\Root
> ```

4. 各証明書の **ProtectTo** でユーザーまたはグループのセミコロンで区切られた一覧を指定します。 **ProtectTo** タグで指定された Active Directory ユーザーとグループのみに、スクリプトを使用してエクスポートされる証明書をインポートするアクセス許可があります。 エクスポートした証明書を保護するため、スクリプトによりパスワードがサポートされていません。

5. 証明書を .pfx ファイルにエクスポートします。

    ```powershell
    # Exports Pfx files into a directory VMs\<VMName>, all the certs will be written to infrastructure\Certs folder.
    .\Export-PfxFiles.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

### <a name="setupvms"></a> 9. VM の設定
1. 各 VM で実行する必要があるスクリプトをエクスポートします。

    ```powershell
    # Exports the script files to be execute on each VM into a directory VMs\<VMName>.
    .\Export-Scripts.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

2. 次の Microsoft Windows Installers (MSI) を全ての VM でアクセス可能なファイル共有にダウンロードします。

| コンポーネント | リンクのダウンロード |
|-----------|---------------|
| SNAC – ODBC ドライバー 13 | <https://www.microsoft.com/download/details.aspx?id=53339> |
| SNAC – ODBC ドライバー 17 | <https://www.microsoft.com/download/details.aspx?id=56567> |
| Microsoft SQL ServerManagement Studio 17.5 | <https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms> |
| Microsoft Visual Studio 2013 用 Microsoft Visual C++ 再頒布可能パッケージ | <https://support.microsoft.com/help/3179560> |
| Microsoft Access データベース エンジン 2010 再頒布可能パッケージ | <https://www.microsoft.com/download/details.aspx?id=13255> |

> [!IMPORTANT]
> Microsoft SQL Server Management Studio の設定が、対象となるコンピューターのオペレーティング システムと同じ言語であることを確認します。
> NodeTopologyDefinition.xml で定義されているインストーラー ファイルが指定されていることを確認します。
> msodbcsql.ms SSMS-Setup-*.exe vcredist_x64.exe AccessDatabaseEngine_x64.exe

#### <a name="follow-these-steps-for-each-vm-or-use-remoting-from-a-single-machine"></a>各 VM についてこれらのステップに従うか、または単一のコンピューターからリモート処理を使用します。

> [!NOTE]
> 次のセクションでは、複数の VM での実行が必要です。 このプロセスは、指定されたリモート処理スクリプトを使用して、1 台のマシン (`.\Export-Scripts.ps1` を実行するのと同じマシンなど) から必要なスクリプトを実行するオプションを提供することで、簡単に行うことができます。 利用可能な場合、リモート処理スクリプトは、PowerShell セクションの「`# If Remoting`」コメントの後に宣言されます。 リモート処理スクリプトを使用するときは、セクションの残りのスクリプトを実行する必要はありません。そのような例については、セクションの本文を参照してください。 リモート処理では、[WinRM](https://msdn.microsoft.com/library/aa384426(v=vs.85).aspx) が使用され、特定のケースでは [CredSSP](https://msdn.microsoft.com/library/windows/desktop/bb931352(v=vs.85).aspx) が有効になっている必要があります。 CredSSP の有効化と無効化は、実行ごとにリモート処理モジュールによって処理されます。 資格情報の盗難の形でのセキュリティ リスクをもたらすため、CredSSP が使用されていない場合に有効のままにすることはお勧めしません。 設定が完了した場合、[CredSSP を終了処理する](#teardowncredssp) セクションを参照してください。

1. 各 infrastructure\VMs\<VMName> フォルダーのコンテンツを対応する VM にコピーし (リモート処理スクリプトが使用されている場合は、コンテンツをターゲット VM に自動的にコピーします)、次のスクリプトを管理者として実行します。

    ```powershell
    # Install pre-req software on the VMs.

    # If Remoting, execute
    # .\Configure-PreReqs-AllVMs.ps1 -MSIFilePath <share folder path of the MSIs> -ConfigurationFilePath .\ConfigTemplate.xml

    .\Configure-PreReqs.ps1 -MSIFilePath <path of the MSIs>
    ```

    > [!IMPORTANT]
    > 1. 再起動するように求められるたびにコンピューターを再起動します。 再起動した後、すべての前提条件がインストールされるまで、`.\Configure-PreReqs.ps1` スクリプトを再実行することを確認します。 リモート処理の場合、すべてのマシンがオンラインに戻ったときに AllVM スクリプトを再実行します。
    > 2. リモート処理スクリプトを使用するときに、現在のユーザーが MSI の共有フォルダーにアクセス権を持っている必要があります。
    > 3. リモート処理スクリプトを使用するときに、ユーザーが AOSNoteType、MRType、および ReportServerType タイプのマシンにアクセスしていないことを確認します。 それ以外の場合は、コンピューターにログオンしているユーザーが原因で、リモート処理スクリプトはコンピュータの再起動に失敗します。

2. VM セットアップを完了するため、存在する場合は、次のスクリプトを実行します。

    ```powershell
    # If Remoting, only execute
    # .\Complete-PreReqs-AllVMs.ps1 -ConfigurationFilePath .\ConfigTemplate.xml

    .\Add-GMSAOnVM.ps1
    .\Import-PfxFiles.ps1
    .\Set-CertificateAcls.ps1
    ```

3. 次のスクリプトを実行して VM のセットアップを検証します。

    ```powershell
    # If Remoting, execute
    # .\Test-D365FOConfiguration-AllVMs.ps1 -ConfigurationFilePath .\ConfigTemplate.xml

    .\Test-D365FOConfiguration.ps1 
    ```

> [!IMPORTANT]
> リモート処理を使用していた場合は、設定が完了するとクリーンアップ手順を実行します。 [20. Tear down CredSSP](#teardowncredssp) セクションを参照してください。

### <a name="setupsfcluster"></a> 10. スタンドアロン Service Fabric クラスターの設定

1. [Service Fabric スタンドアロン インストール パッケージ](https://go.microsoft.com/fwlink/?LinkId=730690) を使用中の Service Fabric ノードのいずれかにダウンロードします。 ZIP ファイルをダウンロードした後、 ZIP ファイルを右クリックし**プロパティ**を選択してブロックを解除します。 ダイアログ ボックスで、右下の **ブロック解除** チェック ボックスを選択します。

2. ZIP ファイルを Service Fabric クラスター内のいずれかのノードにコピーし、解凍します。 **インフラストラクチャ**フォルダーが、このフォルダーにアクセスすることを確認します。

3. **インフラストラクチャ** フォルダーに移動し、次のコマンドを実行して Service Fabric Cluster の ClusterConfig.json ファイルを生成します。

    ```powershell
   .\New-SFClusterConfig.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -TemplateConfig <ServiceFabricStandaloneInstallerPath>\ClusterConfig.X509.MultiMachine.json
    ```
4. クラスター コンフィギュレーションへの追加の変更は、環境に基づいて必要な場合があります。 詳細については、[手順 1B: 複数のマシンでクラスターを作成する](/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster)、[X.509 証明書を使用して Windows スタンドアロン クラスターを保護する](/azure/service-fabric/service-fabric-windows-cluster-x509-security)、および[Windows Server で実行されているスタンドアロン クラスターを作成する](/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster) を参照してください。

5. 生成された ClusterConfig.json ファイルを \<ServiceFabricStandaloneInstallerPath\> にコピーします。

6. 上位の権限を使用して Windows PowerShell で \<ServiceFabricStandaloneInstallerPath\> に移動します。 次のコマンドを実行して ClusterConfig をテストします。

    ```powershell
    .\TestConfiguration.ps1 -ClusterConfigFilePath .\clusterConfig.json
    ```

7. テストが成功した場合は、次のコマンドを実行してクラスターを展開します。

    ```powershell
    .\CreateServiceFabricCluster.ps1 -ClusterConfigFilePath .\ClusterConfig.json
    ```

8. クラスターが作成された後は、任意のクライアント マシンで Service Fabric エクスプローラーを開き、インストールを検証します。

    1. まだインストールされていない場合、CurrentUser\\My に Service Fabric クライアント証明書をインストールします。
    2. **IE 設定** \> **互換モード** に移動し、**互換モードでイントラネット サイトを表示する** チェック ボックスをオフにします。
    3. `https://sf.d365ffo.onprem.contoso.com:19080` に移動します。sf.d365ffo.onprem.contoso.com は、ゾーンで指定されている Service Fabric クラスターのホスト名です。 DNS 名前解決が設定されていない場合は、マシンの IP アドレスを使用します。
    4. クライアントの証明書を選択します。 **Service Fabric エクスプローラー** ページが表示されます。
    5. すべてのノードが緑で表示されていることを確認します。
    
    > [!IMPORTANT]
    > クライアント マシンが Windows Server 2016 のようなサーバー コンピューターである場合は、**Service Fabric エクスプローラー**ページにアクセスするときに IE のセキュリティ強化の構成をオフにする必要があります。
    > ウィルス対策ソフトウェアがインストールされている場合は、[Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation#environment-setup) ドキュメントのガイダンスに従って除外を設定してください。

### <a name="configurelcs"></a> 11. テナント用 LCS 接続のコンフィギュレーション

Finance + Operations の展開とサービスは、オンプレミスのローカル エージェントを使用して LCS を通じて調整されます。 LCS から Finance + Operations テナントへの接続を確立するには、Azure AD テナント (たとえば、Contoso.onmicrosoft.com) の代わりに動作するローカル エージェントを可能にする証明書をコンフィギュレーションする必要があります。

証明機関から取得したオンプレミス エージェントの証明書またはスクリプトを使用して生成した自己署名証明書を使用します。

オンプレミス エージェント証明書は、テナントごとに複数のサンドボックス環境および実稼動環境で再利用できます。

グローバル管理者ディレクトリの役割を持つユーザー アカウントだけが、LCS を承認するための証明書を追加できます。 既定では、組織の Microsoft Office 365 にサインアップする担当者が、ディレクトリのグローバル管理者です。

   > [!IMPORTANT]
   > テナントごとに証明書を正確に 1 回構成する必要があります。 すべてのオンプレミス環境では、同じ証明書を使用して LCS に接続できます。
   > Windows Server 2016 などのサーバー コンピューターでこれを実行する場合は、IE セキュリティ強化の構成を一時的にオフに必要があります。 そうしないと、Azure ログイン ウィンドウのコンテンツはブロックされます。

1. Azure PowerShell の最新バージョンをクライアント マシンにダウンロードしてインストールします。 詳細については [Azure PowerShell サービス管理モジュールのインストール](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0) を参照してください。
2. [顧客の Azure ポータル](https://portal.azure.com) にサインインして、グローバル管理者ディレクトリの役割があることを確認します。
3. **インフラストラクチャ**フォルダから次のスクリプトを実行します。
    ```powershell
    Install-Module AzureRM
    Import-Module AzureRM
    .\Add-CertToServicePrincipal.ps1 -CertificateThumbprint <OnPremLocalAgent Certificate Thumbprint>
    ```

### <a name="setupfile"></a> 12.ファイル ストレージの設定

以下の SMB 3.0 ファイル共有を設定する必要があります。

- AOS にアップロードされるユーザー ドキュメントを格納するファイル共有 (たとえば、\\\\DAX7SQLAOFILE1\\aos-storage)。
- デプロイメントを調整するための最新のビルド ファイルと構成ファイルを保存するファイル共有 (たとえば、\\\\DAX7SQLAOFILE1\\agent)。

    > [!WARNING]
    > 共有に入れるファイルの最大パス長を超えないように、このファイル共有パスはできるだけ短くしておいてください。

SMB 3.0 を有効にする方法については、[SMB セキュリティの強化](https://technet.microsoft.com/library/dn551363(v=ws.11).aspx#BKMK_disablesmb1) を参照してください。

> [!IMPORTANT]
> - セキュリティで保護されたダイアレクト ネゴシエーションでは、SMB 2.0 または 3.0 から SMB 1.0 へのダウングレードを検出または防止できません。 したがって、SMB 1.0 サーバーを無効にすることを強くお勧めします。 SMB 1.0 サーバーを無効にすることで、SMB 暗号化のすべての機能を利用できます。
> - 環境内の残りの部分でデータが保護されていることを保証するために、BitLocker ドライブ暗号化をすべてのマシンで有効にする必要があります。 BitLocker を有効にする方法については、[BitLocker: Windows Server 2012 以降で配置する方法](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server) を参照してください。

1. ファイル共有マシンで、次のコマンドを実行します。

    ```powershell
    Install-WindowsFeature -Name FS-FileServer -IncludeAllSubFeature -IncludeManagementTools
    ```

2. \\\\DAX7SQLAOFILE1\\aos-storage ファイル共有を設定するには、これらの手順に従います。

   1. サーバー マネージャーで、**ファイルと保管サービス** \> **共有** を選択します。
   2. **タスク**\>**新しい共有** を選択し、新しい共有を作成します。 共有に **aos-storage** と名前を付けます。
   3. **共有のキャッシュを許可**を選択したままにします。
   4. **データ アクセスを暗号化**を確認してください。
   5. OrchestratorType を除いて、Service Fabric クラスター内のすべてのマシンに対して**変更**許可を与えます。
   6. AOS ドメイン ユーザー (contoso\\AXServiceUser) と gMSA ユーザー (contoso\\svc-AXSF$) に対して、**変更**アクセス許可を付与します。

      >[!NOTE]
      > マシンを追加するために**オブジェクト タイプ**の下の**コンピューター**を、またはサービス アカウントを追加するために**オブジェクト タイプ**下の**サービス アカウント**を有効にする必要がある場合があります。

3. \\\\DAX7SQLAOFILE1\\ エージェント ファイル共有を設定するには、これらの手順に従います。

    1. サーバー マネージャーで、**ファイルと保管サービス** \> **共有** を選択します。
    2. **タスク**\>**新しい共有** を選択し、新しい共有を作成します。 共有に**エージェント**と名前を付けます。
    3. ローカル展開エージェント (contoso\\svc-LocalAgent$) の gMSA ユーザーに対して **フル コントロール** のアクセス許可を与えます。

    ```PowerShell
    # Specify user names
    $AOSDomainUser = 'Contoso\AXServiceUser';
    $LocalDeploymentAgent = 'contoso\svc-LocalAgent$';

    # Specify the path
    $AosStorageFolderPath = 'D:\aos-storage';
    $AgentFolderPath = 'D:\agent';

    # Create new directory
    $AosStorageFolder = New-Item -type directory -path $AosStorageFolderPath;
    $AgentFolder = New-Item -type directory -path $AgentFolderPath;

    # Create new SMB share
    New-SmbShare –Name aos-storage -Path $AosStorageFolderPath -EncryptData $True
    New-SmbShare –Name agent -Path $AgentFolderPath

    # Set ACL for AOS storage folder
    $Acl = Get-Acl $AosStorageFolder.FullName;
    $Ar = New-Object system.security.accesscontrol.filesystemaccessrule($AOSDomainUser,'Modify','Allow');
    $Acl.SetAccessRule($Ar);
    Set-Acl $AosStorageFolder.FullName $Acl;

    # Set ACL for AgentFolder
    $Acl = Get-Acl $AgentFolder.FullName;
    $Ar = New-Object system.security.accesscontrol.filesystemaccessrule($LocalDeploymentAgent,'FullControl','Allow');
    $Acl.SetAccessRule($Ar);
    Set-Acl $AgentFolder.FullName $Acl;
    ```

### <a name="setupsql"></a> 13. SQL Server の設定

1. 高可用性を備えた SQL Server 2016 SP1 をインストールします。 (SQL Server の 1 つのインスタンスで十分なサンドボックス環境に配置している場合を除きます。 高可用性シナリオをテストするため、サンドボックス環境に高可用性の SQL Server をインストールできます。)

    > [!IMPORTANT]
    > [SQL Server および Windows 認証モード](https://docs.microsoft.com/sql/database-engine/configure-windows/change-server-authentication-mode) を有効にする必要があります。

    高可用性を備えた SQL Server を、SAN (ストレージ エリア ネットワーク) を含む SQL クラスターまたは Always-On 構成のいずれかとしてインストールすることができます。 データベース エンジン、SSRS、フルテキスト検索、および管理ツールがインストール済みであることを確認します。

    > [!NOTE]
    > Always-On が [初期データ同期ページの選択 (可用性グループ ウィザードで常に使用する)](/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards) で説明されているとおりに設定され、[セカンダリ データベースを手動で準備する](/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards#PrepareSecondaryDbs) の指示に従っていることを確認します。

2. ドメイン ユーザーとして SQL サービスを実行します。
3. Finance + Operations を構成するために証明機関から SSL 証明書を取得します。 テストの目的で、自己署名証明書を作成して使用することができます。 次の例にあるコンピューター名とドメイン名を置き換える必要があります。

    **クラスター化された SQL インスタンスの自己署名証明書**

    ```powershell
    New-SelfSignedCertificate -CertStoreLocation "cert:\CurrentUser\My" -DnsName "DAX7SQLAOSQLA.contoso.com" -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" -Subject "DAX7SQLAOSQLA.contoso.com"
    ```

    **Always-On SQL インスタンスの自己署名証明書**

    Always-On のテスト証明書を設定する場合は、以下の**リモート**スクリプトを使用できます。これは、**マニュアル**スクリプトおよび手順 **4.**、**5.**、**6.** と同じ方法で実行します。

    ```powershell
    .\Create-SQLTestCert-AllVMs.ps1 -ConfigurationFilePath .\ConfigTemplate.xml `
        -SqlMachineNames DAX7SQLAOSQLA01, DAX7SQLAOSQLA02 `
        -SqlListenerName dax7sqlaosqla
    ```

    テスト証明書の**手動**作成。
    ```powershell
    # https://www.derekseaman.com/2014/11/sql-2014-alwayson-ag-pt-13-ssl.html

    # Manually create certificate for each SQL Node (i.e. 2 nodes = 2 certificates)
    # Run script on each node
    $computerName = $env:COMPUTERNAME.ToLower()
    $domain = $env:USERDNSDOMAIN.ToLower()
    $listenerName = 'dax7sqlaosqla'
    $cert = New-SelfSignedCertificate -Subject "$computerName.$domain" -DnsName "$listenerName.$domain", $listenerName, $computerName -Provider 'Microsoft Enhanced RSA and AES Cryptographic Provider'
    ```

4. SQL サーバーで SSL を構成するには、証明書を使用します。 [Microsoft 管理コンソールを使用して SQL Server のインスタンスに対する SSL 暗号化を有効にする方法](https://support.microsoft.com/help/316898/how-to-enable-ssl-encryption-for-an-instance-of-sql-server-by-using-microsoft-management-console) の手順に従います。
5. SQL クラスターの各ノードに対して、次の手順を実行します。 非アクティブなノードで変更を加えて、変更が行われた後フェール オーバーするようにしてください。

    1. LocalMachine\\My に証明書をインポートします。Always-On を設定していない限り、証明書は既にノードに存在します。
    2. SQL サービスを実行するために使用されるサービス アカウントに証明書のアクセス許可を付与します。 Microsoft 管理コンソール (MMC) で証明書 (**certlm.msc**) を右クリックし、**タスク** \> **秘密キーの管理**を選択します。
    3. 証明書の拇印を HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft SQL Server\\*MSSQL.x*\\MSSQLServer\\SuperSocketNetLib\\Certificate に追加します。 たとえば、SQL Server 2016 SP1: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft SQL Server\\MSSQL13.MSSQLSERVER\\MSSQLServer\\SuperSocketNetLib\\Certificate
        1. スタート メニューから、**regedit** をタイプし、**regedit** を選択してレジストリ エディターを開きます。
        2. 証明書に移動し、**変更**を右クリックしてから、証明書の拇印に値を置き換えます。
    4. Microsoft SQL Server 構成マネージャーで、**ForceEncryption** を**はい**に設定します。
        1. **SQL Server 構成マネージャー**で、**SQL Server ネットワークの構成**を展開し、**サーバーのインスタンスのプロトコル**を右クリックしてから、**プロパティ**を選択します。
        2. **インスタンス名プロパティのプロトコル**ダイアログ ボックスの**証明書**タブで、**証明書**ボックスのドロップダウン メニューから目的の証明書を選択して、**OK** をクリックします。
        3. **フラグ**タブの **ForceEncryption** ボックスで、**はい**を選択してから、**OK** をクリックします。
        4. SQL Server サービスを再起動します。

6. 証明書の公開鍵 (.cer ファイル) をエクスポートし、各 Service Fabric ノードの信頼できるルートにインストールします。

> [!IMPORTANT]
> リモート処理を使用していた場合は、設定が完了するとクリーンアップ手順を実行します。 詳細については、[20. CredSSP を終章処理する](#teardowncredssp) セクションを参照してください。

### <a name="configuredb"></a> 14. データベースのコンフィギュレーション

1. [LCS](https://lcs.dynamics.com/v2) にサインインします。

2. ダッシュボードで、**共有アセット ライブラリ**タイルを選択します。

3. **モデル**タブで、必要なリリースのデモ データを選択し、zip ファイルをダウンロードします。

| リリース | デモ データ |
|-------|------|
| オンプレミスの一般提供 (GA) リリース | Dynamics 365 for Operations オンプレミス - デモ データ |
| オンプレミスのプラットフォーム更新プログラム 2017 年 11 月 11 日リリース | Dynamics 365 for Operations オンプレミス Enterprise Edition - 更新プログラム 11 デモ データ |
| オンプレミスのプラットフォーム更新プログラム 2018 年 3 月 12 日リリース | Dynamics 365 for Operations オンプレミス Enterprise Edition - 更新プログラム 12 デモ データ |

4. zip ファイルには空のデモデータ .bak ファイルが含まれています。 必要に応じて、.bak ファイルを選択します。 たとえば、デモ データが必要な場合は、AxBootstrapDB_Demodata.bak ファイルをダウンロードします。

5. infrastructure\ConfigTempate.xml のデータベース セクションが、次のように正しく構成されているか確認します。
    1. データベース名。
    2. db ファイルとログ設定。 dbの設定は、指定された既定値以上にする必要があります。
    3. LCS 共有アセット ライブラリからダウンロードされるバックアップ ファイルへのパス。 Finance + Operations データベースの既定の名前は AXDB です。

   > [!WARNING]
   > - SQL サービスを実行しているユーザーとスクリプトを実行しているユーザーは、バックアップ ファイルが格納されているフォルダーまたは共有に対して READ アクセス権を持っている必要があります。
   > 
   > - 同じ名前のデータベースが存在する場合は、データベースが再利用されます。

6. **インフラストラクチャ**フォルダーを SQL Server マシンにコピーし、権限を昇格した PowerShell ウィンドウでそのフォルダーに移動します。

#### <a name="configure-the-orchestratordata-database"></a>OrchestratorData データベースのコンフィギュレーション

1. 次のスクリプトを実行します。

   ```powershell
   .\Initialize-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName Orchestrator
   ```

   スクリプトは、次の操作を行います。
  
   - **OrchestratorData** という名前の空のデータベースを作成します。 このデータベースは、オンプレミスのローカル エージェントによって配置を調整するために使用されます。
   - データベースにローカル エージェント gMSA (svc-LocalAgent$) **db\_owner** アクセス許可を与えます。

#### <a name="configure-the-finance--operations-database"></a>Finance + Operations データベースの構成

1. 次のスクリプトを実行します。

   ```powershell
   .\Initialize-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName AOS
   .\Configure-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName AOS
   ```

   **Initialize-Database.ps1** スクリプトは、次の操作を行います。

   1. 指定されたバックアップ ファイルからデータベースを復元します。
   2. SQL 認証が有効になっている新しいユーザーを作成します (axdbadmin)。
   3. AXDB の次の表に基づくデータベース ロールにユーザーをマップします。

      | ユーザー            | 種類    | データベース ロール |
      |-----------------|---------|---------------|
      | svc-AXSF$       | gMSA    | db\_owner     |
      | svc-LocalAgent$ | gMSA    | db\_owner     |
      | svc-FRPS$       | gMSA    | db\_owner     |
      | svc-FRAS$       | gMSA    | db\_owner     |
      | axdbadmin       | SqlUser | db\_owner     |


   4. TempDB の次の表に基づくデータベース ロールにユーザーをマップします。

      | ユーザー            | 種類    | データベース ロール |
      |-----------------|---------|---------------|
      | svc-AXSF$       | gMSA    | db_datareader, db_datawriter, db_ddladmin     |
      | axdbadmin       | SqlUser | db_datareader, db_datawriter, db_ddladmin     |

   **Configure-Database.ps1** スクリプトは、次の操作を行います。

    1. READ_COMMITTED_SNAPSHOT ON を設定
    2. ALLOW_SNAPSHOT_ISOLATION ON を設定
    3. 指定したデータベース ファイルとログの設定を設定
    4. サーバー状態の表示を axdbadmin に付与
    5. サーバー状態の表示を [contoso\svc AXSF$] に付与

2. データベース ユーザーをリセットするには、次のコマンドを実行します。

    ```powershell
    .\Reset-DatabaseUsers.ps1 -DatabaseServer '<FQDN of the SQL server>' -DatabaseName '<AX database name>'
    ```

#### <a name="configure-the-financial-reporting-database"></a>財務レポート データベースのコンフィギュレーション

1. 次のスクリプトを実行します。

   ```powershell
   .\Initialize-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName MR
   ```

   スクリプトは、次の操作を行います。
   1. **FinancialReporting** という名前の空のデータベースを作成します。
   2. 次の表に基づくデータベース ロールにユーザーをマップします。

      | ユーザー            | 種類 | データベース ロール |
      |-----------------|------|---------------|
      | svc-LocalAgent$ | gMSA | db\_owner     |
      | svc-FRPS$       | gMSA | db\_owner     |
      | svc-FRAS$       | gMSA | db\_owner     |

### <a name="encryptcred"></a> 15. 資格情報の暗号化

1. 任意のクライアント マシンで、LocalMachine\\My certificate store に暗号化証明書をインストールします。
2. 現在のユーザーにこの証明書の秘密キーへの読み取りアクセスを許可します。
3. 次のようにして、Credentials.json ファイルを作成します。

    ```json
    {
        "AosPrincipal": {
            "AccountPassword": "<encryptedDomainUserPassword>"
        },
        "AosSqlAuth": {
            "SqlUser": "<encryptedSqlUser>",
            "SqlPwd": "<encryptedSqlPassword>"
        }
    }
    ```

    - **AccountPassword** は、AOS ドメインユーザー (contoso\\axserviceuser) の暗号化されたドメイン ユーザー パスワードです。
    - **SqlUser** は、Finance + Operations データベース (AXDB) にアクセスできる暗号化された SQL ユーザー (axdbadmin) で、**SqlPassword** は暗号化された SQL パスワードです。

4. .json ファイルを SMB ファイル共有、\\\\AX7SQLAOFILE1\\agent\\Credentials\\Credentials.json にコピーします。
5. 暗号化された値で Credentials.json ファイルを更新します。

    ```powershell
    # Service fabric API to encrypt text and copy it to the clipboard.
    Invoke-ServiceFabricEncryptText -Text '<textToEncrypt>' -CertThumbprint '<DataEncipherment Thumbprint>' -CertStore -StoreLocation LocalMachine -StoreName My | Set-Clipboard
    ```
    > [!IMPORTANT]
    > *Invoke-ServiceFabricEncryptText* を起動する前に、[Microsoft Azure Service Fabric SDK](https://docs.microsoft.com/azure/service-fabric/service-fabric-get-started#sdk-installation-only) をインストールする必要があります。
    > Azure Service Fabric SDK をインストールした後で、"Invoke-ServiceFabricEncryptText は認識されないコマンドです" というエラーが発生した場合は、コンピューターを再起動して再試行してください。

### <a name="setupssis"></a> 16. SSIS の設定

データ管理と統合ワークロードを有効にするには、各 AOS 仮想マシンに SSIS をインストールする必要があります。 各 AOS 仮想マシン上で、次の手順を実行します。

1. マシンに SSIS インストールへのアクセス許可があることを確認し、SSIS セットアップ ウィザードを開きます。
2. **機能の選択**ウィンドウの**機能**ウィンドウで、**Integration Services** および **SQL クライアント接続 SDK** のチェック ボックスをオンにします。
3. セットアップを完了し、インストールが正常に完了したことを確認します。

詳細については、[統合サービスのインストール](https://docs.microsoft.com/sql/integration-services/install-windows/install-integration-services) を参照してください。

### <a name="setupssrs"></a> 17. SSRS の設定

1. 開始する前に、このトピックの冒頭に記載されている前提条件がインストールされていることを確認してください。
2. [オンプレミス配置の SQL Server Reporting Services のコンフィギュレーション](../analytics/configure-ssrs-on-premises.md) の手順に従います。
    > [!IMPORTANT]
    > SSRS のインストール時にデータベース エンジンをインストールする必要があります。

### <a name="configureadfs"></a>18. AD FS のコンフィギュレーション

この手順を完了する前に、AD FS を Windows Server 2016 に展開する必要があります。 AD FS を展開する方法については、[Windows Server 2016 配置ガイドおよび 2012 R2 AD FS 配置ガイド](/windows-server/identity/ad-fs/deployment/windows-server-2012-r2-ad-fs-deployment-guide) を参照してください。

Finance + Operations では、AD FS の既定で標準のコンフィギュレーション以外の追加のコンフィギュレーションが必要です。 以下の Windows PowerShell コマンドを、AD FS ロール サービスがインストールされているマシン上で実行する必要があります。 ユーザー アカウントには、AD FS を管理するための十分なアクセス許可が必要です。 たとえば、ユーザーには、ドメイン管理者アカウントが必要です。 複雑な AD FS シナリオでは、ドメイン管理者に問い合わせてください。

1. AD FS 識別子を構成して、AD FS トークン発行者と一致するようにします。

   このコマンドは、Finance + Operations クライアントの**ユーザー** ページ (**システム管理 > ユーザー > ユーザー**) で**ユーザーをインポート** オプションを使用した新しいユーザーの追加に関連しています。

    ```PowerShell
    $adfsProperties = Get-AdfsProperties
    Set-AdfsProperties -Identifier $adfsProperties.IdTokenIssuer
    ```

2. 混在環境用に AD FS を構成していない限り、イントラネット認証接続用に Windows 統合認証 (WIA) を無効にする必要があります。 WIA を AD FS で使用できるように構成する方法の詳細については、[AD FS で Windows 統合認証 (WIA) を使用するようにブラウザを構成する](/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia) を参照してください。

   このコマンドは、Finance + Operations クライアントへのログイン時のフォーム認証の使用に関連しています。 シングル サインオンなど、追加の設定が必要な他のオプションが使用可能な場合があります。

    ```powershell
    Set-AdfsGlobalAuthenticationPolicy -PrimaryIntranetAuthenticationProvider FormsAuthentication, MicrosoftPassportAuthentication
    ```

3. サインインの場合、ユーザーの電子メール アドレスは許容される認証入力でなければなりません。

   このコマンドは、電子メール要求の設定に関連しています。 変換ルールなど、追加の設定が必要な他のオプションが使用可能な場合があります。

    ```powershell
    Add-Type -AssemblyName System.Net
    $fqdn = ([System.Net.Dns]::GetHostEntry('localhost').HostName).ToLower()
    $domainName = $fqdn.Substring($fqdn.IndexOf('.')+1)
    Set-AdfsClaimsProviderTrust -TargetIdentifier 'AD AUTHORITY' -AlternateLoginID mail -LookupForests $domainName
    ```

AD FS が認証を交換するために Finance + Operations を信頼するためには、AD FS アプリケーション グループの下の AD FS にさまざまなアプリケーション エントリを登録する必要があります。 設定プロセスをスピードアップし、エラーを減らすために、次のスクリプトを使用して登録します。 Publish-ADFSApplicationGroup.ps1 スクリプトと D365FO-OP ディレクトリを、AD FS ロール サービスがインストールされているマシンにコピーします。 次に、AD FS を管理するための十分なアクセス許可を持つユーザー アカウントを使用してスクリプトを実行します。 (たとえば、管理者アカウントを使用します。)

スクリプトの使用方法の詳細については、スクリプトに記載されているドキュメントを参照してください。 後の手順の LCS でこの情報が必要となるため、出力に指定されているクライアント ID を書き留めておいてください。 クライアント ID を紛失した場合、AD FS がインストールされているコンピューターにログインし、**サーバー マネージャー** \> **ツール** \> **AD FS の管理** \> **アプリケーション グループ** \> **Microsoft Dynamics 365 for Operations On-premises**を開き、ネイティブ アプリケーションでクライアント ID を見つけます。

```powershell
# Host URL is your DNS record\host name for accessing the AOS
.\Publish-ADFSApplicationGroup.ps1 -HostUrl 'https://ax.d365ffo.onprem.contoso.com'
```

![アプリケーション グループのプロパティ](./media/OPSetup_05_ApplicatioGroupProperties.png)

最後に、**AOSNodeType** タイプの Service Fabric ノード上の AD FS OpenID コンフィギュレーション URL にアクセスできることを確認します。 このチェックを行うには、Web ブラウザーで `https://<adfs-dns-name>/adfs/.well-known/openid-configuration` を開きます。 サイトが安全でないことを示すメッセージが表示された場合は、AD FS SSL 証明書が信頼済ルート証明機関ストアに追加されていません。 このステップについては、「AD FS 展開ガイド」で説明されています。リモーティングを使用している場合は、次のスクリプトを使用して、Service Fabric クラスター内のすべてのノードに証明書をインストールできます。

```powershell
# If remoting, execute
.\Install-ADFSCert-AllVMs.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
```

URL に正常にアクセスすると、AD FS コンフィギュレーションを含む JavaScript Object Notation (JSON) ファイルが返され、AD FS URL が信頼されていることがわかります。

これで、インフラストラクチャの設定を完了しました。 次のセクションでは、[LCS](https://lcs.dynamics.com) にアクセスしてコネクタを設定し、Finance + Operations 環境を配置する方法について説明します。

### <a name="configureconnector"></a> 19. コネクタのコンフィギュレーションと、オンプレミスのローカル エージェントのインストール

1. [LCS](https://lcs.dynamics.com/) にサインインし、オンプレミスの実装プロジェクトを開きます。
2. ハンバーガー メニューで、**プロジェクト設定**を選択します。

    ![プロジェクト設定コマンド](./media/OPSetup_06_ProjectSettings.png)

3. **オンプレミス コネクタ** を選択します。
4. 新しいコネクタを作成するには、**追加** を選択します。 
5. **ホスト インフラストラクチャ設定** タブで、エージェント インストーラーをダウンロードします。

    ![[ホスト インフラストラクチャ設定] タブで、エージェント インストーラー ボタンをダウンロードする](./media/OPSetup_07_DownloadAgentInstaller.png)
    
6. zip ファイルがブロックされていないことを確認します。 ファイルを右クリックし、**プロパティ** を選択します。 ダイアログ ボックスで**ブロック解除**を選択します。
7. **OrchestratorType** タイプの Service Fabric ノードの 1 つでエージェント インストーラーを解凍します。
8. **構成エージェント** タブで、コンフィギュレーションの設定を入力します。 必要な値を取得するには、そのマシンと構成ファイルにアクセスできる任意のマシンで次のスクリプトを実行します。

    ```powershell
    .\Get-AgentConfiguration.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

9. コンフィギュレーションを保存し、**コンフィギュレーションのダウンロード** を選択して、localagent-config.json コンフィギュレーション ファイルをダウンロードします。

    ![[エージェントの設定] タブの [コンフィギュレーションのダウンロード] ボタン](./media/OPSetup_08_DownloadConfigurations.png)

10. localagent-config.json ファイルを、エージェント インストーラー パッケージが配置されているマシンにコピーします。
11. **コマンド プロンプト** ウィンドウで、エージェント インストーラーを含むフォルダーに移動して、次のコマンドを実行します。

    ```powershell
    LocalAgentCLI.exe Install <path of config.json>
    ```

    > [!NOTE]
    > このコマンドを実行するユーザーは、OrchestratorData データベースに対して **db\_owner** のアクセス許可を持っている必要があります。

12. ローカル エージェントが正常にインストールされると、LCS のオンプレミス コネクタに戻るようにします。
13. **設定の検証**タブで、**メッセージ エージェント**を選択して、ローカル エージェントへの LCS 接続をテストします。 接続が正常に確立されると、ページは下図のようになります。

    ![エージェントの検証](./media/ValidateAgent.PNG)

### <a name="teardowncredssp"></a> 20. リモート処理が使用された場合、CredSSP を終了処理する

セットアップ中にリモート処理スクリプトのいずれかが使用された場合は、セットアップ プロセスの中断時または完了時に、次のスクリプトを実行してください。

```powershell
.\Disable-CredSSP-AllVMs.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
```

前のリモート PowerShell ウィンドウが誤って終了し、CredSSP が有効にまったままである場合、スクリプトにより、コンフィギュレーション ファイルで指定されたすべてのコンピューター上で無効にされます。

### <a name="deploy"></a> 21. LCS から Finance + Operations 環境を配置する

1. LCS で、オンプレミス プロジェクトに移動し、**環境** > **サンドボックス**に移動してから**構成**を選択します。 必要な値を取得するには、ADFS および DNS サーバー設定にアクセスする必要があるプライマリ ドメイン コントローラ VM で次のスクリプトを実行します。

    ```powershell
    .\Get-DeploymentSettings.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

2. 新しい展開では、環境のトポロジを選択し、展開を開始するウィザードを完了します。

![配置](./media/Deploy.png)

3. 既存のプラットフォーム更新プログラム 8 またはプラットフォーム更新プログラム 11 を展開する場合: 
    - ローカル エージェントを更新します。 詳細については、[ローカル エージェントの更新](../lifecycle-services/update-local-agent.md) を参照してください。
    - LCS からローカル エージェントを検証します。
    - [環境を再構成して新しいプラットフォームまたはトポロジを採用する](../lifecycle-services/reconfigure-environment.md) の手順を実行している間に、プラットフォーム更新 12 を配置します。
4. LCS は準備フェーズ中に環境の Service Fabric アプリケーション パッケージを組み立てます。 配置を開始するローカル エージェントにメッセージを送信します。 下記のように、**準備中** ステータスが表示されます。

![準備中](./media/Preparing.png)

以下に示すような環境の詳細ページに移動するには、**完全な詳細**をクリックします。

![Details_Preparing](./media/Details_Preparing.png)

5. ローカル エージェントは配置要求を受け取り、配置を開始し、環境の準備ができたら LCS に再度通知します。 表示されているとおりに、配置の開始がしたときに、ステータスは**配置**に変更します。

![配置しています](./media/Deploying.png)

![Details_Deploying](./media/Details_Deploying.png)

展開に失敗した場合、LCS のお客様の環境では、**再設定**ボタンは次のように利用可能になります。 基になる問題を修正し、**再コンフィギュレーション**をクリックして、任意のコンフィギュレーションの変更を更新し、**配置**をクリックして配置を再試行します。

![失敗](./media/Failed.png)

再構成の方法の詳細については、[環境を再構成して、新しいプラットフォームまたはトポロジを採用する](../lifecycle-services/reconfigure-environment.md) のトピックを参照してください。 次の図は、正常な配置を示します。
![配置済み](./media/Deployed.png)

### <a name="connect"></a> 22. Finance + Operations 環境への接続
ブラウザーで、https://[yourD365FOdomain]/namespaces/AXSF に移動し、そこでは yourD365FOdomain がこのトピックの[ドメイン名と DNS ゾーンの計画](#plandomain) セクションで定義したドメイン名です。

## <a name="additional-resources"></a>追加リソース
- [オンプレミス配置への更新プログラムの適用](apply-updates-on-premises.md)
- [オンプレミス環境の再配置](redeploy-on-prem.md)
- [ドキュメント管理のコンフィギュレーション](../../fin-ops/organization-administration/configure-document-management.md)
- [電子申告 (ER) コンフィギュレーションのインポート](../analytics/electronic-reporting-import-ger-configurations.md)
- [オンプレミス配置でのドキュメントの生成、発行、印刷](../analytics/printing-capabilities-on-premises.md)
- [オンプレミス環境でのプロキシのコンフィギュレーション](onprem-reverseproxy.md)
- [Finance and Operations アプリの技術サポートの設定](../lifecycle-services/support-experience.md)
- [クライアントのインターネット接続](../user-interface/client-disconnected.md)

## <a name="known-issues"></a>既知の問題

### <a name="error-key-does-not-exist-when-running-the-new-d365fogmsaaccounts-cmdlet"></a>New-D365FOGMSAAccounts cmdlet を実行した際のエラー、「キーが存在しません」
ドメインでグループ管理サービス アカウント パスワードを初めて作成し生成する場合は、最初に**キー配分サービス KDS ルート キー**を作成する必要があります。 詳細については、[キー配分サービス KDS ルート キーの作成](https://docs.microsoft.com/windows-server/security/group-managed-service-accounts/create-the-key-distribution-services-kds-root-key)を参照してください。

### <a name="error-the-winrm-client-cannot-process-the-request-when-running-the-remoting-script-configure-prereqs-allvms-cmdlet"></a>リモート処理スクリプト Configure-Prereqs-AllVms cmdlet を実行した際のエラー、「WinRM クライアントは要求を処理できません」
Service Fabric Cluster のすべてのマシンでコンピューター ポリシー**新しい資格情報委任を許可**を有効にするには、エラー メッセージの指示に従う必要があります。

### <a name="error-not-process-argument-transformation-on-parameter-test-cannot-convert-value-systemstring-to-type-systemmanagementautomationswitchparameter-when-running-the-config-prereqs-allvms-cmdlet"></a>エラー、「'テスト'パラメータでの引数変換を処理できません」 Config-Prereqs-AllVms cmdlet 実行時、値 "System.String" を、タイプ "System.Management.Automation.SwitchParameter" に変換することはできません
このエラーを回避するには、**インフラストラクチャ** フォルダーにある Config-Prereqs-AllVms.ps1 の 56 行目の「-Test:$Test」を削除します。

### <a name="error-not-process-argument-transformation-on-parameter-test-cannot-convert-value-systemstring-to-type-systemmanagementautomationswitchparameter-when-running-the-complete-prereqs-allvms-cmdlet"></a>エラー、「'テスト'パラメータでの引数変換を処理できません」 Complete-Prereqs-AllVms cmdlet 実行時、値 "System.String" を、タイプ "System.Management.Automation.SwitchParameter" に変換することはできません
このエラーを回避するには、**インフラストラクチャ** フォルダーにある Complete-Prereqs-AllVms.ps1 の 56、61、66 行目の「-Test:$Test」を削除します。

### <a name="error-install-windowsfeature-the-request-to-add-or-remove-features-on-the-specified-server-failed-when-running-configure-prereqs-on-mrtype-and-reportservertyoe-servers"></a>MRType および ReportServerTyoe サーバーで Configure-Prereqs を実行した際のエラー、「Install-WindowsFeature: 指定されたサーバーへの機能の追加または削除の要求に失敗しました」
.NET Framework 3.5 には、MRType および ReportServerType サーバーが必要です。 ただし、既定では .NET Framework 3.5 ソース ファイルは Windows Server 2016 インストールに含まれていません。 このエラーを回避するには、サーバー マネージャーによって新機能を手動で追加するときに**ソース** オプションを使用してインストールし、ソース ファイルを指定します。

### <a name="error-msis7628-scope-names-should-be-a-valid-scope-description-name-in-ad-fs-configuration-when-running-the-publish-adfsapplicationgroup-cmdlet"></a>Publish-ADFSApplicationGroup cmdlet を実行した際のエラー、「MSIS7628: スコープ名は AD FS コンフィギュレーションで有効なスコープ説明でなければなりません」
このエラーは D365FO-OP-ADFSApplicationGroup で必要とされる OpenID スコープ **allatclaims** が原因で表示されます。ただし、一部の Windows Server 2016 インストールでは表示されないことがあります。 このエラーを回避するには、AD FS Management\Service\Scope Descriptions を使用してスコープの説明 **allatclaims** を追加します。

### <a name="error-admin0077-access-control-policy-does-not-exist-permit-everyone-when-running-the-publish-adfsapplicationgroup-cmdlet"></a>Publish-ADFSApplicationGroup cmdletを実行した際のエラー、「ADMIN0077: アクセス制御ポリシーが存在しません: すべてのユーザーを許可」
英語以外のバージョンの Windows Server 2016 と共に AD FS をインストールすると、すべてのユーザーのアクセス許可のアクセス許可ポリシーがローカル言語で作成されます。 AccessControlPolicyName パラメーターを指定することによりコマンドレットを呼び出します: .\Publish-ADFSApplicationGroup.ps1 - HostUrl 'https://ax.d365ffo.onprem.contoso.com' - AccessControlPolicyName '<Permit everyone access control policy in your language>'。 
