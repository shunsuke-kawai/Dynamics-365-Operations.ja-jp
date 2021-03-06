---
title: POS ビューの拡張によるカスタム列およびアプリ バー ボタンの追加
description: このトピックでは、[顧客の追加/編集] 画面などの既存の POS ビューを拡張する方法について説明します。
author: mugunthanm
manager: AnnBe
ms.date: 10/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Operations, Retail
ms.custom: 24411
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2017-11-22
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b0ff3afc24796c40189814f26d6834880a322927
ms.sourcegitcommit: a3fbcd63f10f204350a058a124ba80abeb34309e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "2564181"
---
# <a name="extend-pos-views-to-add-custom-columns-and-app-bar-buttons"></a>POS ビューの拡張によるカスタム列およびアプリ バー ボタンの追加

[!include [banner](../../includes/banner.md)]

このトピックでは、既存の [販売時点管理 (POS)] ビューを拡張する方法について説明します。 **トランザクション** 画面および **ようこそ** 画面を拡張するには、画面レイアウト デザイナーを使用します。 **顧客の追加/編集** 画面など、他のすべての POS ビューを拡張するには、Retail ソフトウェア開発キット (SDK) を使用します。 このトピックでは、Retail SDK による既存の POS ビューの拡張について説明します。



POS ビューでは、次の拡張ポイントとパターンがサポートされます。

- **カスタム アプリケーション バーのボタン** - 選択したページのアプリケーション バーにカスタム ボタンを追加します。
- **カスタム列セット** - 選択したページのグリッド列をカスタム列に置き換えます。
- **カスタム コントロール** - 選択したページに、新しいコントロールを追加します。

## <a name="pos-views-that-currently-support-extensions"></a>現在拡張機能をサポートする POS ビュー

次のテーブルに、現在拡張機能をサポートしている POS ビューを示します。 また、各 POS ビューがサポートする拡張ポイントのタイプも示します。

> [!NOTE]
> 今後のリリースと修正プログラムで、他のビューの拡張ポイントをさらにサポートします。


| POS ビュー                        | カスタム コントロールがサポートされています | カスタム列がサポートされています | カスタムのアプリ バーのボタンがサポートされています |
|---------------------------------|-------------------------------|------------------------------|--------------------------------------|
| カート ビュー (画面レイアウトに基づく) | 有                           | 有                          | 無                                   |
| CustomerAddEditView             | 有                           | 無                           | 有                                  |
| CustomerDetailsView             | 有                           | 無                           | 有                                  |
| SearchView                      | 無                            | 有                          | 有                                  |
| InventoryLookupView             | 無                            | 有                          | 有                                  |
| ShowJournalView                 | 無                            | 有                          | 有                                  |
| SimpleProductDetailsView        | はい                           | いいえ                           | はい                                  |
| AddressAddEditView              | はい                           | いいえ                           | はい                                    |
| PaymentView                     | いいえ                            | いいえ                           | はい                                  |
| PriceCheckView                  | はい                           | いいえ                           | はい                                   |
| PriceCheckViewPhone             | いいえ                            | いいえ                           | はい                                   |
| SearchOrdersView                | いいえ                            | はい                          | いいえ                                   |
| SearchPickingAndReceivingView   | 無                            | 有                          | 有                                   |
| CustomerOrderHistoryView        | 無                            | 有                          | 無                                   |
| SearchStockCountView            | 無                            | 有                          | 無                                   |
| StockCountDetailsView           | 無                            | 有                          | 無                                   |
| ResumeCartView                  | 無                            | 有                          | 無                                    |
| OrderFulfillmentView            | 無                            | 無                           | 有                                   |
| InventoryLookupMatrixView       | 無                            | 無                           | 有                                   |
| SuspendTransactionView          | 無                            | 有                          | 無                               |   
| ManageShiftView                 | 無                            | 無                           | 有                               |  
| ReportDetailsView               | 無                            | 無                           | 有                               |
| SearchReceiptsView              | 無                            | 無                           | 有                               |
| StockCountDetailsView           | いいえ                            | いいえ                           | はい                               |
| TransferOrderDetailsView        | いいえ                            | いいえ                           | はい                               |
| FulfillmentLineView             | いいえ                            | はい                          | いいえ                               |
| ReturnTransactionView           | いいえ                            | はい                          | はい                               |
| PickingAndReceivingDetailsView  | いいえ                            | はい                          | はい                    |
| PickingAndReceivingDetailsView (高度な倉庫)  | いいえ                            | はい                          | はい           |



