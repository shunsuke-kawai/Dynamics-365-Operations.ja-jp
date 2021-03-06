---
title: Microsoft Dynamics 365 Talent で日付と時刻を操作する
description: Microsoft Dynamics 365 Talent で日付と時刻フィールドを使用する際の予想事項を把握します。 人材、外部ソース、または Common Data Service のフォームで日付と時刻データを操作する際に予想される内容を明確にします。
author: Darinkramer
manager: AnnBe
ms.date: 06/24/2019
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
ms.search.validFrom: 2019-06-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: abd215243cbda68ba3f57b5fa41054a10745d11f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551029"
---
# <a name="work-with-date-and-time-in-microsoft-dynamics-365-talent"></a>Microsoft Dynamics 365 Talent で日付と時刻を操作する

[!include [banner](includes/banner.md)]

**日付と時刻**フィールドは、Dynamics 365 Talent の基本的な概念です。 Dynamics 365 フォーム、Common Data Service、および外部ソースにおいて**日付と時刻**データを操作する方法を理解しておくことが重要です。

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>日付フィールドと日付と時刻フィールドのデータ型の違いを理解する

**日付と時刻**フィールドにはタイム ゾーン情報が含まれますが、**日付**フィールドには含まれません。 **日付**フィールドには、どの場所でも同じ情報が表示されます。 日付を**日付**フィールドに入力すると、Talent によって同じ日付がデータベースに書き込まれます。

**日付と時刻**フィールドにデータを表示する場合、**ユーザー オプション** フォームで設定されたユーザーのタイム ゾーンに基づいて、Talent によって日付と時刻が調整されます (**共通 > 設定 > ユーザー オプション**)。 フィールドに入力した日付と時刻の情報は、データベースに書き込まれた情報とは異なる場合があります。

[![ユーザー オプション フォーム](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>フォームの日付と時刻のフィールドを理解する 

**日付と時刻**フィールドにデータを入力する際、ユーザーのタイム ゾーンが協定世界時 (UTC) に設定されていないと、画面に表示されるデータはデータベースに格納されているデータとは異なります。 **日付と時刻**フィールドのデータは、常に UTC として保存されます。

[![作業者フォーム](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>データベースの日付と時刻のフィールドを理解する 

Talent が**日付と時刻**の値をデータベースに書き込む際、データを UTC で保存します。 これにより、ユーザーは、ユーザー オプションで定義されたタイムゾーンに関連する**日付と時刻**のデータを参照できます。
 
上記の例では、開始時刻は特定の日付ではなく特定時点の時刻です。 ログインしているユーザーのタイム ゾーンを GMT + 12:00 から GMT UTC に変更すると、作成された同じレコードが 05/01/2019 12:00:00 ではなく 04/30/2019 12:00:00 と表示されます。
  
次の例では、従業員 000724 の雇用が、タイム ゾーンに関係なく同時に有効になります。 従業員は GMT タイム ゾーンの 04/30/2019 で有効になり、GMT + 12:00 タイムゾーンの 05/01/2019 と同じになります。 どちらも、特定の日付ではなく、同じ特定時点を参照します。 

[![作業者フォーム](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a>データ管理フレームワーク、Excel、Common Data Service、および Power BI における日付と時刻のデータ 

データ管理フレームワーク、Excel アドイン、Common Data Service、および Power BI レポートは、データベース レベルでデータを直接操作できるように設計されています。 **日付と時刻**のデータをユーザーのタイム ゾーンに調整するクライアントは存在しないため、**日付と時刻**の値はすべて UTC となり、データを入力したり表示したりするときに、誤った推測につながる可能性があります。  
 
DMF、Excel、または Common Data Service を介して送信された**日付と時刻**データは、データベースによって UTC と見なされます。 データを表示するユーザーのユーザー タイム ゾーンが UTC に設定されていないため、送信された**日付と時間**の値が期待どおりに表示されない場合、混乱が生じる可能性があります。 
 
データがエクスポートされると、同じことが逆に発生する可能性があります。 エクスポートされた DMF エンティティの**日付と時刻**データは、Dynamics クライアントに表示されるものと異なる場合があります。 
 
DMF などの外部ソースを使用してデータを表示または作成するため場合、ユーザーのコンピューターのタイム ゾーンや現在のユーザーのタイム ゾーンの設定に関係なく、**日付と時刻**の値は既定で UTC であると見なされる点に注意してください。 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>同じレコードが異なる製品領域に表示されている例 

**UTC に設定されているユーザー タイム ゾーンのある Talent**

[![作業者フォーム](./media/worker-form3.png)](./media/worker-form3.png)

**GMT +12:00 に設定されているユーザー タイム ゾーンのある Talent** 

[![作業者フォーム](./media/worker-form4.png)](./media/worker-form4.png)

**OData を介した Excel**

[![OData を介した Excel](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**DMF ステージング**

[![DMF ステージング](./media/DMFStaging.png)](./media/DMFStaging.png)

**DMF エクスポート**

[![DMF ステージング](./media/DMFexport.png)](./media/DMFexport.png)

**Common Data Service を介した Excel**

[![Common Data Service を介した Excel](./media/ExcelCDS.png)](./media/ExcelCDS.png)

### <a name="see-also"></a>参照

[日付と時刻データ](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[ユーザーの優先タイム ゾーン](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
