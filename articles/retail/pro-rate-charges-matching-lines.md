---
title: ヘッダーの諸費用を一致する販売明細行に比例配分する
description: このトピックでは、高度な自動請求機能を使用して、自動請求を小売チャネル注文に計算および適用するための追加の機能について説明します。
author: hhaines
manager: annbe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: d225f1ed3922f72c33e77fc3c488db8d1f2bc8d5
ms.sourcegitcommit: 0bd0215d0735ed47b1b8af93a80bcdbf7ca2cc49
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "790224"
---
# <a name="prorate-header-charges-to-matching-sales-lines"></a>ヘッダーの諸費用を一致する販売明細行に比例配分する

[!include [banner](includes/preview-banner.md)]

[!include [banner](includes/banner.md)]

このトピックでは、ヘッダー レベルの自動請求をグループ化して、小売販売明細行に比例配分する機能について説明します。 この機能は、Microsoft Dynamics 365 for Retail バージョン 10.0.1 の販売時点管理 (POS) で作成されたトランザクションと、Microsoft Dynamics 365 for Retail バージョン 10.0.2 のコール センターで作成された販売で使用できます。

この機能は、[高度な自動請求](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges) 機能が**小売パラメーター**ページのオプションを使用して有効になっている場合にのみ使用できます。 さらに、自動請求の拡張された計算方法は、小売チャネル (POS、コール センター、および Dynamics E コマース プラットフォーム) で作成した小売販売注文にのみ適用できます。

この新しい機能により、ヘッダー レベルの自動請求が計算され小売販売トランザクションに適用されるという点で組織はさらに柔軟になります。

バージョン 10.0.1 よりも前の Microsoft Dynamics 365 for Retail のバージョンでは、特定の荷渡方法リレーションを持つヘッダーレベルの自動請求は、販売注文ヘッダーで定義されている荷渡方法と一致する場合にのみ計算されます。

たとえば、ヘッダー レベルの自動請求は荷渡方法 **99** および荷渡方法 **11** に対して定義されます。 販売注文が作成されると、荷渡方法 **99** は、注文ヘッダーで定義されます。 ただし、一部の販売注文明細行は荷渡方法 **11** を使用して出荷されるように設定されています。 この場合、荷渡方法 **99** に関連付けられているヘッダー レベルの請求金額のみが考慮され、販売注文に適用されます。

Dynamics 365 for Retail のヘッダー レベルの請求金額には、注文金額に基づいた[階層型費用のコンフィギュレーション](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery) を定義することのできる追加の機能があります。 たとえば、注文金額が $50.00 から $200.00 である場合、組織は $5.00 の配送料を請求する場合があります。 しかし、注文金額が $200.01 から $500.00 である場合は、配送料を $4.00 にするかもしれません。

一部の組織は、ヘッダー レベルの請求金額で提供される階層型費用の計算の利点を求めています。 ただし、さまざまな荷渡方法が関係するシナリオの場合、計算される請求金額が各販売明細行で定義されている荷渡方法との一致に基づいていることを確認する必要もあります。

これで、請求金額の計算時に注文のすべての荷渡方法が考慮されるようにヘッダー レベルの自動請求をコンフィギュレーションできます。 この機能には、ヘッダー レベルの請求金額を計算するためのより複雑な計算ロジックが必要です。 ロジックは、同じ荷渡方法を使用して出荷されるすべての品目をグループ化し、ヘッダー レベルの自動請求を計算するときにそのグループを品目の計算グループとして扱います。 同じ荷渡方法がある品目の場合は、自動請求は品目の合計販売値に基づいて計算されます。 この方法で、適切な自動請求層が決定されます。

同じ荷渡方法を使用して出荷された販売明細行に対して適切なヘッダー レベルの請求金額が取得された後、計算された請求金額は販売明細行レベルまで比例配分されます。 これらの請求は明細行レベルであり、ヘッダー レベルでは維持されないため、品目とそれに対して計算された請求金額の値との間に、より具体的なリンクが作成されます。 この動作は、一部の商品のみが返品されたときに、組織が全額ではなく一部の料金のみを返金することを希望する部分返品シナリオで役立ちます。

## <a name="scenarios"></a>シナリオ

次の 2 つのサンプルシナリオでは、新しい機能が使用されている場合と使用されていない場合の両方で、これらの請求金額がどのように計算されるかについての概要を説明しています。

### <a name="scenario-1"></a>シナリオ 1

このシナリオは、自動請求の設定で**一致する販売明細行への比例配分**オプションが**いいえ**に設定されているときの動作についての概要を説明します。 (この動作は、バージョン 10.0.1 より前の小売バージョンでのヘッダー レベルの請求金額の動作に相当します)。

このシナリオでは、組織には、荷渡方法リレーション **99** および荷渡方法リレーション **11** の定義されているヘッダー レベルの請求金額があります。 荷渡方法 **21** には自動請求はコンフィギュレーションされません。

![一致する明細行の比例配分がオフになっているときの荷渡方法 99 の自動請求](media/99_disabled.png)

![一致する明細行の比例配分がオフになっているときの荷渡方法 11 の自動請求](media/11_disabled.png)

コール センターで販売注文が作成されると、荷渡方法は **99** に設定されます。 この注文には、5 つの品目が含まれています。 次のテーブルが示すように、2 つの注文明細行が荷渡方法 **99** を使用するようにコンフィギュレーションされ、2 つの明細行が荷渡方法 **11** を使用するようにコンフィギュレーションされ、1 つの明細行が荷渡方法 **21** を使用するようにコンフィギュレーションされています。

