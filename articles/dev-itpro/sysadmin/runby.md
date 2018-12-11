---
title: "バッチ マネージャーのセキュリティ ロール"
description: "このトピックでは、バッチ ジョブの管理に使用されるバッチ管理者のセキュリティ ロールに関する情報を提供します。"
author: hasaid
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 62333
ms.assetid: 6135bcf7-bf8f-42ae-b2c6-458f6538e6a4
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2018-08-15
ms.dyn365.ops.version: Platform update 20
ms.translationtype: HT
ms.sourcegitcommit: f3e3a22dbc343db1485190402371859861e46d1c
ms.openlocfilehash: ddbd50f13e92802b738bf9fd44aa332c8cb2ea7a
ms.contentlocale: ja-jp
ms.lasthandoff: 10/26/2018

---

# <a name="batch-manager-security-role"></a><span data-ttu-id="2cd57-103">バッチ マネージャーのセキュリティ ロール</span><span class="sxs-lookup"><span data-stu-id="2cd57-103">Batch manager security role</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2cd57-104">プラットフォーム更新 20 より前では、バッチ ジョブを管理するシステム管理者や IT 管理者セキュリティ ロールにユーザーを割り当てる必要がありました。</span><span class="sxs-lookup"><span data-stu-id="2cd57-104">Before Platform update 20, users needed to be assigned to the system admin or IT admin security role to manage batch jobs.</span></span> <span data-ttu-id="2cd57-105">プラットフォーム更新 20 のリリースには、より対象を絞り込んだロール、バッチ マネージャーがあります。</span><span class="sxs-lookup"><span data-stu-id="2cd57-105">With the release of Plaform update 20 there is a more targeted role, Batch manager.</span></span> <span data-ttu-id="2cd57-106">このセキュリティ ロールでは、ユーザーはバッチ ジョブをコピーする、ジョブを実行するユーザーを変更する、ジョブを実行できる時間範囲を指定するアクセス許可を持ちます。</span><span class="sxs-lookup"><span data-stu-id="2cd57-106">With this security role, a user now has permissions to copy batch jobs, change who will execute jobs, and specify the time ranges during which jobs can execute.</span></span> <span data-ttu-id="2cd57-107">バッチ管理セキュリティ特権は、バッチ管理者セキュリティ ロールの一部です。これによって、ユーザーはアド ホック バッチ ジョブを作成して、他のユーザーに権限を付与できます。</span><span class="sxs-lookup"><span data-stu-id="2cd57-107">The Batch maintain security privilege is part of the Batch manager security role and it allows a user to create an ad hoc batch job and grant privileges to other users.</span></span>

> [!NOTE]
> <span data-ttu-id="2cd57-108">この機能は、Platform update 20 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="2cd57-108">This feature is available as of Platform update 20.</span></span>

## <a name="assign-the-batch-manager-role-to-a-user"></a><span data-ttu-id="2cd57-109">バッチ管理者ロールをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="2cd57-109">Assign the Batch manager role to a user</span></span>
<span data-ttu-id="2cd57-110">特定のユーザーにバッチ管理者のセキュリティ ロールを割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2cd57-110">Complete the following steps to assign the Batch manager security role to a specific user.</span></span>

1.  <span data-ttu-id="2cd57-111">**システム管理** > **セキュリティ** > **ユーザーをロールに割り当てる** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cd57-111">Click **System administration** > **Security** > **Assign users to roles**.</span></span>

![ロールへのユーザーの割り当て](./media/assign-batchmanager-role.png) 

2.  <span data-ttu-id="2cd57-113">**バッチ ジョブ マネージャー** をクリックし、左ウィンドウで **ユーザーを手動で割り当てる/除外する** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cd57-113">Click **Batch Job Manager**, and on the left pane, click **Manually assign/exclude user**.</span></span>

![バッチ マネージャー ロール](./media/assign-batchmanager-role-2.png) 

3.  <span data-ttu-id="2cd57-115">一覧からユーザーを選択し、**ロールに割り当て** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cd57-115">Select a user from the list, and then click **Assign to role**.</span></span>
4.  <span data-ttu-id="2cd57-116">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2cd57-116">Close the page.</span></span> 

## <a name="run-by-user"></a><span data-ttu-id="2cd57-117">実行者ユーザー</span><span class="sxs-lookup"><span data-stu-id="2cd57-117">Run by user</span></span>

<span data-ttu-id="2cd57-118">**実行者ユーザー**機能により、バッチ管理者は、バッチ ジョブを実行するユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2cd57-118">The **run by user** functionality allows Batch managers to specify a user to run the batch job.</span></span> <span data-ttu-id="2cd57-119">これは、現在ジョブの実行が割り当てられているユーザーを変更する場合、または別の会社にバッチ ジョブをコピーするときにユーザーをすばやく設定する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="2cd57-119">This is useful when you want to change the user who is currently assigned to run the job or if you want to quickly set a user while copying the batch jobs from one company to another.</span></span> <span data-ttu-id="2cd57-120">この機能は、バッチ ジョブをコピーするのにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="2cd57-120">You can also use this functionality to copy batch jobs.</span></span>

 ![実行者ユーザー](./media/runby-user.png)  
 
