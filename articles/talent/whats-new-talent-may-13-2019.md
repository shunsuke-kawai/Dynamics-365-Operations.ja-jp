---
title: Dynamics 365 Talent (2019 年 5 月 13 日) の新機能および変更された機能
description: このトピックでは、Microsoft Dynamics 365 Talent の新機能または変更された機能について説明します。
author: Darinkramer
manager: AnnBe
ms.date: 05/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-05-13
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 42feeb044d0a4cd25faf2d74863aa4e948c200fd
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008823"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-13-2019"></a>Dynamics 365 Talent (2019 年 5 月 13 日) の新機能および変更された機能

[!include [banner](includes/banner.md)]

このトピックでは、Dynamics 365 Talent の新機能または変更された機能について説明します。

## <a name="coming-soon-in-attract"></a>Attract で間もなく公開

### <a name="job-approvals-on-home-page"></a>ホーム ページのジョブ承認

承認は、ダッシュボードの**承認**セクションに表示されます。 承認者は**自分に割り当て済み**で自分の承認を確認できます。ここではジョブ ID、職位、他の承認者、および割り当て日が表示されます。 承認のジョブを送信するユーザーは、**ユーザーにより要求済**で自分のジョブを確認できます。ここでは送信したジョブをまだ承認する必要がある承認者を表示します。

## <a name="changes-in-onboard"></a>Onboard の変更

今回のリリースには、Dynamics 365 Talent: Onboard のマイナーなバグ修正が含まれています。

## <a name="changes-in-core-hr"></a>Core HR の変更

このセクションに記載された変更は、ビルド番号 8.1.2297 に適用されます。 ヘッダーにあるかっこ内の数字は、Microsoft Dynamics Lifecycle Services (LCS) のサポート番号を参照していることがあります。

### <a name="indicate-instance-type-when-provisioning-talent"></a>Talent のプロビジョニング時に、インスタンス タイプを示す

Talent の新しいインスタンスのプロビジョニング時に、インスタンス タイプが**実稼働**か**サンドボックス**であるかを示すことができ、新しい機能を事前にテストできるようになります。 既存の Talent のインスタンスすべては、**実稼働**インスタンス タイプに更新されます。 既存のインスタンスのいずれかを**サンドボックス** インスタンス タイプに更新する場合は、変更要求を開始するよう [サポート](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) に連絡してください。

### <a name="common-data-service-entity-support-for-custom-fields"></a>カスタム フィールドに対する Common Data Service エンティティのサポート

今週のリリースでは、次の Common Data Service エンティティでカスタム フィールドがサポートされるようになりました。雇用、給付金計算頻度、給付金の計算レート、作業カレンダーの休日、および ID タイプです。

### <a name="common-data-service-integration-page"></a>Common Data Service 統合ページ

このリリースは、**システム管理 > リンク > 統合 > Common Data Service コンフィギュレーション**で新しいオプションを提供します。 **Common Data Service コンフィギュレーション** オプションを使用すると、管理者またはデータ管理者は、Common Data Service を使用してある程度の柔軟性と洞察を得ることができます。 このオプションにより、Talent インスタンスとの Common Data Service 統合を有効または無効にでき、Talent インスタンスと Common Data Service 間の同期の詳細を表示できます。

### <a name="import-performance-data-with-final-employee-rating-316710"></a>最終従業員評価 (316710) でパフォーマンス データをインポートします

このリリースでは、過去の従業員評価データをインポートできます。 **FinalEmployeeRatingId** フィールドに書き込み許可が与えられます。

### <a name="cant-create-worker-address-in-common-data-service-and-sync-it-with-talent-317555"></a>作業者の住所を Common Data Service で作成して、Talent と同期することはできません (317555)

この変更により、Common Data Service で作成された住所データと Talent との同期が可能になります。

## <a name="in-preview"></a>プレビュー

### <a name="new-page-to-validate-position-hierarchy-data"></a>職位階層データを検証する新しいページ

人事管理 (HR) および管理者は、誤ってインポートされた循環参照に対して、管理階層を検証できます。 この新しいページは、**組織管理 > リンク > 職位 > 職位階層の検証**からアクセスできます。

### <a name="specify-reason-codes-on-leave-types"></a>休暇タイプの理由コードの指定

組織は、休暇申請に関する追加情報を要求する場合があります。 休暇タイプに理由コードを指定し、従業員は休暇申請で理由コードを選択できるようになりました。

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>休暇申請で固有の休暇タイプについては理由コードが必要

従業員が休暇申請を送信するときに、組織は特定の休暇タイプに理由コードを要求することがあります。 この要件は、会社のポリシーや規制要件が原因であることがあります。 どの休暇タイプに理由コードが必要かを指定できます。また、従業員に休暇申請で休暇タイプに理由コードを指定するように要求できます。

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>HR の休暇および欠勤トランザクション リストを提供します

従業員の休暇を追跡し、どのように計算するかを理解する機能は、HR が従業員の質問に答えるのに役立つだけでなく、従業員に正確な休暇を付与することにも役立ちます。 HR において、トランザクション (交付、見越、調整、および要求) の表示が新しくなり、HR スタッフは休暇残高の背後にある理由を確認することができるようになりました。
