---
title: N クラス
description: 文字 N で始まるシステム API クラス。
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: 52351
ms.assetid: 4816db3a-defc-4057-ba08-50d85f597eeb
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cc3311c6c477f60a98a115eec7ee7221e92909f4
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183364"
---
# <a name="n-classes"></a>N クラス

[!include [banner](../includes/banner.md)]

文字 N で始まるシステム API クラス。

<a name="class-numbersequence"></a>クラス NumberSequence
--------------------

    class NumberSequence extends Object

### <a name="remarks"></a>備考

### <a name="examples"></a>例

### <a name="methods"></a>方法

| 方法                                                                                                                                                                | 説明                                             |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------|
| ::public static int getNextNumber(Connection connection, Int64 numbersequencerecordid, Int64 globaltransid, str userid, int sessionid, DateTime sessionLoginDateTime) |                                                         |
| public void new()                                                                                                                                                     | NumberSequence クラスの新しいインスタンスを初期化します。 |

### <a name="method-getnextnumber"></a>メソッド getNextNumber

    public static int getNextNumber(Connection connection, Int64 numbersequencerecordid, Int64 globaltransid, str userid, int sessionid, DateTime sessionLoginDateTime)

#### <a name="parameters"></a>パラメーター

connection  

<!-- -->

numbersequencerecordid  

<!-- -->

globaltransid  

<!-- -->

userid  

<!-- -->

sessionid  

<!-- -->

sessionLoginDateTime  

#### <a name="return-value"></a>戻り値

### <a name="method-new"></a>メソッド new

NumberSequence クラスの新しいインスタンスを初期化します。

    public void new()

## <a name="class-numbersequencesessionlesscache"></a>クラス NumberSequenceSessionLessCache
    class NumberSequenceSessionLessCache extends Object

### <a name="remarks"></a>備考

### <a name="examples"></a>例

### <a name="methods"></a>メソッド

| 方法                                                                         | 説明                                                             |
|--------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| public int getNumFromCache(Common numbersequencetable)                         |                                                                         |
| public int valueLastNumFromCache(Int64 numbersequecerecordid)                  |                                                                         |
| public int valueNextNumFromCache(Int64 numbersequecerecordid)                  |                                                                         |
| public void flushCache(Int64 numbersequecerecordid)                            |                                                                         |
| public void fillCache(Int64 numbersequecerecordid, int nextRec, int blockSize) |                                                                         |
| public void new()                                                              | NumberSequenceSessionLessCache クラスの新しいインスタンスを初期化します。 |

### <a name="method-getnumfromcache"></a>メソッド getNumFromCache

    public int getNumFromCache(Common numbersequencetable)

#### <a name="parameters"></a>パラメーター

numbersequencetable  

#### <a name="return-value"></a>戻り値

### <a name="method-valuelastnumfromcache"></a>メソッド valueLastNumFromCache

    public int valueLastNumFromCache(Int64 numbersequecerecordid)

#### <a name="parameters"></a>パラメーター

numbersequecerecordid  

#### <a name="return-value"></a>戻り値

### <a name="method-valuenextnumfromcache"></a>メソッド valueNextNumFromCache

    public int valueNextNumFromCache(Int64 numbersequecerecordid)

#### <a name="parameters"></a>パラメーター

numbersequecerecordid  

#### <a name="return-value"></a>戻り値

### <a name="method-flushcache"></a>メソッド flushCache

    public void flushCache(Int64 numbersequecerecordid)

#### <a name="parameters"></a>パラメーター

numbersequecerecordid  

### <a name="method-fillcache"></a>メソッド fillCache

    public void fillCache(Int64 numbersequecerecordid, int nextRec, int blockSize)

#### <a name="parameters"></a>パラメーター

numbersequecerecordid  

<!-- -->

nextRec  

<!-- -->

blockSize  

### <a name="method-new"></a>メソッド new

NumberSequenceSessionLessCache クラスの新しいインスタンスを初期化します。

    public void new()



