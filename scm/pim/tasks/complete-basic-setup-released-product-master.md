--- 
title: "リリース済み製品マスターの基本設定の完了"
description: "この手順は、製品マスターを BOM バージョンで使用する前に必要な最小限の設定の完了方法を示します。"
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 1c7c499b3df92fee5010c731e331e711ea0d1883
ms.contentlocale: ja-jp
ms.lasthandoff: 07/28/2017

---
# <a name="complete-basic-setup-of-a-released-product-master"></a>リリース済み製品マスターの基本設定の完了

[!include[task guide banner](../../includes/task-guide-banner.md)]

この手順は、製品マスターを BOM バージョンで使用する前に必要な最小限の設定の完了方法を示します。

これは、分析コードベースのコンフィギュレーションでの組み合わせの作成方法を説明する 8 つの手順の 3 番目です。 この手順の作成に使用するデモ データの会社は USMF です。

1. [製品情報管理] > [製品] > [リリースされた製品] の順に移動します。
2. 一覧で、目的のレコードを見つけ、選択します。
    * 2 番目の手順でリリースする製品マスターを選択します。 この製品マスターは、分析コード ベースのコンフィギュレーション テクノロジで作成されます。  
3. アクション ウィンドウで、[製品] をクリックします。
4. [分析コード グループ] をクリックすると、ドロップ ダイアログが開きます。
5. [保管分析コード グループ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
6. 一覧で、目的のレコードを見つけ、選択します。
    * 保管分析コード グループにより、製品トランザクションに使用される保管分析コードが決まります。 この手順で [サイト] を選択します。  
7. 一覧で、選択された行のリンクをクリックします。
8. [追跡用分析コード グループ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
9. 一覧で、目的のレコードを見つけ、選択します。
    * 追跡用分析コード グループにより、製品トランザクションに使用される追跡用分析コードが決まります。 この手順で [いいえ] を選択します。  
10. 一覧で、選択された行のリンクをクリックします。
11. [OK] をクリックします。
12. 一覧で、選択された行のリンクをクリックします。
13. [編集] をクリックします。
    * [リリース済製品の詳細] フォームを開き、設定作業を続行します。  
14. [品目モデル グループ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
15. 一覧で、目的のレコードを見つけ、選択します。
    * 品目モデル グループには、品目の入庫および出庫時における品目の管理方法および処理方法を決定する設定が含まれています。 在庫モデル グループは、品目消費の計算方法も決定します。 この手順では [FIFO] を選択します。  
16. 一覧で、選択された行のリンクをクリックします。
17. [原価の管理] セクションを展開または折りたたみます。
18. [品目グループ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
19. 一覧で、目的のレコードを見つけ、選択します。
    * 品目グループは、在庫品目の分類による在庫管理に使用されます。 この手順では [CarAudio] を選択します。  
20. 一覧で、選択された行のリンクをクリックします。
21. アクション ウィンドウで、[計画] をクリックします。
22. [既定の注文設定] をクリックします。
23. [既定の注文タイプ] フィールドで、オプションを選択します。
    * [生産] を選択して、この製品マスターの既定の供給オプションが製品の生産であることを指定します。  
24. ページを閉じます。
25. [リリース製品の詳細] フォームを閉じます。

