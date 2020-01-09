---
title: アプリケーション拡張機能ロードマップ
description: このトピックでは、コードをオーバーレイ ベースから拡張ベースに変換するための要件とスケジュールについて説明します。
author: FrankDahl
manager: AnnBe
ms.date: 07/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2017-07-10
ms.dyn365.ops.version: Platform update 1
ms.openlocfilehash: bc418745e3f14b8c5b24383fbc66e0ba721bcbc7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191639"
---
# <a name="application-extensibility-roadmap"></a>アプリケーション拡張機能ロードマップ

[!include [banner](../includes/banner.md)]

実装およびアップグレード作業を減らすことが、開発チームの主要な取り組みです。 この構想のメリットは、短期間で、Microsoft とパートナーからの新しいイノベーションを利用でき、総保有コストが削減され、品質向上を実現できることです。 この取り組みの主要な部分は、製品のカスタマイズ方法を変更することです。 Dynamics AX 2012 では、いくつかの拡張性機能が製品に追加されました。 たとえば、プリイベントとポストイベントのメソッドを使用する、イベントに基づくカスタマイズの機能が導入されました。 拡張性機能は新しいアプリケーションへの進化と共に成長を続けています。  

拡張子ベース カスタマイズには、特に実装およびアップグレードの作業量を削減する場合に、オーバーレイヤー ベースのカスタマイズの従来のアプローチよりもいくつかの利点があります。  
+ オーバーレイヤー ベースのカスタマイズには、コード アップグレード、再コンパイル時刻、広範なテストが必要です。 これにより、修正プログラムをシームレスに適用する機能が制限されます。 これらの原価は、お客様が Microsoft やパートナーの新機能を含む新しいバージョンにアップグレードする際の阻害要因となります。  
+ 拡張子ベース カスタマイズはまた、開発経験を改善します。 オーバーレイされたカスタマイズを含むモデルは、基本オブジェクトと同じパッケージにする必要があります。 これにより、コンパイル サイクルが長くなり、パッケージの配布が大規模になります。 拡張子では、基準オブジェクトから分離して単体テストを行う方がはるかに簡単です。  
+ 拡張機能ベースのカスタマイズを通じてアップグレード コストを削減すると、サポートが必要なリリースの組み合わせが減るため、パートナーのサポート マトリックスが減少します。

これらの理由により、製品モデルを徐々にシールしてきており、拡張ベース カスタマイズのみをサポートします。 **AppPlatform** および **AppFoundation** が最初のものでした。 これらのモデルは、プラットフォーム更新プログラム 3 (2016 年 11 月) にオーバーレイされてシールされました。 これらのモデルにはバイナリ更新プログラムが月ごとに提供されており、アップグレード コストを削減しより速いリズムで顧客にイノベーションを届けるという目標を達成しています。 

Microsoft Dynamics 365 for Finance and Operations リリース 8.0 では、すべての製品モデルをシールします。 現在、拡張機能ベースのカスタマイズのみがサポートされています。

次の図は、オーバーレイから、拡張機能に移動したときに従ったロードマップを示しています。

![拡張性ロードマップ](media/extensibility-roadmap.jpg)

> [!NOTE]
> ソフト シールは、オーバーレイ時にコンパイラの警告を表示します。 ハード シールは、オーバーレイ時にコンパイラのエラーを表示します。 

最新のサポート ポリシーは、リリースから 3 年間のサポートを提供します。 このため、overlayered コードは 2017 年 11 月を起点として 3 年間継続して、Microsoft Dynamics 365 for Finance and Operations、Enterprise edition 7.3 リリースでサポートされます。 ただし、このコードは、オーバーレイ コードが拡張機能に移動されるまでは、後続の製品リリースに移動されません。  

この目標を達成するために、Microsoft、パートナー、顧客には相当量の作業があります。 ワークショップ、営業時間、ヘルプ トピック、および他のリソースは、このエコシステムのトレーニングおよび共同作業で使用可能です。 内部的には、コア プラットフォームとアプリケーションの両方でより多くの拡張性を構築する準備が整いました。 パートナーが拡張機能に移行しているときにパターンを定義するために、AppSource でのアプリケーションに関して、パートナーと密接に連携して作業しています。

アップグレード時の摩擦が緩和されるというメリットが得られ、イノベーションが実現されるため、オーバーレイを削除する作業を行う価値があります。