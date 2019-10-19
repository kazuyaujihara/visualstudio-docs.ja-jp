---
title: 視覚化およびモデリング SDK のサポートされている Visual Studio のエディション |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools, supported Visual Studio editions
ms.assetid: 7c313ba0-031d-45b8-8220-eead61754747
caps.latest.revision: 29
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 89d65aab64ba82f152e2fe888ab10b88b73a7c42
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672378"
---
# <a name="supported-visual-studio-editions-for-visualization-amp-modeling-sdk"></a>視覚化 &amp; モデリング SDK のサポートされている Visual Studio のエディション
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

次に示すのは、作成環境と配置環境の [!INCLUDE[dsl](../includes/dsl-md.md)] でサポートされている Visual Studio のエディションの一覧です。 これらのエディションの詳細については、Microsoft [!INCLUDE[vsprvs](../includes/vsprvs-md.md)][デベロッパーセンター](http://go.microsoft.com/fwlink/?LinkId=75628)を参照してください。

## <a name="authoring-edition"></a>作成エディション
 DSL を定義するには、以下のコンポーネントをインストールしておく必要があります。

|||
|-|-|
|[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|Visual Studio SDK|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|Visual Studio Visualization and Modeling SDK|[http://go.microsoft.com/fwlink/?LinkID=186128](http://go.microsoft.com/fwlink/?LinkID=186128)|

## <a name="deployment-editions"></a>配置エディション
 [!INCLUDE[dsl](../includes/dsl-md.md)] では、作成したドメイン固有言語を配置するために、以下の構成がサポートされています。

- Visual Studio Enterprise

- Visual Studio Professional

- Visual Studio Shell (統合モード) 再頒布可能パッケージの再頒布可能パッケージ

- Visual Studio Shell (分離モード) 再頒布可能パッケージ

> [!NOTE]
> DSL をシェル製品で実行できるようにするには、拡張機能マニフェストで **[サポートされている VS Edition]** フィールドを設定する必要があります。 詳細については、「[ドメイン固有言語ソリューションの配置](../modeling/deploying-domain-specific-language-solutions.md)」を参照してください。

## <a name="see-also"></a>参照
 [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