> [!NOTE]
> 上記に表示される表は、リリースされた最新バージョンおよび修正プログラムに基づいて更新されています。 旧バージョンでは、これらの拡張ポイントの一部は使用できません。

> [!NOTE]
> 仕訳帳の表示 (行グリッド) と 返品トランザクション ビューのカスタム列は、行サブ フィールドの使用をサポートしています。 これらのサブ フィールドは、情報コード メッセージ、シリアル番号、割引の値などのように、列ではなく行として表示されます。

フィルターの拡張機能は**仕訳帳ビューを表示**および**注文ビューを検索**でもサポートされ、カスタム フィルターを追加します。 **注文ビューを検索** は拡張機能を使用してユーザー インターフェイス (UI) に検索用の既定パラメーターを設定することもサポートしています。 たとえば、既定のストア検索パラメータを追加する場合は、拡張機能を使用して UI に表示することでそれを実行できます。 

## <a name="add-a-custom-column-and-an-app-bar-button"></a>カスタム列とアプリ バー ボタンの追加

1. Microsoft Visual Studio 2015 を管理者として起動します。
2. **ModernPOS** ソリューションを **…\\RetailSDK\\POS** から開きます。
3. **POS.Extensions** プロジェクトで、**SearchExtension** というフォルダーを作成します。
4. **SearchExtension** フォルダーで、**ViewExtensions** というフォルダーを作成します。
5. **ViewExtensions** フォルダーで、**Search** というフォルダーを作成します。
6. **Search** フォルダーで、**CustomCustomerSearchColumns.ts** という Typescript ファイルを作成します。
7. **CustomCustomerSearchColumns.ts** ファイルで、次の **import** ステートメントを追加して関連するエンティティおよびコンテキストをインポートします。

    ```Typescript
    import { ICustomerSearchColumn } from "PosApi/Extend/Views/SearchView";
    import { ICustomColumnsContext } from "PosApi/Extend/Views/CustomListColumns";
    import { ProxyEntities } from "PosApi/Entities";
    ```

8. ファイルに既存の列とカスタム列を追加します。

    ```Typescript
    export default (context: ICustomColumnsContext): ICustomerSearchColumn[] => {
        return [
            {
                title: context.resources.getString("string_2"),
                computeValue: (row: ProxyEntities.GlobalCustomer): string => { return row.AccountNumber; },
                ratio: 15,
                collapseOrder: 5,
                minWidth: 120
             }, {
                title: context.resources.getString("string_3"),
                computeValue: (row: ProxyEntities.GlobalCustomer): string => { return row.FullName; },
                ratio: 20,
                collapseOrder: 4,
                minWidth: 200
            }, {
                title: context.resources.getString("string_4"),
                computeValue: (row: ProxyEntities.GlobalCustomer): string => { return row.FullAddress; },
                ratio: 25,
                collapseOrder: 1,
                minWidth: 200
            }, {
                title: context.resources.getString("string_5"),
                computeValue: (row: ProxyEntities.GlobalCustomer): string => { return row.Email; },
                ratio: 20,
                collapseOrder: 2,
                minWidth: 200
            }, {
                title: context.resources.getString("string_7"),
                computeValue: (row: ProxyEntities.GlobalCustomer): string => { return row.Phone; },
                ratio: 20,
                collapseOrder: 3,
                minWidth: 120
            }
        ];
    };
    ```

