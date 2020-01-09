---
title: 資産カウンターの手動更新
description: このトピックでは、資産管理での資産カウンターの手動更新について説明します。
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3072ab204b53b16988d2973b28a697041cb84c27
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626138"
---
# <a name="manual-update-of-asset-counters"></a>資産カウンターの手動更新

[!include [banner](../../includes/banner.md)]



カウンターは、資産が処理された時間数や生産された量に関する登録など、資産の登録を作成するために使用されます。

カウンターに対して選択されたカウンター タイプは、カウンター値を継承するように設定されている場合があります。 つまり、**カウンター** ページの**一般**クイック タブで**資産のカウンター値の継承**オプションが**はい**に設定されている場合 (**資産管理** > **設定** > **資産のタイプ** > **カウンター**)。 この場合、そのタイプの新しいカウンター明細行を作成すると、同じカウンター タイプを使用するすべての子アセットが自動的に更新されます。

**全資産**ページで、資産の測定値に基づき、資産に対する時間または数量のカウンター登録を作成します。

1. **資産管理** >  **共通** >  **資産** > **全資産**の順に選択します。

2. 資産を選択してから、アクション ペインの、**資産**タブの、**予防的**グループで、**カウンター**を選択します。 **資産カウンター** ページに、選択した資産に対して行われた以前のカウンター登録のすべてのリストが表示されます。

3. **新規** を選択して、登録を作成します。 資産 ID は**資産**フィールドに自動的に入力されます。

4. **カウンター** フィールドで、関連するカウンターを選択します。 資産で選択された資産タイプに関連するカウンターのみを選択できます。 関連する単位が**単位**フィールドに自動的に入力されます。

5. **登録済**フィールドで、カウンター登録の日時を選択します。

6. **値**フィールドに、最後のカウンター登録以降の数値を入力します。 または、**集計値**フィールドに、合計カウント数を入力します。

次のポイントに注意します。

- 資産に新しいカウンターを物理的にインストールする場合、**資産カウンター**ページで、資産の変更を登録する必要があります。 次に、同じタイムスタンプを持つ 2 つの登録明細行を作成する必要があります。 最初の行は、置換しているカウンター用である必要があります。 新しいカウンターに関連付けられている行で、**カウンター リセット** チェックボックスをオンにします。 **合計**フィールドで、合計カウント数は、カウンター タイプに登録されているすべての値のカウンターの合計になります。

- 「以降」または「到達」の間隔タイプを持つメンテナンス計画を使用している資産で**カウンター リセット** チェック ボックスがオンになっている場合、別のカウンター明細行を作成し、新しいカウンターでやり直すため、カウンターは新しいカウンター明細行でもまだ有効です。

次の図は、**資産カウンター** ページの例を示しています。

![図 1](media/11-work-orders.png)

**資産カウンター** ページ (**資産管理** > **照会** > **資産** > **資産カウンター**) では、必要に応じて、複数の資産に対して同時にカウンター登録を行うことができます。

>[!NOTE]
>手動のカウンター登録に対する差異を定義する範囲を設定できます。 登録が定義された範囲に含まれていない場合に表示されるメッセージのタイプを指定することもできます。 カウンターの設定方法の詳細については、[カウンター](../setup-for-objects/counters.md) を参照してください。
