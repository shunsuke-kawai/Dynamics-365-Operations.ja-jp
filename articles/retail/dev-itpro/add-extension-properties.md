---
title: "顧客エンティティへの拡張プロパティの追加"
description: "このチュートリアルでは、拡張プロパティを使用してエンティティを拡張する方法を示します。"
author: mugunthanm
manager: AnnBe
ms.date: 06/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations, Retail
ms.custom: 196163
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 36951e152771d01050100a9ae318de9a61d037d4
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="add-extension-properties-to-a-customer-entity"></a><span data-ttu-id="27e71-103">顧客エンティティへの拡張プロパティの追加</span><span class="sxs-lookup"><span data-stu-id="27e71-103">Add extension properties to a customer entity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="27e71-104">このチュートリアルでは、拡張プロパティを使用してエンティティを拡張する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="27e71-104">This tutorial shows how to use extension properties to extend an entity.</span></span> 

<span data-ttu-id="27e71-105">このチュートリアルでは、エンティティが Microsoft 365 for Retail で拡張され、Retail とチャネル データベースの両方で保持されます。</span><span class="sxs-lookup"><span data-stu-id="27e71-105">In this tutorial, an entity is extended in Microsoft 365 for Retail, and persisted in both Retail and the channel databases.</span></span> <span data-ttu-id="27e71-106">これにより、販売時点管理 (POS) ユーザー インターフェイス (UI) で値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="27e71-106">The point of sale (POS) user interface (UI) then provides access to the value.</span></span> <span data-ttu-id="27e71-107">新しい値は、Commerce Data Exchange (CDX) トランザクション サービスを介して Dynamics AX に同期的に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="27e71-107">The new value is also written synchronously to Dynamics AX via the Commerce Data Exchange (CDX) transaction service.</span></span> <span data-ttu-id="27e71-108">拡張機能プロパティは自動的にフローするため、Commerce Runtime または Retail サーバーに必要なカスタマイズはありません。</span><span class="sxs-lookup"><span data-stu-id="27e71-108">No customizations are required for the commerce runtime or Retail Server, because extension properties flow automatically.</span></span> <span data-ttu-id="27e71-109">フォーム、テーブル、Real-time Service (RTS) クライアント、CDX、チャネル データベース、POS (Retail Modern POS およびクラウド POS の両方) の変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="27e71-109">Changes are required in forms, tables, the Real-time Service (RTS) client, CDX, the channel database, and the POS (both Retail Modern POS and Cloud POS).</span></span> <span data-ttu-id="27e71-110">このチュートリアルでは、オフライン モードをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="27e71-110">This tutorial doesn't support offline mode.</span></span>

<a name="create-a-new-dynamics-ax-project"></a><span data-ttu-id="27e71-111">新しい Dynamics AX プロジェクトを作成します</span><span class="sxs-lookup"><span data-stu-id="27e71-111">Create a new Dynamics AX project</span></span>
--------------------------------

