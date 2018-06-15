---
title: "ステージ理由コードの使用"
description: "理由コードを使用して、サービス レベル契約 (SLA) がキャンセルされた理由、またはサービス注文が SLA で定義されている期限を過ぎた理由を示します。"
author: YuyuScheller
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable, SMAParameters
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
ms.openlocfilehash: e42172fe1b484b91e9a3e3d05d438e7e9b0b0eb4
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---


# <a name="use-stage-reason-codes"></a><span data-ttu-id="87a27-103">ステージ理由コードの使用</span><span class="sxs-lookup"><span data-stu-id="87a27-103">Use stage reason codes</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="87a27-104">理由コードを使用して、サービス レベル契約 (SLA) がキャンセルされた理由、またはサービス注文が SLA で定義されている期限を過ぎた理由を示します。</span><span class="sxs-lookup"><span data-stu-id="87a27-104">You use a reason code to indicate why a service level agreement (SLA) has been canceled, or why a service order has exceeded the time limit that is you define in the SLA.</span></span>

<span data-ttu-id="87a27-105">また、SLA がキャンセルされた場合、または期日がサービス注文に対して SLA に指定された時間を超えたときに理由コードが必要であることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="87a27-105">You can also specify that a reason code is required when an SLA is canceled, or when the time limit exceeds the time that is specified in the SLA for the service order.</span></span>

<span data-ttu-id="87a27-106">理由コードが必要であることを指定した場合、次の状況で理由コードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87a27-106">If you have specified that a reason code is required, you must enter a reason code in the following situations:</span></span>

  - <span data-ttu-id="87a27-107">サービス注文の SLA に対する時刻記録を停止するステージにサービス注文が移行される場合。</span><span class="sxs-lookup"><span data-stu-id="87a27-107">When a service order is moved to a stage that stops time recording against the SLA for the service order.</span></span>

  - <span data-ttu-id="87a27-108">サービス注文が承認される場合</span><span class="sxs-lookup"><span data-stu-id="87a27-108">When the service order is signed off.</span></span>

  - <span data-ttu-id="87a27-109">時刻記録が手動で停止される場合。</span><span class="sxs-lookup"><span data-stu-id="87a27-109">When time recording is manually stopped.</span></span>

## <a name="set-up-reason-codes"></a><span data-ttu-id="87a27-110">理由コードの設定</span><span class="sxs-lookup"><span data-stu-id="87a27-110">Set up reason codes</span></span>

1.  <span data-ttu-id="87a27-111">**サービス管理** \> **設定** \> **サービス注文** \> **ステージ理由コード**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="87a27-111">Click **Service management** \> **Setup** \> **Service orders** \> **Stage reason codes**.</span></span>

2.  <span data-ttu-id="87a27-112">**ステージ理由コード**フォームで、**新規**をクリックして新しい理由コードを作成します。</span><span class="sxs-lookup"><span data-stu-id="87a27-112">In the **Stage reason codes** form, click **New** to create a new reason code.</span></span>

3.  <span data-ttu-id="87a27-113">**ステージ理由コード**フィールドに、固有のステージの理由コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="87a27-113">In the **Stage reason code** field, enter a unique stage reason code.</span></span>

4.  <span data-ttu-id="87a27-114">**説明**フィールドに、ステージの理由コードの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="87a27-114">In the **Description** field, enter a description of the stage reason code.</span></span>

5.  <span data-ttu-id="87a27-115">フォームを閉じて、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="87a27-115">Close the form to save your changes.</span></span>

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a><span data-ttu-id="87a27-116">サービス レベル契約がキャンセルされた場合の理由コードの要求</span><span class="sxs-lookup"><span data-stu-id="87a27-116">Require reason codes when a service level agreement is canceled</span></span>

1.  <span data-ttu-id="87a27-117">**サービス管理** \> **設定** \> **サービス管理パラメーター**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="87a27-117">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="87a27-118">**サービス管理パラメーター**フォームで、**一般**リンクをクリックし、次に**キャンセルの理由コード**チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="87a27-118">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on canceling** check box.</span></span>

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a><span data-ttu-id="87a27-119">サービス注文がサービス レベル契約で設定されている期限を過ぎた場合の理由コードの要求</span><span class="sxs-lookup"><span data-stu-id="87a27-119">Require reason codes when the a service order exceeds the time limit that is set by the service level agreement</span></span>

1.  <span data-ttu-id="87a27-120">**サービス管理** \> **設定** \> **サービス管理パラメーター**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="87a27-120">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="87a27-121">**サービス管理パラメーター**フォームで、**一般**リンクをクリックし、次に**時間超過の理由コード**チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="87a27-121">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on exceeding time** check box.</span></span>

## <a name="see-also"></a><span data-ttu-id="87a27-122">参照</span><span class="sxs-lookup"><span data-stu-id="87a27-122">See also</span></span>

[<span data-ttu-id="87a27-123">サービス注文の時刻記録の開始および停止</span><span class="sxs-lookup"><span data-stu-id="87a27-123">Start and stop time recording on a service order</span></span>](start-and-stop-time-recording-on-a-service-order.md)

  


