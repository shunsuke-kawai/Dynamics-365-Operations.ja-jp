---
title: "登録 ID"
description: "このトピックでは、設定、登録IDの使用方法について説明します。"
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264824
ms.assetid: e86f0a35-be58-4ef5-b5ab-bcfc495eaa13
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 32cd09975861083b8940368ed53ae16e89bcd748
ms.lasthandoff: 03/31/2017


---

# <a name="registration-ids"></a>登録 ID

このトピックでは、設定、登録IDの使用方法について説明します。

多くの国や地域に登録番号またはIDを記録するためのさまざまなルールおよび要件があります。 このトピックでは、欧州諸国/地域の関係者に必要な設定の概要とサポートされる登録タイプの処理を提供します。 すべての国や地域に異なる都道府県の会社で提供される登録番号に関連するさまざまな国固有の機能をサポートするための要件があります。 登録番号の例は、社会保障番号(SSN)、税ID番号(TIN)、および欧州VATのID (EU) VAT IDが含まれます。 この機能は、一部のEU諸国の国別の要件を考慮に入れるすべての地域のすべての国で統一されたフレームワークを提供します。 次のセクションでは、登録IDを設定して処理するために使用する全体的な情報の流れについて説明します。

## <a name="registration-type-creation"></a>登録タイプの作成
登録IDを入力する前に、関係者が対象であること登録番号のタイプの登録タイプを設定する必要があります。 **コンフィギュレーション** ** ** &gt; グローバル アドレス帳、管理実行 &gt; **登録タイプ** &gt; **登録タイプ**異なる国/地域で仕入先、顧客、ワーカー、法人の登録タイプを作成および管理するページ。

|フィールド                 |説明      |
|------------------------------|----------------------------|                                                                           
| 氏名                | 登録タイプの名前。 |                                                                           
| 説明         | 登録タイプの説明。 |
| 国/地域      | 国/地域の固有ID。|
| 税務署長殿       | 登録タイプに関連付けられる税務当局。|
| 次のものに制限       | 税金の登録タイプに適用する制限のタイプ: どちらの従業員、組織。|
| 書式設定              | 登録タイプの検証形式。|
| 更新可能      | 入力した登録タイプの登録番号を更新することがわかります定義します。|
| 固有              | 登録タイプの登録番号は一意で定義します。 |
| 主要国 | 当事者が一つ以上の住所の国と、関連付けられ、登録IDがすべてこれらの住所で有効の場合、国で主工程として一つのアドレスを指定する必要があります。 基本として一つのIDのみを登録できます。 登録番号を国住所の主にのみ入力できる場合、定義します。 |

## <a name="assign-a-registration-type-to-a-registration-category"></a>登録カテゴリに登録タイプを割り当てます。
登録カテゴリは、税、関税、他の目的の国/地域を特に使用することを許可する国/地域登録IDです。 このカテゴリは、特定のID (を含むチェック ディジットなど)、複数のレポートは登録IDの検証ルールを定義します。 ページ**組織管理**を** &gt; グローバル アドレス帳**使用して、**登録タイプ** &gt; **登録カテゴリ**特定の国の登録タイプをサポートする登録カテゴリに配賦されます。

| フィールド            | 説明|
|-----------------------|----------------|
| 登録タイプ     | 登録タイプ、国/地域。|
| 次のものに制限         | 制限のタイプは、税額の登録タイプに適用します: どちらの従業員、組織。|
| 登録カテゴリ | 国の使用が承認された固有の登録ID。 AX7.1でサポートされているカテゴリの詳細な一覧は、あります。 |