1.  <span data-ttu-id="27e71-112">**RetailCustPreference** という名前の新しいテーブルを作成し、CustTable テーブルを参照します。</span><span class="sxs-lookup"><span data-stu-id="27e71-112">Create a new table that is named **RetailCustPreference** and that references the CustTable table.</span></span>
2.  <span data-ttu-id="27e71-113">Microsoft Visual Studio を開始します。</span><span class="sxs-lookup"><span data-stu-id="27e71-113">Start Microsoft Visual Studio.</span></span>
3.  <span data-ttu-id="27e71-114">新しいモデルおよびプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="27e71-114">Create a new model and project.</span></span> <span data-ttu-id="27e71-115">**Dynamics AX** メニューで、**モデル管理** &gt; **モデルの作成**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-115">On the **Dynamics AX** menu, click **Model Management** &gt; **Create Model**.</span></span>
4.  <span data-ttu-id="27e71-116">USR レイヤーに新しいモデルを作成し、**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-116">Create a new model in the USR layer, and then click **Next**.</span></span>
5.  <span data-ttu-id="27e71-117">既存の ApplicationSuite パッケージへモデルを追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-117">Add the model to the existing ApplicationSuite package.</span></span> <span data-ttu-id="27e71-118">**次へ**をクリックし、**完了**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-118">Click **Next**, and then click **Finish**.</span></span>
6.  <span data-ttu-id="27e71-119">プロジェクト名を入力し、**OK** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-119">Enter a name for the project, and then click **OK**.</span></span>
7.  <span data-ttu-id="27e71-120">ソリューション エクスプローラーで、新しいプロジェクトを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-120">In Solution Explorer, right-click your new project.</span></span> <span data-ttu-id="27e71-121">**追加** &gt; **新しい品目** を選択し、**RetailCustPreference** という新しいテーブルを追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-121">Select **Add** &gt; **New Item**, and add a new table that is named **RetailCustPreference**.</span></span>
8.  <span data-ttu-id="27e71-122">プロジェクトで、**RetailCustPreference** をダブルクリックしてテーブル デザイナーを開きます。</span><span class="sxs-lookup"><span data-stu-id="27e71-122">In your project, double-click **RetailCustPreference** to open the table designer.</span></span>
9.  <span data-ttu-id="27e71-123">**EmailOptIn** という名前の新しい列挙フィールドを作成し、**Enum Type** プロパティーを **NoYes** に設定します。</span><span class="sxs-lookup"><span data-stu-id="27e71-123">Create a new enumeration field that is named **EmailOptIn**, and set the **Enum Type** property to **NoYes**.</span></span>
10. <span data-ttu-id="27e71-124">**AccountNum** という名前の新しい文字列フィールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="27e71-124">Create a new string field that is named **AccountNum**.</span></span> <span data-ttu-id="27e71-125">フィールドの拡張データ型を **CustAccount** に設定し、**Mandatory** プロパティを **Yes** に設定します。</span><span class="sxs-lookup"><span data-stu-id="27e71-125">Set the field's extended data type to **CustAccount**, and set the **Mandatory** property to **Yes**.</span></span>
11. <span data-ttu-id="27e71-126">CustTable テーブルを使用して新しいリレーションを作成し、**RetailCustPreference.AccountNum** と **CustTable.AccountNum** の間に新しい通常のリレーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-126">Create a new relation with the CustTable table, and add a new normal relation between **RetailCustPreference.AccountNum** and **CustTable.AccountNum**.</span></span>
12. <span data-ttu-id="27e71-127">変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="27e71-127">Save your changes.</span></span>
13. <span data-ttu-id="27e71-128">ソリューション エクスプローラーで、プロジェクトを右クリックしてから**プロパティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="27e71-128">In Solution Explorer, right-click your project, and then select **Properties**.</span></span>
14. <span data-ttu-id="27e71-129">**ビルドでデータベースを** **同期** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="27e71-129">Select the **Synchronize database** **on build** check box.</span></span>
15. <span data-ttu-id="27e71-130">プロジェクトを右クリックし、**ビルド** を選択して新しいコードを作成およびデータベースを同期します。</span><span class="sxs-lookup"><span data-stu-id="27e71-130">Right-click your project, and then select **Build** to build the new code and synchronize the database.</span></span>
16. <span data-ttu-id="27e71-131">ビルドが完了したら、プロジェクトのプロパティに戻り、**ビルドでの** **データベースの同期** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="27e71-131">When the build is completed, return to the project properties, and clear the **Synchronize database** **on build** check box.</span></span>

