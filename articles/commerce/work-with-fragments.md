---
title: フラグメントで動作
description: このトピックでは、Microsoft Dynamics 365 Commerce でフラグメントを使用する理由、時期、および方法について説明します。
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d92b9077f8584bfa0710bbaacbc7caa3220baa4a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698099"
---
# <a name="work-with-fragments"></a>フラグメントで動作 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

このトピックでは、Microsoft Dynamics 365 Commerce でフラグメントを使用する理由、時期、および方法について説明します。

## <a name="overview"></a>概要

フラグメントを使用すると、サイト全体で再利用する必要があるモジュール コンフィギュレーションに対して、一元的な作成エクスペリエンスを実行できます。 たとえば、ヘッダー、フッター、およびバナーは多くのページに渡って共有されるため、フラグメントとしてコンフィギュレーションされることがよくあります。 サイトの別のページに挿入することができる小さな Web ページとして、フラグメントを考えることができます。 フラグメントには独自のライフサイクルがあります。 つまり、作成ツールでは、独立したエンティティとして作成、参照、更新、削除されるということです。

フラグメントをコンフィギュレーションした後は、サイト構造でモジュールを使用できる場所ではどこでも使用できます。 フラグメントは、ページ、レイアウト、テンプレート、およびその他のフラグメントで参照できます。

> [!NOTE]
> フラグメントは、他のフラグメント内の 7 つの階層にまで入れ子にすることができます。

たとえば、季節のイベントをサイト内の多数のページで推進したい場合に、フラグメントを使用できます。 新しいフラグメントを作成するプロセスの最初のステップとして、開始するモジュールのタイプを選択します。 この例では、ヒーロー モジュールからフラグメントを作成できます。

> [!NOTE]
> フラグメントは、どのモジュール タイプからでも作成できます。

その後、特定の販促コンテンツで、ヒーロー フラグメントをコンフィギュレーションすることができます。 必要に応じてローカライズすることもできます。 新しいスタンドアロンのヒーローのフラグメントを、サイト全体で事前にコンフィギュレーションされたモジュールとして使用できます。 これは、テンプレート、特定のページ、またはヒーロー モジュールを含むことができるその他のフラグメントに、簡単に追加できます。

フラグメントが追加された場所はすべて、作成したセントラル ヒーロー フラグメントへの参照です。 フラグメントに変更を発行した場合、その変更は、サイト全体でそのフラグメントが参照されているすべての場所にすぐに反映されます。 したがって、フラグメントは、サイトのモジュール コンフィギュレーションを再利用して一元管理するための、強力かつ効率的な方法です。 これらを効果的に使用することにより、機敏性を大幅に向上させ、サイトのコンテンツ管理に関連するコストを削減することができます。

次の図は、フラグメントを使用して、E コマース サイト全体で共有しているモジュールのコンフィギュレーションを一元的に作成する方法を示しています。

