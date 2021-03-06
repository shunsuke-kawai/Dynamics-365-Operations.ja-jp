---
title: 計画の最適化フィット分析
description: このトピックでは、計画の最適化機能の能力に対して、現在の設定およびデータを検証する方法について説明します。
author: ChristianRytt
manager: AnnBe
ms.date: 1030/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 26b067f8526df16474c0ab52d0abf816170ff5cb
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773998"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="planning-optimization-fit-analysis"></a>計画の最適化フィット分析

現在の設定およびデータと計画の最適化機能との互換性を確認するには、**マスター プラン** \> **設定** \> **計画の最適化フィット分析**の順に移動してから、**分析の実行**を選択します。 分析で不整合が見つかった場合は、同じページに一覧表示されます。 (分析を実行するには数分かかります。)

> [!NOTE]
> 不整合が見つかった場合でも、計画の最適化を引き続き使用できます。 フィット分析の結果は、計画サービスが現在の設定を遵守しない箇所を示しているだけです。 つまり、一部のプロセスが無視される、またはサポートされない可能性がある場所を示します。

## <a name="analysis-results-example-1"></a>分析結果: 例 1

- **機能:** 生産
- **問題:** BOM レベルがゼロより大きい品目: 56
- **説明:** フィット分析で、生産の部品表 (BOM) 設定がある 56 品目が見つかりました。 計画の最適化の現在のバージョンは生産をサポートしていないため、計画の最適化では計画製造オーダーではなく計画発注書が生成されます。 また、影響を受ける品目を一覧表示する警告も表示されます。

### <a name="analysis-results-example-2"></a>分析結果: 例 2

- **機能:** アクション
- **問題:** アクション計算が有効な補充グループ: 6
- **説明:** フィット分析で、アクション計算が有効になっている 6 つの補充グループが見つかりました。 計画の最適化の現在のバージョンではアクションがサポートされていないため、マスター プラン中にアクションが生成されることはありません。

## <a name="related-resources"></a>関連するリソース

[計画の最適化の概要](planning-optimization-overview.md)

[計画の最適化を開始する](get-started.md)

[計画の履歴と計画ログの表示](plan-history-logs.md)

[プランへのフィルターの適用](plan-filters.md)

[計画ジョブのキャンセル](cancel-planning-job.md)
