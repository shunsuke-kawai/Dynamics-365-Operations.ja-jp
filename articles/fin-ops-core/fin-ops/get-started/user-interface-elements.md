---
title: ユーザー インターフェイスの要素
description: このトピックでは、アプリのユーザー インターフェイス (UI) の要素について説明します。
author: ''
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: ''
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 4b64ed55546a998caf80e7a83cdb7cd3fdde10a3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178780"
---
# <a name="user-interface-elements"></a>ユーザー インターフェイスの要素

このトピックでは、アプリで使用されるユーザー インターフェイス (UI) の要素について説明します。 ユーザーがインターフェイスを操作できるようにするには、インターフェイスを構成する要素の名前と機能を把握しておくことが重要です。

## <a name="overview"></a>概要

- **アクション ウィンドウ** - ナビゲーション バーの下のバー。 ここでタブを選択して、ページに表示されるレコードを変更できます。 ここでレコードを編集、および保存できます。  
- **情報ボックス** - このウィンドウでは情報を表示して、特定のレコードの活動を追跡することができます。  
- **情報ボックス ウィンドウ**では、レコードのさまざまな側面をスクロールして、それを情報ボックスに表示できます。  
- **フィルター ウィンドウ** - 一部のページでは、**フィルターの表示**を選択してこのウィンドウを開くことができます。 ページに表示される結果を絞り込むことができます。  
- **ナビゲーション バー**バー - インターフェイスの上部に表示されるバー。 **Dynamics 365 ポータル**、**検索**、**会社のピッカー**、**アクション センター**、**設定**、**ヘルプとサポート**、およびユーザー プロファイルが含まれます。  
- **ナビゲーション リスト** - 一部のページでは、このウィンドウをスクロールして特定のレコードを探すことができます。 選択すると、レコードの詳細がページに表示されます。  
- **ナビゲーション ウィンドウ** - 左端のウィンドウ。 ここから、製品内のページを検索できます。  
- **ページ** - インターフェイスの中心的な焦点。 他の UI コンポーネントで行われた選択は、ここに表示されるレコードに影響します。  
- **ウィンドウ** - 右端のウィンドウ。 これは、レコードの要素を変更して保存する必要がある場合に表示されます。  
- **タブ** - アクション ウィンドウを参照するときに、アクション ウィンドウで特定のオプションを選択したときに表示されるオプションのメニューです。  

![次の図は、インターフェイス上でのこれらの要素の配置を示しています。](media/user-interface-01.png)

## <a name="tabs-fields-and-sections"></a>タブ、フィールド、およびセクション

*タブ*は、ページ上で行われる選択であり、同じページでレコードの異なる側面を開きます。 多くの場合、特定*のフィールド*または入力を許可する UI 要素を変更できます。 

*クイック タブ*には、複数のタブを同時に表示できるという利点があります。 クイック タブを展開するには、クイックタブの右端にある下向き矢印を選択します。

![次の図は、タブとクイック タブの例を示しています。](media/user-interface-02.png)

*セクション*は、タブに似ています。「セクション」という用語は、特定の情報カテゴリを整理するページ領域を示すためによく使用されます。 次の図の、概要、注文とお気に入り、およびリンクは、すべてセクションの例です。

![次の図は、セクションの例を示しています。](media/user-interface-03.png)

## <a name="dialog-boxes-and-drop-down-menus"></a>ダイアログ ボックスおよびドロップダウン メニュー

*ダイアログ ボックス*は、レコードを変更または作成するために特定の選択が行われたときに開くウィンドウです。 ダイアログ ボックスには、タイプ入力を入力できるフィールドが含まれています。 特定のフィールドでは、選択可能なオプションの一覧を開く下向きの矢印を選択できる場合があります。 これは、*ドロップダウン メニュー*と呼ばれます。 次の図では、**タイプ**と**顧客グループ**のフィールドにドロップダウン メニューを開くためのオプションが含まれています。

![次の図は、ダイアログ ボックスの例を示しています。](media/user-interface-04.png)

場合によっては、選択したボタンの近くにダイアログ ボックスが表示されることがあります。 これは、*ドロップダウン ダイアログ ボックス*と呼ばれます。 次の図では、**現在の日付**ボタンをクリックしてドロップダウン ダイアログ ボックスを開きました。

![次の図は、ドロップダウン ダイアログ ボックスの例を示しています。](media/user-interface-05.png)

## <a name="notifications"></a>通知

監督するオブジェクトへの特定の変更は、*通知*として表示されます。 通知は、特定の顧客の情報が変更されたときに通知したり、特定のフィールドに追加した入力をシステムが受け入れられない場合に警告する場合があります。 [警告の概要](../get-started/alerts-overview.md)で、通知を受け取る内容をカスタマイズする方法を学ぶことができます。

通知は、さまざまな方法で表示されます。
- **機能のコールアウト** - このボタンは、フィールド、タブ、またはその他のボタンの横に表示され、機能の用途を説明します。 
- **アクション センター** - ナビゲーション バーのアクション センター ボタンの横に、通知を含むボックスが表示されます。 通知の詳細を表示するには、**アクション センター**を選択します。  
- **メッセージ バー** - アクション ウィンドウの下に表示されます。  

次の図は、これら通知タイプの例を示しています。

![次の図は、通知の例を示しています。](media/user-interface-06.png)

- **メッセージ ボックス** - これはインターフェイス上に表示され、製品の引き続き使用する前に、連携する必要があります。  

![次の図は、メッセージ ボックスの例を示しています。](media/user-interface-07.png)

## <a name="toolbars-grids-and-lists"></a>ツールバー、グリッド、およびリスト

*ツールバー*には、フィールドの追加や、レコードの削除などのツールが含まれます。 場合によっては、ツールバーが*グリッド*の上のページに表示されます。 この領域 (グリッド) は、データのさまざまな列を含むレコードの行に付けられた名前です。 すべてのグリッドにツールバーがあるわけではありません。

*リスト*は、スクロールして表示できるレコードのコレクションに付けられた名前です。 これらのレコードを選択してページに取り込むことができます。 多くの場合、これによってグリッドが開きます。

![次の図は、ツールバー、グリッド、およびリストの例を示しています。](media/user-interface-08.png)