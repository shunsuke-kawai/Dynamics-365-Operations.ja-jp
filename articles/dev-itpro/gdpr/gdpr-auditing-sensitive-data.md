---
title: "機密データへのアクセスを管理"
description: "このトピックでは、Microsoft Dynamics 365 for Finance and Operations のユーザー ログ機能について説明します。"
author: ToddLefor
manager: AnnBe
ms.date: 12/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 10031
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f061c93884e9766c4752b9e6a65199fb9de0d0d4
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="manage-access-to-sensitive-data"></a><span data-ttu-id="0fdab-103">機密データへのアクセスを管理</span><span class="sxs-lookup"><span data-stu-id="0fdab-103">Manage access to sensitive data</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0fdab-104">システム管理者は、Microsoft Dynamics 365 for Finance and Operations の **ユーザー ログ** ページを使用して、システムにログオンしたユーザーの監査ログを保持できます。</span><span class="sxs-lookup"><span data-stu-id="0fdab-104">System administrators can use the **User log** page in Microsoft Dynamics 365 for Finance and Operations to keep an audit log of users who have logged on to the system.</span></span> <span data-ttu-id="0fdab-105">ログインしているユーザーを知ることは、組織のデータを保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0fdab-105">Knowing who has logged in can help protect your organization's data.</span></span> <span data-ttu-id="0fdab-106">機密データへのアクセスを提供するロールを管理者が識別できるようにするために、ユーザーのログ機能を拡張しました。</span><span class="sxs-lookup"><span data-stu-id="0fdab-106">We've enhanced the user logging capability to let the administrator identify roles that provide access to sensitive data.</span></span> 

![顧客からのデータ フロー](../media/gdpr-sensitive-data-1.jpg)

## <a name="what-is-sensitive-data"></a><span data-ttu-id="0fdab-108">機密データとは何ですか ?</span><span class="sxs-lookup"><span data-stu-id="0fdab-108">What is sensitive data?</span></span>
<span data-ttu-id="0fdab-109">組織は、ニーズにあった方法で*機密データ*を構成する要素を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="0fdab-109">An organization can define what constitutes *sensitive data* in whatever way serves its needs.</span></span> <span data-ttu-id="0fdab-110">一部の組織によっては、機密データが財務または人事データに関連付けられている任意のデータ、または個人のデータである単なるデータである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0fdab-110">For some organizations, sensitive data might be any data that is related to financial or human resource data, or just data that is personal data.</span></span> <span data-ttu-id="0fdab-111">一部の業界や一部の国または地域には、組織自体が採用できる機密データのより詳細な定義がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0fdab-111">Some industries or some countries or regions might have a more specific definition of sensitive data that an organization can adopt for itself.</span></span> <span data-ttu-id="0fdab-112">機密データ識別子を使用するかどうか、およびその方法を決定するのは各組織次第です。</span><span class="sxs-lookup"><span data-stu-id="0fdab-112">It's up to each organization to decide whether and how to use the sensitive data identifier.</span></span> 

<span data-ttu-id="0fdab-113">機密データ識別子は、システム内で誰が機密データへのアクセス権を持っているかを示す監査ログを作成させることで、ユーザーのログ操作を向上させます。</span><span class="sxs-lookup"><span data-stu-id="0fdab-113">The sensitive data identifier enhances the user logging experience by letting your organization produce audit logs that show who in your system has access to sensitive data.</span></span> <span data-ttu-id="0fdab-114">この機能は、特定のデータへのアクセスの度合いが異なる複数のロールを持つ組織に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0fdab-114">This capability is helpful for organizations that might have multiple roles that have varying degrees of access to certain data.</span></span> <span data-ttu-id="0fdab-115">また、機密性の高いデータとして識別されているデータにアクセスしたユーザーを追跡する監査の詳細なレベルを必要とする組織でも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0fdab-115">It can also be helpful for organizations that want a detailed level of auditing to track users who have had access to data that's been identified as sensitive data.</span></span>

