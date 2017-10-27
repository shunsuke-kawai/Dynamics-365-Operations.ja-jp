--- 
title: "入庫済品目を登録するためのモバイル デバイスのメニュー項目の設定"
description: "このタスクでは、モバイル デバイスのメニュー項目の設定を中心に説明します。"
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 7b5d757361c1163bbd0300abd3da4e0a2dd6b0e0
ms.contentlocale: ja-jp
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>入庫済品目を登録するためのモバイル デバイスのメニュー項目の設定

[!include[task guide banner](../../includes/task-guide-banner.md)]

このタスクでは、モバイル デバイスのメニュー項目の設定を中心に説明します。 このメニュー項目は、発注書によって注文された品目の入庫の登録のために使用されます。 

デモ データの会社 USMF でこのガイドを使用できます。 この手順は、倉庫マネージャーを対象としています。


## <a name="create-a-mobile-device-menu-item"></a>品目のモバイル デバイス メニューの作成
1. [倉庫管理] > [設定] > [モバイル デバイス] > [モバイル デバイスのメニュー品目] の順に移動します。
2. [新規] をクリックします。
3. [メニュー項目名] フィールドで、値を入力します。
    * これは、このモバイル デバイスのメニュー項目の固有 ID です。 たとえば、「My PO registration (自分の発注書の登録)」と入力できます。  
4. [タイトル] フィールドに値を入力します。
    * これは、モバイル デバイスのユーザーに表示されるタイトルです。 たとえば、「PO registration (発注書の登録)」と入力できます。  
5. [モード] フィールドで [作業] を選択します。
    * 購買注文明細行に対して受領した手持数量の登録は、入庫エリアから在庫へと品目を移動する作業を作成します。 品目が登録されるまでは作業は作成されません。  そのため、[既存の作業を使用] オプションを [いいえ] に設定したままにします。  
6. [全般] セクションを展開または折りたたみます。
7. [作業の作成プロセス] フィールドで、「発注書品目受取」を選択します。
    * 購買注文明細行は、手持在庫が倉庫で登録される前に一意に識別される必要があります。 このシナリオでは、モバイル デバイスは、発注書の番号および品目番号を登録します。これによりはシステムは購買注文明細行を識別することができます。 プット アウェイ作業が作成され、別の作業者が集荷することができるようになります。    選択した作業の作成方法は、[一般] クイック タブで、どのフィールドが利用可能になるかを決定します。  
    * [既定のデータの使用] オプションを選択すると、[既定のデータ] ボタンが有効になります。 ここで、作業者が毎日の作業で通常必要なデータを表示するようにフィールドを選択できます。これによりそれらの値がモバイル デバイスに表示されます。  
    * ライセンス プレートのグループ化パラメータは、受取中の品目に割り当てられる単位順序グループと組み合わせて機能します。 1 つ以下または 1 つ以上のパレットの受入を 1 枚のライセンス プレートにグループ分けするか、または単位ごとのライセンス プレートに分割するのかを指定できます。  
    * [ライセンス プレートの生成] オプションを選択する場合、番号順序の選択に基づいて固有のライセンス プレート番号が生成されます。   
    * 作業の作成時に使用するテンプレートを選択できます。 たとえば、発注書の品目を登録する場合、プット アウェイ作業が作業テンプレートに基づいて生成されます。 ここで作業テンプレートを選択しないと、システムはテンプレートに関連するクエリ基準に基づいてテンプレートを割り当てます。  
    * 廃棄コードがモバイル デバイスに表示されている場合、作業者は品目の状態や品質を評価し、適切なコードを選択します。 廃棄コードのルールによって、品目を他の倉庫プロセスで使用できるようにするかどうかが決まります。 このルールにより、作成された作業に使用される場所のディレクティブも決定します。   
    * [バッチ廃棄コード] オプションを選択している場合、作業者はバッチの状態や品質を評価して、適切な廃棄コードを選択できます。  バッチ廃棄コードに設定されているルールによって、バッチが他の倉庫プロセスで使用できるかどうかが決まります。  
    * [ラベルの印刷] オプションを選択した場合、ライセンス プレート ラベルは品目の入荷後自動的に印刷されます。  
8. [保存] をクリックします。
9. ページを閉じます。

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>モバイル デバイス メニューへのメニュー項目の追加
1. [倉庫管理] > [設定] > [モバイル デバイス] > [モバイル デバイスのメニュー] の順に移動します。
2. クイック フィルターを使用して、「inbound」の値で [名前] フィールドをフィルターします。
3. [編集] をクリックします。
4. ツリーで、「使用できるメニューと品目のツリーで、以前に作成したメニュー項目を選択する」を選択します。
    * 以前に作成したメニュー項目を選択します。  
5. 右を指している矢印をクリックします。
6. [保存] をクリックします。
7. ページを閉じます。

