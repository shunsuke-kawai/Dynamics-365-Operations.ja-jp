---
title: 会社間データ共有
description: このトピックでは、企業間のデータ共有について説明します。 会社間共有は、Finance and Operations 配置において、参照およびグループ データを会社間で共有するためのメカニズムです。
author: aprilolson
manager: AnnBe
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SysDataSharingConfiguration
audience: IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 89071
ms.assetid: 0bbe7453-624f-4551-a1d0-842484067311
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: Platform update 1
ms.openlocfilehash: e1e4a3f245c226cc040580a80baa8d221728e7ac
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811944"
---
# <a name="cross-company-data-sharing"></a>会社間データ共有

[!include [banner](../includes/banner.md)]

このトピックでは、企業間のデータ共有について説明します。 会社間共有は、Finance and Operations 配置において、参照およびグループ データを会社間で共有するためのメカニズムです。 この機能は、Microsoft Dynamics AX 2012 の仮想会社機能に似ています。

<a name="what-is-this-feature-and-how-does-it-work"></a>これはどういう機能で、どのように動作しますか ?
------------------------------------------

会社間のデータの共有を使用すると、会社間で参照およびグループのデータをレプリケート (共有) できます。 レプリケーションが行われる前にデータの整合性が確認されます。 

会社間のデータ共有の例を次に示します。

-   同じ支払条件と支払日定義が 15 の法人に使用されています。
-   3 つの国/地域の 7 つの法人に、同じ配送条件が適用されています。

会社間のデータの共有には、次の制限があります。

-   会社間でトランザクション データを共有するために使用できません。
-   参照データおよびグループ データだけが共有されます。
-   ジョブごとに合計 100 万レコード未満のレプリケーションをサポートします。 (この合計は、共有レコードの数 × 共有会社の数として計算されます。)
-   子の関係の1 つのレベルだけが公開されます。 データの一貫性を保護するため、別のレベルが必要な場合、レプリケーションは実行されません。

### <a name="policies"></a>ポリシー

データ共有は、データ パッケージに保存された定義済みポリシーによって管理されます。 Microsoft がテスト済みでサポートしているテンプレートは、Microsoft Dynamics Lifecycle Services (LCS) でダウンロード可能なデータ パッケージとして使用できます。 ポリシーでは、データ共有の次の側面を制御できます。

-   複製されるフィールド
-   レプリケーションに参加するエンティティ

> [!IMPORTANT]
> 顧客は、LCS から使用可能な Microsoft データ テンプレートを変更できますが、このシナリオには対応していません。

### <a name="conflict-resolution"></a>競合の解決

検証ポリシーは、共有ポリシーが有効な場合に実行されます。 不整合が検出された場合、システムを実装するユーザーがどの会社のレコードが優先されるかを選択できます。

### <a name="considerations-for-successful-data-sharing"></a>データ共有を成功させるための注意事項

Microsoft データ パッケージの複数のエンティティに、エンティティを有効にするときに考慮する必要があるリファレンスがあります。 参照が一致しない場合、ポリシーを共有する一部のデータを有効にすることはできません。 他のポリシーを有効にすることができますが、不整合検出チェック ツールを使用して、データが一貫していることを確認する必要があります。 次にいくつか例を挙げます。

-   生産グループ共有ポリシーには、会社の勘定科目表への参照があります。 したがって、この共有ポリシーに追加されたすべての企業は、同じ勘定科目表を使用する必要があります。
-   番号シーケンスを使用するエンティティを有効にする場合、番号シーケンス タイプは、それらのエンティティの共有ポリシーにおいて、すべての企業で同じである必要があります。
-   設定オプションは、共有ポリシーに関連する会社間で同じでなければなりません。 設定オプションの例には、税金が既定で含まれるかどうかを指定する設定が含まれます。

## <a name="when-should-i-use-cross-company-data-sharing"></a>会社間のデータ共有をいつ使用すればよいでしょうか ?
次の業務シナリオでは、会社間データ共有を使用します。

-   1 つの配置の単純な参照とグループのデータの共有
-   構成が非常に似ている会社間で共有
-   Microsoft が明示的にテスト済みのシナリオを共有

会社間のデータの共有は、次のシナリオではサポートされていません。

-   多くの会社間で共有される多くのレコードのある、ソリューションのフランチャイズ化。
-   連結など、レポートまたは管理目的のトランザクション レコードの共有
-   配置間で共有
-   サブタイプ/スーパータイプ テーブルまたは日付の有効性ルールを持つテーブルの複製などの複雑なシナリオ
-   マスター データの管理

## <a name="customer-and-vendor-master-data-sharing"></a>顧客および仕入先のマスター データ共有
顧客および仕入先のマスタ データ共有により、複数の会社間で顧客および仕入先のデータを共有することができます。 この機能は、バージョン 8.0 およびそれ以降の顧客が使用できます。 この機能に関してご検討されている場合は、以下のアンケートに記入し、 [データ共有申請](https://aka.ms/MSDYN365FODataSharing)  サポートに問い合わせてください。

> [!NOTE]
> 顧客または仕入先に対する既定の分析コードの設定は、会社間で共有することはできません。 会社間のデータ共有用に顧客または仕入先レコードの構成すると、**DefaultDimension**フィールドが無効になり、データ共有ポリシーに含まれることができません。

> 既定の分析コードには、背景の分析コード データに対する緩い外部キー参照が保持されます。これは、会社固有のデータと非会社固有のデータの両方を参照できます。 各分析コード値に適用される適切なアクションを決定することは本質的に複雑であり、現在の実装からの変更が必要です。これは、パフォーマンスに大幅な影響を与える可能性があります。

## <a name="download-a-cross-company-data-sharing-template-from-lcs"></a>会社間データ 供給テンプレートを LCS からダウンロード
1.  LCS にサインインします。
2.  ホーム ページで、**共有アセット ライブラリ**をクリックします。
3.  **資産タイプ** リストで、**データ パッケージ**をクリックします。
4.  使用可能なデータ パッケージ ファイルのいずれかをクリックしてダウンロードします。

テンプレートの使用方法の詳細については、 [会社間で財務データの共有を構成する](../data-entities/tasks/configure-financial-cross-company-data-sharing.md) を参照してください。

## <a name="currently-supported-cross-company-data-sharing-templates"></a>現時点では、会社間のデータ共有テンプレートがサポートされています
<table>
<thead>
<tr class="header">
<th>LCS でのパッケージ名</th>
<th>データ共有ポリシー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>テンプレートを共有する財務データ</td>
<td><ul>
<li>銀行パラメーター</li>
<li>仕訳元帳の名前</li>
<li>支払期日</li>
<li>支払スケジュール</li>
<li>支払条件</li>
<li>非課税コード</li>
</ul></td>
</tr>
<tr class="even">
<td>サプライ チェーン データ共有テンプレート</td>
<td><ul>
<li>バーコード パラメーター</li>
<li>バーコード設定</li>
<li>購入担当グループ</li>
<li>諸掛グループ</li>
<li>コミッション</li>
<li>出荷先コード</li>
<li>不適合タイプ</li>
<li>注文入力期限グループ</li>
<li>発注元コード</li>
<li>注文管理グループ</li>
<li>生産グループ</li>
<li>生産管理グループ</li>
<li>配送の理由</li>
<li>提供品グループ</li>
<li>配送条件</li>
<li>作業時間カレンダー</li>
</ul></td>
</tr>
</tbody>
</table>


<a name="additional-resources"></a>その他のリソース
--------

[会社間財務データ共有を構成する (タスクガイド)](../data-entities/tasks/configure-financial-cross-company-data-sharing.md)



