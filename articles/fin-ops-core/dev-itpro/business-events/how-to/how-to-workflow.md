---
title: ビジネス イベントおよびワークフローの承認
description: このトピックでは Microsoft Power Automate を使用して購買要求の承認のワークフロー ビジネス イベントを構成して使用する方法を説明します。
author: ibenbouzid
manager: AnnBe
ms.date: 11/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: imbenbou
ms.search.validFrom: Platform update 27
ms.dyn365.ops.version: 2019-6-30
ms.openlocfilehash: 4d9df04e714c1a22e5773d8dbef143a7cd3081a0
ms.sourcegitcommit: ae0efac749ab34d423fac44d00a597801c143fbb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "2830223"
---
# <a name="business-events-and-workflow-approvals"></a>ビジネス イベントおよびワークフローの承認
[!include [banner](../../includes/banner.md)]

このトピックでは Microsoft Power Automate を使用して購買要求の承認のワークフロー ビジネス イベントを構成して使用する方法を説明します。

このトピックを完了するには、プラットフォーム アップデート 26 以降で Microsoft Dynamics 365 for Finance and Operations バージョン 10.0.2 (2019 年 5 月) を実行する必要があります。

## <a name="scenario-overview"></a>シナリオの概要

次の図は Power Automate を使用して構成する必要がある高レベル プロセスを示しています。 次のポイントに注意します。

1. アプリケーションは、新しい承認が開始するたびにビジネス イベントを発生させます。
2. Power Automate トリガーが開始されます。 
3. F&O からビジネス イベント ペイロードを解析した後、次のステップは F&O から受信したワークフロー インスタンス ID がまだ有効か確認することです。 これは、承認が既に行われた場合、またはワークフローが取り消された場合のセキュリティ ステップです。
4. 確認が失敗すると、ワークスペース内の潜在的な作業項目についてユーザーに通知する電子メールが送信されます。
4. 確認が成功すると新しい Power Automate の承認が開始されます。
5. 次に、承認の結果を使用してワークフローが完了します。 結果は **承認** または **否認** のいずれかです。

<img alt="Scenario overview"  src="../../media/BEF-Howto-workflow-01.png" width="70%">

## <a name="exercise-1-create-a-new-flow"></a>練習 1: 新しいフローの作成

1. Power Automate ポータルにサインインします。
2. フロー リソースを作成する権限がある既存の環境を選択します。 **(既定)** 環境はすべての会社が利用できます。
3. **空白から新規 \> を作成する**選択します。
4. **Dynamics 365 for Finance and Operations** を検索して、コネクタを選択します。
5. 新しいトリガーが作成されます。 このトリガーの名前は **ビジネス イベントの発生時** です。 それを選択します。
6. 次の特性を持つ環境インスタンスを選択します。 

    - カテゴリは **ワークフロー作業項目** です。
    - イベント名は **購買要求の確認 (000062) – 購買要求の承認** です。
    - 任意の法人が選択されます。

7. **新規ステップ** を選択して新しいアクションを追加します。
8. **JSON の解析** データ処理を検索します。 このステップは、アプリケーションが提供するデータ コントラクトのスキーマを使用してメッセージを解析するために必要です。
9. **Json 解析** アクションのコンテンツ フィールドを選択します。 前の手順の **本文** 出力がオプションとして表示されます。 **Body** を選択します。

    次に、契約のスキーマを入力する必要があります。 アプリケーションでは、サンプル ペイロードのみ提供します。 ただし Microsoft Flow の機能を使用してペイロードからスキーマを生成できます。

10. カタログの **000062** ワークフロー イベントを選択し、**スキーマのダウンロード**リンクを選択します。 ダウンロードしたテキスト ファイルを開いて内容をコピーします。
11. Power Automate に戻り、**サンプル ペイロードを使用してスキーマを生成** リンクを選択します。 テキスト ファイルの内容を貼り付けて **完了** を選択します。
12. 新しいステップを追加して、正しいインスタンス ID を持つワークフローが実行中で承認を待っているか検証するワークフロー アクションを呼び出します。

    <img alt="workitem validate action" src="../../media/BEF-Howto-workflow-08.png" width="70%">