![フラグメントを使用して、E コマース サイト全体で共有しているモジュールのコンフィギュレーションを一元的に作成する方法を示した図](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a>フラグメントの作成

新しいフラグメントを作成するか、既存のモジュール コンフィギュレーションをフラグメントとして保存することができます。

### <a name="create-a-new-fragment"></a>新しいフラグメントの作成

新しいフラグメントを作成するには、次の手順に従います。

1. 左のナビゲーション ウィンドウで、**フラグメント**を選択します。
1. **新しいページ フラグメント**を選択します。 使用可能なすべてのモジュール タイプを示すダイアログ ボックスが表示されます。 先に説明したように、どのモジュール タイプからでもフラグメントを作成できます。
1. フラグメントのモジュール タイプを選択し、**OK** を選択します。

    > [!TIP]
    > 汎用コンテナー モジュール タイプを選択することで、後でフラグメントを更新およびコンフィギュレーションする必要がある場合に、最大の柔軟性を得ることができます。

### <a name="save-an-existing-module-configuration-as-a-fragment"></a>フラグメントとして既存のモジュール コンフィギュレーションを保存

以前にコンフィギュレーションしたモジュールを再利用可能なフラグメントに変換するには、次の手順に従います。

1. フラグメントに変換するモジュールを含むページまたはテンプレートを開きます。
1. 左のアウトライン ウィンドウで、モジュールの名前の横にある省略記号ボタン (**...**) を選択し、**フラグメントとして保存**を選択します。 ダイアログ ボックスが表示されます。
1. フラグメントの名前とメタデータを入力します。
1. **OK** を選択すると、他のページに追加できるフラグメントとしてモジュール コンフィギュレーションが保存されます。

## <a name="add-remove-or-edit-fragments-on-a-page"></a>ページでのフラグメントの追加、削除、または編集

次の手順では、フラグメントを追加、削除、および編集する方法について説明します。

### <a name="add-a-fragment"></a>フラグメントの追加

ページにフラグメントを追加するには、次の手順に従います。

1. 左側のアウトライン ウィンドウで、子モジュールを追加できるコンテナーまたはスロットを選択します。
1. コンテナーまたはスロットの名前の横にある省略記号ボタンを選択し、**フラグメントの追加**を選択します。 ダイアログ ボックスが表示されます。

    > [!NOTE]
    > コンテナーまたはスロットが新しい子モジュールをサポートしていない場合、**フラグメントの追加**オプションは使用できません。

1. ダイアログ ボックスで、追加するフラグメントを検索して選択します。 利用可能なフラグメントが一覧にない場合は、まず最初に、選択したコンテナーまたはスロットがサポートするモジュール タイプからフラグメントを作成する必要があります。
1. **OK** をクリックすると、選択したフラグメントがページ内で選択したコンテナーまたはスロットに追加されます。

> [!NOTE]
> コンテナーまたはスロットで許可されるモジュールは、ページのテンプレートまたはモジュール自体の定義によって定義されます。

### <a name="remove-a-fragment"></a>フラグメントの削除

ページ上のスロットまたはコンテナーからフラグメントを削除するには、次の手順に従います。

1. 左のアウトライン ウィンドウで、削除するフラグメントの名前の横にある省略記号ボタンを選択し、ごみ箱ボタンを選択します。
1. フラグメントを削除するかどうかを確認するメッセージが表示されたら、**OK** を選択します。

> [!NOTE]
> ページからフラグメントを削除する場合は、そのページからそのフラグメントへの参照を削除するだけです。 サイトからフラグメントを削除することは**ありません**。 サイトからフラグメントを削除するには、フラグメント インスペクター ユーザーインターフェイス (UI) を使用する必要があります。 すべてのページ、テンプレート、またはその他のフラグメントで、フラグメントが参照されていない場合にのみ、フラグメントをサイトから削除することができます。

### <a name="edit-a-fragment"></a>フラグメントの編集

フラグメントを編集するには、フラグメント エディター UI を使用する必要があります。 この制限は仕様です。 作成者が、特定のページでモジュールを編集するプロセスを、多くのページで共有される可能性のあるフラグメントを編集するプロセスと混同しないようにすることができます。

フラグメントを編集するには、次の手順に従います。

1. 左のナビゲーション ウィンドウで、**フラグメント**を選択します。
1. **フラグメント**下で、編集するフラグメントを選択します。
1. 必要に応じて、フラグメントのモジュール プロパティと構造を編集します。 このプロセスは、ページ エディター ビューで編集するモジュールの編集プロセスに似ています。

ページ、テンプレート、または親フラグメントでフラグメントを選択し、右側のプロパティ ウィンドウで**フラグメントの編集**を選択することによって、フラグメントを編集することもできます。

## <a name="additional-resources"></a>追加リソース

[テンプレートとレイアウトの概要](templates-layouts-overview.md)

[テンプレートの使用](work-with-templates.md)

[プリセット レイアウトの使用](work-with-layouts.md)