---
title: X++ ランタイム関数リソース
description: このトピックでは、X++ のランタイム関数について説明します。
author: RobinARH
manager: AnnBe
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: 31461
ms.assetid: 9cf83640-536c-4a99-8e0d-7a4e97d3c91f
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5585aac0d3cf4cb44734e49733ed8e650ac43175
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769569"
---
# <a name="x-runtime-function-resources"></a>X++ ランタイム関数リソース

[!include [banner](../includes/banner.md)]

このトピックでは、X++ のランタイム関数について説明します。

X++ 言語は、約 200 のシステム関数を提供しており、これらは、任意のクラスの一部ではなく、実行時に実行されます。 ランタイム関数は、データ型変換、算術操作などに使用されます。 いくつかの共通のランタイム関数を次に示します。

-   **str2Int** – は、str 値から int 値を作成します。
-   **abs** – 正または負の実際の値から正の実数値を作成します。
-   **conFind** – コンテナー内の要素の位置を取得します。

### <a name="call-run-time-functions-from-net"></a>.NET からランタイム関数を呼び出す

X++ ランタイム関数のロジックは、次の .NET アセンブリでも実装されています。

    Microsoft.Dynamics.AX.Xpp.Support.DLL

このアセンブリ内で、X++ ランタイム関数は次のクラスの静的メソッドとして実装されます。

    Microsoft.Dynamics.AX.Xpp.PredefinedFunctions

## <a name="categories-and-functions"></a>カテゴリおよび機能
次のテーブルは、X++ 関数のカテゴリのみを一覧表示して説明しています。 これらのカテゴリは、多数の機能を理解するのに役立つものです。 ただし、カテゴリでは任意の正式コンストラクトが表されません。

