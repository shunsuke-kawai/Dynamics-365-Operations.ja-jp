---
title: ユーザー エクスペリエンスのパーソナライズ
description: このトピックでは、アプリを個人用設定する方法について説明します。
author: jasongre
manager: AnnBe
ms.date: 10/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3cf2b82470887ee617704b72e47a53d299911e3
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811534"
---
# <a name="personalize-the-user-experience"></a>ユーザー エクスペリエンスのパーソナライズ

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

このトピックでは、アプリを個人用設定する方法について説明します。

個人用設定の基本クラスは 3 つの種類があります。

- 設定ページで設定される個人用設定。 例には、配色テーマとタイム ゾーンが含まれます。
- ページの使用状況に関連する個人用設定。 これらの個人用設定は、*暗黙的な*個人用設定と呼ばれます。 例えば、システムは調整したグリッド列の幅およびクイック タブの展開、または折りたたみの状態を追跡します。
- 通常、対話型個人用設定モードで行われる、要素の表示あるいは機能方法を変更して、ページの外観を変更するような個人用設定。 これらの個人用設定は、*明示的な*個人用設定と呼ばれます。 例えば、ページに要素を追加したり、隠したり、並べ替えたりすることもあります。

ユーザーが行うすべての個人用設定は、そのタイプや現在連携している会社に関係なく、そのユーザーのみのためです。 あるユーザーがページに加えた変更は、システム内の他のユーザーには影響を与えません。

## <a name="system-wide-options-for-the-current-user"></a>現在のユーザーのシステム全体のオプション

**ユーザー オプション**ページには、現在のユーザーに対する、複数のシステム全体の設定が含まれています。 **ユーザー オプション** ページを開くには、ナビゲーション バーの**設定**ボタン (ギヤ記号) を選択し、**ユーザー オプション**を選択します。 **ユーザー オプション**ページには、次のようなさまざまなユーザー設定を含む 4 つのタブがあります。

- **視覚** - ページの要素の配色テーマおよび既定のサイズを選択します。
- **基本設定** - システムを開くたびに使用される既定値を選択します。 これらの値は、会社、最初のページ、および既定の表示/編集モードを含みます。 (表示/編集モードは、表示のためにロックするかどうか、あるいはページを開くたびに編集用に開くかどうかを決定します。) このタブには、言語、タイム ゾーン、および日付、時刻、数字の形式のオプションも含まれます。 最後に、このタブにはリリースごとに異なる複数のさまざまな設定が含まれます。
- **アカウント** - ユーザー名および他のアカウントに関連付けられたオプションを調整します。
- **ワークフロー** - ワークフローに関連付けられたオプションを選択します。

ユーザー設定の変更に加えて、**ユーザー オプション** ページを使用して、使用状況データと個人用設定を表示および削除することもできます。 アクションウィンドウの**使用状況データ**を選択するだけです。

アプリを使用する場合は、今後使用するシステムを使いやすくするため、選択項目の多くが保存されます。 **個人用設定**タブでは、システム内のページに加えた個人的な変更を表示および管理できます。 このタブでは、機能のコールアウトをリセットすることもできます (つまり、新しいシステムの機能を導入するポップアップ ウィンドウ)。 次に、以前に発生した機能について警告を受信することができます。

> [!NOTE]
> [保存されたビュー](saved-views.md) 機能がオンになっている場合は、**ユーザー オプション** ページのアクション ウィンドウで**個人用設定**を選択して、個人用設定を表示および管理できます。

## <a name="implicit-personalizations"></a>暗黙的な個人用設定

暗黙的な個人用設定は、現在の表示状態を保存するコントロールとの関わりだけで実行する個人用設定のことです。

