---
title: クラウドおよびオンプレミスの機能比較
description: このトピックでは、クラウドとオンプレミスでサポートされる機能を示します。
author: sericks007
manager: AnnBe
ms.date: 10/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: 8fa5ff0de4e97d5dc178581f721f3a6ea72fc974
ms.sourcegitcommit: 70c6257bd6833de3e8de34d9a7561088194e59cc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2019
ms.locfileid: "2573933"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>クラウドとオンプレミスの機能比較

[!include [banner](../includes/banner.md)]

このトピックでは、次のアプリケーションに対するクラウドおよびオンプレミスで利用可能な機能の比較を示します。

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Retail](cloud-prem-comparison.md#dynamics-365-retail)
- [Dynamics 365 Talent](cloud-prem-comparison.md#dynamics-365-talent)

[開発および管理機能](cloud-prem-comparison.md#development-and-administration-features) についての情報も含まれています。

次の表では、アプリケーション領域を一覧表示します。 クラウドおよびオンプレミスのサポートは、全体の機能として一覧表示されます。 特定の機能がエリア全体とは異なる場合、その機能は「機能」列の別の行で表示されます。

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **エリア**             | **機能**                | **クラウド** | **オンプレミス** |
|---------------------|-----------------------------|-----------|-----------------|
| コンプライアンスおよび証明書        |                                                                                           | はい       | はい             |
|                                      | SOC 1 タイプ 1 証明書                                                                | はい       | いいえ              |
| データの管理および統合      |                                                                                           | はい       | はい             |
|                                      | コンフィギュレーション駆動型の拡張機能                                                            | 有       | 無              |
|                                      | 独自のデータ ウェアハウスへのデータのエクスポート                                                    | 有       | 有             |
|                                      | データ エンティティへの差分更新のエクスポート有効化                                 | 有       | 無              |
|                                      | データ統合                                                                         | 有       | 有             |
| ドキュメント管理                  |                                                                                           | 有       | 有             |
| 財務管理                 |                                                                                           | 有       | 有             |
| ヘルプ                                 |                                                                                           | 有       | 無              |
| 人事管理                      |                                                                                           | はい       | はい             |
| インテリジェンス                         |                                                                                           | はい       | はい             |
|                                      | 電子申告 (ER)                                                                 | はい       | はい             |
|                                      | ER: LCS との統合                                                                  | はい       | いいえ              |
|                                      | ER: SharePoint との統合                                                           | はい       | いいえ              |
|                                      | ER: 規制コンフィギュレーション サービス (RCS) との統合                              | はい       | いいえ              |
|                                      | ER: ER リポジトリからアクセス可能な ER コンフィギュレーションの記憶域としてローカル ファイル システムを使用。 | いいえ        | はい             |
|                                      | PowerBI.com との統合                                                              | はい       | いいえ              |
|                                      | PowerBI Desktop との統合                                                          | いいえ        | はい             |
|                                      | 分析ワークスペース                                                                     | はい       | いいえ              |
|                                      | インテリジェントなビジネス プロセス: Recommendations                                             | 有       | 無              |
|                                      | Power BI デスクトップまたは Excel PowerQuery ツールを使い、OData の Power BI レポートの作成    | 有       | 無              |
|                                      | SQL Server Reporting Services (SSRS) は、スケール アウトをサポートします。                                 | はい       | いいえ              |
|                                      | テレメトリがクラウドへ転送されます                                                   | はい       | いいえ              |
| Lifecycle サービス                   |                                                                                           | はい       | はい             |
|                                      | コンフィギュレーション可能な業務プロセス                                                           | はい       | いいえ              |
| ローカライズ                        |                                                                                           | はい       | はい             |
| モバイル アプリ、ワークスペース、およびプラットフォーム |                                                                                           | はい       | はい             |
| Office 統合                   |                                                                                           | 有       | 有             |
| 組織管理          |                                                                                           | はい       | はい             |
| 給与                              |                                                                                           | はい       | はい             |
|                                      | 口座振込                                                                            | はい       | いいえ              |
| プロジェクト管理および会計    |                                                                                           | はい       | はい             |
| セキュリティ                             |                                                                                           | はい       | はい             |
| サービス管理                   |                                                                                           | はい       | はい             |
| Web クライアント                           |                                                                                           | はい       | はい             |
|                                      | タスク レコーダー - BPM ライブラリからのタスク記録の保存または読み込み                         | 有       | 無              |
| サポート                              |                                                                                           | はい       | はい             |
|                                      | [ヘルプとサポート] メニューからのサポートへのアクセス                                             | はい       | いいえ              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **エリア**                | **機能**             | **クラウド** | **オンプレミス** |
|-------------------------|-------------------|-----------|-----------------|
| コンプライアンスおよび証明書        |                                                                                           | 有       | 有             |
|                                      | SOC 1 タイプ 1 証明書                                                                | 有       | 無              |
| 原価計算                      |                                                                                           | 有       | 有             |
|                                      | Power BI 用の原価会計コンテンツ パック                                                 | 有       | 無              |
|                                      | モバイル アプリ用の原価会計ワークスペース                                                  | 有       | 無              |
| 原価管理                      |                                                                                           | 有       | 有             |
|                                      | Power BI 用の原価管理コンテンツ パック                                                 | 有       | 無              |
| データの管理および統合      |                                                                                           | 有       | 有             |
|                                      | コンフィギュレーション駆動型の拡張機能                                                            | 有       | 無              |
|                                      | 独自のデータ ウェアハウスへのデータのエクスポート                                                    | 有       | 有             |
|                                      | データ エンティティへの差分更新のエクスポート有効化                                 | はい       | いいえ              |
|                                      | データ統合                                                                         | はい       | はい             |
| ドキュメント管理                  |                                                                                           | はい       | はい             |
| ヘルプ                                 |                                                                                           | はい       | いいえ              |
| インテリジェンス                         |                                                                                           | はい       | はい             |
|                                      | 電子申告 (ER)                                                                 | はい       | はい             |
|                                      | ER: LCS との統合                                                                  | はい       | いいえ              |
|                                      | ER: SharePoint との統合                                                           | はい       | いいえ              |
|                                      | ER: 規制コンフィギュレーション サービス (RCS) との統合                              | はい       | いいえ              |
|                                      | ER: ER リポジトリからアクセス可能な ER コンフィギュレーションの記憶域としてローカル ファイル システムを使用。 | いいえ        | はい             |
|                                      | PowerBI.com との統合                                                              | はい       | いいえ              |
|                                      | PowerBI Desktop との統合                                                          | いいえ        | はい             |
|                                      | 分析ワークスペース                                                                     | はい       | いいえ              |
|                                      | インテリジェントなビジネス プロセス: Recommendations                                             | 有       | 無              |
|                                      | Power BI デスクトップまたは Excel PowerQuery ツールを使い、OData の Power BI レポートの作成    | 有       | 無              |
|                                      | SQL Server Reporting Services (SSRS) は、スケール アウトをサポートします。                                 | 有       | 無              |
|                                      | テレメトリがクラウドへ転送されます                                                   | 有       | 無              |
| 在庫管理                 |                                                                                           | 有       | 有             |
| Lifecycle サービス                   |                                                                                           | 有       | 有             |
|                                      | コンフィギュレーション可能な業務プロセス                                                           | 有       | 無              |
| ローカライズ                        |                                                                                           | 有       | 有             |
| 製造                        |                                                                                           | 有       | 有             |
| マスター プランおよび予測      |                                                                                           | 有       | 有             |
| モバイル アプリ、ワークスペース、およびプラットフォーム |                                                                                           | 有       | 有             |
| Office 統合                   |                                                                                           | はい       | はい             |
| 組織管理          |                                                                                           | はい       | はい             |
| 調達             |                                                                                           | はい       | はい             |
|                                      | 購買要求から外部カタログへのパンチアウト                                   | 有       | 無              |
|                                      | 購入支出分析 Power BI レポート                                                  | 有       | 無              |
| 製品情報管理       |                                                                                           | 有       | 有             |
| 製品マスター データ                  |                                                                                           | 有       | 有             |
| 生産                           |                                                                                           | 有       | 有             |
|                                      | 生産実績 Power BI レポート                                                   | 有       | 無              |
| プロジェクト管理および会計    |                                                                                           | 有       | 有             |
| 販売注文                                |                                                                                           | 有       | 有             |
|                                      | 販売と収益性のパフォーマンス Power BI レポート                                      | 有       | 無              |
| セキュリティ                             |                                                                                           | 有       | 有             |
| サービス管理                   |                                                                                           | 有       | 有             |
| サプライ チェーン マネジメント              |                                                                                           | 有       | 有             |
| 輸送管理            |                                                                                           | 有       | 有             |
| 仕入先コラボレーション                 |                                                                                           | 有       | 無              |
| 倉庫管理                 |                                                                                           | 有       | 有             |
|                                      | モバイル倉庫アプリ                                                                      | 有       | 有             |
|                                      | 倉庫 Power BI レポート                                                              | 有       | 無              |
| Web クライアント                           |                                                                                           | 有       | 有             |
|                                      | タスク レコーダー - BPM ライブラリからのタスク記録の保存または読み込み                         | 有       | 無              |
| サポート                              |                                                                                           | はい       | はい             |
|                                      | [ヘルプとサポート] メニューからのサポートへのアクセス                                             | はい       | いいえ              |

## <a name="dynamics-365-retail"></a>Dynamics 365 Retail 

オンプレミス展開で利用可能な小売機能の一覧を表示するには、「[オンプレミス展開で利用可能な小売機能](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/PeterRFriis-patch-1/articles/retail/retail-onprem.md)」を参照してください。

## <a name="dynamics-365-talent"></a>Dynamics 365 Talent 

| **エリア**         | **機能**         | **クラウド** | **オンプレミス** |
|------------------|---------------------|-----------|-----------------|
| すべての Talent エリア | すべての Talent 機能 | はい       | いいえ              |

## <a name="development-and-administration-features"></a>開発と管理機能

| **エリア**                   | **機能**                               | **クラウド** | **オンプレミス** |
|----------------------------|-------------------------------------------|-----------|-----------------|
| ビルドとテスト             |                                           | はい       | はい             |
| 拡張性              |                                           | 有       | 有             |
| モニタリングとテレメトリー   |                                           | 有       | 有             |
| プラットフォーム互換性     |                                           | 有       | 有             |
| サービス                  |                                           | 有       | 有             |
|                            | サービス環境                    | 有       | 無              |
| Trace Parser および PerfTimer |                                           | 有       | 無              |
| アップグレード                    |                                           | 有       | 有             |
|                            | アップグレード                                   | 有       | 無              |
|                            | アップグレードおよび以前のバージョンのサポート | はい       | いいえ              |
| Visual Studio 開発  |                                           | はい       | はい             |