| カテゴリ                  | 説明  |
|---|---|
| [勤務先](#business)     | 財務データを入力し、式を計算する機能。 詳細については、[X++ ビジネス ランタイム関数](xpp-business-run-time-functions.md) を参照してください。                              |
| [コンテナ](#container)   | X++ のコンテナー データ型で操作する機能。 詳細については、[X++ コンテナー ランタイム関数](xpp-container-run-time-functions.md) を参照してください。                               |
| [換算](#conversion) | 1 つのタイプのデータを別のタイプのデータに翻訳する機能。 詳細については、[X++ 換算ランタイム関数](xpp-conversion-run-time-functions.md) を参照してください。                  |
| [日付](#date)             | 日付データ型で操作する機能。 詳細については、[X++ 日付ランタイム関数](xpp-date-run-time-functions.md) を参照してください。                                                     |
| [計算](#math)             | 数学的な計算を実行する機能。 詳細については、[X++ 数学ランタイム関数](xpp-math-run-time-functions.md) を参照してください。                                                 |
| [反映](#reflection) | オブジェクトに関するメタデータにアクセスし、それらに関するその他のメタデータを返す機能。 詳細については、[X++ リフレクションランタイム関数](xpp-reflection-run-time-functions.md) を参照してください。 |
| [セッション](#session)       | 現在のユーザー接続のコンテキストで変更またはレポートする機能。 詳細については、[X++ セッション ランタイム関数](xpp-session-run-time-functions.md) を参照してください。             |
| [文字列](#string)         | str データ型で操作する機能。 詳細については、[X++ 文字列ランタイム関数](xpp-string-run-time-functions.md) を参照してください。                                                 |
| 外                     | [ビープ音](#beep)、[newGuid](#newguid)、[スリープ](#sleep)                                                                                                                                                                        |

## <a name="business"></a>勤務先
詳細については、[X++ ビジネス ランタイム関数](xpp-business-run-time-functions.md) を参照してください。

|          |         |          |        |
|----------|---------|----------|--------|
| cTerm    | ddb     | dg       | fV     |
| idg      | intvMax | intvName | intvNo |
| intvNorm | pmt     | pt       | pv     |
| レート     | sln     | syd      | term   |

## <a name="container"></a>コンテナー
詳細については、[X++ コンテナー ランタイム関数](xpp-container-run-time-functions.md) を参照してください。

- conDel
- conFind
- conIns
- conLen
- conNull
- conPeek
- conPoke

## <a name="conversion"></a>換算
詳細については、[X++ 換算ランタイム関数](xpp-conversion-run-time-functions.md) を参照してください。

|           |              |              |            |
|-----------|--------------|--------------|------------|
| any2Date  | any2Enum     | any2Guid     | any2Int    |
| any2Int64 | any2Real     | any2Str      | anytodate  |
| anytoenum | anytoguid    | anytoint     | anytoint64 |
| anytoreal | anytostr     | char2Num     | date2Num   |
| date2Str  | datetime2Str | enum2str     | guid2Str   |
| int2Str   | int642Str    | num2Char     | num2Date   |
| num2Str   | str2Date     | str2Datetime | str2Enum   |
| str2Guid  | str2Int      | str2Int64    | str2Num    |
| str2Time  | time2Str     | uint2Str     |            |

## <a name="date"></a>日
詳細については、[X++ 日付ランタイム関数](xpp-date-run-time-functions.md) を参照してください。

|         |          |               |               |
|---------|----------|---------------|---------------|
| dayName | dayOfMth | dayOfWk       | dayOfYr       |
| endMth  | mkDate   | mthName       | mthOfYr       |
| nextMth | nextQtr  | nextYr        | prevMth       |
| prevQtr | prevYr   | systemDateGet | systemDateSet |
| timeNow | 今日    | wkOfYr        | 年          |

## <a name="math"></a>計算
詳細については、[X++ 数学ランタイム関数](xpp-math-run-time-functions.md) を参照してください。

|         |          |               |               |
|---------|----------|---------------|---------------|
|abs|acos|asin|atan|
|corrFlagGet|corrFlagSet|cos|cosh|
|decRound|exp|exp10|frac|
|log10|logN|最大|最小|
|power|round|sin|sinh|
|tan|tanh|trunc||

## <a name="reflection"></a>反映
詳細については、[X++ リフレクションランタイム関数](xpp-reflection-run-time-functions.md) を参照してください。

|              |               |              |               |
|--------------|---------------|--------------|---------------|
| classIdGet   | dimOf         | fieldId2Name | fieldId2PName |
| fieldName2Id | indexId2Name  | indexName2Id | refPrintAll   |
| tableId2Name | tableId2PName | tableName2Id | typeOf        |

## <a name="session"></a>セッション
詳細については、[X++ セッション ランタイム関数](xpp-session-run-time-functions.md) を参照してください。

|                          |           |           |                     |
|--------------------------|-----------|-----------|---------------------|
| curExt                   | curUserId | funcName  | getCurrentPartition |
| getCurrentPartitionRecId | getPrefix | sessionId | prmIsDefault        |
| runAs                    | setPrefix |           |                     |

## <a name="string"></a>文字列
詳細については、[X++ 文字列ランタイム関数](xpp-string-run-time-functions.md) を参照してください。

|         |          |          |           |
|---------|----------|----------|-----------|
| 照合   | strAlpha | strCmp   | strColSeq |
| strDel  | strFind  | strFmt   | strIns    |
| strKeep | strLen   | strLine  | strLTrim  |
| strLwr  | strNFind | strPoke  | strPrompt |
| strRem  | strRep   | strRTrim | strScan   |
| strUpr  | subStr   |          |           |

## <a name="beep"></a>beep
コンピューターのスピーカーから短いサウンドを出力します。

```xpp
void beep()
```

### <a name="example"></a>例

```xpp
static void beepExample(Args _args)
{
        beep();
}
```

## <a name="newguid"></a>newGuid
グローバル一意識別子 (GUID) を作成します。

    guid newGuid()

### <a name="return-value"></a>戻り値

GUID。

### <a name="example"></a>例

次の例では、GUID を作成します。

    static void newGuidExample(Args _arg)
    {
            guid myGuid;

            myGuid = newguid();
            print strfmt("The GUID is: %1", myGuid);
    }

## <a name="sleep"></a>sleep
指定されたミリ秒間、現在のスレッドの実行を一時停止します。

    int sleep(int _duration)

### <a name="parameters"></a>パラメーター

| パラメーター  | 説明                          |
|------------|--------------------------------------|
| \_期間 | 一時停止するミリ秒数。 |

### <a name="return-value"></a>戻り値

スレッドが実際に一時停止した時間 (ミリ秒)。

### <a name="example"></a>例

    static void sleepExample(Args _arg)
    {
            int seconds = 10;
            int i;

            i = sleep(seconds*1000);
            print "job slept for " + int2str(i/1000) + " seconds";
    }





