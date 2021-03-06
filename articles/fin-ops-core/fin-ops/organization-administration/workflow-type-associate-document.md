---
title: ワークフロー ドキュメント クラスをワークフロー タイプと関連付ける
description: このトピックでは、ワークフロー タイプにワークフロー ドキュメント クラスを関連付ける方法について説明します。
author: RobinARH
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: 202694
ms.assetid: 33349e0d-d8ac-4d20-8f9b-5f85d4e01004
ms.search.region: Global
ms.author: RobinARH
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: Platform update 1
ms.openlocfilehash: 3c2ffa78c6467c1f15df6d59f0d5d6d93d90d887
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180477"
---
# <a name="associate-a-workflow-document-class-with-a-workflow-type"></a>ワークフロー ドキュメント クラスとワークフロー タイプの関連付け 

[!include [banner](../includes/banner.md)]

ワークフローを作成するには、ワークフロー ドキュメント クラスをワークフロー タイプにバインドする必要があります。 ワークフロー ドキュメント クラスには、ワークフローが使用するテーブル データ フィールドへの参照が含まれています。 このトピックでは、ワークフロー タイプにワークフロー ドキュメント クラスをバインドする方法について説明します。

> [!NOTE]
> **ワークフロー** ウィザードを使用してワークフロー タイプを作成した場合は、ワークフロー ドキュメント クラスをワークフロー タイプに既にバインドしています。

次の手順を開始する前に、コンフィギュレーション ユーザー インターフェイス (UI) の条件に使用されるテーブル フィールドを公開するためのワークフロー ドキュメント クラスを作成する必要があります。 詳細については、 [新しいワークフロー ドキュメント クラスの作成](workflow-type-document-create.md) を参照してください。

## <a name="bind-a-workflow-document-class-to-a-workflow-type"></a>ワークフロー ドキュメント クラスをワークフロー タイプにバインドする

1. アプリケーション エクスプローラーで、 **ワークフロー** ノードを展開します。
2. **ワークフロー タイプ** ノードで、ワークフロー ドキュメント クラスをバインドするワークフロー タイプを右クリックし、 **プロパティ** を選択します。
3. **プロパティ** シートで、 **ドキュメント** プロパティをワークフロー ドキュメントを定義するワークフロー ドキュメント クラスに設定します。

## <a name="see-also"></a>参照

[新しいワークフロー タイプの作成](workflow-type-create-new.md)

[ワークフロー ドキュメント クラスの作成](workflow-type-document-create.md)
