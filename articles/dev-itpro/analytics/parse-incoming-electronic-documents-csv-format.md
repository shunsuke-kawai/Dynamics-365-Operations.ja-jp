---
title: "CSV 形式で受信したドキュメントを解析する"
description: "このトピックでは、受信した CSV 形式のドキュメントを解析するように電子報告 (ER) 形式を設定する方法について説明します。"
author: nickselin
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 27621
ms.assetid: 
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2017-11-10
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 319cb2f8ee84b85c5bfce067efd12a531238c8d7
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---
# <a name="parse-incoming-documents-in-csv-format"></a><span data-ttu-id="48345-103">CSV 形式で受信したドキュメントを解析する</span><span class="sxs-lookup"><span data-stu-id="48345-103">Parse incoming documents in CSV format</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="48345-104">電子申告 (ER) 書式をデザインして、プレーン テキスト内 (CSV 形式のファイル) の表形式データを表す受信した電子ドキュメントを解析し、これらのドキュメントからの内容を使用してアプリケーション データを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="48345-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents that represent tabular data in plain text (files in CSV format) and then use the content from these documents to update application data.</span></span> <span data-ttu-id="48345-105">次のアプローチを使用できます。</span><span class="sxs-lookup"><span data-stu-id="48345-105">The following approach can be used:</span></span>

+ <span data-ttu-id="48345-106">解析ファイル内の各明細行は別々のレコードとみなすように指定して、新しいルート シーケンス要素を追加することによりフォーマットのデザインを開始します。</span><span class="sxs-lookup"><span data-stu-id="48345-106">Begin your format’s design by adding a new root sequence element to specify that each line in the parsing file is considered a separate record.</span></span>
  + <span data-ttu-id="48345-107">追加されたシーケンス要素で、適切な値を選択します。たとえば、**シーケンス要素の区切り記号**フィールド グループの**特殊文字**フィールドの**改行 - Windows (CR LF)**。</span><span class="sxs-lookup"><span data-stu-id="48345-107">In the added sequence element, select the appropriate value, for example **New line - Windows (CR LF)**, in the **Special characters** field in the **Sequence element delimiter** field group.</span></span>
