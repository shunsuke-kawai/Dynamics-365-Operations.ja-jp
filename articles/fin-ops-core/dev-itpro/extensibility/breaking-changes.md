---
title: 変更の分割
description: このトピックでは、分割変更について説明します。
author: smithanataraj
manager: AnnBe
ms.date: 09/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: 268724
ms.assetid: ''
ms.search.region: Global
ms.author: smithanataraj
ms.search.validFrom: 2018-09-09
ms.dyn365.ops.version: Platform update 20
ms.openlocfilehash: ef116f4a8834816546a7e8963f2efa409ba5a414
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191652"
---
# <a name="breaking-changes"></a>変更の分割

[!include [banner](../includes/banner.md)]

ソリューションを拡張可能にすると、後で拡張ポイントを壊さずに済むことにもなります。 分割変更は、コードのユーザーを分割できる任意の変更です。

このトピックでは、コードを分割できる変更のタイプを一覧表示します。 

> [!IMPORTANT]
> このリストは、包括的ではありません。 ここに登録されていない他のタイプの変更が分割変更となることもあります。

## <a name="data-model-changes"></a>データ モデルの変更

### <a name="general"></a>一般
データ モデルの変更で、データ アップグレード スクリプトを実行する必要がある場合は、ユーザーがデータ モデルを同期できなくなったり、データにアクセスできなくなる可能性があります。

### <a name="data-types"></a>データ型
+ **列挙を拡張可能から拡張不可に変更する**: ユーザーは、列挙の拡張を持っている可能性があります。
+ **列挙を拡張不可から拡張可能に変更する**: ユーザーは、比較で列挙を使用している可能性があります。 詳細については、[拡張可能な列挙の記述](extensible-enums.md)を参照してください。
+ **実数型の拡張データ型 (EDT) の小数点以下の精度を下げる**: ユーザーは、精度を使用するデータを入力する機能に依存関係を持っている可能性があります。
+ **文字列型の EDT のサイズを小さく**: ユーザーは文字列のサイズに依存関係を持っている可能性があります。
+ **別の EDT を拡張することにより EDT を特殊化する**: ユーザーは、文字列の長さ、または EDT への小数点以下の精度の拡張を持っている可能性があります。
+ **列挙が拡張可能な場合に、列挙型の EDT の列挙型を変更する**: ユーザーは、列挙の拡張を持っている可能性があります。
 
### <a name="data-model"></a>データ モデル
+ **テーブルを古い形式にし、情報がテーブルで入力されないようにする**: ユーザーは、情報が入力されるテーブルで依存関係を持っている可能性があります。
+ **フィールドを古い形式にし、情報がフィールドで入力されないようにする**: ユーザーは、情報が入力されるフィールドで依存関係を持っている可能性があります。
+ **フィールド グループの名前を変更する**: ユーザーは、フィールド グループへの拡張、またはコードまたはメタデータの依存関係を持っている可能性があります。
+ **制約またはインデックスの変更**
+ **テーブル マップを古い形式にし、テーブル マップが使用されないようにする**
+ **テーブル マップ フィールドを古い形式にする**
+ **テーブル マップ フィールドを追加する**
+ **テーブル マップ フィールド マッピングを削除する**
+ **データ エンティティを古い形式にする**
+ **データ エンティティ フィールドを古い形式にする**

## <a name="code-changes"></a>コードの変更

### <a name="class-members"></a>クラス メンバー
+ **パブリックまたは保護されたクラス レベルのメンバーを削除するか名前を変更する**: ユーザーは、拡張クラスでこれらのメンバーを使用している可能性があります。
+ **クラス メンバーをパブリックまたは保護から保護またはプライベートに変更する**: ユーザーは、フィールドに値をクエリ済みまたは割り当て済みの可能性があります。

### <a name="classes-and-interfaces"></a>クラスおよびインターフェイス
+ **クラスに抽象メソッドを追加する**: ユーザーは、派生タイプを作成した可能性があります。
+ **クラスに最終を追加する**: ユーザーは、派生タイプを作成した可能性があります。
+ **メソッドをインターフェイスに追加する**: 消費者は、独自の種類でインターフェイスを実装した可能性があります。
+ **パブリック クラスを古い形式にし、クラスのインスタンス化を停止する**: ユーザーは、インスタンス メソッドをオーバーライド、折り返し、またはサブスクライブしている可能性があります。

