--- 
title: "従業員のけが/病気の情報の管理"
description: "設定情報の一部をここで使用するため、「けがおよび病気の設定」タスク ガイドを最初に完了することをお勧めします。"
author: ShielaSogge
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: e3b7dea463ce154df29844af95789611faae405b
ms.contentlocale: ja-jp
ms.lasthandoff: 07/27/2017

---
# <a name="maintain-employee-injury-and-illness-information"></a>従業員のけが/病気の情報の管理

[!include[task guide banner](../../includes/task-guide-banner.md)]

設定情報の一部をここで使用するため、「けがおよび病気の設定」タスク ガイドを最初に完了することをお勧めします。 



このタスク記録では、傷害または疾病ケースを作成する基本的な手順について説明します。 傷害または疾病の詳細の追跡に加え、ケース ステータスも同様に追跡されます。  ケースは「未処理」ステータスを規定値に設定しています。  ステータスは、フォーム上部のアプリケーション バーの [ケース ステータス] メニュー項目から管理できます。

1. [人事管理] > [作業者] > [けが / 病気] > [けがまたは病気のインシデント] に移動します。
2. [新規] をクリックします。
3. [ケースの説明] フィールドで、値を入力します。
    * 例 : 手首のけが  
4. [作業者] フィールドで値を入力または選択します。
    * 例 : アーメド バーネット  
5. [インシデントの日時] フィールドに日時を入力します。
    * 例 : 1/20/2016 10:00 AM  
6. [けが / 病気のタイプ] フィールドで、値を入力または選択します。
    * 例: 挫傷  
7. [身体部位] フィールドで、値を入力または選択します。
    * 例: 手首  
8. [結果タイプ] フィールドで、値を入力または選択します。
    * 例: 療法  
9. [報告された日時] フィールドに日時を入力します。
    * 報告された日時はインシデントの日時よりも後にする必要があります。  
10. [ケースの報告者] フィールドで、値を入力または選択します。
    * これは従業員またはインシデントの別の証人である場合があります。  例 : アーメド バーネット  
11. [インシデント] セクションを展開します。
12. [インシデントが発生した場所] フィールドに値を入力します。
    * 例 : 倉庫  
13. [作業敷地内] フィールドで [はい] を選択します。
    * 作業構内でインシデントが発生した場合、[はい] を選択します。  
14. [作業開始日時] フィールドに日時を入力します。
    * インシデントの発生する前に、対象の個人が作業を開始した日時を入力します。  
15. [従業員のジョブまたはタスク] フィールドで、値を入力します。
    * インシデント発生時に作業者が実行していたジョブまたはタスクを入力します。  例: 箱の荷積  
16. [インシデントの原因] フィールドに値を入力します。
    * インシデントの原因を入力します。  例: ぬれたフロアで滑った  
17. [重大度] フィールドで、値を入力または選択します。
18. [実行されるアクション] フィールドに値を入力します。
    * 例 : こぼれをすみやかに掃除  
19. [仕事を休む予測日数] に、数値を入力します。
    * 個人が仕事を休む予測日数を入力します。  個人が作業に戻ったら、「離職日数」フィールドで、実際に休んだ日数を更新します。  
20. [けが / 病気のコスト] セクションを展開します。
21. [追加] をクリックします。
22. [日付] フィールドに日付を入力します。
23. [コスト タイプ] フィールドで、値を入力または選択します。
    * 例: [治療] 金額を入力し、請求書または医者の注記などのサポート ドキュメントを費用に添付できます。  
24. [追加] をクリックします。
25. [日付] フィールドに日付を入力します。
26. [コスト タイプ] フィールドで、値を入力または選択します。
    * 例 : [医師]  
27. [けが / 病気の処置] セクションを展開します。
28. [追加] をクリックします。
29. [処置の日付] フィールドに日時を入力します。
30. [処置のタイプ] フィールドで、値を入力または選択します。
    * 例 : [そえ木]  
31. 必要に応じて、救急病院の利用セクションを [はい] に設定します。
32. [処置に関するコメント] フィールドに値を入力します。
    * 例 : そえ木を2週間  
33. [医師名] フィールドで、値を入力します。
    * 例 : 先生 アンダーソン  
34. [処置施設および場所] フィールドに値を入力します。
    * 例 : エルム ストリート 緊急事態  
35. [処置の詳細] フィールドに値を入力します。
    * 例 : x 線で骨折を確認、そえ木を装着  
36. [保存] をクリックします。
    * ケース ステータスはいつでも更新できます。  傷害または疾病が処理中の場合、ケースを処理中に設定します。  インシデントを閉じた後は、コスト、治療、インシデント関連のファイリングのみ追加や削除ができます。  他の情報を変更するには、ケースを再度開きます。  