## <a name="update-the-custtable-form"></a><span data-ttu-id="27e71-132">CustTable フォームの更新</span><span class="sxs-lookup"><span data-stu-id="27e71-132">Update the CustTable form</span></span>
1.  <span data-ttu-id="27e71-133">アプリケーション エクスプローラーで、**ユーザー インターフェイス** &gt; **フォーム** &gt; **CustTable** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27e71-133">In Application Explorer, select **User Interface** &gt; **Forms** &gt; **CustTable**.</span></span> <span data-ttu-id="27e71-134">**CustTable** を右クリックし、**拡張子の作成** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27e71-134">Right-click **CustTable**, and then select **Create Extension**.</span></span>
2.  <span data-ttu-id="27e71-135">これで、プロジェクトに **CustTable.Extension** という名前の新しい要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="27e71-135">Your project now includes a new element that is named **CustTable.Extension**.</span></span> <span data-ttu-id="27e71-136">フォーム デザイナーを開くには、要素をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-136">Double-click this element to open the form designer.</span></span>
3.  <span data-ttu-id="27e71-137">**RetailCustPreference** という名前の新しいデータ ソースを追加し、設定し、**リンク タイプ** プロパティを **OuterJoin** に設定します。</span><span class="sxs-lookup"><span data-stu-id="27e71-137">Add a new data source that is named **RetailCustPreference**, and set the **Link Type** property to **OuterJoin**.</span></span>
4.  <span data-ttu-id="27e71-138">**CustTable** フォームの **小売**タブ ページで、**顧客の優先**という名前の新しいグループを追加し、**キャプション**プロパティに**顧客の優先**を設定します。</span><span class="sxs-lookup"><span data-stu-id="27e71-138">On the **CustTable** form on the **Retail** tab page, add a new group that is named **CustomerPreference** and that has the **Caption** property set to **Customer Preference** .</span></span>
5.  <span data-ttu-id="27e71-139">**CustomerPreference** グループの **RetailCustPreference** テーブルに、**EmailOptIn** という名前の新しいチェック ボックス フィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-139">To the **RetailCustPreference** table in the **CustomerPreference** group, add a new check box field that is named **EmailOptIn**.</span></span>
6.  <span data-ttu-id="27e71-140">**CustTable\_Extension** という名前の新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-140">Add a new class that is named **CustTable\_Extension**.</span></span> <span data-ttu-id="27e71-141">コード エディターで、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-141">In the code editor, add the following code.</span></span>

        public static class CustTable_Extension
        {
            [FormDataSourceEventHandler(formDataSourceStr(CustTable, CustTable), FormDataSourceEventType::ValidatingWrite)]
            public static void foo(FormDataSource fds, FormDataSourceEventArgs e)
            {
                FormRun                             form = fds.formRun();
                CustTable                           custTable = fds.cursor() as CustTable;
                RetailCustPreference                retailCustPreference = form.dataSource(formDataSourceStr(CustTable, RetailCustPreference)).cursor() as RetailCustPreference;
                retailCustPreference.AccountNum     = custTable.AccountNum; form.dataSource(formDataSourceStr(CustTable, RetailCustPreference)).write(); 
            } 
        }

7.  <span data-ttu-id="27e71-142">すべての変更を保存し、プロジェクトを再度ビルドします。</span><span class="sxs-lookup"><span data-stu-id="27e71-142">Save all your changes, and build your project again.</span></span>
8.  <span data-ttu-id="27e71-143">**iisreset** を実行します。</span><span class="sxs-lookup"><span data-stu-id="27e71-143">Run **iisreset**.</span></span>
9.  <span data-ttu-id="27e71-144">Dynamics 365 for Retail で、**売掛金勘定** &gt; **共通** &gt; **顧客** &gt; **すべての顧客**と移動します。</span><span class="sxs-lookup"><span data-stu-id="27e71-144">In Dynamics 365 for Retail, go to **Accounts receivable** &gt; **Common** &gt; **Customers** &gt; **All customers**.</span></span>
10. <span data-ttu-id="27e71-145">顧客レコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="27e71-145">Edit a customer record.</span></span> <span data-ttu-id="27e71-146">**小売**クイック タブで、**電子メール申し込み**チェック ボックスをオンにし、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="27e71-146">On the **Retail** FastTab, select the **Email Opt In** check box, and then save your change.</span></span>

