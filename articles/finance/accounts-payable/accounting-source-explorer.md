---
title: 会計ソース エクスプローラー
description: この記事は、総勘定元帳の勘定項目の背後にあるソース情報の詳細分析に使用できる会計のソース エクスプローラに関する情報を提供します。
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 904f1f9fb139248205b426aec5a0372f2edb1e59
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178736"
---
# <a name="accounting-source-explorer"></a>会計ソース エクスプローラー

[!include [banner](../includes/banner.md)]

この記事は、総勘定元帳の勘定項目の背後にあるソース情報の詳細分析に使用できる会計のソース エクスプローラに関する情報を提供します。

会計のソース エクスプローラーは、ソース情報を表示する新しいページです。 会計のソース エクスプローラーをスタンドアロンのツールとして、または総勘定元帳の勘定項目の後にある詳細を分析するために使用できます。 たとえば、試算表の残高または伝票トランザクションの最も詳細なソース情報を得るために会計のソース エクスプローラーを使用できます。 これにより、MS Excel へのエクスポート機能を使用して、Microsoft Excel で情報をより詳しく分析できます (たとえば、ピボット テーブルで、またはピボット テーブルのレポートで)。

会計のソース エクスプローラーは、総勘定元帳と同じ勘定科目ごとの合計金額を常に表示します (たとえば、試算表で)。 試算表の場合と同様に、別の列の区分を表示できます。 適切な財務分析コード セットを選択します。 

パラメーターを使用すると、分析の日付範囲を定義できます。 この機能は、試算表の機能に似ています。

元伝票フレームワークを使用するすべてのドキュメントでは、会計のソース エクスプローラーは、勘定配布に基づき、または必要に応じてプロジェクト勘定配布に基づき、追加情報を表示します。 この情報は、金額タイプ、プロジェクト、活動、カテゴリ、および明細行プロパティを含みます。 次に実行できる分析の例を示します。

-   発注書と仕入先請求書の差異、これは各差異が差額などの金額タイプにより表示されるためです。
-   プロジェクト、事業単位、主勘定ごとの支払請求可能な時間および経費に対する支払請求不可能な時間および経費

元伝票参照 ID の概念を使用する元伝票では、会計のソース エクスプローラーは、顧客、仕入先、作業者、製品、数量、単位テキスト、および説明などの詳細を表示します。 次に実行できる分析の例を示します。

-   経費精算書に基づく、事業単位ごとの宿泊費、および会計年度期間のホテルのブランド
-   仕入先、製品、部門ごとの割引

これらのドキュメントでは、会計のソース エクスプローラーから実際の元伝票に移動できます。



