--- 
title: "利息の処理"
description: "この手順では、利子計算書の作成、印刷、および転記の方法を示します。"
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 8a53c4deb146d336fdd8ca88a081e6a5af71465a
ms.contentlocale: ja-jp
ms.lasthandoff: 07/27/2017

---
# <a name="process-interest"></a>利息の処理

[!include[task guide banner](../../includes/task-guide-banner.md)]

この手順では、利子計算書の作成、印刷、および転記の方法を示します。 このタスクでは、USMF というデモ会社を使用します。


## <a name="set-up-interest-on-the-posting-profile"></a>転記プロファイルの利息を設定します。
1. [貸方転記および取立] > [設定] > [顧客転記プロファイル] の順に移動します。
2. [編集] をクリックします。
    * ドロップダウン リストから利息コードを選択します。 この転記プロファイルを使用してトランザクションの利息を計算したくない場合、フィールドを空白のままにします。  
    * テーブル制限タブで利息の処理方法を変更することができます。 このフィールドが [はい] に設定されている場合、利息はこの転記プロファイルに対して作成されます。  

## <a name="calculate-interest"></a>利息の計算
1. [貸方転記および取立] > [利息] > [利子計算書の作成] の順に移動します。
    * 利息を計算するためのトランザクション タイプを選択する必要があります。 これらのタイプのすべての未処理トランザクションがこの計算に含まれます。  
    * 利息を選択すると、利子の利息を計算します。 これらのトランザクションを含める前に、利子の利息計算を規定する法令を確認できます。  
    * この日付から「終了日」までの利子が計算されます。 「開始日」を特定しない場合、すべての未転記の利子計算書はキャンセルされ、利息はトランザクションの日付から再度計算されます。  
2. 利子計算書の日付を入力します。
    * 3 つの転記プロファイルのオプションがあります: [口座] – 各利子計算書の顧客 ID に割り当てられた転記プロファイルを使用します。   選択 – [転記プロファイル] フィールドで選択した転記プロファイルを使用します。   [トランザクション]: 利子計算書ごとに利息が計算されるトランザクションから個々の転記プロファイルを使用します。 割り当てられた転記プロファイルのないトランザクションでは、[買掛金勘定パラメータ] フォーム上の [元帳と売上税] エリアで指定された転記プロファイルが使用されます。  
    * [転記プロファイルの使用] を [選択] に変更した場合、転記プロファイルをここで選択します。  
3. [対象に含めるレコード] セクションを展開または折りたたみます。
4. [フィルター] をクリックします。
5. [基準] フィールドに、顧客 ID を入力します。 たとえば、「US-001」と入力します。
6. [OK] をクリックします。
7. [OK] をクリックします。

## <a name="print-interest-notes"></a>利子計算書の印刷
1. [貸方転記および取立] > [利息] > [利子計算書の確認と処理] の順に移動します。
2. [ステータス] フィールドで [作成済] を選択します。
3. [印刷済] フィールドで、「印刷せず」を選択します。
4. [印刷] をクリックします。
5. [対象に含めるレコード] セクションを展開または折りたたみます。
6. [OK] をクリックします。
7. ページを閉じます。

## <a name="post-the-interest-note"></a>利子計算書の転記
1. 転記の準備が整った利子計算書を選択します (ステータスは作成済)。
2. [転記] をクリックします。
3. 利子計算書の転記日付を入力します。
    * 利子計算書ごとに総勘定元帳トランザクションを作成する場合は、「はい」を選択します。     「はい」を選択しない場合、顧客に対するすべての利子計算書の利子が累計され、1 つのトランザクションで総勘定元帳に転記されます。  
4. [対象に含めるレコード] セクションを展開または折りたたみます。
5. [OK] をクリックします。
6. [ステータス] フィールドで [転記済] を選択します。