![機密データにアクセスできるロールを表示する [ユーザー ログ] ページ](../media/gdpr-sensitive-data-2.jpg)

## <a name="language-specific-information"></a><span data-ttu-id="0fdab-117">言語固有の情報</span><span class="sxs-lookup"><span data-stu-id="0fdab-117">Language-specific information</span></span>
<span data-ttu-id="0fdab-118">ユーザーログの役割情報は言語固有で、現在のユーザー言語と一致します。</span><span class="sxs-lookup"><span data-stu-id="0fdab-118">The role information in the user log is language-specific and matches the current user language.</span></span>

![時間 ID を持つロール情報](../media/gdpr-sensitive-data-3.jpg)

## <a name="log-retention"></a><span data-ttu-id="0fdab-120">ログの保持</span><span class="sxs-lookup"><span data-stu-id="0fdab-120">Log retention</span></span>
<span data-ttu-id="0fdab-121">機密データであると宣言されたデータにアクセスするユーザーのログ エントリは、ログ内の他のすべてのデータとは別に保持できます。</span><span class="sxs-lookup"><span data-stu-id="0fdab-121">The log entries of users who have access to data that's been declared to be sensitive data can be retained separately from all other data in the log.</span></span> <span data-ttu-id="0fdab-122">管理者は、**ユーザー ログのクリーンアップ** ページでオプションを設定して、この機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0fdab-122">The administrator can enable this functionality by setting an option on the **User log cleanup** page.</span></span>

![[ユーザー ログのクリーンアップ] ページ](../media/gdpr-sensitive-data-4.jpg)

## <a name="additional-resources"></a><span data-ttu-id="0fdab-124">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="0fdab-124">Additional resources</span></span>
<span data-ttu-id="0fdab-125">GDPR の詳細については、[欧州連合の Web サイト](http://europa.eu/) および [Microsoft Trust Center](https://www.microsoft.com/en-us/TrustCenter/Privacy/gdpr/default.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fdab-125">You can learn more about the GDPR on the [European Union's website](http://europa.eu/) and on the [Microsoft Trust Center](https://www.microsoft.com/en-us/TrustCenter/Privacy/gdpr/default.aspx).</span></span>

### <a name="disclaimer"></a><span data-ttu-id="0fdab-126">免責事項</span><span class="sxs-lookup"><span data-stu-id="0fdab-126">Disclaimer</span></span>
<span data-ttu-id="0fdab-127">(c)2018 Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="0fdab-127">(c)2018 Microsoft Corporation.</span></span> <span data-ttu-id="0fdab-128">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="0fdab-128">All rights reserved.</span></span> <span data-ttu-id="0fdab-129">このドキュメントは、"現状のまま" 提供されます。</span><span class="sxs-lookup"><span data-stu-id="0fdab-129">This document is provided "as-is."</span></span> <span data-ttu-id="0fdab-130">URL およびその他のインターネット Web サイトの参照を含む、このドキュメントの情報および見解は、予告なしに変更することがあります。</span><span class="sxs-lookup"><span data-stu-id="0fdab-130">Information and views expressed in this document, including URL and other Internet Web site references, may change without notice.</span></span> <span data-ttu-id="0fdab-131">このドキュメントの使用上のリスクは、すべてユーザーが負うものとします。</span><span class="sxs-lookup"><span data-stu-id="0fdab-131">You bear the risk of using it.</span></span> <span data-ttu-id="0fdab-132">このドキュメントは、Microsoft の製品に含まれる知的財産に対する法律上の権利をお客様に付与するものではありません。</span><span class="sxs-lookup"><span data-stu-id="0fdab-132">This document does not provide you with any legal rights to any intellectual property in any Microsoft product.</span></span> <span data-ttu-id="0fdab-133">内部での参照を目的とする場合、このドキュメントをコピーして使用できます。</span><span class="sxs-lookup"><span data-stu-id="0fdab-133">You may copy and use this document for your internal, reference purposes.</span></span>
