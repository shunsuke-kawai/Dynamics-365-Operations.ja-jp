---
title: アプリケーション クラスのメソッドを呼び出す ER 式の設計
description: このガイドは、ER の式で必要なアプリケーション クラスのメソッドを呼び出すことによって、電子申告 (ER) コンフィギュレーションで既存のアプリケーション ロジックを再利用する方法に関する情報を提供します。
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f61228d328521d0c6fe8e0ae704001a65d03151f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249230"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>アプリケーション クラスのメソッドを呼び出す ER 式の設計

[!include [task guide banner](../../includes/task-guide-banner.md)]

このガイドは、ER の式で必要なアプリケーション クラスのメソッドを呼び出すことによって、電子申告 (ER) コンフィギュレーションで既存のアプリケーション ロジックを再利用する方法に関する情報を提供します。 呼び出しクラスの引数の値は、実行時に動的に定義することができます。たとえば、解析文書内の情報に基づいて、その正確性を確保します。 このガイドでは、サンプル会社 Litware, Inc. に必要な ER コンフィギュレーションを作成します。この手順は、「システム管理者」または「電子レポート開発者」ロールが割り当てられているユーザー用に作成されています。 

これらのステップは、任意のデータ セットを使用して完了することができます。 次のファイルもローカルでダウンロードして保存する必要があります: (https://go.microsoft.com/fwlink/?linkid=862266): SampleIncomingMessage.txt。

これらの手順を完了するには、まず手順の「ER はコンフィギュレーションプロバイダーを作成し、それを有効としてマークする」にある手順を完了する必要があります。

1. [組織管理] > [ワークスペース] > [電子申告] の順に移動します。
    * サンプル会社 Litware, Inc. のコンフィギュレーション プロバイダーが使用可能であり、アクティブとしてマークされていることを確認します。 このコンフィギュレーション プロバイダーが表示されない場合は、「コンフィギュレーション プロバイダーの作成および有効なプロバイダーとしてのマーク付け」という手順のステップを完了する必要があります。   
    * アプリケーション データ更新のために受取口座取引明細書を解析するプロセスを設計しているとしましょう。 受取口座取引明細書が、IBAN コードを含んだテキスト ファイルとして届きます。 口座取引明細書のインポート プロセスの一部として、すでに利用可能なロジックを使用して、この IBAN コードの正確性を検証する必要があります。   

## <a name="import-a-new-er-model-configuration"></a>新しい ER モデル コンフィギュレーションのインポート
1. 一覧で、目的のレコードを見つけ、選択します。
    * Microsoft プロバイダー タイルを選択します。  
2. [リポジトリ] をクリックします。
3. [フィルターの表示] をクリックします。
4. [タイプ名] フィルター フィールドを追加します。 [名前] フィールドでは、値「リソース」を入力し、「次の値を含む」フィールド オペレーターを選択します。
5. [開く] をクリックします。
6. ツリーで、「支払モデル」を選択します。
    * [バージョン] クイック タブの [インポート] ボタンが有効でない場合は、ER コンフィギュレーション [支払モデル] のひとつである、「バージョン 1」がすでにインポートされています。 この下位タスクの残りの手順はスキップできます。   
7. [インポート] をクリックします。
8. [はい] をクリックします。
9. ページを閉じます。
10. ページを閉じます。

## <a name="add-a-new-er-format-configuration"></a>新しい ER 形式コンフィギュレーションを追加する
1. [コンフィギュレーションをレポートする] をクリックします。
    * 新しい ER 形式を追加して、受取口座取引明細書を TXT 形式で解析します。  
2. ツリーで、「支払モデル」を選択します。
3. [コンフィギュレーションの作成] をクリックすると、ダイアログ メニューが開きます。
4. [新規] フィールドで、「PaymentModel データ モデルに基づいた書式」と入力します。
5. [名前] フィールドに「口座取引明細書のインポート形式 (サンプル)」と入力します。
    * 口座取引明細書のインポート形式 (サンプル)  
6. [データのインポートのサポート] フィールドで [はい] を選択します。
7. [コンフィギュレーションの作成] をクリックします。

## <a name="design-the-er-format-configuration---format"></a>ER 形式のコンフィギュレーションをデザイン- 形式
1. [デザイナー] をクリックします。
    * 設計された形式は、TXT 形式の外部ファイルの予想構造を表します。  
2. [ルートの追加] をクリックして、ダイアログ メニューを開きます。
3. ツリーで、「Text\Sequence」を選択します。
4. [名称] のフィールドに、「Root」を入力します。
    * ルート  
5. [特殊文字] フィールドでは、「New line - Windows (CR LF)」を選択します。
    * 「New line - Windows (CR LF)」オプションが、「特殊文字」フィールドで選択されています。 この設定に基づいて、解析ファイル内の各明細行は別々のレコードとみなします。  
6. [OK] をクリックします。
7. [追加] をクリックしてドロップ ダイアログを開きます。
8. ツリーで、「Text\Sequence」を選択します。
9. [名前] フィールドに、「行」を入力します。
    * 行  
10. [多様性] フィールドで、「1 つ、多数」を選択します。
    * [多様性] フィールドで、「1 つ、多数」オプションが選択されています。 この設定に基づいて、解析ファイルに少なくとも 1 つの明細行が表示されることが予想されます。  
11. [OK] をクリックします。
12. ツリーで、[ルート\行] を選択します。
13. [順番の追加] をクリックします。
14. [名前] フィールドに、「フィールド」を入力します。
    * フィールド  
15. [多様性] フィールドで、「1 つのみ」を選択します。
16. [OK] をクリックします。
17. ツリーで、[ルート\行\フィールド] を選択します。
18. [追加] をクリックしてドロップ ダイアログを開きます。
19. ツリーで、[Text\String] を選択します。
20. [名前] フィールドに、「IBAN」と入力します。
    * IBAN  
21. [OK] をクリックします。
    * 解析ファイルの各明細行に IBAN コードのみが含まれるように構成されています。  
22. [保存] をクリックします。

## <a name="design-the-er-format-configuration--mapping-to-data-model"></a>ER 形式のコンフィギュレーションをデザイン- データ モデルへのマッピング
1. [形式をモデルにマップ] をクリックします。
2. [新規] をクリックします。
3. [定義] フィールドに、「BankToCustomerDebitCreditNotificationInitiation」を入力します。
    * BankToCustomerDebitCreditNotificationInitiation  
4. [定義の変更] を解決します。
5. [名前] フィールドで、「データモデルのマッピング」と入力します。
    * データ モデルへのマッピング  
6. [保存] をクリックします。
7. [デザイナー] をクリックします。
8. ツリーで、「Dynamics 365 for Operations\Class」を選択します。
9. [ルートの追加] をクリックします。
    * IBAN コード検証のために既存のアプリケーション ロジックを呼び出すための新しいデータ ソースを追加します。  
10. [名称] フィールドで、「check_codes」と入力します。
    * check_codes  
11. [クラス] フィールドに「ISO7064」と入力します。
    * ISO7064  
12. [OK] をクリックします。
13. ツリーで、「形式」を展開します。
14. ツリーで、[形式\ルート: 順番 (ルート)] を展開します。
15. ツリーで、[形式\ルート: 順番 (ルート)\行: 順番 1..* (行)] を選択します。
16. [バインド] をクリックします。
17. ツリーで、[形式\ルート: 順番 (ルート)\行: 順番 1..* (行)] を展開します。
18. ツリーで、[形式\ルート: 順番 (ルート)\行: 順番 1..* (行)\フィールド: 順番 1..1 (フィールド)] を展開します。
19. ツリーで、[形式\ルート: 順番 (ルート)\行: 順番 1..* (行)\フィールド: 順番 1..1 (フィールド)\IBAN: 文字列 (IBAN)] を展開します。
20. ツリーで、[支払い = format.Root.Row] を展開します。
21. ツリーで、[支払い = format.Root.Rows\債権者勘定 (CreditorAccount)] を展開します。
22. ツリーで、[支払い = format.Root.Rows\債権者勘定 (CreditorAccount)\ID] を展開します。
23. ツリーで、[支払い = format.Root.Rows\債権者勘定 (CreditorAccount)\ID\IBAN] を選択します。
24. [バインド] をクリックします。
25. [検証] タブをクリックします。
26. [新規] をクリックします。
    * 無効な IBAN コードを含む解析ファイルで任意の明細行のエラーを表示する新しい検証ルールを追加します。  
27. [条件の編集] をクリックします。
28. ツリーで、[check_codes] を展開します。
29. ツリーで、[check_codes\verifyMOD1271_36] を選択します。
30. [データ ソースの追加] をクリックします。
31. [式] フィールドに、「check_codes.verifyMOD1271_36(」を入力します。
    * check_codes.verifyMOD1271_36(  
32. ツリーで、「形式」を展開します。
33. ツリーで、[形式\ルート: 順番 (ルート)] を展開します。
34. ツリーで、[形式\ルート: 順番 (ルート)\行: 順番 1..* (行)] を展開します。
35. ツリーで、[形式\ルート: 順番 (ルート)\行: 順番 1..* (行)\フィールド: 順番 1..1 (フィールド)] を展開します。
36. ツリーで、[形式\ルート: 順番 (ルート)\行: 順番 1..* (行)\フィールド: 順番 1..1 (フィールド)\IBAN: 文字列 (IBAN)] を展開します。
37. [データ ソースの追加] をクリックします。
38. [式] フィールドに、「check_codes.verifyMOD1271_36 (format.Root.Rows.Fields.IBAN)」を入力します。
    * check_codes.verifyMOD1271_36 (形式です。Root.Rows.Fields.IBAN)  
39. [保存] をクリックします。
40. ページを閉じます。
    * 検証条件は、アプリケーション クラス 「ISO7064」の既存のメソッド 「verifyMOD1271_36」を呼び出すことによって、無効な IBAN コードに対して FALSE を返すように構成されています。 IBAN コードの値は、解析中の TXT ファイルの内容に基づいて、呼び出しメソッドの引数として実行時に動的に定義されることに注意してください。   
41. メッセージの編集をクリックします。
42. [式] フィールドに、「CONCATENATE("無効な IBAN コードが検出されました:  ", format.Root.Rows.Fields.IBAN)」を入力します。
    * CONCATENATE("無効な IBAN コードが検出されました:  "、書式設定します.Root.Rows.Fields.IBAN)  
43. [保存] をクリックします。
44. ページを閉じます。
45. [保存] をクリックします。
46. ページを閉じます。

## <a name="run-the-format-mapping"></a>形式マッピングの実行
テストのために、ダウンロードした SampleIncomingMessage.txt ファイルを使用して形式マッピングを実行します。 生成された出力は選択された TXT ファイルからインポートされ、実際のインポート中にカスタム データ モデルに読み込まれるデータが含まれます。   
1. [実行] をクリックします。
    * [参照] をクリックし、以前ダウンロードした SampleIncomingMessage.txt ファイルに移動します。  
2. [OK] をクリックします。
    * 選択ファイルからインポートされてデータ モデルにポートされたデータを表すXML 書式の出力を確認します。 インポートされた TXT ファイルの 3 つの行のみが処理されたことに注意してください。 有効でない明細行 4 の IBAN コードはスキップされ、情報ログにエラー メッセージが表示されます。  

