---
title: "BOMバージョンの展開"
description: "この記事では、部品表の(BOM)バージョンのBOMを含むマスタ プランのシナリオを説明します。"
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 6461a07f8c8f02f584e5ef70b21ebaf04f29b57b
ms.lasthandoff: 03/31/2017


---

# <a name="explosion-of-a-bom-version"></a>BOMバージョンの展開

この記事では、部品表の(BOM)バージョンのBOMを含むマスタ プランのシナリオを説明します。

BOM バージョンの需要展開は、特定サイト (および場合によっては特定倉庫) における各 BOM 明細行品目に対する需要を作ります。 サイト固有 BOM では、各 BOM 明細行に対して、特定の倉庫が定義される可能性があります。 また、各 BOM 明細行に対し、倉庫が必要かどうかが品目の分析コード設定によって決まります。 その後、結果としての各 BOM 明細行品目に対する需要は、追加の需要展開の開始点となります。 このマスター計画シナリオの前提条件を次に示します。

-   サイト分析コードが必須であり、需要トランザクションで入力する必要がある。
-   サイト分析コードが一貫している。 したがって、下位レベル需要のサイトは、初期需要トランザクションのサイトと同じである。

次の図は、マスタ プラン需要展開のプロセス方法を示しています。 ![BOM バージョンを使用した展開が必要    ](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="see-also"></a>参照
--------

- BOMバージョンを決定するかどのように[マスター プラン] (マスター プランbomバージョンdetermined.md) 

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

