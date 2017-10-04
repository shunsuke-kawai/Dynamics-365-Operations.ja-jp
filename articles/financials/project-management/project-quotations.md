---
title: "プロジェクト見積"
description: "この記事では、プロジェクト フェーズにおける最初のステップとして顧客に魅力的な提案をするために使用できる、プロジェクト見積の概念を紹介します。 プロジェクト見積には、見積を作成する品目およびサービス、基本連絡先情報、特別な売買契約や割引、適用される可能性のある税金や割増金が含まれます。"
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesQuotationProjTable
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23621
ms.assetid: 1ba67109-8c5b-4ada-b730-a72cd46203fd
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: 8a5138a75ff17575ae789124b1d1aa08eaa4a986
ms.contentlocale: ja-jp
ms.lasthandoff: 09/14/2017

---

# <a name="project-quotations"></a><span data-ttu-id="ea0bc-104">プロジェクト見積</span><span class="sxs-lookup"><span data-stu-id="ea0bc-104">Project quotations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ea0bc-105">この記事では、プロジェクト フェーズにおける最初のステップとして顧客に魅力的な提案をするために使用できる、プロジェクト見積の概念を紹介します。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-105">This article introduces the concept of project quotations, which you can use to make an attractive offer to a customer as the first step of the project phase.</span></span> <span data-ttu-id="ea0bc-106">プロジェクト見積には、見積を作成する品目およびサービス、基本連絡先情報、特別な売買契約や割引、適用される可能性のある税金や割増金が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-106">A project quotation might include the items and services that are quoted, basic contact information, special trade agreements and discounts, and possible taxes and surcharges.</span></span> 

<span data-ttu-id="ea0bc-107">プロジェクト見積と注文のパイプラインを、監視、確認、制御する能力は、プロジェクト管理において重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-107">The ability to monitor, review, and control the pipeline of project quotations and orders is an important part of project management.</span></span> <span data-ttu-id="ea0bc-108">これらの作業には、Microsoft Dynamics 365 for Finance and Operations,Enterprise エディションのさまざまなツールが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-108">Various tools in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition can help with these tasks.</span></span> <span data-ttu-id="ea0bc-109">たとえば、正しい参照データ定義 (見積タイプ、見積の発生元、および妥当性判断と確度) の修正などのツールはパイプラインの分析に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-109">For example, correct reference data definitions (quotation types, quotation origin, and prognosis and probability) help you analyze the pipeline.</span></span> <span data-ttu-id="ea0bc-110">これらのツールを使用して、プロジェクト見積が受注または失注した理由を分類し、および見積の見込値を決定できます。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-110">You can use these tools to categorize the reasons why a project quotation was won or lost, and to determine the potential value of a quotation.</span></span> 

<span data-ttu-id="ea0bc-111">プロジェクト見積には、プロジェクトに対して見積もった、サービス、基本連絡先情報、特別な売買契約や割引、見積税や割増金を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-111">In a project quotation, you enter the services, basic contact information, special trade agreements and discounts, and estimated taxes and surcharges for a project.</span></span> <span data-ttu-id="ea0bc-112">プロジェクトの活動またはタスクを選択し、タスクやサブタスクの階層を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-112">You can also select the activities or tasks for a project, and create a hierarchy of tasks and subtasks.</span></span> <span data-ttu-id="ea0bc-113">各活動について、活動のタイミングと期間と、活動を実行する作業者に必要なスキルと経験に関する詳細を入力できます。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-113">For each activity, you can enter details about the timing and duration of the activity, and about the skills and experience that are required for workers who perform the activity.</span></span> 

<span data-ttu-id="ea0bc-114">プロジェクト見積は、実行する必要がある作業に対して拘束力がない見積です。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-114">The project quotation is a non-binding estimate of the work that must be performed.</span></span> <span data-ttu-id="ea0bc-115">ただし、見積の情報がプロジェクト契約と関連付けられたプロジェクトにコピーされると、その情報は当事者間で拘束力のある合意の一部になります。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-115">However, when the information in the quotation is copied to a project that is associated with a project contract, that information becomes part of a binding agreement between two parties.</span></span> 

<span data-ttu-id="ea0bc-116">顧客がプロジェクト見積を承認した場合、プロジェクトにプロジェクト見積の情報をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-116">If the customer approves the project quotation, you can copy the information in the project quotation to a project.</span></span> <span data-ttu-id="ea0bc-117">また、プロジェクト予測にプロジェクト見積の情報を同時にコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ea0bc-117">You can also copy the project quotation information to a project forecast at the same time.</span></span>



