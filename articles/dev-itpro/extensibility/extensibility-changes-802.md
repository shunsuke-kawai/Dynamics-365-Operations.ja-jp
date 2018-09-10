---
title: "Dynamics 365 for Finance and Operations 更新プログラム 8.0.2 の拡張機能の変更"
description: "このトピックでは、Dynamics 365 for Finance and Operations 更新プログラム 8.0.2 でリリースされた拡張機能を一覧表示します。"
author: FrankDahl
manager: AnnBe
ms.date: 06/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: josaw
ms.search.scope: Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2018-06-30
ms.dyn365.ops.version: App 8.0.2
ms.translationtype: HT
ms.sourcegitcommit: ba03473dd6fc31d51fd4e890acac1cd1494ef5a3
ms.openlocfilehash: f207323fce53e684514246c27bb159a5f48aa1eb
ms.contentlocale: ja-jp
ms.lasthandoff: 08/09/2018

---

# <a name="extensibility-changes-in-dynamics-365-for-finance-and-operations-update-802"></a>Dynamics 365 for Finance and Operations 更新プログラム 8.0.2 の拡張機能の変更

[!include [banner](../includes/banner.md)]

これは、Dynamics 365 for Finance and Operations 更新プログラム 8.0.2 に実装された拡張機能の一覧です。 拡張性をサポートする変更のスケジュールの詳細については、「[アプリケーション機能拡張計画](extensibility-roadmap.md)」を参照してください。

## <a name="refactored-methods-to-support-extensibility"></a>拡張性をサポートするためにリファクターされたメソッド

これらのメソッドはリファクターされ、コマンド チェーン、デリゲート、またはメンバーへのアクセスの提供によって、拡張性をサポートします。

| メソッド|
| --------------- |
|AccDistProcessorProjectExtension.allocateExistingDistribution|
|AccDistProcessorProjectExtension.createDistributionLists|
|AccDistProcessorProjectExtension.ledgerDimensionAllocationList|
|AgreementConfirmationDP.processReport|
|Bank_FR.checkControlText|
|Bank_IT.checkCIN|
|Bank_IT.checkRegistrationNum|
|CustVendCheque.initTmpChequePrintout|
|FBSpedFileCreator_Contabil_BR.createRecordI052|
|HierarchyTemplateCopying_proj.createFromHierarchySource|
|HierarchyTreeLookup.datasource smmActivities.init|
|InventDim.validateFieldCombination|
|InventTransWMS_Register|
|InventUpd_Financial.updateFinancialIssue|
|InventUpd_Registered|
|JmgPostStandardSystem.PostProjTime|
|MarkupAllocation.run|
|MarkupTrans。 MarkupTrans(datasource).active|
|PdsBatchAttribByItem.checkDuplicateAttributes|
|PdsBatchAttribByItem.validateFieldValue|
|PdsBatchAttribReserve.linkActive|
|PdsBatchAttributes.Datasource.PdsBatchAttributes.linkactive|
|ProjInvoiceProposalCreateLines.closeOK|
|ProjInvoiceProposalInsertLines.doCost|
|ProjInvoiceProposalInsertLines.doEmpl|
|ProjInvoiceProposalInsertLines.doItem|
|ProjInvoiceProposalInsertLines.doOnAccount|
|ProjPeriodPostingLedgerSales.enteItem|
|ProjPeriodPostingLedgerSales.enterCost|
|ProjPeriodPostingLedgerSales.enterEmpl|
|ProjPeriodPostingLedgerSales.enterRevenue|
|ProjPeriodPostingLedgerSales.run|
|ProjPlanVersionsManager.CopyHierarchy|
|ProjPlanVersionsManager::copyHierarchy|
|ProjPlanVersionsManager::createDraftVersion|
|ProjPlanVersionsManager::createTemplateHierarchy|
|PurchAutoCreate_PurchReq.initializeAndCreatePurchLine|
|PurchOrderLineSourceDocumentLineItem.calculateSourceDocumentAmountMap|
|PurchRFQPriceDiscAdmCreate.createPriceDiscAdmTrans|
|SalesFormLetter.validate|
|SalesTable2LineUpdatePrompt.salesTableFieldModifiedHandler|
|SalesUpdateRemain.cancelOpenOrderLinesDeliveryRemainder|
|WHSShipmentTable.createShipmentNotes|
|WHSUnShipLoadLineTmpDataCreator.createTmpLoadLineInventoryFromContainerLines|

## <a name="additional-extensibility-enhancements"></a>追加の拡張性強化

リファクタされたメソッドに加えて、次の拡張性の強化が実行されました。

- 拡張子からマップのサポート: CustVendTrans
- 拡張子からマップのサポート: CustVendTransOpen
- SQL 明細書の機能拡張をサポート: PriceDiscAdmCheckPost.postJournal