9. ここで、列の名前のローカライズのためのリソース ファイルを追加します。 **SearchExtension** フォルダーで、**Resources** というフォルダーを作成します。
10. **Resources** フォルダーで、**Strings** というフォルダーを作成します。
11. **Strings** フォルダーで、**en-US** というフォルダーを作成します。
12. **en-us** フォルダーで、**resources.resjson** というファイルを作成します。
13. **resources.resjson** ファイルに次のコードを追加します。

    ```Typescript
    {
        //======================== Sample View extensions strings. ========================
        "string_0" : "Quick compare products",
        "_string_0.comment" : "Product search page app bar command label.",
        "string_1" : "View customer summary",
        "_string_1.comment" : "Customer search page app bar command label.",
        //======================== Column names. ========================
        "string_2" : "ACCOUNT NUMBER_CUSTOMIZED",
        "_string_2.comment" : "Customer search column name.",
        "string_3" : "NAME",
        "_string_3.comment" : "Customer search column name.",
        "string_4" : "ADDRESS",
        "_string_4.comment" : "Customer search column name.",
        "string_5" : "CONTACT EMAIL",
        "_string_5.comment" : "Customer search column name.",
        "string_7" : "PHONE NUMBER",
        "_string_7.comment" : "Customer search column name."
    }
    ```

14. **SearchExtension** フォルダーで、**DialogSample** というフォルダーを作成します。
15. **DialogSample** フォルダーで、**MessageDialog.ts** という Typescript ファイルを作成します。
16. **MessageDialog.ts** ファイルで、次の **import** ステートメントを追加して関連するエンティティおよびコンテキストをインポートします。

    ```Typescript
    import { ShowMessageDialogClientRequest, ShowMessageDialogClientResponse, IMessageDialogOptions } from "PosApi/Consume/Dialogs";
    import { IExtensionContext } from "PosApi/Framework/ExtensionContext";
    import { ClientEntities } from "PosApi/Entities";
    ```

17. **MessageDialog** という名前のクラスを作成します。

    ```Typescript
    export default class MessageDialog {}
    ```

18. **MessageDialog** クラスで、次の **show** メソッドを追加します。

    ```Typescript
    public static show(context: IExtensionContext, message: string): Promise<void> {
        let promise: Promise<void> = new Promise<void>((resolve: () => void, reject: (reason?: any) => void) => 
        {
            let messageDialogOptions: IMessageDialogOptions = {
                title: "Extension Message Dialog",
                message: message,
                showCloseX: true, // this property will return "Close" as result when "X" is clicked to close dialog.
                button1: {
                    id: "Button1Close",
                    label: "OK",
                    result: "OKResult"
                },
                button2: {
                    id: "Button2Cancel",
                    label: "Cancel",
                    result: "CancelResult"
                }
            };
            let dialogRequest: ShowMessageDialogClientRequest<ShowMessageDialogClientResponse> =
                new ShowMessageDialogClientRequest<ShowMessageDialogClientResponse>(messageDialogOptions);
                context.runtime.executeAsync(dialogRequest).then((
                    result: ClientEntities.ICancelableDataResult<ShowMessageDialogClientResponse>) => {
                if (!result.canceled) {
                    context.logger.logInformational("MessageDialog result: " + result.data.result.dialogResult);
                    resolve();
                }
            }).catch((reason: any) => {
            context.logger.logError(JSON.stringify(reason));
            reject(reason);
            });
        });
        return promise;
    }
    ```

