---
title: 原価および日付の管理
description: このトピックでは、資産管理の価および日付の管理について説明します。
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 74e42207e5f3418e6e80b46a1d2634fbd8065126
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652221"
---
# <a name="cost-and-date-control"></a>原価および日付の管理

[!include [banner](../../includes/banner.md)]

 

資産管理では、原価を計算して、資産、機能的な場所、およびワーク オーダーの予算原価と比較した実際の原価の概要を取得できます。 実際原価は、転記されたトランザクションに基づいています。 

またスケジュールされた開始日と終了日を、作業指示書の実際の開始日と終了日と比較する場合に、日付計算を行うこともできます。

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a>資産、機能的な場所、および作業指示書の原価管理

資産、機能的な場所、およびワーク オーダーに対して行われる計算は、ほぼ同一です。 唯一の違いは、資産と機能的な場所に対して、下位資産とサブ場所を計算に含めることもできるという点です。 日付は、登録が記録されたトランザクション日付です。

1. **資産管理** > **照会** > **資産** > **資産原価管理**または**機能的な場所の原価管理**の順に、または**資産管理** > **照会** > **作業指示書** > **作業指示書の原価管理**の順にクリックしてください。

2. **資産原価管理** / **機能的な場所の原価管理** / **作業指示書の原価管理**ダイアログで、計算する時間範囲を選択します。

3. 必要に応じて、計算に含める財務分析コード セットを選択します。

4. 原価がゼロの結果を表示しない場合は、**ゼロをスキップ** トグル ボタンで "はい" を選択します。

5. **レベル** フィールドを使用すると、機能的な場所に関する原価管理明細行の詳細度を指定できます。 

    たとえば、フィールドに数値 "1" を挿入し、複数レベルの機能的な場所の階層がある場合、機能的な場所に対するすべての原価管理明細行が最上位レベルに表示されます。そのため、明細行の時間が下位レベルにある機能的な場所から追加されます。 
    
    **レベル** フィールドに数値 "0" を挿入すると、関連するすべての機能的な場所レベルのすべての原価管理明細行を示す詳細結果が表示されます。

6. 計算に列を含める場合は、**オープン状態の確定済み費用の表示**トグル ボタンで "はい" を選択します。

7. **下位資産を含める**トグルボタンで「はい」を選択し、下位資産に関連する原価を別の明細行として表示します。

8. 検索を制限する場合は、**対象に含めるレコード** クイック タブで特定の資産、機能的な場所、およびワーク オーダーを選択できます。

9. **OK** をクリックして、計算を開始します。

    次の図は、**資産原価管理**ダイアログの例を示します。

    ![資産原価管理ダイアログ ボックス](media/01-controlling-and-reporting.png)

10. **資産原価管理**ページの、**グループ化**ボタンをクリックすると、計算の必要な詳細レベルが表示されます。 選択した**グループ化**ボタンが強調表示されます。 ボタンをクリックして、有効または無効にします。

## <a name="example"></a>例

次のスクリーンショットは、**資産原価管理**の計算結果の例を示します。

- **元の予算**フィールドでは、作業指示書予測からの予算原価が表示されます。 
- **確定済費用**フォールドでは、法人が支払を確定した経費の合計金額が表示されます。 
- **オープン状態の確定済み費用**フィールドでは、注文または入庫したもののまだ支払われていない品目、時間、およびサービスに対する支払の確定が表示されます。 
- すべての消費登録が転記された後、**実際原価**フィールドでは関連する原価が表示されます。

![資産原価管理での計算結果の例](media/02-controlling-and-reporting.png)

原価計算を行う別の方法は、**すべての資産**または**有効な資産**で複数の資産を選択することです。 その後、**一般**タブで**原価管理**ボタンをクリックします。**資産原価管理**ダイアログでは、選択された資産が**対象に含めるレコード**クイック タブの**資産**フィールドに自動的に挿入されます。 **OK** をクリックすると、選択された資産に対する原価計算が表示されます。 同じ手順を、**すべての機能的な場所**または**有効な機能的な場所**の機能的な場所、および**すべてのワーク オーダー**または**有効なワーク オーダー**のワーク オーダーに対して実行できます。


## <a name="work-order-date-control"></a>作業指示書日付管理

このページを使用して、予定された開始日および終了日を、作業指示書にある実際の開始日および終了日と比較した概要を取得します。

1. **資産管理** > **照会** > **作業指示書** > **作業指示書の日付管理**の順にクリックします。

2. **計算** をクリックします。

3. **機能的な場所**フィールドで、機能的な場所を選択します。

4. **開始日**および**終了日**フィールドで、計算を実行する範囲を挿入します。 範囲内の開始予定日のすべての作業指示書が含まれます。

5. **OK**をクリックします。

6. **グループ化**ボタンをクリックすると、計算の必要な詳細レベルが表示されます。 選択した**グループ化**ボタンが強調表示されます。 ボタンをクリックして、有効または無効にします。

## <a name="example"></a>例

次のスクリーンショットは、**作業指示書の日付管理**の計算結果の例を示します。

- **平均開始遅延**フィールドには、実際の開始日と比較した作業指示書での開始予定日との日数の差が表示されます。 たとえば、実際の開始日が開始予定日の 2 日前だった場合、このフィールドに "-2" が表示されます。  
- **平均終了遅延**フィールドには、実際の終了日と比較した作業指示書での終了予定日との日数の差が表示されます。 たとえば、実際の終了日が終了予定日の 3 日後だった場合、このフィールドに "3" が表示されます。  
- **発生回数**フィールドには、作業指示書での開始予定日と実際の開始日、および終了予定日と実際の終了日に関連して誤差が発生した回数が表示されます。

![作業指示書日付管理での計算結果の例](media/03-controlling-and-reporting.png)