## <a name="customize-the-existing-retailtransactionservice-class-so-that-it-handles-the-new-data-correctly"></a><span data-ttu-id="27e71-147">新しいデータが正しく処理できるように、既存の RetailTransactionService クラスをカスタマイズします</span><span class="sxs-lookup"><span data-stu-id="27e71-147">Customize the existing RetailTransactionService class so that it handles the new data correctly</span></span>
1.  <span data-ttu-id="27e71-148">アプリケーション エクスプローラーで、**RetailTransactionService (sys)** クラスを右クリックしてから**カスタマイズ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="27e71-148">In Application Explorer, right-click the **RetailTransactionService (sys)** class, and then select **Customize**.</span></span>
2.  <span data-ttu-id="27e71-149">終了時に、次の 2 つの方法を追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-149">Add the following two methods at the end.</span></span>

        /// <summary>
        /// Processes all Extension properties. This is a sample only. Should be re-factored into its own class for better reuse and better decoupling from RetailTransactionService
        /// </summary>
        /// <param name = "extensionProperties"></param>
        private static void processExtensionProperties(AccountNum accountNum, str extensionProperties)
        {
            XmlElement                  xmlElementExtensionProperties;
            XmlNodeList                 xmlListExtensionProperties;
            int                         i;
            XmlElement                  xmlElementExtensionProperty;
            str                         propertyName;
            str                         propertyValue;
            int                         emailOptInValue;
            if(extensionProperties != null && extensionProperties != '')
            {
                XmlDocument xmlExtensionProperties = new XmlDocument();
                xmlExtensionProperties.loadXml(extensionProperties);
                xmlElementExtensionProperties = xmlExtensionProperties.getNamedElement('ExtensionProperties');
                xmlListExtensionProperties = xmlElementExtensionProperties.childNodes();
                if (xmlListExtensionProperties)
                {
                    for (i = 0; i < xmlListExtensionProperties.length(); i++)
                    {
                        xmlElementExtensionProperty = xmlListExtensionProperties.item(i);
                        if(xmlElementExtensionProperty)
                        {
                            propertyName = xmlElementExtensionProperty.tagName();
                            propertyValue = xmlElementExtensionProperty.innerText();
                            switch(propertyName)
                            {
                                case "EMAILOPTIN":
                                    // update the EMAILOPTIN value
                                    if(propertyValue != null && propertyValue != '')
                                    {
                                        emailOptInValue = str2Int(propertyValue);
                                    }
                                    else
                                    {
                                        emailOptInValue = 0;
                                    }
                                    RetailTransactionService::updateOptIn(accountNum, emailOptInValue);
                                    break;
                                default:
                                    // do something else here...
                                    break; 
                            } 
                        } 
                    } 
                } 
            } 
        }

        /// <summary>
        /// Updates the customer email optin value. This is a sample only. Should be re-factored into its own class for better reuse and better decoupling from RetailTransactionService
        /// </summary>
        /// <param name = "accountnum"></param>
        /// <param name = "emailOptIn"></param>
        /// <returns></returns>
        private static container updateOptIn(AccountNum accountnum, int emailOptIn)
        {
            RetailCustPreference        retailCustPreference;
            boolean validUpdate = false;
            str error = "NO error";
            int fromLine;
            try
            {
                //Extensibility code for cust preference
                select forUpdate EmailOptIn from retailCustPreference  where  retailCustPreference.AccountNum == accountnum;
                if(retailCustPreference.RecId)
                {
                    //retailCustPreference.clear();
                    ttsBegin;
                    retailCustPreference.EmailOptIn = emailOptIn;
                    retailCustPreference.update();
                    ttscommit;
                }
                else
                {
                    retailCustPreference.clear();
                    retailCustPreference.AccountNum = accountNum;
                    retailCustPreference.EmailOptIn = emailOptIn;
                    retailCustPreference.insert();
                }
                validUpdate = true;
            }
            catch(Exception::Error)
            {
                ttsabort;
                error = RetailTransactionServiceUtilities::getInfologMessages(fromLine);
                RetailTracer::Error('RetailTransactionService', funcName(), error);
            }
            // Returning the status as a container
            return [validUpdate, error,retailCustPreference.AccountNum];
        }

3.  <span data-ttu-id="27e71-150">次のコードを末尾に追加して、**updateCustomerExt** メソッドを更新します。</span><span class="sxs-lookup"><span data-stu-id="27e71-150">Update the **updateCustomerExt** method by adding the following code to the end.</span></span> <span data-ttu-id="27e71-151">(また、コードの最初の行に **customerContainer** の変数申告を追加します。)</span><span class="sxs-lookup"><span data-stu-id="27e71-151">(Also add the variable declaration for **customerContainer** on the first line of code.)</span></span>

        // the third element in container is the account number
        AccountNum accountNum = conPeek(customerContainer, 3);
        RetailTransactionService::processExtensionProperties(accountNum, extensionProperties);
        return customerContainer;