- **グリッドの列** - 列のヘッダーの左または右のサイズ変更バーを選択し、それを必要な幅まで左または右にスライドしてグリッドの列の幅を調整できます。 アプリは、列に設定する幅を保存します。 そして、次にそのグリッドを含むページを開いたときに、列の幅がサイズ調整されます。
- **クイック タブ** - 一部のページには*クイック タブ*と呼ばれる拡張可能なセクションがあります。 アプリには、展開または折りたたんだクイック タブに関する情報も格納されています。 そして、次にそのページを開くときに、ページとの最後の相互作用に基づいて、同じクイック タブが展開されるか折りたたまれます。 場合によっては、クイック タブを折りたたむことで、システム パフォーマンスを向上させます。アプリは、クイックタブが展開されるまでクイック タブの情報を取得する必要がないためです。 このトピックの後半で説明するように、ページ上のクイック タブの順序を変更することもできます。
- **情報ボックス** – あるページには、ページの現在の件名に関連付けられた読み取り専用情報を表示する**関連情報**ウィンドウがあります。 **関連情報**ウィンドウの各セクションは、*情報ボックス*と呼ばれます。 **関連情報**ウィンドウを展開または折りたたんだりできるほか、各情報ボックスを展開または折りたたむこともできます。 アプリは、これらの基本設定を保存します。 そして、次にそのページを開くときに、ページとの最後の相互作用に基づいて、**関連情報**ウィンドウと各情報ボックスが展開されるか折りたたまれます。 場合によっては、情報ボックスを折りたたむことで、システム パフォーマンスを向上させます。アプリは、情報ボックスが展開されるまで情報ボックスの情報を取得する必要がないためです。
- **アクション ウィンドウ** - ほとんどのページの先頭に*アクション ウィンドウ*が表示されます。 アクション ウィンドウには、現在のページで実行できるアクションの多くのボタンが含まれています。 これらのボタンは、通常、タブ上で整理されています。 アクション ウィンドウ全体を開いたまま「固定する」、あるいは既定で折りたたむこともできます。 そして、次にそのページを開くときに、ページとの最後の相互作用に基づいて、アクション ウィンドウが開かれるか折りたたまれます。 アクション ウィンドウを開いたまま固定した場合は、最後に使用したタブが表示されます。
- **QuickFilter** - 多くのグリッド上に *QuickFilter* が表示されます。 QuickFilter を使用して、選択した列に基づいてグリッドをフィルター処理できます。 アプリは、フィルター処理した列を保存します。 そして、次にそのグリッドを含むページを開いたときに、グリッドは同じ列でフィルター処理されます。 ただし、別の列を選択してグリッドをフィルター処理することもできます。
- **列ヘッダーのフィルター** - *列ヘッダーのフィルター*を使用してグリッドをフィルター処理する場合、目的のデータを見つけるのに必要とするフィルター演算子を変更できます。 例えば、演算子を**で始まる**から、**次の値と完全に一致する**に変更できます。 列ヘッダーのフィルターを使用してフィルター演算子を変更するたびに、アプリはその変更を保存します。 そして、次にその列でフィルター処理をするときに、フィルター演算子が復元されます。
- **ナビゲーション ウィンドウ** – 任意のページの左上の**ナビゲーション ウィンドウの拡張**ボタンを選択して、*ナビゲーション ウィンドウ*を開けます。 (このボタンは、_**メニュー** ボタン_*ハンバーガー*、*ハンバーガー メニュー*、あるいは*ハンバーガー ボタン*と呼ばれることがあります。) ナビゲーション ウィンドウを開いたまま固定する、あるいは既定で折りたたんだ状態で保持することもできます。 ナビゲーション ウィンドウを開いたまま固定すると、アプリは折りたたむまで開かれた状態を保持します。

## <a name="explicit-personalizations"></a>明示的な個人用設定

人々や企業が異なれば、彼らにとって最も重要なデータ、および業務の実行に必要ではないデータに対する分析視点も変わってきます。 情報を管理し、連携する方法をカスタマイズできます。 一部の情報を非表示にするよう指定することもできます。 これらの機能は個人的で生産性な経験にとって重要であり、明示的な個人用の設定の例です。 明示的な個人用設定とは、要素またはページの外観または動作を変更する必要があるため、明示的に行う個人用設定のことです。