### <a name="methods"></a>メソッド
+ **アクセス修飾子を保護またはパブリックから別のアクセス修飾子に変更する**: ユーザーは、メソッドを呼び出し、オーバーライド、折り返し、サブスクライブした可能性があります。
+ **具体的なパブリックまたは保護されているメソッドを抽象的にする**: ユーザーは、クラスへのサブクラスを持っており、それらのサブクラスがメソッドを実装していないか、上位を呼び出す可能性もあります。
+ **メソッド パラメーターの名前を変更する**: ユーザーは、名前によるパラメーターの依存関係を持っている可能性があります (引数または C\# から外部でなど)。
+ **保護またはパブリック メソッドでメソッド パラメーターのタイプを追加、削除、または変更する**: ユーザーは、メソッドを呼び出し、オーバーライド、折り返し、サブスクライブした可能性があります。
+ **保護またはパブリック メソッドで既定のメソッド パラメーターを追加または削除する**: ユーザーは、メソッドを折り返しまたはサブスクライブした可能性があります。
+ **メソッドの戻り値の型を変更する**: ユーザーは、メソッドを呼び出し、オーバーライド、折り返し、またはサブスクライブした可能性があります。
+ **保護またはパブリック メソッドに Hookable(false) を追加する**: ユーザーは、メソッドを折り返しまたはサブスクライブした可能性があります。
+ **保護またはパブリック メソッドに Wrappable(false) を追加する**: ユーザーは、メソッドを折り返した可能性があります。
+ **プライベートまたは保護メソッドから Hookable(true) を削除する**: ユーザーは、メソッドをサブスクライブした可能性があります。
+ **プライベートまたは保護メソッドから Wrappable(true) を削除する**: ユーザーは、メソッドを折り返した可能性があります。
+ **メソッドから Replaceable(true) を削除する**: ユーザーは、条件付きでメソッドを折り返した可能性があります。
+ **保護またはパブリック メソッドに最終を追加する**: ユーザーは、メソッドをオーバーライド、折り返し、またはサブスクライブした可能性があります。
+ **インスタンスから静的または静的からインスタンスにメソッドを変更する**: ユーザーは、メソッドを呼び出し、オーバーライド、折り返し、サブスクライブした可能性があります。
+ **メソッドを古い形式にし、メソッドの呼び出しを停止する**: ユーザーは、メソッドを呼び出し、オーバーライド、折り返し、またはサブスクライブしている可能性があります。
+ **メソッドの責任を変更する**: ユーザーは、メソッドを呼び出し、オーバーライド、折り返し、またはサブスクライブした可能性があります。
+ **メソッドへの参照を削除する**: ユーザーは、メソッドをオーバーライド、折り返し、またはサブスクライブしている可能性があり、ロジックが実行されることを期待している可能性があります。

### <a name="delegates"></a>委任
+ **シグネチャで変更を行う**: ユーザーは、動的にサブスクライブしている場合があります。
+ **デリゲートへの参照を削除する**: ユーザーは、サブスクライブしている可能性があり、ロジックが実行されることを期待している可能性があります。

## <a name="label-changes"></a>ラベルの変更
+ **ラベルを変更または削除する**: ユーザーは、ラベル テキストの現在のコンテキストにあるラベルと渡されたパラメーターなどを使用している可能性があります。 今後は、ラベルの変更が発生した場合は新しいラベルを追加することをお勧めします。

## <a name="application-element-changes"></a>アプリケーション要素の変更
+ **要素を削除する**: ユーザーは、要素の存在にコンパイル時間の依存関係を持っている可能性があります。
     
## <a name="metadata-extensions"></a>メタデータの拡張
+ **メタデータまたは拡張クラスの名前付けガイドラインに従わない**: ユーザーは、同じ名前を持つ要素を持っている可能性があります。