4.  <span data-ttu-id="27e71-152">プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="27e71-152">Compile the project.</span></span>

## <a name="configure-cdx-to-sync-the-new-table"></a><span data-ttu-id="27e71-153">新しいテーブルを同期させる CDX をコンフィギュレーションします。</span><span class="sxs-lookup"><span data-stu-id="27e71-153">Configure CDX to sync the new table</span></span>
1.  <span data-ttu-id="27e71-154">Dynamics 365 for Retail で、**Retail** &gt; **設定** &gt; **小売用スケジューラ** &gt; **小売チャネル** **スキーマ**と移動し、新しいテーブルを追加してチャネル スキーマを編集します。</span><span class="sxs-lookup"><span data-stu-id="27e71-154">In Dynamics 365 for Retail, go to **Retail** &gt; **Setup** &gt; **Retail scheduler** &gt; **Retail channel** **schema**, and edit the channel schema by adding a new table:</span></span>
    1.  <span data-ttu-id="27e71-155">**チャネル テーブル**、**新規**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-155">Click **Channel tables**, and then click **New**.</span></span>
    2.  <span data-ttu-id="27e71-156">テーブルに **ax.RetailCustPreference** と名前を付けて保存します。</span><span class="sxs-lookup"><span data-stu-id="27e71-156">Name the table **ax.RetailCustPreference**, and save it.</span></span>
    3.  <span data-ttu-id="27e71-157">次のフィールドを追加します: **ACCOUNTNUM**、**DATAAREAID**、**EMAILOPTIN**、**RECID**。</span><span class="sxs-lookup"><span data-stu-id="27e71-157">Add the following fields: **ACCOUNTNUM**, **DATAAREAID**, **EMAILOPTIN**, and **RECID**.</span></span>
    4.  <span data-ttu-id="27e71-158">**OK** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-158">Click **OK**.</span></span>

2.  <span data-ttu-id="27e71-159">**Retail** &gt; **設定** &gt; **小売用スケジューラ** &gt; **スケジューラ サブジョブ**の順に移動し、新しいサブジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="27e71-159">Go to **Retail** &gt; **Setup** &gt; **Retail scheduler** &gt; **Scheduler subjobs**, and create a new subjob:</span></span>
    1.  <span data-ttu-id="27e71-160">**Name** フィールドを **RetailCustPreference** に、**Description** フィールドを **RetailCustPreference** に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="27e71-160">Set the **Name** field to **RetailCustPreference** and the **Description** field to **RetailCustPreference**.</span></span>
    2.  <span data-ttu-id="27e71-161">**チャネル テーブル名**フィールドを **ax.RetailCustPreference** に設定します。</span><span class="sxs-lookup"><span data-stu-id="27e71-161">Set the **Channel table name** field to **ax.RetailCustPreference**.</span></span>
    3.  <span data-ttu-id="27e71-162">**AX テーブル** フィールドを **RetailCustPreference** に設定します。</span><span class="sxs-lookup"><span data-stu-id="27e71-162">Set the **AX table** field to **RetailCustPreference**.</span></span>
    4.  <span data-ttu-id="27e71-163">**フィールドの照合**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-163">Click **Match fields**.</span></span>
    5.  <span data-ttu-id="27e71-164">**保存** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-164">Click **Save**.</span></span>