### <a name="shortcut-menu-options"></a>ショートカット メニュー オプション

ショートカット メニューは、ユーザーあるいはユーザーの会社の要件により適合するようにページを明示的に変更するいくつかの方法を説明します。 (ショートカット メニューは*右クリック メニュー*あるいは*コンテキスト メニュー*とも呼ばれます)。

ページに加えられる最も一般的で重要な変更の一部は、ショートカット メニューのオプションとして直接使用することができます。 例えば、プラットフォーム更新プログラム 17 以降で、グリッドの列を追加または非表示にする場合は、列のヘッダーを右クリックして、**列を追加**または**この列を非表示**を選択するだけです。

さらに、明示的な個人用設定の最も基本的なタイプは、要素を右クリックし、**個人用設定**を選択することで利用可能です。 (ページ上のすべての要素が個人用に設定できるわけではないことに注意してください。) この個人用設定の方法を使用すると、要素のプロパティ ウィンドウが表示されます。

![要素のプロパティの個人用設定](./media/personalization-element-properties.png)

プロパティ ウィンドウを使用して、次の方法で、要素を個人用に設定できます。

- 要素のラベルを変更します。
- 要素を非表示にすることによって、ページに表示されません。 フィールドのデータは削除または変更されません。 これ以上ページに情報が表示されなくなっただけです。
- クイックタブの集計セクションの情報を含みます (要素がクイックタブにある場合)。
- このフィールドをスキップして、ページをタブで移動するときにフォーカスを受け取らないようにします。
- フィールド内のデータが編集されるのを防ぎます (すべてのレコードの)。

プロパティ ウィンドウは、要素に応じてその他の個人用設定機能を含むことがあります。 例えば、タイルのプロパティ ウィンドウで、タイルからダッシュボードへのレベル上げができる場合があります。またダッシュボードのプロパティ ウィンドウでは、そのダッシュボードで新規ワークスペースを作れる場合があります。

### <a name="the-personalization-toolbar"></a>個人用設定ツールバー

ページに複数の変更を加える、または他のメカニズム (要素の並べ替えなど) によって利用できない変更を加える場合は、**個人用設定**ツールバーを使用できます。 **個人用設定**ツールバーを開くには、次のいずれかの手順に従います。

- 要素のプロパティ ウィンドウで、**このフォームのパーソナライズ**を選択します。
- ページのアクション ウィンドウの**オプション** タブ上の**個人用設定**グループで、**このフォームのパーソナライズ**を選択します。
- ナビゲーションバーの**設定**ボタン (歯車記号) を選択し、**パーソナライズ**を選択します。

