---
title: Microsoft Flow を使用してビジネス イベントを消化する
description: このトピックでは、Finance and Operations コネクタを介して Microsoft Flow で使用可能となるビジネス イベントに関する情報を提供します。
author: ibenbouzid
manager: AnnBe
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global for most topics. Set Country/Region name for localizations
ms.author: imbenbou
ms.search.validFrom: Platform update 27
ms.dyn365.ops.version: 2019-6-30
ms.openlocfilehash: 7f0be999d0a64d1eb6f15f96dbcf0e0f008a2876
ms.sourcegitcommit: 0db7759947bd5fa20a6f4965e4eb4b48401f1299
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "1723208"
---
# <a name="consume-business-events-with-microsoft-flow"></a><span data-ttu-id="5cb98-103">Microsoft Flow を使用してビジネス イベントを消化する</span><span class="sxs-lookup"><span data-stu-id="5cb98-103">Consume business events with Microsoft Flow</span></span>

[!include[banner](../../includes/banner.md)]

<span data-ttu-id="5cb98-104">このトピックでは、 Microsoft Flow エンドポイントから Microsoft Dynamics 365 for Finance and Operations ビジネスイベントを設定・使用する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-104">This topic provides steps detailing how to configure and consume a Microsoft Dynamics 365 for Finance and Operations business event from a Microsoft Flow endpoint.</span></span>

<span data-ttu-id="5cb98-105">このトピックでは、以下のタスクを実行する方法について説明します:</span><span class="sxs-lookup"><span data-stu-id="5cb98-105">This topic shows how to perform the following tasks:</span></span>

-   <span data-ttu-id="5cb98-106">新規 Microsoft Flow の作成</span><span class="sxs-lookup"><span data-stu-id="5cb98-106">Create a new Microsoft Flow.</span></span>
-   <span data-ttu-id="5cb98-107">ビジネス イベントのトリガー</span><span class="sxs-lookup"><span data-stu-id="5cb98-107">Trigger a business event.</span></span>

## <a name="create-a-new-microsoft-flow"></a><span data-ttu-id="5cb98-108">新しい Microsoft Flow の作成</span><span class="sxs-lookup"><span data-stu-id="5cb98-108">Create a new Microsoft Flow</span></span>

1.  <span data-ttu-id="5cb98-109">Microsoft Flow portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5cb98-109">Sign in to Microsoft Flow portal.</span></span>

2.  <span data-ttu-id="5cb98-110">フローリソースを作成するために必要なアクセス権限のある既存の環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-110">Select an existing environment where you have the permissions needed to create a flow resource.</span></span> <span data-ttu-id="5cb98-111">既定の環境は、すべての会社に対して開かれています。</span><span class="sxs-lookup"><span data-stu-id="5cb98-111">The default environment is open to all companies.</span></span>

3.  <span data-ttu-id="5cb98-112">**空白から新規 \> を作成する**選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-112">Select **New \> Create from blank**.</span></span>

4.  <span data-ttu-id="5cb98-113">**Dynamics 365 for Finance and Operations** を検索して、コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-113">Search for **Dynamics 365 for Finance and Operations** and select the connector.</span></span>
     
5.  <span data-ttu-id="5cb98-114">**ビジネス イベントが発生した場合** という名称の Finance and Operations のトリガーが確認できるかと思います。</span><span class="sxs-lookup"><span data-stu-id="5cb98-114">You will notice a trigger for Finance and Operations named **When a Business Event occurs**.</span></span> <span data-ttu-id="5cb98-115">このトリガーを選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-115">Select this trigger.</span></span>

6.  <span data-ttu-id="5cb98-116">環境インスタンス、カテゴリ、イベント名称、法的エンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-116">Select your environment instance, category, event name, and legal entity.</span></span>

    <img src="../../media/BEF-Howto-Flow-04.png" width="50%">