| 項目  | 明細行の数量 | 荷渡方法 | 単位あたりの価格 |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | 10 ドル            |
| 81332 | 1             | 99            | $50            |
| 81333 | 2             | 11            | $30            |
| 81334 | 3             | 99            | 10 ドル            |
| 81334 | 3             | 21            | $5             |

このシナリオでは、注文全体が荷渡方法 **99** の自動請求に対して評価されます。 すべての販売明細行の完全な合計は、自動請求のコンフィギュレーションの一致する階層を決定するために使用され、この請求金額は注文ヘッダー レベルで適用されます。 この例では、注文の合計は $165.00 で、$15.00 の配送料は注文ヘッダーに適用されます。 荷渡方法 **11** にコンフィギュレーションされている自動請求は、参照または適用されることはありません。

このシナリオでは、顧客が注文の一部の品目を返品し、[請求金額コードが払戻されるようにコンフィギュレーションされている](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges#setup-and-configuration-2) 場合、一部の品目のみが返品された場合でも、ヘッダー レベルの合計請求金額が体系的に払戻に適用されます。

### <a name="scenario-2"></a>シナリオ 2

このシナリオでは、ヘッダー レベルの請求金額は荷渡方法リレーション **99** および荷渡方法リレーション **11** に定義されています。 ただし、これらの自動請求テーブルでは**一致する販売明細行への比例配分**オプションが**はい**に設定されています。

![一致する明細行の比例配分がオンになっているときの荷渡方法 99 の自動請求](media/99_enabled.png)

![一致する明細行の比例配分がオンになっているときの荷渡方法 11 の自動請求](media/11_enabled.png)

このシナリオでは、5 つの明細行を含む同じ販売注文を使用します。 注文ヘッダーの荷渡方法は **99** に設定されていますが、販売注文の各品目の荷渡方法は次のテーブルに示すようにコンフィギュレーションされています。

| 項目  | 明細行の数量 | 荷渡方法 | 単位あたりの価格 |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | 10 ドル            |
| 81332 | 1             | 99            | $50            |
| 81333 | 2             | 11            | $30            |
| 81334 | 3             | 99            | 10 ドル            |
| 81334 | 3             | 21            | $5             |

自動請求のコンフィギュレーションは一致する販売明細行に比例配分するように設定されているため、システムは次の計算手順を実行します。

1. 同じ荷渡方法があるすべての品目はグループ化され、システムはグループ内の品目の製品の合計値を計算します。

    **荷渡方法 11**

    - 品目 81331、数量 1 = $10
    - 品目 81333、数量 2 = 正味 $60 (単位あたり $30)
    - **荷渡方法 11 の製品の合計値 = $70**

    **荷渡方法 99**

    - 品目 81332、数量 1 = $50
    - 品目 81334、数量 3 = 正味 $30
    - **荷渡方法 99 の製品の合計値 = $80**

    **荷渡方法 21**

    - 品目 81334、数量 3 = 正味 $15
    - **荷渡方法 21 の製品の合計値 = $15**

2. システムは、品目のグループごとの顧客および荷渡方法に一致するヘッダー レベルの自動請求のコンフィギュレーションを検索します。 コンフィギュレーションが見つかった場合、システムは、荷渡方法グループの品目の製品の合計値に基づいて、適用されるべき請求金額を見つけるために階層型のコンフィギュレーション内を検索します。

    **荷渡方法 11**

    - 小売製品の合計値 = $70
    - **請求金額の値 = $7**

    **荷渡方法 99**

    - 小売製品の合計値 = $80
    - **請求金額の値 = $15**

    **荷渡方法 21**

    - 小売製品の合計値 = $15
    - **請求金額の値 = $0** (この顧客および荷渡方法の組み合わせには、自動請求はコンフィギュレーションされていません)。

    ![荷渡方法 11 の請求金額は強調表示された層に分類される](media/step2mode11.png)

    ![荷渡方法 99 の請求金額は強調表示された層に分類される](media/step2mode99.png)

3. システムは、グループの製品の合計値に対する明細行の比例値を考慮した比例配分ロジックに基づいて、各明細行に適用されるべき請求金額の値を計算します。

    **荷渡方法 11**

    - 請求金額の値 = $7
    - グループ製品の値 = $70
    - 明細行 1 の 値e = $10 (= グループ値の 14.2857 パーセント)
    - 明細行 3 の 値 = $60 (= グループ値の 85.7143 パーセント)
    - **明細行 1 の明細行手数料 = $1**
    - **明細行 3 の明細行手数料 = $6**

    **荷渡方法 99**

    - 請求金額の値 = $15
    - グループ製品の値 = $80
    - 明細行 2 の 値 = $50 (= グループ値の 62.5 パーセント)
    - 明細行 4 の 値 = $30 (= グループ値の 37.5 パーセント)
    - **明細行 2 の明細行手数料 = $9.38**
    - **明細行 4 の明細行手数料 = $5.62**

    **荷渡方法 21**

    - 請求金額の値 = $0
    - グループ製品の値 = $15
    - 明細行 5 の 値 = $15 (= グループ値の 100 パーセント)
    - **明細行 5 の明細行手数料 = $0**

したがって、この例では、品目 81334 には $5.62 の配送料が割り当てられます。 販売明細行の**諸費用の管理**ページでこれらの請求金額を表示できます。 次の図は、品目 81334 に対するこのページの外観を示しています。

![品目 81334 の販売明細行の比例配分された請求金額](media/proratedlinecharge.png)

この計算メソッドが部分返品シナリオで使用される場合、請求金額コードが払戻可能な場合、その明細行に割り当てられた請求金額の一部のみが商品の返品時に返金されます。