[![個人用設定ツールバー](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>ページのナビゲーション

**個人用設定**ツールバーが開いている場合、ページはまだ読み取り専用 (つまり、データを編集することはできません) ですが、より対話型になりました。 具体的には、通常、ページでこれらのアクションを実行するように、**関連情報**ウィンドウを展開または折りたたんだり、タブを切り替えたり、セクションを展開したり折りたたんだりできます。 折りたたみ可能なセクションまたはタブ (クイック タブを非表示にするなど) に個人用設定を適用するには、そのセクションまたはタブがキーボード フォーカスを得るときまたはその上にマウス ポインターを移動するときに表示されるボタンを選択するだけです。

#### <a name="personalization-tools"></a>個人用設定ツール

**個人用設定**ツールバーで次のツールが使用できます。

- **選択**ツールを使用し、要素のプロパティを選択して変更します。 このツールを使用するには、ツールバーの**選択**ボタンを選択し、目的の要素を選択します。 要素のプロパティ ウィンドウが表示され、その要素のプロパティを変更できます。 そのページでカスタマイズできる他の要素にプロセスを繰り返すことができます。 一部のシナリオでは、一部のパーソナル化プロパティを使用できない場合があることに注意してください。 たとえば、必要なフィールドをロックすることはできません。
- ページの要素を非表示にする場合は、**非表示**ツールを使用します。 このツールを使用するには、ツールバーの**非表示**ボタンを選択し、非表示の要素を選択します。 **非表示**ツールを使用すると、すべての現在非表示の要素が見えるようになりますが、影付きのコンテナに表示されます。 これにより、要素を選択して表示することができます。 要素が非表示になったときにページがどのように表示されるかを表示するには、別の個人用設定ツールに切り替えます。
- **フィールドの追加**ツールを使用して、フィールドをページに追加します。 このツールを使用すると、ページ定義の一部であるフィールドのみを追加できます。 現在のページ定義に含まれない新しいフィールドを作成する方法の情報は、[カスタム フィールドの作成と操作](user-defined-fields.md) を参照してください。 ツールバーで**フィールドの追加**ボタンを選択したら、フィールドを追加したいグループまたはエリアを最初に選択する必要があります。 ダイアログ ボックスは、選択したグループまたはエリアに関連付けられたフィールドの一覧を表示します。 ダイアログ ボックスでは、追加する 1 つ以上のフィールドを選択してから、**挿入**を選択します。 以前に追加したフィールドを削除するには、プロセスを繰り返しますが、ダイアログ ボックスのフィールドの選択を解除します。
- 要素の現在のグループ内の別の場所に要素を移動する場合、**移動**ツールを使用します。 親グループの外部の要素は移動できないことに注意してください。 このツールを使用するには、ツールバーの**移動**ボタンを選択し、移動する要素を選択します。 要素を選択する場合、アプリは要素が移動できる場所を決定します。 これらの場所は、*ドロップ ゾーン*と呼ばれます。 現在のグループで要素をドラッグすると、各ドロップ ゾーンは要素がドロップされるエリアの横に、色分けされた太字のラインとして表示されます。
- **スキップ** ツールを使用して、ページのキーボード タブの順序から要素を削除します。 ツールバーの**スキップ** ボタンを選択すると、現在スキップされているすべての要素が影付きのコンテナに表示されます。 タブ順にフィールドを対話的に削除したり、追加したりすることができます。
- フィールドをクイック タブの集計セクションに表示したい場合は、**ヘッダーに表示**ツールを使用します。 ツールバーで**ヘッダーに表示**ボタンを選択すると、集計フィールドとして選択されているすべてのフィールドが影付きのコンテナに表示されます。 クイック タブ集計に対話型でフィールドを追加したり、フィールドを選択することでフィールドを削除したりできます。
- **ロック** ツールを使用して、編集可能または編集不可と要素にマークします。 ツールバーの**ロック** ボタンを選択すると、現在編集不可のすべての要素が影付きのコンテナに表示されます。 その後、それらを再び編集可能にすることができます。 一部のフィールドは必要で、編集不可にすることはできないことに注意してください。 これらのフィールドの横に、南京錠の記号が表示されます。
- **PowerApp の追加**ボタンを使用して、Microsoft PowerApps を使用して作成されたアプリをページに埋め込みます。 PowerApps アプリをページに埋め込む方法の詳細については、[PowerApps アプリの埋め込み](embed-power-apps.md) を参照してください。
- **クリア** ツールを使用して、ページを既定のインストール済みの状態にリセットします。 現在のページですべての個人用設定はクリアされます。 元に戻すアクションはありません。 したがって、ページをリセットする場合にのみ、このツールを使用します。
- **インポート** ツールを使用して、自分で、または誰かが以前に作成したファイルからの個人用設定を読み込みます。 ページの個人用設定をインポートするとき、ページの既存の個人用設定をすべて追加または置換するかどうかを選択できます。 元に戻すアクションはありません。 したがって、個人用設定をインポートした後は、不要な変更を手動でクリアまたは取り消す必要があります。
- **エクスポート**を使用して、ページの個人用設定をファイルに保存します。 その後、他のユーザーと個人用設定を共有できます。 それらのユーザーは、ページの個人用設定を含むファイルをインポートすればよいだけです。
- **閉じる**ボタンを選択して、**個人用設定**ツールバーを閉じ、以前にインタラクティブな状態だったページに戻ります。

従来、**個人用設定**ツールバーを使用している場合は、個人用設定を行うとすぐに有効になります。 ただし、[保存されているビュー](saved-views.md) 機能がオンになっている場合は、選択したビューへの個人用設定を明示的に保存する必要があります。

場合によっては、ツールを選択すると、要素の横に南京錠の記号が表示されます。 この記号は、選択したツールに関連付けられた要素のプロパティが変更できないことを示しています。それらのプロパティへの変更によって、ページが正常に機能するのを妨ぎます。

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>ワークスペースへのタイル、リスト、またはリンクの追加

リストを含む一部のページでは、**ワークスペースへの追加**個人用設定機能は、アクション ウィンドウの**オプション** タブにある**個人用設定**グループで使用できます。 この機能を使用すると、現在のリストから特定のワークスペースに関連情報をプッシュできます。 ワークスペースに表示される情報は、リスト全体、またはリストのフィルター処理および並べ替えバージョンのいずれかに基づいています。 ワークスペースで情報を、一覧、アイテム数を示す集計タイル、あるいはリンクとして表示されるかどうかも指定できます。

> [!NOTE]
> [保存されているビュー](saved-views.md) 機能がオンになっている場合は、ワークスペースにプッシュしたコンテンツがビューに直接リンクされます。 ビューのクエリはワークスペースのデータをフェッチするために使用され、ワークスペース内の対応するタイルまたはリンクによってそのビューにページが表示されるので、ビューのクエリと個人用設定が適用されます。

[![ワークスペースに追加](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- ワークスペースに一覧を追加するには、まずページで一覧を並べ替えるかフィルター処理します。そうすることで、ワークスペースに表示したい情報が表示されます。 (保存されているビュー機能がオンになっている場合は、これらの条件を満たすビューを保存するまで続行できません。) その後、**ワークスペースに追加**を選択します。 ワークスペースを選択して、**プレゼンテーション**フィールドで、**リスト**を選択します。 **構成**を選択すると、ダイアログ ボックスが表示され、ワークスペースの一覧に表示される列を選択できます。 ワークスペースの一覧に使用されるラベルを指定することもできます。
- ワークスペースにタイルを追加するには、最初にページのリストをフィルター処理します。そうすることで、集計する必要がある、あるいはすばやくアクセスしたいデータを表示できます。 (保存されているビュー機能がオンになっている場合は、これらの条件を満たすビューを保存するまで続行できません。) その後、**ワークスペースに追加**を選択します。 ワークスペースを選択して、**プレゼンテーション**フィールドで、**タイル**を選択します。 **構成**を選択すると、ダイアログ ボックスが表示され、ワークスペースでタイルに使用するラベルを指定できます。 タイルがカウントを表示するかどうかを指定することもできます。 タイルがワークスペースに追加されたら、タイルを選択してワークスペースから現在のページを開くことができます。 その後、そのタイルに関連付けられているフィルター処理されたリストを表示できます。
- ワークスペースにリンクを追加するには、まずページの一覧をフィルター処理します。そうすることで、興味のあるデータが表示されます。 (保存されているビュー機能がオンになっている場合は、これらの条件を満たすビューを保存するまで続行できません。) その後、**ワークスペースに追加**を選択します。 ワークスペースを選択して、**プレゼンテーション**フィールドで、**リンク**を選択します。 **構成**を選択すると、ダイアログ ボックスが表示され、リンクに使用するラベルを指定できます。 必要に応じて、このリンクを含む新しいセクションのラベルを指定することもできます。

リスト、タイル、あるいはリンクがワークスペースに追加されたら、そのワークスペースを開いて、要素の順序を好きなように並べ替えることができます。

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>ワークスペースからダッシュボードへの集計の追加

一部のワークスペースはカウント タイル (すなわち、そこに数値を含むタイル) を含み、ダッシュボードにもそれらのタイルを表示させることもできます。 ワークスペースで、カウント タイルを右クリックし、**個人用設定**を選択して、タイルのプロパティ ウィンドウで**ダッシュボードにピン留め**を選択します。 その後、選択されたダッシュボードを開いて最新の情報を更新すると、そのワークスペースのナビゲーション タイルの下にカウントが表示されます。 それが表すデータに直接移動するカウントを選択できます。

### <a name="personalizing-your-dashboard"></a>ダッシュボードの個人用設定

ダッシュボードとは、多くの場合アプリを開くと最初に表示されるページのことです。 表示したいワークスペース タイルのみ表示されるように、ダッシュ ボードをカスタマイズできます。 また、タイルを並べ替えて、表示したい順に表示したり、ワークスペースのナビゲーション タイルの名前を変更したり、新しいワークスペース タイルを追加したりできます。

ダッシュ ボードを個人用に設定するには、任意のタイルを右クリックして、**個人用設定**を選択し、タイルのプロパティ ウィンドウを開きます。

- 非表示にしたり、選択したタイルの名前を変更したりする場合、プロパティ ウィンドウで直接変更できます。
- ワークスペース タイルを再配置するには、プロパティ ウィンドウで、**このフォームのパーソナライズ**を選択し、**個人用設定**ツール バーを開きます。 その後、タイルを並び替えるのに、必要に応じて**移動**ツールを使用できます。
- 新しいワークスペース タイルを追加するには、プロパティ ウィンドウで、**ワークスペースの追加**を選択します。 新しいワークスペース タイルがダッシュ ボードの下部に作成されます。 この新しいワークスペース タイルの名前は、必要に応じて変更できます。 このトピックの[ワークスペースへのリスト、タイル、またはリンクの追加](#adding-a-tile-list-or-link-to-a-workspace)セクションで説明されているように、ワークスペースにリスト、タイル、リンクを追加することもできます。

## <a name="administration-of-personalizations"></a>個人用設定の管理

ページのカスタマイズ後は、その個人用ページをエクスポートすることで、その他のユーザーに個人用の設定を共有できます。 その後、他のユーザーにカスタマイズされたページに移動し、作成した個人用設定ファイルをインポートするように要求できます。 または、個人用設定を管理者権限を持つユーザーに与えることができます。 そのユーザーは、個人用設定ファイルをたくさんのユーザーに同時に適用できます。

管理者権限があるユーザーは、**個人用設定**ページで、他のユーザーの個人用設定を管理することもできます。

[保存されたビュー](saved-views.md) 機能をオンにしていない顧客の場合、このページには次の 4 つのタブがあります。

- **適用** – 1 つまたは複数のユーザーの個人用設定をインポートまたは選択することができます。 1 人以上のユーザーに個人用設定を適用するには、まずロールとそのロールを持つユーザーを選択します。 次に、選択したユーザーに適用する既存の個人用設定を選択するか、個人用設定ファイルをインポートします。 選択したページを次回開いたときに、個人用設定が検証され、選択したすべてのユーザーに適用されます。
- **クリア** – 1 つまたは複数のユーザーの、ページのすべての個人用設定またはワークスペースをクリアできます。 まず、ページまたはワークスペースを選択して、個人用設定を行ったユーザーの一覧を表示します。 次に、そのページまたはワークスペースの個人用設定を削除するユーザーを選択してから、**クリア**を選択します。 選択したユーザーが選択したページまたはワークスペースに適用したすべての個人用設定が削除されます。 このアクションを元に戻すことはできません。 ただし、ページまたはワークスペースに個人用設定が保存されている場合、個人用設定を再インポートできます。
- **ユーザー** – ユーザーが個人設定を行ったページのリストを表示するユーザーを選択します。 その後、特定のページまたはシステム全体の個人用設定を使用するユーザーの機能をオンまたはオフにできます。 ユーザーの個人用設定をインポート、エクスポート、またはクリアすることもできます。 さらに、ユーザーの機能のコールアウトをリセットすることもできます。 この場合、ユーザーが以前に新しい機能を導入するポップアップ ウィンドウを閉じた場合、ユーザーがそれらの機能に次回アクセスしたときに再び表示されます。
- **システム** – システム内のすべてのユーザーの個人用設定を一時的にオフにすることができます。 この場合、すべてのユーザーのすべての個人用設定が削除され、すべてのページが既定の状態にリセットされます。 後で個人用設定をオンに戻すと、すべての個人用設定が再度適用されます。 また、システム内のすべてのユーザーの個人設定を完全に削除することもできます。 削除された個人用設定を復元することはできません。 したがって、このタスクを実行する前に、後に必要となる可能性があるすべての個人用設定をエクスポートすることを確認します。

[保存されたビュー](saved-views.md) 機能をオンにしている顧客の場合、**個人用設定**ページには、次の 5 つのタブがあります。

- **公開済ビュー** – これらのビューは組織に公開されています。 これらのビューの対象となるユーザーを変更するには、各ビューに関連付けられているセキュリティ ロールまたは法人を変更できます。 1 つ以上の公開されたビューをエクスポートまたは削除することもできます。
- **未公開ビュー** – これらのビューは、システムにインポートされているが、まだ発行されていないテンプレート ビューです。 これらのビューは、公開、エクスポート、または削除することができます。
- **個人用ビュー** – これらのビューは、システム内のユーザーによって作成されています。 個人用ビューを組織に公開したり、これらのビューの 1 つ以上を他のユーザーにコピーしたりすることができます。 必要に応じてこれらのビューは、エクスポートまたは削除することもできます。
- **ユーザー** – ユーザーが個人設定を行ったページのリストを表示するユーザーを選択します。 その後、特定のページまたはシステム全体の個人用設定を使用するユーザーの機能をオンまたはオフにできます。 ユーザーの個人用設定をインポート、エクスポート、またはクリアすることもできます。 さらに、ユーザーの機能のコールアウトをリセットすることもできます。 この場合、ユーザーが以前に新しい機能を導入するポップアップ ウィンドウを閉じた場合、ユーザーがそれらの機能に次回アクセスしたときに再び表示されます。
- **システム** – システム内のすべてのユーザーの個人用設定を一時的にオフにすることができます。 この場合、すべてのユーザーのすべての個人用設定が削除され、すべてのページが既定の状態にリセットされます。 後で個人用設定をオンに戻すと、すべての個人用設定が再度適用されます。 また、システム内のすべてのユーザーの個人設定を完全に削除することもできます。 削除された個人用設定を復元することはできません。 したがって、このタスクを実行する前に、後に必要となる可能性があるすべての個人用設定をエクスポートすることを確認します。

**個人用設定**ページへのアクセス権を持つユーザーは、アクション ウィンドウの**インポート ビュー** ボタンを使用して、個人用ビューまたはテンプレートビューをインポートすることもできます。

## <a name="personalizing-inventory-dimensions"></a>在庫分析コードの個人用設定

ページ上の在庫分析コードの設定をカスタマイズするときは、**分析コードの表示** オプションを使用して作成した設定を考慮に入れます。 たとえば、個人用設定を使用して、バッチ番号在庫分析コードの列を非表示にしますが、次にそのページが開かれるとき、列は表示されます。 この動作が発生するのは、**分析コード表示**の設定が、表示されている在庫分析コードの列をコントロールするからです。 **分析コード表示設定**はすべてのページに適用され、個々のページの在庫分析コード フィールドの個人用設定をすべて上書きします。

したがって、前の例では、ページにバッチ番号在庫分析コードの列を表示したくない場合、そのページの**分析コードの表示**オプションの一部としてその分析コードをクリアする必要があります。