7.  <span data-ttu-id="5cb98-117">**新規ステップ** ボタンを選択して新しいアクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-117">Select the **New Step** button to add a new action.</span></span>

8.  <span data-ttu-id="5cb98-118">**JSON解析** データ処理を検索します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-118">Search for the **Parse JSON** data operation.</span></span> <span data-ttu-id="5cb98-119">この手順は、Finance and Operationsから提供されるデータコントラクトのスキーマを使用してメッセージを解析するために必要となります。</span><span class="sxs-lookup"><span data-stu-id="5cb98-119">This step is needed to parse the message with the schema of the data contract provided by Finance and Operations.</span></span>

    <img src="../../media/BEF-Howto-Flow-06.png" width="50%">

9.  <span data-ttu-id="5cb98-120">**Jsonの解析** アクションの コンテンツ フィールドを選択すると、前のステップの **Body** がオプションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="5cb98-120">Select the content field of **Parse Json** action, then the **Body** output from the previous step should appear as an option.</span></span> <span data-ttu-id="5cb98-121">**Body** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-121">Select **Body**.</span></span>

    <img src="../../media/BEF-Howto-Flow-07.png" width="50%">

10. <span data-ttu-id="5cb98-122">Finance and Operationsから受け取る契約のスキーマを入力します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-122">Enter the schema of the contract received from Finance and Operations.</span></span> <span data-ttu-id="5cb98-123">Finance and Operationsではサンプルのペイロードしか提供されないため、ペイロードからスキーマを生成する Microsoft Flow の機能を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="5cb98-123">Because Finance and Operations provides only a sample payload you can use the Microsoft Flow capability to generate a schema from a payload.</span></span> <span data-ttu-id="5cb98-124">Finance and Operations へと戻り、カタログ内のイベント (顧客支払など) を選択し、 **スキーマのダウンロード** のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-124">Go back to Finance and Operations, select an event in the catalog (for example, Customer Payment) and select the **Download schema** link.</span></span> <span data-ttu-id="5cb98-125">テキストファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="5cb98-125">This will download a text file.</span></span> <span data-ttu-id="5cb98-126">テキストファイルを開き、内容をコピーします。</span><span class="sxs-lookup"><span data-stu-id="5cb98-126">Open the text file and copy the content.</span></span>

    <img src="../../media/BEF-Howto-Flow-08.png" width="50%">

11. <span data-ttu-id="5cb98-127">Microsoft Flow に戻り、 **サンプル ペイロードを使用してスキーマを生成する** リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-127">Go Back to Microsoft Flow and select the **Use sample payload to generate schema** link.</span></span> <span data-ttu-id="5cb98-128">テキストファイルの内容を貼り付け、 **完了** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-128">Paste your text file content and select **Done**.</span></span>

    <img src="../../media/BEF-Howto-Flow-09.png" width="70%">

12. <span data-ttu-id="5cb98-129">サンプル ペイロードの品質によっては、自動生成機能が数値を認識できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5cb98-129">Depending on the quality of your sample payload, your generator will not recognize an integer from a real number.</span></span> <span data-ttu-id="5cb98-130">これは、サンプル ペイロードに実数が整数として提供される場合に該当します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-130">This is true if the real number is provided as a whole number in the sample payload.</span></span> <span data-ttu-id="5cb98-131">生成されたスキーマを確認し、「整数」を「数値」に変更する必要があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-131">Review your generated schema and check if you need to change an “integer” into “number”.</span></span> <span data-ttu-id="5cb98-132">(JSONでは、"数値" データ型は実数値を意味します)。</span><span class="sxs-lookup"><span data-stu-id="5cb98-132">(In JSON, a “number” data type means real number).</span></span>

    <img src="../../media/BEF-Howto-Flow-10.png" width="100%">

