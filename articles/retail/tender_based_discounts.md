---
title: 支払/入金ベースの割引
description: このトピックでは、小売業者が特定の支払/入金タイプに対する割引を構成できるようにする機能の概要を示します。
author: bebeale
manager: AnnBe
ms.date: 10/30/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: ed17b43ac16ebcd310716271b84bbbd904a3253a
ms.sourcegitcommit: dc31a0f0d9216aa05be76046ac7410702b20706f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "2692226"
---
# <a name="tender-based-discounts"></a>支払/入金ベースの割引

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

小売業者の間でプライベート ブランドのクレジット カードをリリースすることは一般的なことです。 小売業者は、銀行から優先レートを取得することから利益を得ています。 また、これらのクレジットカードにより顧客はより頻繁に店舗に来るようになるので、小売業者の収益を改善するのに役立ちます。 したがって、小売業者は、自社ブランドのクレジット カードの使用の増加を目指しています。 この目標を達成するために、これらのクレジット カードを使用する顧客に対して追加の割引を提供することが多くあります。

または、ブランドのクレジット カードを提供していない小売業者は、現金、ギフト カード、またはロイヤルティ ポイントなどの、他の支払/入金タイプを使用して支払を行うように顧客に勧めることができます。 このようにして、クレジット カード処理手数料の経費を減らすことができます。 したがって、小売業者はこれらの代替の支払/入金タイプを使用する顧客に対して割引を提供する場合があります。

Microsoft Dynamics 365 Retail では、小売業者は、顧客が優先支払/入金タイプを使用して支払う場合に適格な明細行に適用される割引率を構成することができます。 顧客は一部支払または全額支払を実行するかを決定することができ、Retail によって適切な割引金額が決定されます。 割引は常に適格な明細行の課税前の金額に与えられます。

支払/入金ベースの割引は、期間割引または手動割引などの品目ベースの割引とは競合しません。 常に品目割引に対して組み入れられます。 したがって、排他的期間割引が品目に適用されている場合でも、支払/入金ベースの割引は、さらに排他的期間割引の上に適用されます。 同様に、トランザクションにしきい値割引が適用され、支払/入金ベースの割引により合計金額がしきい値を未満になった場合でも、しきい値割引がトランザクションに適用されます。

支払/入金ベースの割引によりトランザクションの小計が少なくなったとしても、トランザクションに適用される自動請求は影響を受けません。 たとえば、小計が 100 ドルを超えたために配送料が 5 ドルとして計算され、支払/入金ベースの割引により金額が 100 ドル未満になった場合、注文に対する配送料は 5 ドルのままです。


> [!NOTE]
> 支払/入金ベースの割引は、適格とされた販売明細行に比例して配分され、個々の明細行の課税前の金額を減らすことができます。 支払/入金タイプ (たとえば、現金) に対して複数の支払/入金ベースの割引が構成されている場合、最適な支払/入金ベースの割引が適用されます。

支払/入金ベースの割引は、価格がロックされていない販売明細行にのみ適用することができます。 新しい販売明細行が注文に追加された場合、新しい販売明細行に対する支払/入金ベースの割引は支払中にのみ適用されます。 集配または出荷に対する顧客注文が行われている間、支払/入金ベースの割引は前金額に対してのみ適用されます。 フルフィルメント中、注文の実行時には、販売明細行の価格はロックされます。 したがって、支払/入金ベース割引は、集配中に支払われる残高、または出荷中に承認された残高に対しては適用されません。 支払/入金ベース割引は、注文が行われている間、小売業者が金額全体を前金として収集する場合にのみ、顧客注文の金額全体に適用できます。

> [!IMPORTANT]
> Retail では、現在、支払/入金ベースの割引はクレジット カードと現金の 2 つの支払タイプに制限されています。

## <a name="pos-user-experience"></a>POS ユーザー エクスペリエンス

支払/入金ベースの割引が現金に対して設定されており、販売時点 (POS) でレジ担当者が現金で支払う操作にマップされているボタンを選択した場合、支払/入金ベース割引は自動的にトランザクションに適用されます。 次に、減額された金額が残高として表示されます。 ただし、レジ担当者が支払画面の**戻る**ボタンを選択した場合、割引が削除され、トランザクション画面に元の金額が表示されます。 支払明細行が無効になっている場合、支払/入金ベースの割引は削除されます。

カード支払の場合、小売業者は 1 つ以上のクレジット カード タイプに対して支払/入金ベースの割引を設定できます。 ただし、カードが承認されている場合を除き、システムは使用されるクレジット カードのタイプを確認できません。 承認後に割引が適用された場合、支払の承認の対象はより大きな金額になりますが、支払のキャプチャの対象はより少ない金額になります。

このような状況を防止するため、顧客がクレジット カードで支払う場合、顧客に対して追加の割引となるクレジット カードを一覧表示するダイアログ ボックスがレジ担当者に表示されます。 レジ担当者は、追加の割引のある優先カードのいずれかを使用するかどうかを顧客に尋ねることができます。 レジ担当者が優先カードを使用すると、支払/入金ベースの割引がトランザクションに対して適用され、減額された金額が支払画面に表示されます。 承認は減額された金額に対して行われます。 顧客がレジ担当者が選択したカードとは異なるカードを挿入した場合、エラー メッセージが表示され、認証は無効になります。


## <a name="call-center-user-experience"></a>コール センターのユーザー エクスペリエンス

ユーザーがコール センター注文の間**完了**を選択した場合、**合計**画面が表示されます。 最初、支払方法がまだ選択されていないため、この画面の合計に支払/入金ベースの割引は含まれていません。 **支払の追加**画面で、ユーザーが支払/入金ベースの割引が構成されている支払方法を選択した場合、支払金額は自動的に調整され、割引された金額を反映します。 POS の顧客と同様に、コール センターの顧客は、全額支払か一部支払のどちらで支払うかを選択できます。 支払われる金額に基づいて、支払/入金ベースの割引は販売注文に対して適用されます。

> [!NOTE]
> コール センター注文の場合、カードの検証は行われません。 たとえば、コール センター ユーザーがクレジットカードとして Visa を選択し、顧客が Mastercard を使用した場合でも、システムは割引を適用します。

## <a name="exclude-items-from-discounts"></a>割引から品目を除外する

多くの場合、小売業者は、新しい品目や需要品目などの一部の製品を割引から除外する選択をします。 それでも支払/入金ベースの割引を適用したい場合もあります。 たとえば、小売業者が品目ベースの割引や手動割引を許可しないように Retail を構成したとします。 ただし、顧客が優先支払/入金を使用して支払を行う場合、Retail は、支払/入金ベースの割引を適用します。 この方法で Retail を設定するには、小売業者は**製品情報管理 > 製品 > 製品のリリース**の順に進み、品目を選択してから、**小売**クイック タブで**すべての割引を禁止**および**支払/入金ベースの割引を禁止**オプションを**いいえ**に設定し、**小売業者の割引を禁止**および**手動の割引を禁止**オプションを**はい**に設定します。

> [!NOTE]
> **すべての割引を禁止**のコンフィギュレーションが**はい**に設定されている場合、製品に割引は適用されません。 非偶数の支払/入金ベースの割引は適用されません。