3.  <span data-ttu-id="27e71-165">**小売** &gt; **設定** &gt; **小売用スケジューラ** &gt; **スケジューラ サブジョブ**、**顧客 - 1010** ジョブに新しいサブジョブを追加して、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="27e71-165">**Retail** &gt; **Setup** &gt; **Retail Scheduler** &gt; **Scheduler subjobs**, add the new subjob to the **Customers - 1010** job, and save your change.</span></span>
4.  <span data-ttu-id="27e71-166">**小売** &gt; **設定** &gt; **小売用スケジューラ** &gt; **小売チャンネル スキーマ**、**エクスポート、編集、** **新しい名前で保存**、**インポート**の順に移動し、CDX テーブル配送 XML を編集します。</span><span class="sxs-lookup"><span data-stu-id="27e71-166">Go to **Retail** &gt; **Setup** &gt; **Retail Scheduler** &gt; **Retail channel schema**, **export, edit,** **save with new name**, **import**, and edit the CDX table distribution XML.</span></span> <span data-ttu-id="27e71-167">両方の **CustTable** ノード内に、次の XML フラグメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-167">Add the following XML fragment inside both **CustTable** nodes.</span></span> <span data-ttu-id="27e71-168">(この XML フラグメントを追加することで、チャンネルと同期しているときに、このテーブルの変更を明示的に含めることになります。)</span><span class="sxs-lookup"><span data-stu-id="27e71-168">(By adding this XML fragment, you're explicitly including changes in this table when it's synced with the channels.)</span></span>

        <Table name="RetailCustPreference">
            <LinkGroup>
                <Link type="FieldMatch" fieldName="accountNum" parentFieldName="AccountNum" />
            </LinkGroup>
        </Table>

5.  <span data-ttu-id="27e71-169">**小売チャネル スキーマ**ページで、スキーマ名として **AX** を選択し、**クエリの生成**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-169">On the **Retail channel schema** page, select **AX** as the schema name, and then click **Generate queries**.</span></span>

## <a name="channel-database"></a><span data-ttu-id="27e71-170">チャネル データベース</span><span class="sxs-lookup"><span data-stu-id="27e71-170">Channel database</span></span>
<span data-ttu-id="27e71-171">開発用チャンネル データベースを手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="27e71-171">You will manually change the channel database for development.</span></span> <span data-ttu-id="27e71-172">実際の展開については、このトピックで後述の「実際の展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e71-172">For the live deployment, see the "Live deployment" section later in this topic.</span></span> <span data-ttu-id="27e71-173">新しいテーブルを追加するには ChannelDBUpgrade.sql から正しいチャンネル データベースへスキーマの変更を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e71-173">You must apply the schema change from ChannelDBUpgrade.sql to the correct channel database to add the new table.</span></span>

1.  <span data-ttu-id="27e71-174">\[crt\].\[CUSTOMERSVIEW\] の変更:</span><span class="sxs-lookup"><span data-stu-id="27e71-174">Change \[crt\].\[CUSTOMERSVIEW\]:</span></span>
    -   <span data-ttu-id="27e71-175">UNION All の前に、選択する必要がある列のリストの最後に「, isnull(rcp.EMAILOPTIN, 0) as EMAILOPTIN」を追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-175">Before the UNION All, add ", isnull(rcp.EMAILOPTIN, 0) as EMAILOPTIN" to the end of the list of columns that should be selected.</span></span>
    -   <span data-ttu-id="27e71-176">UNION All の前に、「LEFT OUTER JOIN \[ax\].RETAILCUSTPREFERENCE rcp ON ct.ACCOUNTNUM = rcp.ACCOUNTNUM AND ct.DATAAREAID = rcp.DATAAREAID」を追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-176">Before the UNION All, add "LEFT OUTER JOIN \[ax\].RETAILCUSTPREFERENCE rcp ON ct.ACCOUNTNUM = rcp.ACCOUNTNUM AND ct.DATAAREAID = rcp.DATAAREAID".</span></span>
    -   <span data-ttu-id="27e71-177">UNION All の後に、選択する必要がある列のリストの最後に、「, 0  as EMAILOPTIN」を追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-177">After the UNION All, add ", 0  as EMAILOPTIN" to the end of the list of columns that should be selected.</span></span>
    -   <span data-ttu-id="27e71-178">ストアド プロシージャ \[crt\].\[CREATEUPDATECUSTOMER\] を変更します:</span><span class="sxs-lookup"><span data-stu-id="27e71-178">Change sproc \[crt\].\[CREATEUPDATECUSTOMER\]:</span></span>