13.  <span data-ttu-id="5cb98-133">ビジネス イベント コンテンツを使用するための最終アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-133">Choose another final action to consume the business event content.</span></span> <span data-ttu-id="5cb98-134">たとえば、電子メールで (または、テキストメッセージをチームに共有する) 支払の詳細を顧客に送信することができます。</span><span class="sxs-lookup"><span data-stu-id="5cb98-134">For instance, you can send an email (or post a text message to Teams) to notify the customer about payment details.</span></span> <span data-ttu-id="5cb98-135">**電子メールの送信** アクションを検索し、自分の Office 365 アカウントにログインします。</span><span class="sxs-lookup"><span data-stu-id="5cb98-135">Search for the **Send email** action, then sign in to your Office 365 account.</span></span>

14.  <span data-ttu-id="5cb98-136">メッセージの本文および、必須項目を入力します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-136">Fill in the message with the required fields.</span></span>

   <img src="../../media/BEF-Howto-Flow-12.png" width="70%">

15. <span data-ttu-id="5cb98-137">フローを保存します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-137">Save Flow.</span></span>

## <a name="trigger-a-business-event"></a><span data-ttu-id="5cb98-138">ビジネス イベント の トリガー</span><span class="sxs-lookup"><span data-stu-id="5cb98-138">Trigger a Business Event</span></span>

<span data-ttu-id="5cb98-139">Microsoft Flow は、自動的にFinance and Operationsを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="5cb98-139">Microsoft Flow can configure Finance and Operations automatically for you.</span></span> <span data-ttu-id="5cb98-140">フローを保存すると、Finance and Operations にてエンドポイントが作成され、ビジネスイベントが有効となります。</span><span class="sxs-lookup"><span data-stu-id="5cb98-140">After you save your Flow it creates an endpoint in Finance and Operations, then it activates the business event for you.</span></span> <span data-ttu-id="5cb98-141">イベントを起動する前にエンドポイントが正しく構成されていることを確認する以外に、Finance and Operationsに必要とされる構成手順はありません。</span><span class="sxs-lookup"><span data-stu-id="5cb98-141">There is no remaining configuration step in Finance and Operations apart from verifying that the endpoint has been correctly configured before triggering an event.</span></span>

1. <span data-ttu-id="5cb98-142">Finance and Operations クライアントにログインします</span><span class="sxs-lookup"><span data-stu-id="5cb98-142">Sign in to the Finance and Operations client.</span></span>

2.  <span data-ttu-id="5cb98-143">**システム管理 \> 設定 \> システム パラメーター** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-143">Go to **System Administration \> Setup \> System Parameters**.</span></span>

3.  <span data-ttu-id="5cb98-144">**ビジネス イベント**  タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-144">Select the **Business events** tab.</span></span>

4.  <span data-ttu-id="5cb98-145">**ビジネス イベント**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-145">Select **Business events**.</span></span>

5.  <span data-ttu-id="5cb98-146">**エンドポイント**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cb98-146">Click **Endpoints**.</span></span>

6.  <span data-ttu-id="5cb98-147">新たなエンドポイントが作成され、名称にGUIDが追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5cb98-147">Verify that a new endpoint has been created with a GUID appended in the name.</span></span>

    <img src="../../media/BEF-Howto-Flow-13.png" width="100%">

7.  <span data-ttu-id="5cb98-148">**有効なイベント** タブをオンにした場合は、法的エンティティGBSIに対し **支払転記済** が有効化されていることも確認することができます。</span><span class="sxs-lookup"><span data-stu-id="5cb98-148">If you check the **Active events** tab you can also verify that “**Payment Posted**” is activated for legal entity GBSI.</span></span>

    <img src="../../media/BEF-Howto-Flow-14.png" width="100%">

8.  <span data-ttu-id="5cb98-149">最後の手順では、転記された顧客支払のビジネス イベントをトリガーし、フローの実行と顧客の支払詳細を含む電子メールを受信するかどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="5cb98-149">The final step is to trigger the business event of a posted customer payment and check whether the Flow runs and you receive an email with customer payment details.</span></span>