19. ここで、選択した顧客に関する詳細を含むダイアログ ボックスを開くために、検索ビューにカスタムのアプリ バー ボタンを追加します。 **ViewExtensions** フォルダーで、**ViewCustomerSummaryCommand.ts** という Typescript ファイルを作成します。
20. **ViewCustomerSummaryCommand.ts** ファイルで、次の **import** ステートメントを追加して関連するエンティティおよびコンテキストをインポートします。

    ```Typescript
    import { ProxyEntities } from "PosApi/Entities";
    import { ArrayExtensions, ObjectExtensions } from "PosApi/TypeExtensions";
    import { IExtensionCommandContext } from "PosApi/Extend/Views/AppBarCommands";
    import * as SearchView from "PosApi/Extend/Views/SearchView";
    import MessageDialog from "../DialogSample/MessageDialog";
    ```

21. **ViewCustomerSummaryCommand** という名前のクラスを作成し、**CustomerSearchExtensionCommandBase** からクラスを拡張します。

    ```Typescript
    export default class ViewCustomerSummaryCommand extends SearchView.CustomerSearchExtensionCommandBase {}
    ```

22. **ViewCustomerSummaryCommand** クラスで、選択した顧客を検索するときに、結果をキャプチャするプライベート変数を宣言します。

    ```Typescript
    private _customerSearchResults: ProxyEntities.GlobalCustomer[];
    ```

23. クラス **コンストラクター** メソッドを追加して、検索ハンドラーを初期化してクリアします。

    ```Typescript
    constructor(context: IExtensionCommandContext<SearchView.ICustomerSearchToExtensionCommandMessageTypeMap>) {
        super(context);
        this.id = "viewCustomerSummaryCommand";
        this.label = context.resources.getString("string_1");
        this.extraClass = "iconLightningBolt";
        this._customerSearchResults = [];
        this.searchResultsSelectedHandler = (data: SearchView.CustomerSearchSearchResultSelectedData): void => {
            this._customerSearchResults = data.customers;
            this.canExecute = true;
        };
        this.searchResultSelectionClearedHandler = (): void => {
            this._customerSearchResults = [];
            this.canExecute = false;
        };
    }
    ```

24. **init** メソッドを追加して、**表示**プロパティを初期化します。

    ```Typescript
    protected init(state: SearchView.ICustomerSearchExtensionCommandState): void {
        this.isVisible = true;
    }
    ```

25. アプリ ボタン クリック ハンドラーを処理する**実行**メソッドを追加します。 **execute** メソッドは、ハンドラーから選択した顧客のデータを読み取り、単純なダイアログ ボックスに表示します。

    ```Typescript
    protected execute(): void {
        let customer: ProxyEntities.GlobalCustomer = ArrayExtensions.firstOrUndefined(this._customerSearchResults);
        if (!ObjectExtensions.isNullOrUndefined(customer)) {
            let message: string = "Customer Account: " + (customer.AccountNumber || "") + " | ";
            message += "Name: " + customer.FullName + " | ";
            message += "Phone Number: " + customer.Phone + " | ";
            message += "Email Address: " + customer.Email;
            MessageDialog.show(this.context, message);
        } 
    }
    ```

    コード サンプルの全体は次のようになります。

    ```Typescript
    import { ProxyEntities } from "PosApi/Entities";
    import { ArrayExtensions, ObjectExtensions } from "PosApi/TypeExtensions";
    import { IExtensionCommandContext } from "PosApi/Extend/Views/AppBarCommands";
    import * as SearchView from "PosApi/Extend/Views/SearchView";
    import MessageDialog from "../../DialogSample/MessageDialog";
    export default class ViewCustomerSummaryCommand extends SearchView.CustomerSearchExtensionCommandBase {
        private _customerSearchResults: ProxyEntities.GlobalCustomer[];

        /**
        * Creates a new instance of the ViewCustomerSummaryCommand class.
        * @param {IExtensionCommandContext<CustomerDetailsView.ICustomerSearchToExtensionCommandMessageTypeMap>} context The command context.
        * @remarks The command context contains APIs through which a command can communicate with POS.
        */
        constructor(context: IExtensionCommandContext<SearchView.ICustomerSearchToExtensionCommandMessageTypeMap>) {
            super(context);
            this.id = "viewCustomerSummaryCommand";
            this.label = context.resources.getString("string_1");
            this.extraClass = "iconLightningBolt";
            this._customerSearchResults = [];

            this.searchResultsSelectedHandler = (data: SearchView.CustomerSearchSearchResultSelectedData): void => {
                this._customerSearchResults = data.customers;
                this.canExecute = true;
            };

            this.searchResultSelectionClearedHandler = (): void => {
                this._customerSearchResults = [];
                this.canExecute = false;
            };
        }

        /**
        * Initializes the command.
        * @param {CustomerDetailsView.ICustomerDetailsExtensionCommandState} state The state used to initialize the command.
        */
        protected init(state: SearchView.ICustomerSearchExtensionCommandState): void {
            this.isVisible = true;
        }

        /**
        * Executes the command.
        */
        protected execute(): void {
            let customer: ProxyEntities.GlobalCustomer = ArrayExtensions.firstOrUndefined(this._customerSearchResults);
            if (!ObjectExtensions.isNullOrUndefined(customer)) {
                let message: string = "Customer Account: " + (customer.AccountNumber || "") + " | ";
                message += "Name: " + customer.FullName + " | ";
                message += "Phone Number: " + customer.Phone + " | ";
                message += "Email Address: " + customer.Email;
                MessageDialog.show(this.context, message);
            }
        }
    }
    ```