2.  <span data-ttu-id="27e71-179">行 「MERGE INTO \[ax\].DIRADDRESSBOOKPARTY」の直前に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="27e71-179">Add the following code just before line "MERGE INTO \[ax\].DIRADDRESSBOOKPARTY":</span></span>

        MERGE INTO [ax].RETAILCUSTPREFERENCE
        USING (SELECT DISTINCT
        tp.PARENTRECID, tp.PROPERTYVALUE as [EMAILOPTIN], ct.ACCOUNTNUM, ct.DATAAREAID
        FROM @TVP_EXTENSIONPROPERTIESTABLETYPE tp
        JOIN [ax].CUSTTABLE ct on ct.RECID = tp.PARENTRECID
        WHERE tp.PARENTRECID <> 0 and tp.PROPERTYNAME = 'EMAILOPTIN') AS SOURCE
        ON [ax].RETAILCUSTPREFERENCE.RECID = SOURCE.PARENTRECID
            and [ax].RETAILCUSTPREFERENCE.DATAAREAID = SOURCE.DATAAREAID
            and [ax].RETAILCUSTPREFERENCE.ACCOUNTNUM = SOURCE.ACCOUNTNUM
        WHEN MATCHED THEN
        UPDATE SET [EMAILOPTIN] = source.[EMAILOPTIN]
        WHEN NOT MATCHED THEN
        INSERT
        (
            RECID
            ,DATAAREAID
            ,EMAILOPTIN
            ,ACCOUNTNUM
        )
        VALUES
        (
            SOURCE.PARENTRECID
            ,SOURCE.DATAAREAID
            ,SOURCE.EMAILOPTIN
            ,SOURCE.ACCOUNTNUM
        );
        SELECT @i_Error = @@ERROR;
        IF @i_Error <> 0
        BEGIN
        SET @i_ReturnCode = @i_Error;
        GOTO exit_label;
        END;

## <a name="verify-cdx"></a><span data-ttu-id="27e71-180">CDX の確認</span><span class="sxs-lookup"><span data-stu-id="27e71-180">Verify CDX</span></span>
1.  <span data-ttu-id="27e71-181">完全な同期 (チャネル データ グループ) を使用して、1010 ジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="27e71-181">Run the 1010 job by using full synchronization (channel data group).</span></span>
2.  <span data-ttu-id="27e71-182">ダウンロード セッションとチャネル データベースをチェックして、データが到着したことを確認します。(**適用済**として表示されます)。</span><span class="sxs-lookup"><span data-stu-id="27e71-182">Check the download sessions and the channel database to verify that the data arrived (it should appear as **Applied**).</span></span>

<span data-ttu-id="27e71-183">**注記:** Commerce Runtime または Retail サーバーのカスタマイズは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="27e71-183">**Note:** No customizations are required for the commerce runtime or Retail Server.</span></span> <span data-ttu-id="27e71-184">拡張プロパティは自動的にフローされます。</span><span class="sxs-lookup"><span data-stu-id="27e71-184">Extension properties flow automatically.</span></span>

## <a name="test-the-customizations-business-logic-by-using-the-retail-server-test-client"></a><span data-ttu-id="27e71-185">Retail Server テスト クライアントを使用して、カスタマイズのビジネス ロジックをテスト</span><span class="sxs-lookup"><span data-stu-id="27e71-185">Test the customization's business logic by using the Retail Server test client</span></span>
1. <span data-ttu-id="27e71-186">プロジェクトを **RetailSdk\\SampleExtensions\\RetailServer\\Extensions.TestClient** で開いて、コンパイルし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27e71-186">Open the project at **RetailSdk\\SampleExtensions\\RetailServer\\Extensions.TestClient**, and then compile and run it.</span></span>
2. <span data-ttu-id="27e71-187">**新しく有効化**ボタンの横にあるフィールドに、Retail サーバー URL を入力してから、**新しく有効化**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-187">In the field next to the **Activate New** button, enter the Retail Server URL, and then click **Activate New**.</span></span>
3. <span data-ttu-id="27e71-188">デバイスを入力し、ID を登録し、次に**アクティブにする**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-188">Enter the device and register IDs, and then click **Activate**.</span></span>
4. <span data-ttu-id="27e71-189">登録権限を持つ Microsoft Azure Active Directory (Azure AD) の資格情報を入力し、**OK** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-189">Enter the Microsoft Azure Active Directory (Azure AD) credentials that have registration privileges, and then click **OK**.</span></span>
5. <span data-ttu-id="27e71-190">テスト クライアントが登録されているデバイスを表示するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="27e71-190">Wait for the test client to show which device is registered.</span></span>
6. <span data-ttu-id="27e71-191">サインイン ボタンをクリックし、作業者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="27e71-191">Click the sign-in button, and sign in by using worker credentials.</span></span>
7. <span data-ttu-id="27e71-192">**Sdk テスト**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e71-192">Click **Sdk Tests**.</span></span> <span data-ttu-id="27e71-193">このボタンは、**EmailOptIn** 拡張プロパティが適用された顧客を保存する新しい機能を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="27e71-193">This button calls the new functionality that saves a customer with the **EmailOptIn** extension property applied.</span></span>
8. <span data-ttu-id="27e71-194">Dynamics AX またはデータベースで、顧客の <strong>EmailOptIn</strong> 値が正しく保存されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27e71-194">In Dynamics AX or the database, verify that the customer's <strong>EmailOptIn</strong> value is stored correctly.</span></span> <span data-ttu-id="27e71-195"><strong>注記: **エラー/ログを含むコンソールを表示するには、**デバッグ</strong>ボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="27e71-195"><strong>Note: **To see a console that includes errors/logs, use the **Debug</strong> button.</span></span>

