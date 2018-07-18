---
title: "X++ 文字列ランタイム関数"
description: "このトピックでは、文字列ランタイム関数について説明します。"
author: RobinARH
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 31401
ms.assetid: f8d76054-c863-40de-b32a-73dfaa77aeff
ms.search.region: Global
ms.author: robinr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 17ae4850a27716f2a490c1533b88292b3b483f0c
ms.contentlocale: ja-jp
ms.lasthandoff: 05/08/2018

---

# <a name="x-string-run-time-functions"></a><span data-ttu-id="82119-103">X++ 文字列ランタイム関数</span><span class="sxs-lookup"><span data-stu-id="82119-103">X++ string run-time functions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82119-104">このトピックでは、文字列ランタイム関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="82119-104">This topic describes the string run-time functions.</span></span>

<a name="match"></a><span data-ttu-id="82119-105">照合</span><span class="sxs-lookup"><span data-stu-id="82119-105">match</span></span>
-----

<span data-ttu-id="82119-106">文字列や別の文字列内の式を検索します。</span><span class="sxs-lookup"><span data-stu-id="82119-106">Searches for a string or expression in another string.</span></span>

    int match(str pattern, str text)

### <a name="parameters"></a><span data-ttu-id="82119-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-107">Parameters</span></span>

| <span data-ttu-id="82119-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-108">Parameter</span></span> | <span data-ttu-id="82119-109">説明</span><span class="sxs-lookup"><span data-stu-id="82119-109">Description</span></span>                             |
|-----------|-----------------------------------------|
| <span data-ttu-id="82119-110">pattern</span><span class="sxs-lookup"><span data-stu-id="82119-110">pattern</span></span>   | <span data-ttu-id="82119-111">検索する文字列または式。</span><span class="sxs-lookup"><span data-stu-id="82119-111">The string or expression to search for.</span></span> |
| <span data-ttu-id="82119-112">テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-112">text</span></span>      | <span data-ttu-id="82119-113">検索する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-113">The string to search.</span></span>                   |

### <a name="return-value"></a><span data-ttu-id="82119-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-114">Return value</span></span>

<span data-ttu-id="82119-115">パターンが文字列内にある場合は **1**、それ以外の場合は、**0** (ゼロ)。</span><span class="sxs-lookup"><span data-stu-id="82119-115">**1** if the pattern is located in the string; otherwise, **0** (zero).</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-116">備考</span><span class="sxs-lookup"><span data-stu-id="82119-116">Remarks</span></span>