+ <span data-ttu-id="48345-108">追加されたルート シーケンス要素の入れ子になった順序要素を追加して、解析ファイル内の各行が一連のフィールドとみなされるように指定して、フォーマットのデザインを続行します。</span><span class="sxs-lookup"><span data-stu-id="48345-108">Continue your format’s design by adding a nested sequence element of the added root sequence element to specify that each line in the parsing file is considered as a set of fields.</span></span>
  + <span data-ttu-id="48345-109">解析明細行でフィールド区切りとして認識される <strong>区切り記号</strong> フィールドで、文字列を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="48345-109">You can specify the character in the <strong>Custom delimiter</strong> field that will be recognized in the parsing line as a fields separator.</span></span>
    >
    > [!NOTE]
    > <span data-ttu-id="48345-110">異なるシーケンス要素に異なるフィールド区切りを定義して、フィールドが異なる文字で区切られている特定のファイルの明細行を解析することができます。</span><span class="sxs-lookup"><span data-stu-id="48345-110">You can define different field separators for different sequence elements to parse specific file lines in which fields are separated by different characters.</span></span>
    >
    > [!NOTE]
    > <span data-ttu-id="48345-111">**カスタム区切り記号** フィールドは、特定のシーケンス要素では空白のままにできます。</span><span class="sxs-lookup"><span data-stu-id="48345-111">The **Custom delimiter** field can be left blank for certain sequence elements.</span></span> <span data-ttu-id="48345-112">空のフィールドは、この順序を使用して解析されるファイル行が .txt (固定長テキスト) ファイル行のように解析されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="48345-112">An empty field means that any file line that is parsed by using this sequence will be parsed like a .txt (fixed length text) file line.</span></span>

  + <span data-ttu-id="48345-113">**見積申請**フィールドで、このシーケンス要素で解析される明細行の一部のフィールドが特定の文字で囲まれることが期待される場合は値を選択します。</span><span class="sxs-lookup"><span data-stu-id="48345-113">In the **Quotation application** field, select the value when you expect that some fields of any line that is parsed by this sequence element will be enclosed by certain characters.</span></span> <span data-ttu-id="48345-114"> 次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="48345-114">The following options are available:</span></span>
    + <span data-ttu-id="48345-115">**すべて** - 任意のデータ型の任意のフィールドについて、解析明細行の引用文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="48345-115">**All** - Include quotation characters in the parsing line for any field of any data type.</span></span> <span data-ttu-id="48345-116">これを選択した場合、フィールド見積に使用される**引用符**フィールドで目的の文字を定義します。</span><span class="sxs-lookup"><span data-stu-id="48345-116">If you select this, define the desired characters in the **Quotation mark** field that will be used for fields quotation.</span></span> <span data-ttu-id="48345-117">たとえば、二重引用符文字。</span><span class="sxs-lookup"><span data-stu-id="48345-117">For example, the double quotes character.</span></span>
    + <span data-ttu-id="48345-118">**テキストのみ** - は **文字列** データ型の任意のフィールドの解析行に引用符を含めます。</span><span class="sxs-lookup"><span data-stu-id="48345-118">**Text only** - Include quotation characters in the parsing line for any field of the **String** data type.</span></span> <span data-ttu-id="48345-119">これを選択した場合、フィールド見積に使用される**引用符**フィールドで目的の文字を定義します。</span><span class="sxs-lookup"><span data-stu-id="48345-119">If you select this, define the desired characters in the **Quotation mark** field that will be used for fields quotation.</span></span>
    + <span data-ttu-id="48345-120">**親のみから派生** - 親シーケンス要素に定義されている、同じ**見積申請**フィールド設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="48345-120">**Derive from parent only** - Use the same **Quotation application** field settings that are defined for the parent sequence element.</span></span> <span data-ttu-id="48345-121">**引用符**フィールドの設定も親シーケンス要素の設定から取得されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="48345-121">Note that the **Quotation mark** field setting will be taken from the settings of the parent sequence element as well.</span></span>
    + <span data-ttu-id="48345-122">**なし** - 任意のデータ型の任意のフィールドについて、解析明細行の引用文字を除外します。</span><span class="sxs-lookup"><span data-stu-id="48345-122">**None** - Exclude quotation characters in the parsing line for any field of any data type.</span></span>
+ <span data-ttu-id="48345-123">解析明細行のフィールド セットを表す、追加されたシーケンス要素の入れ子になった要素を追加して、フォーマットのデザインを完成させます。</span><span class="sxs-lookup"><span data-stu-id="48345-123">Complete your format’s design by adding nested elements for the added sequence element that represents the set of fields of the parsing line.</span></span> <span data-ttu-id="48345-124">**文字列**、**DateTime**、**数値**のような**テキスト** グループの必要な要素を追加して、異なるデータ型の個々のフィールドのセットとして解析行の構造を記述することができます。</span><span class="sxs-lookup"><span data-stu-id="48345-124">Add the required elements of the **Text** group, such as **String**, **DateTime**, and **Numeric**, to describe the structure of the parsing line as a set of individual fields of different data types.</span></span>
  + <span data-ttu-id="48345-125">解析の明細行の個々のフィールドを表す形式要素については、既定では、<strong>多様性</strong>フィールドでは何も選択されません。</span><span class="sxs-lookup"><span data-stu-id="48345-125">For each format element that represents an individual field of the parsing line, by default, nothing is selected in the <strong>Multiplicity</strong> field.</span></span> <span data-ttu-id="48345-126">これは、解析行のフィールドの値が必須と見なされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="48345-126">This means that the value of the field in the parsing line is considered required.</span></span> <span data-ttu-id="48345-127"><strong>多様性</strong>フィールドで、<strong>ゼロ、1 つ</strong>を選択してオプションとして解析明細行のこのフィールドの値を検討します。</span><span class="sxs-lookup"><span data-stu-id="48345-127">In the <strong>Multiplicity</strong> field, select <strong>Zero one</strong> to consider the value of this field in the parsing line as optional.</span></span>
    >
    > [!NOTE]
    > <span data-ttu-id="48345-128">データソースの品目 <strong>isMatch</strong> は、<strong>多様性</strong>フィールドで<strong>ゼロ、1 つ</strong>が選択されている場合、この形式を各<strong>文字列</strong>、<strong>日時</strong>、または<strong>数値</strong>形式要素の ER データモデルにマップすると使用できます。</span><span class="sxs-lookup"><span data-stu-id="48345-128">The data source item <strong>isMatch</strong> is available when you map this format to ER data model for each <strong>String</strong>, <strong>DateTime</strong>, or <strong>Numeric</strong> format element with the option <strong>Zero one</strong> selected in the <strong>Multiplicity</strong> field.</span></span> <span data-ttu-id="48345-129">このフィールドに値が含まれているときは、<strong>isMatch</strong> は <strong>True</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="48345-129">When this field contains a value,  <strong>isMatch</strong> will return <strong>True</strong>.</span></span> <span data-ttu-id="48345-130">フィールドに値がない場合は、<strong>False</strong> が返されます。</span><span class="sxs-lookup"><span data-stu-id="48345-130">If there is no value in the field, it will return <strong>False</strong>.</span></span>