## <a name="enter-registration-ids-for-global-address-book-records"></a>グローバル アドレス帳レコードの登録IDを入力します。
、Microsoft Dynamics 365のグローバル アドレス帳(GAB)は、顧客、仕入先、連絡先、取引関係、法人の連結された住所情報が含まれます。 詳細については、" "を参照してください、[グローバル アドレス帳の概要] (/dynamics365/operations/organization administration/overviewグローバル アドレス ブック)。 グローバル アドレス帳で保存される関係レコードは、一つ以上の住所レコードを含めることができます。 これらの住所は、請求または配送など、さまざまな目的で使用されます。 顧客、仕入先、ワーカー、法人の住所の登録IDを設定できます。 レコードが登録IDを入力する、**登録IDクリックして関係者を検索します (法人、仕入先、** **住所を管理します。**ページを開くには、当事者、法人、仕入先、顧客、ワーカーに関連するフォームでは、顧客ため)。 **税登録**]タブで、[**追加します。**、登録IDに関する次の情報を入力します。

|フィールド                |説明                                                |
|---------------------|-----------------------------------------------------------|
| 登録タイプ   | 選択した国/地域の登録タイプ。     |
| 登録番号 | 当事者登録ID。                                |
| 説明         | 登録番号の説明。               |
| 項             | 登録番号に関する追加情報。 |
| 発行機関      | 登録番号を発行機関。        |
| 発行日         | 登録番号の発行された日付。              |
| 開始           | 登録番号の有効日。           |
| 有効期限          | 登録番号の有効期限。          |

> [!NOTE]
> 法人、仕入先、顧客の課税控除番号はVAT IDに関連すると当事者に入力された登録IDから選択できます。

## <a name="search-for-records-by-registration-id"></a>登録IDごとにレコードの検索
登録IDに基づいて関係レコードの検索、当事者、法人、仕入先、顧客、およびために関連するフォームで使用できます。 **登録IDの検索基準**ページを開くには、[**登録ID検索**。 検索条件を指定し、をクリックして検索** **。 [グローバル アドレス帳から選択したレコードと当事者レコードに関連付けられているタイプを表示します。

## <a name="supported-registration-categories"></a>サポートされる登録カテゴリ
次の表に、Dynamics 365 for Operationsでサポートされている登録タイプを示します。 工程登録カテゴリ365 for Operationsに登録IDにMicrosoft Dynamics AX 2012を使い慣れている場合は、このフィールドに有効なテーブルにすると、そのフィールドを。

| 工程登録カテゴリ365 for Operations         |国/地域  | Dynamics AX 2012 "とフィールド|
|---------------------------------------------------------------|---------------------|---------------------------------|
| VAT ID                                                        | 欧州連合(EU)のすべての国|  課税控除番号 (AX2012 R3法での税IDタイプ) |
| エンタープライズ ID (COID)                                          | ベルギー チェコ エストニア ハンガリー ラトビア リスアニア ポーランド スイス | 企業番号 (EnterpriseNumber) の登録番号 (W) RegNum\_登録番号 (W) RegNum\_登録番号 (W) RegNum\_登録番号 (W) RegNum\_会社コード (EnterpriseCode) 登録W (UID番号) (AX2012 R3の法律タイプUID RegNum\_)  |
| 支店 ID                                                     | ベルギー            | 支店番号 (BranchNumber) |
| Spisováのznačka (代理店、セクションを発行登録番号)  | チェコ共和国     | 差込み数 (CommercialRegisterInsetNumber) はコマース登録 (CommercialRegisterSection) の商業登録 (CommercialRegister) セクションで保ちました|
| 税関顧客 ID                                           | フィンランド | カスタムの顧客番号 (CustomsCustomerNumber\_FI) |
| イン                                                           | ロシア連邦| イン (AX2012 R3の法律タイプのイン) |
| RRC                                                           | ロシア連邦| RRC (AX2012 R3の法律タイプRRC) |
| OKDP                                                          | ロシア連邦| OKDP (AX2012 R3の法律タイプOKDP) |
| OKPO                                                          | ロシア連邦| OKPO (AX2012 R3の法律タイプOKPO) |
| RCOAD                                                         | ロシア連邦| RCOAD (AX2012 R3の法律タイプRCOAD) |
| OGRN                                                          | ロシア連邦| OGRN (AX2012 R3の法律タイプOGRN)  |
| SNILS                                                         | ロシア連邦| SNILS (AX2012 R3の法律タイプSNILS) |
| CIFTS                                                         | ロシア連邦| CIFTS (AX2012 R3の法律タイプCIFTS) |

、必須の前提条件が処理する登録IDに関する詳細については、Lifecycle Services (LCS)のVAT IDについては、次のタスク記録を表示します:

-   VAT ID の設定
-   仕入先のVAT登録ID
-    VAT ID を使用する関係者の検索