<span data-ttu-id="82119-117">検索では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="82119-117">The search is case-insensitive.</span></span> <span data-ttu-id="82119-118">次の特殊文字を使用して、*pattern* パラメーターのパターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="82119-118">The following special characters can be used to create the pattern for the *pattern* parameter.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82119-119">特徴</span><span class="sxs-lookup"><span data-stu-id="82119-119">Character</span></span></th>
<th><span data-ttu-id="82119-120">説明</span><span class="sxs-lookup"><span data-stu-id="82119-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="82119-121">&lt;/td&gt;</span><span class="sxs-lookup"><span data-stu-id="82119-121">&lt;/td&gt;</span></span>
<td><span data-ttu-id="82119-122">バックスラッシュ () は、特殊文字の特別な扱いを無効にしたりエスケープしたりするため、特殊文字を通常の文字のように一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="82119-122">A backslash () nullifies, or escapes, the special treatment of special characters, so that a special character can be matched like a normal letter.</span></span> <span data-ttu-id="82119-123">バックスラッシュのペアは、1 つの非特殊バックスラッシュに変換されます。</span><span class="sxs-lookup"><span data-stu-id="82119-123">A pair of backslashes is translated into one non-special backslash.</span></span> <span data-ttu-id="82119-124">例</span><span class="sxs-lookup"><span data-stu-id="82119-124">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-125"><strong>照合 (&quot;ab$cd&quot;、&quot;ab$cd&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-125"><strong>match(&quot;ab$cd&quot;,&quot;ab$cd&quot;);</strong> returns <strong>0</strong>.</span></span></li>
<li><span data-ttu-id="82119-126"><strong>照合 (&quot;ab$cd&quot;、&quot;ab$cd&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-126"><strong>match(&quot;ab$cd&quot;,&quot;ab$cd&quot;);</strong> returns <strong>0</strong>.</span></span> <span data-ttu-id="82119-127">バックスラッシュはエスケープされません。</span><span class="sxs-lookup"><span data-stu-id="82119-127">The backslash isn&#39;t escaped.</span></span></li>
<li><span data-ttu-id="82119-128"><strong>照合 (&quot;ab$cd&quot;、&quot;ab$cd&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-128"><strong>match(&quot;ab$cd&quot;,&quot;ab$cd&quot;);</strong> returns <strong>1</strong>.</span></span> <span data-ttu-id="82119-129">バックスラッシュとドル記号はエスケープされます。</span><span class="sxs-lookup"><span data-stu-id="82119-129">The backslash and dollar sign are escaped.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="82119-130">&lt; または ^</span><span class="sxs-lookup"><span data-stu-id="82119-130">&lt; or ^</span></span></td>
<td><span data-ttu-id="82119-131">式の先頭にある始め山かっこ (&lt;) またはサーカムフレックス (^) は、明細行の始まりと照合するために使用します。</span><span class="sxs-lookup"><span data-stu-id="82119-131">A left angle bracket (&lt;) or a circumflex (^) at the start of an expression is used to match the start of a line.</span></span> <span data-ttu-id="82119-132">例</span><span class="sxs-lookup"><span data-stu-id="82119-132">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-133"><strong>照合 (&quot;&lt;abc&quot;、&quot;abcdef&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-133"><strong>match(&quot;&lt;abc&quot;,&quot;abcdef&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-134"><strong>照合 (&quot;&lt;abc&quot;、&quot;defabc&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-134"><strong>match(&quot;&lt;abc&quot;,&quot;defabc&quot;);</strong> returns <strong>0</strong>.</span></span></li>
<li><span data-ttu-id="82119-135"><strong>照合 (&quot;^abc&quot;、&quot;abcdef&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-135"><strong>match(&quot;^abc&quot;,&quot;abcdef&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-136"><strong>照合 (&quot;^abc&quot;、&quot;defabc&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-136"><strong>match(&quot;^abc&quot;,&quot;defabc&quot;);</strong> returns <strong>0</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="82119-137">&gt; または $</span><span class="sxs-lookup"><span data-stu-id="82119-137">&gt; or $</span></span></td>
<td><span data-ttu-id="82119-138">式の最後の終わり山かっこ (&gt;) またはドル記号 (?) は、明細行の末尾と照合するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="82119-138">A right angle bracket (&gt;) or a dollar sign (?) at the end of the expression is used to match the end of a line.</span></span> <span data-ttu-id="82119-139">例</span><span class="sxs-lookup"><span data-stu-id="82119-139">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-140"><strong>照合 (&quot;abc&gt;&quot;、&quot;abcdef&quot;);</strong> は、<strong>0</strong> 返します。</span><span class="sxs-lookup"><span data-stu-id="82119-140"><strong>match(&quot;abc&gt;&quot;,&quot;abcdef&quot;);</strong> returns <strong>0</strong>.</span></span></li>
<li><span data-ttu-id="82119-141"><strong>照合 (&quot;abc&gt;&quot;、&quot;defabc&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-141"><strong>match(&quot;abc&gt;&quot;,&quot;defabc&quot;);</strong> returns <strong>1</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="82119-142">?</span><span class="sxs-lookup"><span data-stu-id="82119-142">?</span></span> <span data-ttu-id="82119-143">or .</span><span class="sxs-lookup"><span data-stu-id="82119-143">or .</span></span></td>
<td><span data-ttu-id="82119-144">疑問符 (?) またはピリオド (.) は、同じ位置にある任意の 1 文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="82119-144">A question mark (?) or a period (.) matches any one character in the same position.</span></span> <span data-ttu-id="82119-145">例</span><span class="sxs-lookup"><span data-stu-id="82119-145">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-146"><strong>照合 (&quot;abc.def&quot;、&quot;abc#def&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-146"><strong>match(&quot;abc.def&quot;,&quot;abc#def&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-147"><strong>照合 (&quot;colou?r&quot;、&quot;colouXr&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-147"><strong>match(&quot;colou?r&quot;,&quot;colouXr&quot;);</strong> returns <strong>1</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="82119-148">:x</span><span class="sxs-lookup"><span data-stu-id="82119-148">:x</span></span></td>
<td><span data-ttu-id="82119-149">直後の文字が示すように、コロンは、一致する文字のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="82119-149">A colon specifies a group of characters to match, as indicated by the character that immediately follows.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="82119-150">:a</span><span class="sxs-lookup"><span data-stu-id="82119-150">:a</span></span></td>
<td><span data-ttu-id="82119-151">文字に一致を設定します。</span><span class="sxs-lookup"><span data-stu-id="82119-151">Sets the match to letters.</span></span> <span data-ttu-id="82119-152">例</span><span class="sxs-lookup"><span data-stu-id="82119-152">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-153"><strong>照合 (&quot;ab:acd&quot;、&quot;ab#cd&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-153"><strong>match(&quot;ab:acd&quot;,&quot;ab#cd&quot;);</strong> returns <strong>0</strong>.</span></span></li>
<li><span data-ttu-id="82119-154"><strong>照合 (&quot;ab:acd&quot;、&quot;abxyzcd&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-154"><strong>match(&quot;ab:acd&quot;,&quot;abxyzcd&quot;);</strong> returns <strong>0</strong>.</span></span></li>
<li><span data-ttu-id="82119-155"><strong>照合 (&quot;ab:acd&quot;、&quot;abxcd&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-155"><strong>match(&quot;ab:acd&quot;,&quot;abxcd&quot;);</strong> returns <strong>1</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="82119-156">:d</span><span class="sxs-lookup"><span data-stu-id="82119-156">:d</span></span></td>
<td><span data-ttu-id="82119-157">数字に一致を設定します。</span><span class="sxs-lookup"><span data-stu-id="82119-157">Sets the match to numeric characters.</span></span> <span data-ttu-id="82119-158">例</span><span class="sxs-lookup"><span data-stu-id="82119-158">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-159"><strong>照合 (&quot;ab:dcd&quot;、&quot;ab3cd&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-159"><strong>match(&quot;ab:dcd&quot;,&quot;ab3cd&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-160"><strong>照合 (&quot;ab:dcd&quot;、&quot;ab123cd&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-160"><strong>match(&quot;ab:dcd&quot;,&quot;ab123cd&quot;);</strong> returns <strong>0</strong>.</span></span></li>
<li><span data-ttu-id="82119-161"><strong>照合 (&quot;ab:dcd&quot;、&quot;abcd&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-161"><strong>match(&quot;ab:dcd&quot;,&quot;abcd&quot;);</strong> returns <strong>0</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="82119-162">:n</span><span class="sxs-lookup"><span data-stu-id="82119-162">:n</span></span></td>
<td><span data-ttu-id="82119-163">英数字に一致を設定します。</span><span class="sxs-lookup"><span data-stu-id="82119-163">Sets the match to alphanumeric characters.</span></span> <span data-ttu-id="82119-164">例</span><span class="sxs-lookup"><span data-stu-id="82119-164">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-165"><strong>照合 (&quot;ab:ncd&quot;、&quot;ab%cd&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-165"><strong>match(&quot;ab:ncd&quot;,&quot;ab%cd&quot;);</strong> returns <strong>0</strong>.</span></span></li>
<li><span data-ttu-id="82119-166"><strong>照合 (&quot;ab:ncd&quot;、&quot;ab9cd&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-166"><strong>match(&quot;ab:ncd&quot;,&quot;ab9cd&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-167"><strong>照合 (&quot;ab:ncd&quot;、&quot;abXcd&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-167"><strong>match(&quot;ab:ncd&quot;,&quot;abXcd&quot;);</strong> returns <strong>1</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="82119-168">:SPACE</span><span class="sxs-lookup"><span data-stu-id="82119-168">:SPACE</span></span></td>
<td><span data-ttu-id="82119-169">SPACE は、空白文字 ( ) です。</span><span class="sxs-lookup"><span data-stu-id="82119-169">SPACE is the space character ( ).</span></span> <span data-ttu-id="82119-170">空白、タブ、および Enter (改行文字) などの制御文字を入力するには、一致を設定します。</span><span class="sxs-lookup"><span data-stu-id="82119-170">Sets the match to blanks, tabulations, and control characters such as Enter (new line).</span></span> <span data-ttu-id="82119-171">例</span><span class="sxs-lookup"><span data-stu-id="82119-171">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-172"><strong>照合 (&quot;ab: cd&quot;、&quot;ab cd&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-172"><strong>match(&quot;ab: cd&quot;,&quot;ab cd&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-173"><strong>照合 (&quot;ab: cd&quot;、&quot;ab\ncd&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-173"><strong>match(&quot;ab: cd&quot;,&quot;ab\ncd&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-174"><strong>照合 (&quot;ab: cd&quot;、&quot;ab\tcd&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-174"><strong>match(&quot;ab: cd&quot;,&quot;ab\tcd&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-175"><strong>照合 (&quot;ab: cd&quot;、&quot;ab cd&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-175"><strong>match(&quot;ab: cd&quot;,&quot;ab cd&quot;);</strong> returns <strong>0</strong>.</span></span> <span data-ttu-id="82119-176">最初のスペースのみ一致します。</span><span class="sxs-lookup"><span data-stu-id="82119-176">Only the first space is matched.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><em></td>
<td><span data-ttu-id="82119-177">アスタリスク (</em>) の後に続く式には、前の式に 0、1、またはそれ以上の一致が必要です。</span><span class="sxs-lookup"><span data-stu-id="82119-177">An expression that is followed by an asterisk (</em>) requires a match for zero, one, or more occurrences of the preceding expression.</span></span> <span data-ttu-id="82119-178">例</span><span class="sxs-lookup"><span data-stu-id="82119-178">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-179"><strong>一致(&quot;abc<em>d&quot;,&quot;abcccd&quot;);</strong> <strong>1</strong>を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-179"><strong>match(&quot;abc<em>d&quot;,&quot;abd&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-180"><strong>照合 (&quot;abc</em>d&quot;、&quot;abcd&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-180"><strong>match(&quot;abc</em>d&quot;,&quot;abcd&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-181"><strong>一致(&quot;abc<em>d&quot;,&quot;abcccd&quot;);</strong> <strong>1</strong>を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-181"><strong>match(&quot;abc<em>d&quot;,&quot;abcccd&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-182"><strong>照合 (&quot;abc</em>d&quot;、&quot;abxd&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-182"><strong>match(&quot;abc</em>d&quot;,&quot;abxd&quot;);</strong> returns <strong>0</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td>+</td>
<td><span data-ttu-id="82119-183">プラス記号 (+) の後に続く式には、前の式に 1 またはそれ以上の一致が必要です。</span><span class="sxs-lookup"><span data-stu-id="82119-183">An expression that is followed by a plus sign (+) requires a match for one or more occurrences of the preceding expression.</span></span> <span data-ttu-id="82119-184">例</span><span class="sxs-lookup"><span data-stu-id="82119-184">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-185"><strong>照合 (&quot;abc+d&quot;、&quot;abd&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-185"><strong>match(&quot;abc+d&quot;,&quot;abd&quot;);</strong> returns <strong>0</strong>.</span></span></li>
<li><span data-ttu-id="82119-186"><strong>照合 (&quot;abc+d&quot;、&quot;abcd&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-186"><strong>match(&quot;abc+d&quot;,&quot;abcd&quot;);</strong> returns <strong>1</strong></span></span></li>
<li><span data-ttu-id="82119-187"><strong>照合 (&quot;abc+d&quot;、&quot;abcccd&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-187"><strong>match(&quot;abc+d&quot;,&quot;abcccd&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-188"><strong>照合 (&quot;abc+d&quot;、&quot;abxd&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-188"><strong>match(&quot;abc+d&quot;,&quot;abxd&quot;);</strong> returns <strong>0</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td>-</td>
<td><span data-ttu-id="82119-189">マイナス記号 (-) の後に続く式には、前の式に 0 または 1 を一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="82119-189">An expression that is followed by a minus sign (-) requires a match for zero or one occurrence of the preceding expression.</span></span> <span data-ttu-id="82119-190">つまり、前の式はオプションです。</span><span class="sxs-lookup"><span data-stu-id="82119-190">In other words, the preceding expression is optional.</span></span> <span data-ttu-id="82119-191">例</span><span class="sxs-lookup"><span data-stu-id="82119-191">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-192"><strong>照合 (&quot;colou-r&quot;、&quot;color&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-192"><strong>match(&quot;colou-r&quot;,&quot;color&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-193"><strong>照合 (&quot;colou-r&quot;、&quot;colour&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-193"><strong>match(&quot;colou-r&quot;,&quot;colour&quot;);</strong> returns <strong>1</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="82119-194">[]</span><span class="sxs-lookup"><span data-stu-id="82119-194">[]</span></span></td>
<td><span data-ttu-id="82119-195">かっこで囲まれた任意の文字と 1 つの文字を照合します。</span><span class="sxs-lookup"><span data-stu-id="82119-195">Matches a single character with any character that is enclosed in the brackets.</span></span> <span data-ttu-id="82119-196">文字の範囲は、マイナス記号 (-) で区切られた 2 つの文字で指定することができます。</span><span class="sxs-lookup"><span data-stu-id="82119-196">A range of characters can be specified by two characters that are separated by a minus sign (-).</span></span> <span data-ttu-id="82119-197">たとえば、<strong>[a-z]</strong>は a ～ z のすべての文字に一致し、<strong>[0-9]</strong> は数字と一致し、さらに <strong>[0-9a-f]</strong> は 16 進数に一致します。</span><span class="sxs-lookup"><span data-stu-id="82119-197">For example, <strong>[a-z]</strong> matches all letters between a and z, <strong>[0-9]</strong> matches a digit, and <strong>[0-9a-f]</strong> matches a hexadecimal digit.</span></span> <span data-ttu-id="82119-198">例</span><span class="sxs-lookup"><span data-stu-id="82119-198">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-199"><strong>照合 (&quot;[abc]&quot;、&quot;apple&quot;);</strong> は、&quot;apple.&quot; の a が一致するので<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-199"><strong>match(&quot;[abc]&quot;,&quot;apple&quot;);</strong> returns <strong>1</strong>, because it matches the a in &quot;apple.&quot;</span></span></li>
<li><span data-ttu-id="82119-200"><strong>照合 (&quot;[abc]&quot;、&quot;kiwi&quot;);</strong> は、&quot;kiwi&quot; に a、b、c が含まれていないため、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-200"><strong>match(&quot;[abc]&quot;,&quot;kiwi&quot;);</strong> returns <strong>0</strong>, because &quot;kiwi&quot; doesn&#39;t contain an a, b, or c.</span></span></li>
<li><span data-ttu-id="82119-201"><strong>照合 (&quot;gr[ae]y&quot;、&quot;grey&quot;);</strong> は、1 を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-201"><strong>match(&quot;gr[ae]y&quot;,&quot;grey&quot;);</strong> returns 1.</span></span> <span data-ttu-id="82119-202">この式は、&quot;灰色&quot;と一致します。</span><span class="sxs-lookup"><span data-stu-id="82119-202">This expression also matches &quot;gray.&quot;</span></span></li>
<li><span data-ttu-id="82119-203"><strong>照合 (&quot;gr[ae]y&quot;、&quot;graey&quot;);</strong> は、&quot;gr&quot; と &quot;y&quot; の間で、1 つの文字だけが一致したため、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-203"><strong>match(&quot;gr[ae]y&quot;,&quot;graey&quot;);</strong> returns <strong>0</strong>, because only one character between &quot;gr&quot; and &quot;y&quot; is matched.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="82119-204">[^]</span><span class="sxs-lookup"><span data-stu-id="82119-204">[^]</span></span></td>
<td><span data-ttu-id="82119-205">かっこで囲まれたテキスト内で最初の文字が曲折記号 (^) の場合は、かっこで囲まれた文字を除き、式はすべての文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="82119-205">If the first character in the text that is enclosed in brackets is a circumflex (^), the expression matches all characters except the characters that are enclosed in the brackets.</span></span> <span data-ttu-id="82119-206">例</span><span class="sxs-lookup"><span data-stu-id="82119-206">Examples:</span></span>
<ul>
<li><span data-ttu-id="82119-207"><strong>照合 (&quot;[^bc]at&quot;、&quot;bat&quot;);</strong> は、<strong>0</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-207"><strong>match(&quot;[^bc]at&quot;,&quot;bat&quot;);</strong> returns <strong>0</strong>.</span></span></li>
<li><span data-ttu-id="82119-208"><strong>照合 (&quot;[^bc]at&quot;、&quot;hat&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-208"><strong>match(&quot;[^bc]at&quot;,&quot;hat&quot;);</strong> returns <strong>1</strong>.</span></span></li>
<li><span data-ttu-id="82119-209"><strong>照合 (&quot;[^abc]&quot;、&quot;bat&quot;);</strong> は、<strong>1</strong> を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-209"><strong>match(&quot;[^abc]&quot;,&quot;bat&quot;);</strong> returns <strong>1</strong>.</span></span> <span data-ttu-id="82119-210">a、b、または c 以外は一致します。</span><span class="sxs-lookup"><span data-stu-id="82119-210">Anything except a, b, or c is matched.</span></span> <span data-ttu-id="82119-211">したがって、t が一致します。</span><span class="sxs-lookup"><span data-stu-id="82119-211">Therefore, the t is matched.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="stralpha"></a><span data-ttu-id="82119-212">strAlpha</span><span class="sxs-lookup"><span data-stu-id="82119-212">strAlpha</span></span>
<span data-ttu-id="82119-213">文字列の英数字のみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="82119-213">Copies only the alphanumeric characters from a string.</span></span>

    str strAlpha(str _text)

### <a name="parameters"></a><span data-ttu-id="82119-214">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-214">Parameters</span></span>

| <span data-ttu-id="82119-215">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-215">Parameter</span></span> | <span data-ttu-id="82119-216">説明</span><span class="sxs-lookup"><span data-stu-id="82119-216">Description</span></span>              |
|-----------|--------------------------|
| <span data-ttu-id="82119-217">\_テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-217">\_text</span></span>    | <span data-ttu-id="82119-218">コピー元の文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-218">The string to copy from.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-219">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-219">Return value</span></span>

<span data-ttu-id="82119-220">指定した文字列からのすべての英数字を含む新しい文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-220">A new string that contains all the alphanumeric characters from the specified string.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-221">備考</span><span class="sxs-lookup"><span data-stu-id="82119-221">Remarks</span></span>

<span data-ttu-id="82119-222">たとえば、**strAlpha(「2+2=5 これで正しいですか」)** は文字列 **225isthiscorrect** を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-222">For example, **strAlpha("2+2=5 is this correct?")** returns the string **225isthiscorrect**.</span></span>

### <a name="example"></a><span data-ttu-id="82119-223">例</span><span class="sxs-lookup"><span data-stu-id="82119-223">Example</span></span>

    static void strAlphaExample(Args _arg)
    {
            str s;
            ;
            s = strAlpha("?a*bc123.");
            print s;
            pause;
    }

## <a name="strcmp"></a><span data-ttu-id="82119-224">strCmp</span><span class="sxs-lookup"><span data-stu-id="82119-224">strCmp</span></span>
<span data-ttu-id="82119-225">2 つの文字列を比較します。</span><span class="sxs-lookup"><span data-stu-id="82119-225">Compares two text strings.</span></span>

    int strCmp(str text1, str text2)

### <a name="parameters"></a><span data-ttu-id="82119-226">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-226">Parameters</span></span>

| <span data-ttu-id="82119-227">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-227">Parameter</span></span> | <span data-ttu-id="82119-228">説明</span><span class="sxs-lookup"><span data-stu-id="82119-228">Description</span></span>        |
|-----------|--------------------|
| <span data-ttu-id="82119-229">text1</span><span class="sxs-lookup"><span data-stu-id="82119-229">text1</span></span>     | <span data-ttu-id="82119-230">最初の文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-230">The first string.</span></span>  |
| <span data-ttu-id="82119-231">text2</span><span class="sxs-lookup"><span data-stu-id="82119-231">text2</span></span>     | <span data-ttu-id="82119-232">2 番目の文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-232">The second string.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-233">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-233">Return value</span></span>

<span data-ttu-id="82119-234">2 つの文字列が同じ場合は **0**、最初の文字列が以前に並べ替えられている場合は **1**、2 つ目の文字列が以前に並べ替えられている場合は **-1** です。</span><span class="sxs-lookup"><span data-stu-id="82119-234">**0** if the two strings are identical, **1** if the first string sorts earlier, or **-1** if the second string sorts earlier.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-235">備考</span><span class="sxs-lookup"><span data-stu-id="82119-235">Remarks</span></span>

<span data-ttu-id="82119-236">このメソッドで実行される比較では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="82119-236">The comparison performed by this method is case-sensitive.</span></span>

    print strCmp("abc", "abc"); //Returns the value 0.
    print strCmp("abc", "ABC"); //Returns the value 1.
    print strCmp("aaa", "bbb"); //Returns the value -1.
    print strCmp("ccc", "bbb"); //Returns the value 1.

## <a name="strcolseq"></a><span data-ttu-id="82119-237">strColSeq</span><span class="sxs-lookup"><span data-stu-id="82119-237">strColSeq</span></span>
<span data-ttu-id="82119-238">すべての大文字を小文字に変換し、アクセントのあるすべての文字を、対応するアクセントのない小文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="82119-238">Converts all uppercase characters to lowercase characters, and converts all characters that have accents to the corresponding unaccented lowercase characters.</span></span>

    str strColSeq(str text)

### <a name="parameters"></a><span data-ttu-id="82119-239">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-239">Parameters</span></span>

| <span data-ttu-id="82119-240">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-240">Parameter</span></span> | <span data-ttu-id="82119-241">説明</span><span class="sxs-lookup"><span data-stu-id="82119-241">Description</span></span>                                     |
|-----------|-------------------------------------------------|
| <span data-ttu-id="82119-242">テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-242">text</span></span>      | <span data-ttu-id="82119-243">文字をコピーして変換する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-243">The string to copy and convert characters from.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-244">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-244">Return value</span></span>

<span data-ttu-id="82119-245">変換されたテキスト文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-245">The converted text string.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-246">備考</span><span class="sxs-lookup"><span data-stu-id="82119-246">Remarks</span></span>

<span data-ttu-id="82119-247">**strColSeq** 関数は、下位互換性のために存在します。</span><span class="sxs-lookup"><span data-stu-id="82119-247">The **strColSeq** function exists for backward-compatibility purposes.</span></span> <span data-ttu-id="82119-248">この関数は、次の西ヨーロッパの文字のマッピングのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="82119-248">This function supports only the mapping for the following Western European characters:</span></span>

-   <span data-ttu-id="82119-249">AàáâãäÀÁÂÃÄBCçÇDEèéêëÈÉÊËFGHIìíîïÌÍÎÏJKLMNñÑOòóôõöÒÓÔÕÖPQRSTUùúûüÙÚÛÜVWXYýÝZæøåÆØÅ</span><span class="sxs-lookup"><span data-stu-id="82119-249">AàáâãäÀÁÂÃÄBCçÇDEèéêëÈÉÊËFGHIìíîïÌÍÎÏJKLMNñÑOòóôõöÒÓÔÕÖPQRSTUùúûüÙÚÛÜVWXYýÝZæøåÆØÅ</span></span>
-   <span data-ttu-id="82119-250">aaaaaaaaaaabcccdeeeeeeeeefghiiiiiiiiijklmnnnooooooooooopqrstuuuuuuuuuvwxyyyz~¦Ç~¦Ç</span><span class="sxs-lookup"><span data-stu-id="82119-250">aaaaaaaaaaabcccdeeeeeeeeefghiiiiiiiiijklmnnnooooooooooopqrstuuuuuuuuuvwxyyyz~¦Ç~¦Ç</span></span>

<span data-ttu-id="82119-251">Unicode 互換機能は、**DLL** および **DLLFunc** クラスを通じて Win32 LCMapString アプリケーション プログラミング インターフェイス (API) を使用します。</span><span class="sxs-lookup"><span data-stu-id="82119-251">For Unicode-compliant functionality, use the Win32 LCMapString application programming interface (API) via the **DLL** and **DLLFunc** classes.</span></span>

### <a name="example"></a><span data-ttu-id="82119-252">例</span><span class="sxs-lookup"><span data-stu-id="82119-252">Example</span></span>

<span data-ttu-id="82119-253">次の例では、**abcdeabcde** を出力します。</span><span class="sxs-lookup"><span data-stu-id="82119-253">The following example prints **abcdeabcde**.</span></span>

    static void strColSeqExample(Args _arg)
    {
            ;
            print strColSeq("");
            pause;
    }

## <a name="strdel"></a><span data-ttu-id="82119-254">strDel</span><span class="sxs-lookup"><span data-stu-id="82119-254">strDel</span></span>
<span data-ttu-id="82119-255">指定されたサブ文字列が削除された文字列のコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="82119-255">Creates a copy of a string, from which the specified substring is removed.</span></span>

    str strDel(str _text, int _position, int _number)

### <a name="parameters"></a><span data-ttu-id="82119-256">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-256">Parameters</span></span>

| <span data-ttu-id="82119-257">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-257">Parameter</span></span>  | <span data-ttu-id="82119-258">説明</span><span class="sxs-lookup"><span data-stu-id="82119-258">Description</span></span>                                                                                                                                                                                                                      |
|------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="82119-259">\_テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-259">\_text</span></span>     | <span data-ttu-id="82119-260">コピー元の文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-260">The string to copy from.</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="82119-261">\_職位</span><span class="sxs-lookup"><span data-stu-id="82119-261">\_position</span></span> | <span data-ttu-id="82119-262">コピー操作時に文字の無視を開始する位置。</span><span class="sxs-lookup"><span data-stu-id="82119-262">The position at which to begin ignoring characters during the copy operation.</span></span>                                                                                                                                                    |
| <span data-ttu-id="82119-263">\_数値</span><span class="sxs-lookup"><span data-stu-id="82119-263">\_number</span></span>   | <span data-ttu-id="82119-264">無視する文字数。</span><span class="sxs-lookup"><span data-stu-id="82119-264">The number of characters to ignore.</span></span> <span data-ttu-id="82119-265">*\_番号*パラメーターの前のマイナス記号は、*\_位置*にある文字の前の*\_番号*–1 文字が*\_位置*にある文字と一緒に削除される必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="82119-265">A minus sign in front of the *\_number* parameter indicates that *\_number*–1 characters before the character at *\_position* should be removed together with the character at *\_position*.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-266">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-266">Return value</span></span>

<span data-ttu-id="82119-267">文字列からコピーされる残りの文字。</span><span class="sxs-lookup"><span data-stu-id="82119-267">The remaining characters that are copied from the string.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-268">備考</span><span class="sxs-lookup"><span data-stu-id="82119-268">Remarks</span></span>

<span data-ttu-id="82119-269">**strDel** 関数は、**substr** 関数を補完します。</span><span class="sxs-lookup"><span data-stu-id="82119-269">The **strDel** function is complementary to the **substr** function.</span></span>

    strDel("ABCDEFGH",2,3); //Returns the string "AEFGH".
    strDel("ABCDEFGH",4,3); //Returns the string "ABCGH".

## <a name="strfind"></a><span data-ttu-id="82119-270">strFind</span><span class="sxs-lookup"><span data-stu-id="82119-270">strFind</span></span>
<span data-ttu-id="82119-271">指定された文字のいずれかの 1 番目の文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="82119-271">Searches a string for the first occurrence of one of the specified characters.</span></span>

    int strFind(str _text, str _characters, int _position, int _number)

### <a name="parameters"></a><span data-ttu-id="82119-272">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-272">Parameters</span></span>

| <span data-ttu-id="82119-273">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-273">Parameter</span></span>    | <span data-ttu-id="82119-274">説明</span><span class="sxs-lookup"><span data-stu-id="82119-274">Description</span></span>                                                                                                |
|--------------|------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="82119-275">\_テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-275">\_text</span></span>       | <span data-ttu-id="82119-276">検索する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-276">The string to search.</span></span>                                                                                      |
| <span data-ttu-id="82119-277">\_文字</span><span class="sxs-lookup"><span data-stu-id="82119-277">\_characters</span></span> | <span data-ttu-id="82119-278">検索する文字。</span><span class="sxs-lookup"><span data-stu-id="82119-278">The characters to search for.</span></span>                                                                              |
| <span data-ttu-id="82119-279">\_職位</span><span class="sxs-lookup"><span data-stu-id="82119-279">\_position</span></span>   | <span data-ttu-id="82119-280">検索を開始する文字列内の位置。</span><span class="sxs-lookup"><span data-stu-id="82119-280">The position in the string where the search begins.</span></span>                                                        |
| <span data-ttu-id="82119-281">\_数値</span><span class="sxs-lookup"><span data-stu-id="82119-281">\_number</span></span>     | <span data-ttu-id="82119-282">検索の方向と文字列内で検索する位置の数を示す符号付き番号。</span><span class="sxs-lookup"><span data-stu-id="82119-282">A signed number that indicates the direction of the search and how many positions to search in the string.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-283">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-283">Return value</span></span>

<span data-ttu-id="82119-284">指定された文字の 1 つが最初に現れる位置の値。</span><span class="sxs-lookup"><span data-stu-id="82119-284">The value of the position of the first occurrence of one of the specified characters.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-285">備考</span><span class="sxs-lookup"><span data-stu-id="82119-285">Remarks</span></span>

<span data-ttu-id="82119-286">文字列の先頭から最後まで検索するには、*\_位置*パラメーターの値として **1** を使用します。</span><span class="sxs-lookup"><span data-stu-id="82119-286">To search from the beginning of the string to the end, use **1** as the value of the *\_position* parameter.</span></span> <span data-ttu-id="82119-287">*\_番号*パラメーターの値がマイナスである場合、システムは指定された位置から後方に文字数を検索します。</span><span class="sxs-lookup"><span data-stu-id="82119-287">If the value of the *\_number* parameter is negative, the system searches the number of characters backward from the specified position.</span></span> <span data-ttu-id="82119-288">検索では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="82119-288">The search isn't case-sensitive.</span></span> <span data-ttu-id="82119-289">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="82119-289">Here is an example.</span></span>

    strFind("ABCDEFGHIJ","KHD",1,10); //Returns the value 4 (the position where "D" was found).
    strFind("ABCDEFGHIJ","KHD",10,-10); //Returns the value 8 (the position where "H" was found).

<span data-ttu-id="82119-290">**strFind** 関数は、**strNFind** 関数を補完します。</span><span class="sxs-lookup"><span data-stu-id="82119-290">The **strFind** function is complementary to the **strNFind** function.</span></span>

## <a name="strfmt"></a><span data-ttu-id="82119-291">strFmt</span><span class="sxs-lookup"><span data-stu-id="82119-291">strFmt</span></span>
<span data-ttu-id="82119-292">指定された文字列を書式設定し、すべての n を n 番目の引数に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="82119-292">Formats the specified string and substitutes any occurrences of n with the nth argument.</span></span>

    str strFmt(str _string, ...)

### <a name="parameters"></a><span data-ttu-id="82119-293">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-293">Parameters</span></span>

| <span data-ttu-id="82119-294">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-294">Parameter</span></span> | <span data-ttu-id="82119-295">説明</span><span class="sxs-lookup"><span data-stu-id="82119-295">Description</span></span>            |
|-----------|------------------------|
| <span data-ttu-id="82119-296">\_文字列</span><span class="sxs-lookup"><span data-stu-id="82119-296">\_string</span></span>  | <span data-ttu-id="82119-297">フォーマットする文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-297">The strings to format.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-298">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-298">Return value</span></span>

<span data-ttu-id="82119-299">書式設定された文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-299">The formatted string.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-300">備考</span><span class="sxs-lookup"><span data-stu-id="82119-300">Remarks</span></span>

<span data-ttu-id="82119-301">パラメーターに引数が指定されない場合は、文字列内では "%n" として返されます。</span><span class="sxs-lookup"><span data-stu-id="82119-301">If an argument isn't provided for a parameter, the parameter will be returned as "%n" in the string.</span></span> <span data-ttu-id="82119-302">**実数**型の値の文字列変換では、小数点第 2 位に制限されます。</span><span class="sxs-lookup"><span data-stu-id="82119-302">The string conversion of values of the **real** type is limited to two decimal places.</span></span> <span data-ttu-id="82119-303">値は丸められ、切り捨てられません。</span><span class="sxs-lookup"><span data-stu-id="82119-303">Values are rounded, not truncated.</span></span> <span data-ttu-id="82119-304">Microsoft .NET Framework の **System.String::Format** メソッドは、例に示すように、追加機能を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="82119-304">The **System.String::Format** method from the Microsoft .NET Framework can be used to gain additional functionality, as shown in the example.</span></span>

### <a name="example"></a><span data-ttu-id="82119-305">例</span><span class="sxs-lookup"><span data-stu-id="82119-305">Example</span></span>

    static void strFmtExampleJob(Args _arg)
    {
            System.Double sysDouble;
            real r = 8.3456789;
            int  i = 42;
            utcDateTime utc = str2DateTime("2008-01-16 13:44:55" ,321); // 321 == YMD.
            str  s;
            ;
            s = strFmt("real = %1, int = %2, utcDateTime = %3, [%4]", r, i, utc);
            info("X1:  " + s);
            //
            sysDouble = r;
            s = System.String::Format("{0:##.####}", sysDouble);
            info("N1:  " + s);
            //
            s = System.String::Format("{0,6:C}", sysDouble); // $
            info("N2:  " + s);
            /**********  Actual Infolog output
            Message (02:16:05 pm)
            X1:  real = 8.35, int = 42, utcDateTime = 1/16/2008 01:44:55 pm, [%4]
            N1:  8.3457
            N2:   $8.35
            **********/
    }

## <a name="strins"></a><span data-ttu-id="82119-306">strIns</span><span class="sxs-lookup"><span data-stu-id="82119-306">strIns</span></span>
<span data-ttu-id="82119-307">1 つの文字列を別の文字列に挿入して文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="82119-307">Builds a string by inserting one string into another.</span></span>

    str strIns(str _text1, str _text2, int _position)

### <a name="parameters"></a><span data-ttu-id="82119-308">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-308">Parameters</span></span>

| <span data-ttu-id="82119-309">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-309">Parameter</span></span>  | <span data-ttu-id="82119-310">説明</span><span class="sxs-lookup"><span data-stu-id="82119-310">Description</span></span>                                                                                          |
|------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="82119-311">\_text1</span><span class="sxs-lookup"><span data-stu-id="82119-311">\_text1</span></span>    | <span data-ttu-id="82119-312">他の文字列を挿入する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-312">The string to insert the other string into.</span></span>                                                          |
| <span data-ttu-id="82119-313">\_text2</span><span class="sxs-lookup"><span data-stu-id="82119-313">\_text2</span></span>    | <span data-ttu-id="82119-314">他の文字列に挿入する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-314">The string to insert into the other string.</span></span>                                                          |
| <span data-ttu-id="82119-315">\_職位</span><span class="sxs-lookup"><span data-stu-id="82119-315">\_position</span></span> | <span data-ttu-id="82119-316">出力文字列内への*\_text2* パラメーターの最初の文字の配置位置。</span><span class="sxs-lookup"><span data-stu-id="82119-316">The position where the first character of the *\_text2* parameter should occur in the output string.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-317">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-317">Return value</span></span>

<span data-ttu-id="82119-318">結合された。</span><span class="sxs-lookup"><span data-stu-id="82119-318">The combined text string.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-319">備考</span><span class="sxs-lookup"><span data-stu-id="82119-319">Remarks</span></span>

<span data-ttu-id="82119-320">**strIns** 関数は、**strDel** 関数を補完します。</span><span class="sxs-lookup"><span data-stu-id="82119-320">The **strIns** function is complementary to the **strDel** function.</span></span> <span data-ttu-id="82119-321">*\_位置*パラメーターの値が元の文字列より長くなる場合、挿入する文字列が元の文字列の末尾に追加されます。</span><span class="sxs-lookup"><span data-stu-id="82119-321">If the value of the *\_position* parameter is more than the length of the original string, the string to insert is appended to the end of the original string.</span></span>

    strIns("ABFGH","CDE",3); //Returns the string "ABCDEFGH".
    strIns("ABCD","EFGH",10); //Returns the string "ABCDEFGH".

## <a name="strkeep"></a><span data-ttu-id="82119-322">strKeep</span><span class="sxs-lookup"><span data-stu-id="82119-322">strKeep</span></span>
<span data-ttu-id="82119-323">2 番目の入力文字列で指定する最初の入力文字列の文字のみを使用して文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="82119-323">Builds a string by using only the characters from the first input string that the second input string specifies should be kept.</span></span>

    str strKeep(str _text1, str _text2)

### <a name="parameters"></a><span data-ttu-id="82119-324">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-324">Parameters</span></span>

| <span data-ttu-id="82119-325">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-325">Parameter</span></span> | <span data-ttu-id="82119-326">説明</span><span class="sxs-lookup"><span data-stu-id="82119-326">Description</span></span>                                                                         |
|-----------|-------------------------------------------------------------------------------------|
| <span data-ttu-id="82119-327">\_text1</span><span class="sxs-lookup"><span data-stu-id="82119-327">\_text1</span></span>   | <span data-ttu-id="82119-328">出力文字列を作成するために使用できる文字を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-328">The string that contains the characters that can be used to build an output string.</span></span> |
| <span data-ttu-id="82119-329">\_text2</span><span class="sxs-lookup"><span data-stu-id="82119-329">\_text2</span></span>   | <span data-ttu-id="82119-330">出力文字列に保持する文字を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-330">The string that specifies which characters to keep for the output string.</span></span>           |

### <a name="return-value"></a><span data-ttu-id="82119-331">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-331">Return value</span></span>

<span data-ttu-id="82119-332">保存されている文字の文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-332">A string of the characters that are kept.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-333">備考</span><span class="sxs-lookup"><span data-stu-id="82119-333">Remarks</span></span>

    strKeep("ABBCDDEFGHB","BCD"); //Returns the string "BBCDDB".
    strKeep("abcZcba","bc") //Returns the string "bccb".

<span data-ttu-id="82119-334">**strKeep** 関数は、**strRem** 関数を補完します。</span><span class="sxs-lookup"><span data-stu-id="82119-334">The **strKeep** function is complementary to the **strRem** function.</span></span>

## <a name="strlen"></a><span data-ttu-id="82119-335">strLen</span><span class="sxs-lookup"><span data-stu-id="82119-335">strLen</span></span>
<span data-ttu-id="82119-336">指定した文字列の長さを計算します。</span><span class="sxs-lookup"><span data-stu-id="82119-336">Calculates the length of the specified string.</span></span>

    int strLen(str text)

### <a name="parameters"></a><span data-ttu-id="82119-337">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-337">Parameters</span></span>

| <span data-ttu-id="82119-338">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-338">Parameter</span></span> | <span data-ttu-id="82119-339">説明</span><span class="sxs-lookup"><span data-stu-id="82119-339">Description</span></span>                            |
|-----------|----------------------------------------|
| <span data-ttu-id="82119-340">テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-340">text</span></span>      | <span data-ttu-id="82119-341">長さを計算する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-341">The string to calculate the length of.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-342">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-342">Return value</span></span>

<span data-ttu-id="82119-343">指定した文字列の長さ。</span><span class="sxs-lookup"><span data-stu-id="82119-343">The length of the specified string.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-344">備考</span><span class="sxs-lookup"><span data-stu-id="82119-344">Remarks</span></span>

    strLen("ABC"); //Returns the value 3.
    strLen("ABCDEFGHIJ"); //Returns the value 10.

## <a name="strline"></a><span data-ttu-id="82119-345">strLine</span><span class="sxs-lookup"><span data-stu-id="82119-345">strLine</span></span>
<span data-ttu-id="82119-346">複数の行にまたがる文字列から 1 つの行を取得します。</span><span class="sxs-lookup"><span data-stu-id="82119-346">Retrieves a single line from a string that spans multiple lines.</span></span>

    str strLine(str string, int count)

### <a name="parameters"></a><span data-ttu-id="82119-347">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-347">Parameters</span></span>

| <span data-ttu-id="82119-348">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-348">Parameter</span></span> | <span data-ttu-id="82119-349">説明</span><span class="sxs-lookup"><span data-stu-id="82119-349">Description</span></span>                              |
|-----------|------------------------------------------|
| <span data-ttu-id="82119-350">string</span><span class="sxs-lookup"><span data-stu-id="82119-350">string</span></span>    | <span data-ttu-id="82119-351">複数の明細行にまたがる文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-351">A string that might span multiple lines.</span></span> |
| <span data-ttu-id="82119-352">カウント</span><span class="sxs-lookup"><span data-stu-id="82119-352">count</span></span>     | <span data-ttu-id="82119-353">返す線のオフセット。</span><span class="sxs-lookup"><span data-stu-id="82119-353">The offset of the line to return.</span></span>        |

### <a name="return-value"></a><span data-ttu-id="82119-354">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-354">Return value</span></span>

<span data-ttu-id="82119-355">*文字列*パラメーターで指定された文字列のコピーされた明細行です。</span><span class="sxs-lookup"><span data-stu-id="82119-355">A copied line of the string that is specified by the *string* parameter.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-356">備考</span><span class="sxs-lookup"><span data-stu-id="82119-356">Remarks</span></span>

<span data-ttu-id="82119-357">文字列の最初の行には 0 のオフセットがあります。</span><span class="sxs-lookup"><span data-stu-id="82119-357">The first line of the string has an offset of 0.</span></span> <span data-ttu-id="82119-358">文字列に *n* または *rn* 文字を埋め込むことにより、複数行を1 つの文字列に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="82119-358">You can assign multiple lines to one string by embedding the *n* or *rn* characters in the string.</span></span> <span data-ttu-id="82119-359">また、開始引用符の直前にアット マーク (@) を使用することができ、Enter キーを使用して文字列値の一部を X++ コード エディタの複数の行に分散させることができます。</span><span class="sxs-lookup"><span data-stu-id="82119-359">Additionally, you can use the at sign (@) immediately before the opening quotation mark and use the Enter key to spread parts of the string value over multiple lines in the X++ code editor.</span></span>

### <a name="example"></a><span data-ttu-id="82119-360">例</span><span class="sxs-lookup"><span data-stu-id="82119-360">Example</span></span>

    static void strLineExample(Args _arg)
    {
            str mytxt = "first-linensecond-linenlast-line";
            ;
            // Prints "second-line".
            print strLine(mytxt,1);
            // Prints "last-line".
            print strLine(mytxt,2);
            pause;
    }

## <a name="strltrim"></a><span data-ttu-id="82119-361">strLTrim</span><span class="sxs-lookup"><span data-stu-id="82119-361">strLTrim</span></span>
<span data-ttu-id="82119-362">テキスト文字列から先行する空白を削除します。</span><span class="sxs-lookup"><span data-stu-id="82119-362">Removes leading blanks from a text string.</span></span>

    str strLTrim(str text)

### <a name="parameters"></a><span data-ttu-id="82119-363">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-363">Parameters</span></span>

| <span data-ttu-id="82119-364">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-364">Parameter</span></span> | <span data-ttu-id="82119-365">説明</span><span class="sxs-lookup"><span data-stu-id="82119-365">Description</span></span>                                   |
|-----------|-----------------------------------------------|
| <span data-ttu-id="82119-366">テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-366">text</span></span>      | <span data-ttu-id="82119-367">先頭の空白を削除する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-367">The string to delete the leading blanks from.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-368">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-368">Return value</span></span>

<span data-ttu-id="82119-369">先頭の空白が削除されたテキストに相当する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-369">The string equivalent for the text that leading blanks have been removed from.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-370">備考</span><span class="sxs-lookup"><span data-stu-id="82119-370">Remarks</span></span>

<span data-ttu-id="82119-371">**strLTrim** 関数は、**strRTrim** 関数を補完します。</span><span class="sxs-lookup"><span data-stu-id="82119-371">The **strLTrim** function is complementary to the **strRTrim** function.</span></span>

### <a name="example"></a><span data-ttu-id="82119-372">例</span><span class="sxs-lookup"><span data-stu-id="82119-372">Example</span></span>

    // Returns the text string "ABC-DEFG".
    strLTrim("   ABC-DEFG");

## <a name="strlwr"></a><span data-ttu-id="82119-373">strLwr</span><span class="sxs-lookup"><span data-stu-id="82119-373">strLwr</span></span>
<span data-ttu-id="82119-374">指定された文字列のすべての文字を小文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="82119-374">Converts all letters in the specified string to lowercase.</span></span>

    str strLwr(str _text)

### <a name="parameters"></a><span data-ttu-id="82119-375">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-375">Parameters</span></span>

| <span data-ttu-id="82119-376">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-376">Parameter</span></span> | <span data-ttu-id="82119-377">説明</span><span class="sxs-lookup"><span data-stu-id="82119-377">Description</span></span>                         |
|-----------|-------------------------------------|
| <span data-ttu-id="82119-378">\_テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-378">\_text</span></span>    | <span data-ttu-id="82119-379">小文字に変換する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-379">The string to convert to lowercase.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-380">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-380">Return value</span></span>

<span data-ttu-id="82119-381">小文字のみを含んでいる指定された文字列のコピーです。</span><span class="sxs-lookup"><span data-stu-id="82119-381">A copy of the specified string that contains only lowercase letter.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-382">備考</span><span class="sxs-lookup"><span data-stu-id="82119-382">Remarks</span></span>

<span data-ttu-id="82119-383">**strLwr** 関数は、**strUpr** 関数を補完します。</span><span class="sxs-lookup"><span data-stu-id="82119-383">The **strLwr** function is complementary to the **strUpr** function.</span></span> <span data-ttu-id="82119-384">**strLwr** 関数は、Win32 API で **LCMapString** 関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="82119-384">The **strLwr** function uses the **LCMapString** function in the Win32 API.</span></span>

### <a name="example"></a><span data-ttu-id="82119-385">例</span><span class="sxs-lookup"><span data-stu-id="82119-385">Example</span></span>

    static void strLwrExample(Args _args)
    {
            // Returns the text string "abcdd55efghij".
            print strLwr("Abcdd55EFGHIJ");
            pause;
    }

## <a name="strnfind"></a><span data-ttu-id="82119-386">strNFind</span><span class="sxs-lookup"><span data-stu-id="82119-386">strNFind</span></span>
<span data-ttu-id="82119-387">指定した文字リストに含まれていない文字の 1 番目の文字列の一部を検索します。</span><span class="sxs-lookup"><span data-stu-id="82119-387">Searches part of a text string for the first occurrence of a character that isn't included in the specified list of characters.</span></span>

    int strNFind(str _text, str _characters, int _position, int _number)

### <a name="parameters"></a><span data-ttu-id="82119-388">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-388">Parameters</span></span>

| <span data-ttu-id="82119-389">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-389">Parameter</span></span>    | <span data-ttu-id="82119-390">説明</span><span class="sxs-lookup"><span data-stu-id="82119-390">Description</span></span>                                                                                                                                                                                                     |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="82119-391">\_テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-391">\_text</span></span>       | <span data-ttu-id="82119-392">検索するテキスト文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-392">The text string to search.</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="82119-393">\_文字</span><span class="sxs-lookup"><span data-stu-id="82119-393">\_characters</span></span> | <span data-ttu-id="82119-394">検索から除外する文字のリスト。</span><span class="sxs-lookup"><span data-stu-id="82119-394">The list of characters to exclude from the search.</span></span>                                                                                                                                                              |
| <span data-ttu-id="82119-395">\_職位</span><span class="sxs-lookup"><span data-stu-id="82119-395">\_position</span></span>   | <span data-ttu-id="82119-396">検索を開始する文字列内の位置。</span><span class="sxs-lookup"><span data-stu-id="82119-396">The position in the string at which to begin the search.</span></span>                                                                                                                                                        |
| <span data-ttu-id="82119-397">\_数値</span><span class="sxs-lookup"><span data-stu-id="82119-397">\_number</span></span>     | <span data-ttu-id="82119-398">検索の方向と検索する位置の数を示す符号付き番号。</span><span class="sxs-lookup"><span data-stu-id="82119-398">A signed number that indicates the direction of the search and how many positions to search.</span></span> <span data-ttu-id="82119-399">マイナス記号が*\_番号*に先行する場合、システムでは*\_位置*の逆順で*\_番号*文字が検索されます。</span><span class="sxs-lookup"><span data-stu-id="82119-399">If a minus sign precedes *\_number*, the system searches *\_number* characters in reverse order from *\_position*.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-400">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-400">Return value</span></span>

<span data-ttu-id="82119-401">*\_characters* パラメーターによって指定されていない文字の 1 番目の位置。</span><span class="sxs-lookup"><span data-stu-id="82119-401">The position of the first occurrence of a character that isn't specified by the *\_characters* parameter.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-402">備考</span><span class="sxs-lookup"><span data-stu-id="82119-402">Remarks</span></span>

<span data-ttu-id="82119-403">検索では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="82119-403">The search isn't case-sensitive.</span></span> <span data-ttu-id="82119-404">文字列の先頭から最後まで検索するには、*\_位置*パラメーターの値として **1** を使用します。</span><span class="sxs-lookup"><span data-stu-id="82119-404">To search from the beginning of the string to the end, use a value of **1** for the *\_position* parameter.</span></span> <span data-ttu-id="82119-405">マイナス記号が*\_番号*パラメーターの前にある場合、*\_位置*パラメーターで指定された位置から逆の順序で文字が検索されます。</span><span class="sxs-lookup"><span data-stu-id="82119-405">If a minus sign precedes the value of the *\_number* parameter, the characters will be searched in reverse order, starting from the position that is specified by the *\_position* parameter.</span></span>

    strNFind("ABCDEFGHIJ","ABCDHIJ",1,10); //Returns the value 5 (the position of "E");
    strNFind("CDEFGHIJ","CDEFGIJ",10,-10); //Returns the value 6 (the position of "H").
    strNFind("abcdef","abCdef",3,2) //Returns the value 0.
    strNFind("abcdef", "abcef",3,2) //Returns the value 4.

<span data-ttu-id="82119-406">**strNFind** 関数は、**strFind** 関数を補完します。</span><span class="sxs-lookup"><span data-stu-id="82119-406">The **strNFind** function is complementary to the **strFind** function.</span></span>

## <a name="strpoke"></a><span data-ttu-id="82119-407">strPoke</span><span class="sxs-lookup"><span data-stu-id="82119-407">strPoke</span></span>
<span data-ttu-id="82119-408">別の文字列で文字列の一部を上書きします。</span><span class="sxs-lookup"><span data-stu-id="82119-408">Overwrites part of a string with another string.</span></span>

    str strPoke(str _text1, str _text2, int _position)

### <a name="parameters"></a><span data-ttu-id="82119-409">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-409">Parameters</span></span>

| <span data-ttu-id="82119-410">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-410">Parameter</span></span>  | <span data-ttu-id="82119-411">説明</span><span class="sxs-lookup"><span data-stu-id="82119-411">Description</span></span>                                                                     |
|------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="82119-412">\_text1</span><span class="sxs-lookup"><span data-stu-id="82119-412">\_text1</span></span>    | <span data-ttu-id="82119-413">元の文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-413">The original string.</span></span>                                                            |
| <span data-ttu-id="82119-414">\_text2</span><span class="sxs-lookup"><span data-stu-id="82119-414">\_text2</span></span>    | <span data-ttu-id="82119-415">元の文字列の一部を置き換える文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-415">The string to replace part of the original string with.</span></span>                         |
| <span data-ttu-id="82119-416">\_職位</span><span class="sxs-lookup"><span data-stu-id="82119-416">\_position</span></span> | <span data-ttu-id="82119-417">文字の置き換えを開始する元の文字列の位置。</span><span class="sxs-lookup"><span data-stu-id="82119-417">The position of the original string at which to begin replacing the characters.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-418">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-418">Return value</span></span>

<span data-ttu-id="82119-419">新しい文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-419">The new string.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-420">備考</span><span class="sxs-lookup"><span data-stu-id="82119-420">Remarks</span></span>

<span data-ttu-id="82119-421">新しい文字列は、元の文字列より長くすることができます。</span><span class="sxs-lookup"><span data-stu-id="82119-421">The new string can be longer than the original string.</span></span> <span data-ttu-id="82119-422">ただし、*\_位置*パラメーターの値がを文字列の長さを超える場合、元の文字列が置換なしで返されます。</span><span class="sxs-lookup"><span data-stu-id="82119-422">However, if the value of the *\_position* parameter is more than the length of the string, the original string is returned without replacements.</span></span>

    strPoke("12345678","AAA",3); //Returns the string "12AAA678".
    strPoke("abcde","4567",4); //Returns the string "abc4567".
    strPoke("abcde", "4567", "10"); //Returns the string "abcde".

## <a name="strprompt"></a><span data-ttu-id="82119-423">strPrompt</span><span class="sxs-lookup"><span data-stu-id="82119-423">strPrompt</span></span>
<span data-ttu-id="82119-424">指定されたピリオド文字数の後に、コロンと空白文字が続く文字列を追加します。</span><span class="sxs-lookup"><span data-stu-id="82119-424">Appends a string with the specified number of period characters, followed by a colon and space character.</span></span>

    str strPrompt(str _string, _int len)

### <a name="parameters"></a><span data-ttu-id="82119-425">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-425">Parameters</span></span>

| <span data-ttu-id="82119-426">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-426">Parameter</span></span> | <span data-ttu-id="82119-427">説明</span><span class="sxs-lookup"><span data-stu-id="82119-427">Description</span></span>                             |
|-----------|-----------------------------------------|
| <span data-ttu-id="82119-428">\_文字列</span><span class="sxs-lookup"><span data-stu-id="82119-428">\_string</span></span>  | <span data-ttu-id="82119-429">元の文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-429">The original string.</span></span>                    |
| <span data-ttu-id="82119-430">\_len</span><span class="sxs-lookup"><span data-stu-id="82119-430">\_len</span></span>     | <span data-ttu-id="82119-431">文字列の最終的な長さ。</span><span class="sxs-lookup"><span data-stu-id="82119-431">The desired final length of the string.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-432">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-432">Return value</span></span>

<span data-ttu-id="82119-433">ユーザー入力のプロンプトのように見える文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-433">A string that looks like a prompt for user input.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-434">備考</span><span class="sxs-lookup"><span data-stu-id="82119-434">Remarks</span></span>

<span data-ttu-id="82119-435">特別な場合では、*\_len* パラメーターの値が元の文字列の長さより少し大きい場合のみ、末尾へのスペース追加に最も高い優先順位が付与されます。</span><span class="sxs-lookup"><span data-stu-id="82119-435">In atypical cases, where the value of the *\_len* parameter is only slightly more than the length of the original string, the highest precedence is given to adding the trailing space.</span></span> <span data-ttu-id="82119-436">次に、優先順位がコロンに指定されます。</span><span class="sxs-lookup"><span data-stu-id="82119-436">Next, precedence is given to the colon.</span></span> <span data-ttu-id="82119-437">期間には、最下位の優先順位が付けられます。</span><span class="sxs-lookup"><span data-stu-id="82119-437">The lowest precedence is given to the periods.</span></span> <span data-ttu-id="82119-438">*\_len* パラメーターの負の値は、後ろにスペースを付けた入力文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="82119-438">Negative values for the *\_len* parameter return the input string appended with a trailing space.</span></span>

    strPrompt("ab",-1); //Returns "ab ".
    strPrompt("ab",3); //Returns "ab ".
    strPrompt("ab",4); //Returns "ab: ".
    strPrompt("ab",5); //Returns "ab.: ".
    strPrompt("ab",6); //Returns "ab..: ".

### <a name="example"></a><span data-ttu-id="82119-439">例</span><span class="sxs-lookup"><span data-stu-id="82119-439">Example</span></span>

    static void JobStrPromptDemo(Args _args)
    {
            // Printed string is "[abc..: ]"
            print "[", strPrompt("abc", 7), "]";
            pause;
    }

## <a name="strrem"></a><span data-ttu-id="82119-440">strRem</span><span class="sxs-lookup"><span data-stu-id="82119-440">strRem</span></span>
<span data-ttu-id="82119-441">別の文字列から 1 つの文字列で指定されている文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="82119-441">Removes the characters that are specified in one string from another string.</span></span>

    str strRem(str text1, str text2)

### <a name="parameters"></a><span data-ttu-id="82119-442">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-442">Parameters</span></span>

| <span data-ttu-id="82119-443">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-443">Parameter</span></span> | <span data-ttu-id="82119-444">説明</span><span class="sxs-lookup"><span data-stu-id="82119-444">Description</span></span>                                       |
|-----------|---------------------------------------------------|
| <span data-ttu-id="82119-445">text1</span><span class="sxs-lookup"><span data-stu-id="82119-445">text1</span></span>     | <span data-ttu-id="82119-446">文字を削除する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-446">The string to remove characters from.</span></span>             |
| <span data-ttu-id="82119-447">text2</span><span class="sxs-lookup"><span data-stu-id="82119-447">text2</span></span>     | <span data-ttu-id="82119-448">出力文字列から除外する文字。</span><span class="sxs-lookup"><span data-stu-id="82119-448">The characters to exclude from the output string.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-449">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-449">Return value</span></span>

<span data-ttu-id="82119-450">元の文字列の残りのコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="82119-450">The remaining content of the original string.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-451">備考</span><span class="sxs-lookup"><span data-stu-id="82119-451">Remarks</span></span>

<span data-ttu-id="82119-452">この関数は、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="82119-452">This function is case-sensitive.</span></span>

    strRem("abcd_abcd","Bc"); //Returns the string "abd_abd".
    strRem("ABCDEFGABCDEFG","ACEG"); //Returns the string "BDFBDF".

<span data-ttu-id="82119-453"> この関数は、**strKeep** 関数を補完します。</span><span class="sxs-lookup"><span data-stu-id="82119-453">This function is complementary to the **strKeep** function.</span></span>

## <a name="strrep"></a><span data-ttu-id="82119-454">strRep</span><span class="sxs-lookup"><span data-stu-id="82119-454">strRep</span></span>
<span data-ttu-id="82119-455">文字の文字列を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="82119-455">Repeats a string of characters.</span></span>

    str strRep(str _text, str _number)

### <a name="parameters"></a><span data-ttu-id="82119-456">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-456">Parameters</span></span>

| <span data-ttu-id="82119-457">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-457">Parameter</span></span> | <span data-ttu-id="82119-458">説明</span><span class="sxs-lookup"><span data-stu-id="82119-458">Description</span></span>                               |
|-----------|-------------------------------------------|
| <span data-ttu-id="82119-459">\_テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-459">\_text</span></span>    | <span data-ttu-id="82119-460">クエリ返す文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-460">The string to repeat.</span></span>                     |
| <span data-ttu-id="82119-461">\_数値</span><span class="sxs-lookup"><span data-stu-id="82119-461">\_number</span></span>  | <span data-ttu-id="82119-462">文字列を繰り返す回数。</span><span class="sxs-lookup"><span data-stu-id="82119-462">The number of times to repeat the string.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-463">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-463">Return value</span></span>

<span data-ttu-id="82119-464">指定された回数が繰り返される元の文字列の内容を含む新しい文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-464">A new string that contains the contents of the original string that are repeated the specified number of times.</span></span>

### <a name="example"></a><span data-ttu-id="82119-465">例</span><span class="sxs-lookup"><span data-stu-id="82119-465">Example</span></span>

<span data-ttu-id="82119-466">次の例では、テキスト文字列 **ABABABABABAB** を出力します。</span><span class="sxs-lookup"><span data-stu-id="82119-466">The following example prints the text string **ABABABABABAB**.</span></span>

    static void strRepExample(Args _arg)
    {
            str strL;
            ;
            strL = strRep("AB",6);
            print strL;
            pause;
    }

## <a name="strrtrim"></a><span data-ttu-id="82119-467">strRTrim</span><span class="sxs-lookup"><span data-stu-id="82119-467">strRTrim</span></span>
<span data-ttu-id="82119-468">文字列の末尾から空白文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="82119-468">Removes the trailing space characters from the end of a string.</span></span>

    str strRTrim(str _text)

### <a name="parameters"></a><span data-ttu-id="82119-469">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-469">Parameters</span></span>

| <span data-ttu-id="82119-470">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-470">Parameter</span></span> | <span data-ttu-id="82119-471">説明</span><span class="sxs-lookup"><span data-stu-id="82119-471">Description</span></span>                                               |
|-----------|-----------------------------------------------------------|
| <span data-ttu-id="82119-472">\_テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-472">\_text</span></span>    | <span data-ttu-id="82119-473">末尾の空白文字を削除する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-473">The string to remove the trailing space characters from .</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-474">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-474">Return value</span></span>

<span data-ttu-id="82119-475">末尾に空白文字が含まれていない指定の文字列のコピーです。</span><span class="sxs-lookup"><span data-stu-id="82119-475">A copy of the specified string that doesn't include trailing space characters.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-476">備考</span><span class="sxs-lookup"><span data-stu-id="82119-476">Remarks</span></span>

    strRTrim("ABC-DEFG- "); //Returns the string "ABC-DEFG-".
    strRTrim(" CD "); //Returns " CD".

<span data-ttu-id="82119-477">**strRTrim** 関数は、**strLTrim** 関数を補完します。</span><span class="sxs-lookup"><span data-stu-id="82119-477">The **strRTrim** function is complementary to the **strLTrim** function.</span></span>

## <a name="strscan"></a><span data-ttu-id="82119-478">strScan</span><span class="sxs-lookup"><span data-stu-id="82119-478">strScan</span></span>
<span data-ttu-id="82119-479">別の文字列と一致する文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="82119-479">Searches a text string for an occurrence of another string.</span></span>

    int strScan(str _text1, str _text2, int _position, int _number)

### <a name="parameters"></a><span data-ttu-id="82119-480">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-480">Parameters</span></span>

| <span data-ttu-id="82119-481">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-481">Parameter</span></span>  | <span data-ttu-id="82119-482">説明</span><span class="sxs-lookup"><span data-stu-id="82119-482">Description</span></span>                                                                                                                                                                                                                   |
|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="82119-483">\_text1</span><span class="sxs-lookup"><span data-stu-id="82119-483">\_text1</span></span>    | <span data-ttu-id="82119-484">検索する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-484">The string to search in.</span></span>                                                                                                                                                                                                      |
| <span data-ttu-id="82119-485">\_text2</span><span class="sxs-lookup"><span data-stu-id="82119-485">\_text2</span></span>    | <span data-ttu-id="82119-486">検索する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-486">The string to find.</span></span>                                                                                                                                                                                                           |
| <span data-ttu-id="82119-487">\_職位</span><span class="sxs-lookup"><span data-stu-id="82119-487">\_position</span></span> | <span data-ttu-id="82119-488">比較を実行する *\_text1* パラメーターの最初の位置。</span><span class="sxs-lookup"><span data-stu-id="82119-488">The first position in the *\_text1* parameter at which to perform a comparison.</span></span>                                                                                                                                               |
| <span data-ttu-id="82119-489">\_数値</span><span class="sxs-lookup"><span data-stu-id="82119-489">\_number</span></span>   | <span data-ttu-id="82119-490">比較を再試行する *\_text1* パラメーター内の位置の数。</span><span class="sxs-lookup"><span data-stu-id="82119-490">The number of positions in the *\_text1* parameter to retry the comparison for.</span></span> <span data-ttu-id="82119-491">マイナス記号が*\_番号*パラメーターに先行する場合、システムでは特定位置の逆順で文字数が検索されます。</span><span class="sxs-lookup"><span data-stu-id="82119-491">If a minus sign precedes the *\_number* parameter, the system searches the number of characters in reverse order from the specified position.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-492">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-492">Return value</span></span>

<span data-ttu-id="82119-493">文字列内で指定した文字列が見つかった位置。それ以外の場合は **0** (ゼロ)。</span><span class="sxs-lookup"><span data-stu-id="82119-493">The position at which the specified string was found in the string; otherwise, **0** (zero).</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-494">備考</span><span class="sxs-lookup"><span data-stu-id="82119-494">Remarks</span></span>

<span data-ttu-id="82119-495">この比較では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="82119-495">The comparisons aren't case-sensitive.</span></span> <span data-ttu-id="82119-496">*\_位置*パラメーターが **1** 未満の値は **1** として扱われます。</span><span class="sxs-lookup"><span data-stu-id="82119-496">Values for the *\_position* parameter that are less than **1** are treated as **1**.</span></span> <span data-ttu-id="82119-497">スキャンの方向は、*\_number* パラメーターで指定されている符号で制御されます。</span><span class="sxs-lookup"><span data-stu-id="82119-497">The direction of the scan is controlled by the sign that is specified in the *\_number* parameter.</span></span> <span data-ttu-id="82119-498">プラス記号は、連続する各比較が文字列の末尾に 1 つ近い位置から開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="82119-498">A positive sign indicates that each successive comparison will start one position closer to the end of the string.</span></span> <span data-ttu-id="82119-499">マイナス記号は、各比較が文字列の先頭に 1 つ近い位置から開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="82119-499">A negative sign indicates that each comparison will start one position closer to the start of the string.</span></span>

    strScan("ABCDEFGHIJ","DEF",1,10); //Returns the value 4.
    strScan ("ABCDEFGHIJ","CDE",10,-10); //Returns the value 3.

## <a name="strupr"></a><span data-ttu-id="82119-500">strUpr</span><span class="sxs-lookup"><span data-stu-id="82119-500">strUpr</span></span>
<span data-ttu-id="82119-501">文字列内のすべての文字を大文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="82119-501">Converts all the letters in a string to uppercase.</span></span>

    str strUpr(str _text)

### <a name="parameters"></a><span data-ttu-id="82119-502">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-502">Parameters</span></span>

| <span data-ttu-id="82119-503">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-503">Parameter</span></span> | <span data-ttu-id="82119-504">説明</span><span class="sxs-lookup"><span data-stu-id="82119-504">Description</span></span>                                 |
|-----------|---------------------------------------------|
| <span data-ttu-id="82119-505">\_テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-505">\_text</span></span>    | <span data-ttu-id="82119-506">大文字に変換する文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-506">The string to convert to uppercase letters.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-507">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-507">Return value</span></span>

<span data-ttu-id="82119-508">小文字のみを含んでいる指定された文字列のコピーです。</span><span class="sxs-lookup"><span data-stu-id="82119-508">A copy of the specified string that contains only lowercase letters.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-509">備考</span><span class="sxs-lookup"><span data-stu-id="82119-509">Remarks</span></span>

<span data-ttu-id="82119-510">**strUpr** 関数は、**strLwr** 関数を補完します。</span><span class="sxs-lookup"><span data-stu-id="82119-510">The **strUpr** function is complementary to the **strLwr** function.</span></span> <span data-ttu-id="82119-511">**strUpr** 関数は、Win32 API で **LCMapString()** 関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="82119-511">The **strUpr** function uses the **LCMapString()** function in the Win32 API.</span></span>

### <a name="example"></a><span data-ttu-id="82119-512">例</span><span class="sxs-lookup"><span data-stu-id="82119-512">Example</span></span>

<span data-ttu-id="82119-513">次の例は **ABCDD55EFGHIJ** を出力します。</span><span class="sxs-lookup"><span data-stu-id="82119-513">The following example will print **ABCDD55EFGHIJ**.</span></span>

    static void strUprExample(Args _args)
    {
            print strUpr("Abcdd55EFGhiJ");
            pause;
    }

## <a name="substr"></a><span data-ttu-id="82119-514">subStr</span><span class="sxs-lookup"><span data-stu-id="82119-514">subStr</span></span>
<span data-ttu-id="82119-515">文字列の一部を取得します。</span><span class="sxs-lookup"><span data-stu-id="82119-515">Retrieves part of a string.</span></span>

    str subStr(str _text, int _position, int _number)

### <a name="parameters"></a><span data-ttu-id="82119-516">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-516">Parameters</span></span>

| <span data-ttu-id="82119-517">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82119-517">Parameter</span></span>  | <span data-ttu-id="82119-518">説明</span><span class="sxs-lookup"><span data-stu-id="82119-518">Description</span></span>                                                                                                                                                                                                             |
|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="82119-519">\_テキスト</span><span class="sxs-lookup"><span data-stu-id="82119-519">\_text</span></span>     | <span data-ttu-id="82119-520">元の文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-520">The original string.</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="82119-521">\_職位</span><span class="sxs-lookup"><span data-stu-id="82119-521">\_position</span></span> | <span data-ttu-id="82119-522">取得する部分が開始する元の文字列内の位置。</span><span class="sxs-lookup"><span data-stu-id="82119-522">The position in the original string where the part to retrieve begins.</span></span>                                                                                                                                                  |
| <span data-ttu-id="82119-523">\_数値</span><span class="sxs-lookup"><span data-stu-id="82119-523">\_number</span></span>   | <span data-ttu-id="82119-524">元の文字列から取得する位置の方向と数を示す符号付き整数。</span><span class="sxs-lookup"><span data-stu-id="82119-524">A signed integer that indicates the direction and number of positions to retrieve from the original string.</span></span> <span data-ttu-id="82119-525">マイナス記号が*\_番号*に先行する場合、システムでは指定された位置から後方に部分文字列を選択します。</span><span class="sxs-lookup"><span data-stu-id="82119-525">If a minus sign precedes *\_number*, the system selects the substring backward from the specified position.</span></span> |

### <a name="return-value"></a><span data-ttu-id="82119-526">戻り値</span><span class="sxs-lookup"><span data-stu-id="82119-526">Return value</span></span>

<span data-ttu-id="82119-527">元の文字列のサブ文字列。</span><span class="sxs-lookup"><span data-stu-id="82119-527">A substring of the original string.</span></span>

### <a name="remarks"></a><span data-ttu-id="82119-528">備考</span><span class="sxs-lookup"><span data-stu-id="82119-528">Remarks</span></span>

<span data-ttu-id="82119-529">マイナス記号が*\_番号*パラメーターの値より前にある場合、指定された位置から後方に部分文字列を選択します。</span><span class="sxs-lookup"><span data-stu-id="82119-529">If a minus sign precedes the value of the *\_number* parameter, the substring will be selected backward from the specified position.</span></span>

    subStr("ABCDEFGHIJ",3,5); //Returns the string "CDEFG".
    subStr("ABCDEFGHIJ",7,-4); //Returns the string "DEFG".
    subStr("abcdef"),2,99) //Returns the string "cdef".
    subStr("abcdef",2,3) //Returns the string "bcd".
    subStr("abcdef",2,-3); //Returns the string "ab".