<span data-ttu-id="48345-131">この機能の詳細については、**ER 外部 CSV ファイルからデータをインポートするフォーマット構成を作成する**(「IT サービス/ソリューション コンポーネントの取得/開発 (10677)」の一部) タスク ガイドを再生してください。これは、ER フォーマットを使用して、受信した CSV ファイルを解析してアプリケーション データを更新する方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="48345-131">To learn more about this feature, play the task guide, **ER Create a format configuration to import data from an external CSV file** (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walks through how the incoming CSV file can be parsed by using the ER format to update application data.</span></span>

<span data-ttu-id="48345-132">上記のタスクガイドを完成させるには、次のファイルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="48345-132">Download the following files to complete the task guide mentioned above.</span></span>

| <span data-ttu-id="48345-133">肩書き</span><span class="sxs-lookup"><span data-stu-id="48345-133">Title</span></span>                                  | <span data-ttu-id="48345-134">ファイル名</span><span class="sxs-lookup"><span data-stu-id="48345-134">File name</span></span>          |
|----------------------------------------|--------------------|
| <span data-ttu-id="48345-135">ER フォーマット構成</span><span class="sxs-lookup"><span data-stu-id="48345-135">ER format configuration</span></span>                | [<span data-ttu-id="48345-136">1099formatcsv.xml</span><span class="sxs-lookup"><span data-stu-id="48345-136">1099formatcsv.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)  |
| <span data-ttu-id="48345-137">.csv 形式の受信ファイルのサンプル</span><span class="sxs-lookup"><span data-stu-id="48345-137">Sample of incoming file in .csv format</span></span> | [<span data-ttu-id="48345-138">1099entriescsv.csv</span><span class="sxs-lookup"><span data-stu-id="48345-138">1099entriescsv.csv</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |

<span data-ttu-id="48345-139">タスク ガイドを再生していない場合は、上記のタスク ガイドを完了するために必要な次のファイルをダウンロードしてください。現在の Dynamics 365 for Finance and Operation アプリケーションの **ER Create は電子レポート用に外部ファイルからデータをインポートするために必要な設定**。</span><span class="sxs-lookup"><span data-stu-id="48345-139">Download the following file that is required to complete the task guide mentioned above if you have not played the task guide, **ER Create required configurations to import data from an external file for electronic reporting** in the current Dynamics 365 for Finance and Operation application.</span></span>


|         <span data-ttu-id="48345-140">肩書き</span><span class="sxs-lookup"><span data-stu-id="48345-140">Title</span></span>          |                            <span data-ttu-id="48345-141">ファイル名</span><span class="sxs-lookup"><span data-stu-id="48345-141">File name</span></span>                            |
|------------------------|-----------------------------------------------------------------|
| <span data-ttu-id="48345-142">ER モデル構成</span><span class="sxs-lookup"><span data-stu-id="48345-142">ER model configuration</span></span> | [<span data-ttu-id="48345-143">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="48345-143">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |

