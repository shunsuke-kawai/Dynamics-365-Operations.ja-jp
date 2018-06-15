---
title: "優先技術者の設定"
description: "作業者をサービス合意またはサービス注文の優先技術者として選択できます。"
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 390e436b63fdfe82e0b743e7f286cae3bb29be55
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---


# <a name="set-up-a-preferred-technician"></a><span data-ttu-id="962e5-103">優先技術者の設定</span><span class="sxs-lookup"><span data-stu-id="962e5-103">Set up a preferred technician</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="962e5-104">作業者をサービス合意またはサービス注文の優先技術者として選択できます。</span><span class="sxs-lookup"><span data-stu-id="962e5-104">You can select any worker as a preferred technician for a service agreement or service order.</span></span> <span data-ttu-id="962e5-105">ただし、作業者が**派遣表**に含まれるように、作業者を適切な派遣チームに追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="962e5-105">However, it is a good idea to add the worker to the appropriate dispatch team so that the worker is included on the **Dispatch board**.</span></span>

## <a name="assign-employee-to-a-dispatch-team"></a><span data-ttu-id="962e5-106">派遣チームへの従業員の割り当て</span><span class="sxs-lookup"><span data-stu-id="962e5-106">Assign employee to a dispatch team</span></span>

1.  <span data-ttu-id="962e5-107">**人事管理** \> **共通** \> **作業者** \> **作業者**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="962e5-107">Click **Human resources** \> **Common** \> **Workers** \> **Workers**.</span></span> <span data-ttu-id="962e5-108">作業者の詳細ページを開くには、作業者をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="962e5-108">Double-click a worker to open the worker details page.</span></span> <span data-ttu-id="962e5-109">**アクション ウィンドウ**で、**設定**\>**派遣チーム**をクリックして、**出荷作業者**フォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="962e5-109">On the **Action Pane**, click **Setup** \>**Dispatch team** to open the **Dispatch workers** form.</span></span>

2.  <span data-ttu-id="962e5-110">**派遣チーム**フィールドで、作業者を割り当てるチームを選択します。</span><span class="sxs-lookup"><span data-stu-id="962e5-110">In the **Dispatch team** field, select the team to assign the worker to.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a><span data-ttu-id="962e5-111">サービス合意への優先技術者の割り当て</span><span class="sxs-lookup"><span data-stu-id="962e5-111">Assign a preferred technician to a service agreement</span></span>

1.  <span data-ttu-id="962e5-112">**サービス管理** \> **共通** \> **サービス契約** \> **サービス契約**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="962e5-112">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="962e5-113">詳細フォームを開くには、サービス合意をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="962e5-113">Double-click a service agreement to open the details form.</span></span>

2.  <span data-ttu-id="962e5-114">**一般**タブで、**優先技術者**フィールドを選択し、適切な派遣チームのメンバをサービス合意の優先技術者として割り当てます。</span><span class="sxs-lookup"><span data-stu-id="962e5-114">On the **General** tab, select the **Preferred technician** field, and then select a member of the appropriate dispatch team as the preferred technician for the service agreement.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-order"></a><span data-ttu-id="962e5-115">サービス注文への優先技術者の割り当て</span><span class="sxs-lookup"><span data-stu-id="962e5-115">Assign a preferred technician to a service order</span></span>

1.  <span data-ttu-id="962e5-116">**サービス管理** \> **定期処理** \> **派遣表**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="962e5-116">Click **Service management** \> **Periodic** \> **Dispatch board**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="962e5-117"><STRONG>派遣表</STRONG>フォームで、表示する派遣活動の日付範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="962e5-117">In the <STRONG>Dispatch board</STRONG> form, specify a date range for dispatch activities to view.</span></span> <span data-ttu-id="962e5-118">さらに、終了した活動を表示するかどうか、および派遣活動リストを自分が所属するチームまたは監視する権限があるチームに制限するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="962e5-118">Also, specify whether to display closed activities and whether to limit the dispatch activity list to teams that you belong to or are authorized to monitor.</span></span> <span data-ttu-id="962e5-119"><STRONG>OK</STRONG>をクリックして<STRONG>派遣表</STRONG>フォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="962e5-119">Click <STRONG>OK</STRONG> to open the <STRONG>Dispatch board</STRONG>.</span></span></P>



2.  <span data-ttu-id="962e5-120">変更するサービス活動の明細行を選択します。</span><span class="sxs-lookup"><span data-stu-id="962e5-120">Select the line of the service activity to modify.</span></span>

3.  <span data-ttu-id="962e5-121">**関連**タブで、**作業者**リストを使用して、適切な派遣チームのメンバをサービス コールの優先技術者として割り当てます。</span><span class="sxs-lookup"><span data-stu-id="962e5-121">On the **Related** tab, use the **Worker** list to assign a member of the appropriate dispatch team as the preferred technician for the service call.</span></span>

## <a name="see-also"></a><span data-ttu-id="962e5-122">参照</span><span class="sxs-lookup"><span data-stu-id="962e5-122">See also</span></span>

[<span data-ttu-id="962e5-123">サービス合意 </span><span class="sxs-lookup"><span data-stu-id="962e5-123">Service agreements</span></span>](service-agreements.md)

[<span data-ttu-id="962e5-124">サービス注文の手動作成</span><span class="sxs-lookup"><span data-stu-id="962e5-124">Create service orders manually</span></span>](create-service-orders-manually.md)

<span data-ttu-id="962e5-125">[サービス契約 (フォーム)](https://technet.microsoft.com/en-us/library/aa617823\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="962e5-125">[Service agreements (form)](https://technet.microsoft.com/en-us/library/aa617823\(v=ax.60\))</span></span>
  