## <a name="extend-modern-pos"></a><span data-ttu-id="27e71-196">Modern POS 拡張</span><span class="sxs-lookup"><span data-stu-id="27e71-196">Extend Modern POS</span></span>
1.  <span data-ttu-id="27e71-197">**ModernPos.sln** ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="27e71-197">Open the **ModernPos.sln** solution.</span></span>
2.  <span data-ttu-id="27e71-198">ソリューションの **BEGIN SDKSAMPLE\_CUSTOMERPREFERENCES** をグローバル検索します。</span><span class="sxs-lookup"><span data-stu-id="27e71-198">Do a global search for **BEGIN SDKSAMPLE\_CUSTOMERPREFERENCES** in the solution.</span></span>
3.  <span data-ttu-id="27e71-199">見つけたすべての場所でコードを有効にし、再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="27e71-199">Enable the code at all places that you found, and recompile.</span></span> <span data-ttu-id="27e71-200">リソース ファイルが 1 つだけ必要です。</span><span class="sxs-lookup"><span data-stu-id="27e71-200">Only one resources file is required.</span></span> <span data-ttu-id="27e71-201">必要なロケールを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="27e71-201">You can select the required locale.</span></span>
4.  <span data-ttu-id="27e71-202">Modern POS を実行し、新しい顧客を作成できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27e71-202">Run Modern POS, and verify that you can create a new customer.</span></span> <span data-ttu-id="27e71-203">既存の顧客が更新されると、チャネル データベースと Dynamics AX データベースの両方でフラグが正しく更新される必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e71-203">When an existing customer is updated, the flag should be updated correctly in both the channel database and the Dynamics AX database.</span></span>

## <a name="live-deployment"></a><span data-ttu-id="27e71-204">実際の展開</span><span class="sxs-lookup"><span data-stu-id="27e71-204">Live deployment</span></span>
1.  <span data-ttu-id="27e71-205">データベース フォルダーにチャネル データベースの変更ファイルを追加し、**customization.settings** に登録します。</span><span class="sxs-lookup"><span data-stu-id="27e71-205">Add the channel database change file to the database folder, and register it in **customization.settings**.</span></span>
2.  <span data-ttu-id="27e71-206">Retail SDK ソリューションに **msbuild** を実行します。</span><span class="sxs-lookup"><span data-stu-id="27e71-206">Run **msbuild** for the whole Retail SDK solution.</span></span> <span data-ttu-id="27e71-207">すべてのパッケージにはすべての適切な変更があります。</span><span class="sxs-lookup"><span data-stu-id="27e71-207">All packages will have all appropriate changes.</span></span>
3.  <span data-ttu-id="27e71-208">Microsoft Dynamics Lifecycle Services (LCS) を使用するか手動でパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="27e71-208">Deploy packages, either by using Microsoft Dynamics Lifecycle Services (LCS) or manually.</span></span>