13. 検証アクションの結果を確認する新しい条件コントロール ステップを追加します。 動的フィールドは必要な出力を提供しません。 したがって、代わりに次の式を手動で入力する必要があります: **Body('Execute_action')?\['value'\]** その後、**OK** を選択します。

    <img alt="Microsoft Power Automate expression" src="../../media/BEF-Howto-workflow-09.png" width="70%">

    > [!NOTE]
    > 次にワークフローを開いたときに式が更新されて **値** フィールドが表示されることがわかります。 次の図に示すように、このフィールドにはアプリケーション アイコンがあります。

    <img alt="expression value" src="../../media/BEF-Howto-workflow-10.png" width="70%">

14. 条件コントロールは **はい**/**いいえ** 結果の 2 つの分岐を自動的に作成します。 検証ステップの結果が **いいえ** の場合、ユーザーに電子メールを送信する必要があります。 このメールは、新しいタスクに注意が必要であり、クライアントにサイン インする必要があることをユーザーに通知します。 このステップを完了するには、**いいえ** コンテナに新しい電子メール送信アクションを作成し、前のステップ **workflowuseremail** からの承認者の電子メール、選択した件名と本文を、パラメーターに入力します。

    > [!NOTE]
    > ワークフロー ビジネス イベントが返す電子メール アドレスは、ワークフロー承認者の電子メール アドレスです。 デモ環境でワークフロー承認者ユーザーが構成されていない場合、デモに自分の電子メール アドレスを使用できます。

    <img alt="approver email" src="../../media/BEF-Howto-workflow-11.png" width="70%">

15. 検証ステップの結果が **はい** の場合、新しい Power Automate 承認ステップを開始する必要があります。 **はい** コンテナで **開始して承認を待つ (v2)** という名前の新しいアクションを選択し、次のように入力を選択します。承認タイプ: 承認/拒否 最初に応答するタイトル: **workflowworkitemsubject** 出力フォーム ビジネスイベントペイロード割り当て先: **workflowuseremail** 出力 その後、**workflowdocument** や **workflowstepinstruction** などの前のステップで必要な情報を詳細セクションに入力できます。 繰り返しになりますが、特にワークフロー承認者ユーザーがデモ環境で構成されていない場合は、デモ目的で **割り当て先** フィールドで自分の電子メールアドレスを使用できます。

    <img alt="Microsoft Power Automate approval" src="../../media/BEF-Howto-workflow-12.png" width="70%">

16. 次に、承認ステップの結果を使用してワークフローの承認を完了する必要があります。 さらに **はい** コンテナに新しい **Finance and Operations 実行アクション** ステップを追加し、**WorkflowWorkitem-complete** アクションと **WorkflowWorkitemInstanceID** パラメーターを選択します。 次に、承認出力から残りのパラメーターを入力します。 最低限の承認結果がある結果セクションと、承認者の応答があるコメント セクション。 承認ステップは複数の承認者をサポートできるため、応答出力は配列です。 したがって、コメント セクションの入力として出力 **応答** を選択すると、すぐに以下に示すように Power Automate はアクションを **それぞれに適用** コンテナに自動的に埋め込みます。

    <img alt="workitem complete action" src="../../media/BEF-Howto-workflow-13.png" width="70%">

17. **保存** を選択します。

## <a name="exercise-2-trigger-a-business-event"></a>練習 2: ビジネス イベントのトリガー

Power Automate では、アプリケーションを自動的にコンフィギュレーションできます。 フローを保存すると、Power Automate でエンドポイントが作成され、ビジネス イベントが有効となります。 その他のコンフィギュレーションを完了する必要はありません。 エンドポイントが正しく構成されてたことを確認してからイベントをトリガーする必要があります。

1. クライアントにサイン インします。
2. **システム管理 \> 設定 \> ビジネス イベント** に移動します。
3. **ビジネス イベント**を選択します。
4. **エンドポイント** を選択します。
5. 新しいエンドポイントが作成されたこと、そしてグローバル一意識別子 (GUID) が名前に追加されたことを確認します。
6. **有効なイベント** タブで、USMF 会社の **ワークフロー作業項目** がアクティブにであることを確認します。