26. **SearchExtension** フォルダーで、**manifest.json** という JSON ファイルを作成します。
27. **manifest.json** ファイルに次のコードを追加します。

    ```Typescript
    {
        "$schema": "../manifestSchema.json",
        "name": "Pos_Extensibility_Samples",
        "publisher": "Microsoft",
        "version": "7.2.0",
        "minimumPosVersion": "7.2.0.0",
        "components": {
            "resources": {
                "supportedUICultures": [ "en-US" ],
                "fallbackUICulture": "en-US",
                "culturesDirectoryPath": "Resources/Strings ",
                "stringResourcesFileName": "resources.resjson",
                "cultureInfoOverridesFilePath": "Resources/cultureInfoOverrides.json"
            },
            "extend": {
                "views": {
                    "SearchView": {
                        "customerAppBarCommands": [ { "modulePath": "ViewExtensions/Search/ViewCustomerSummaryCommand" } ],
                        "customerListConfiguration": { "modulePath": "ViewExtensions/Search/CustomCustomerSearchColumns" }
                    }
                }
            }
        }
    }
    ```

28. **POS.Extensions** プロジェクトで **extensions.json** ファイルを開き、**SearchExtension** サンプルで更新して、POS が実行時にこの拡張機能に含まれるようにします。

    ```Typescript
    {
        "extensionPackages": [
        {
            "baseUrl": "SampleExtensions2"
        },
        {
            "baseUrl": "SearchExtension"
        }
        ]
    }
    ```

29. **tsconfig.json** ファイルで、除外リストに拡張パッケージ フォルダーをコメントアウトします。 POS は、このファイルを使用して、拡張機能を追加または除外します。 既定では、リストに除外された拡張リスト全体が含まれています。 拡張機能を POS の一部として含めるには、次に示すように、拡張フォルダーの名前を追加し、除外リストの拡張子をコメントアウトします。

    ```Typescript
    "exclude": [
    "SampleExtensions"
    //"SampleExtensions2",
    //"SearchExtension"
    ],
    ```

30. プロジェクトをコンパイル、およびリビルドします。

## <a name="validate-the-customization"></a>カスタマイズの検証

カスタマイズを検証するには、これらの手順に従います。

1. オペレーター ID に **000160**、パスワードに **123** を使用して Retail Modern POS にサインインします。
2. 上部の検索バーを使って顧客 **2001** を検索します。

    追加したカスタム列が表示されました。

3. 顧客を選択し、新しいアプリケーション バーのボタンを選択します。 選択した顧客に関する詳細を含むダイアログ ボックスが表示されます。
