---
title: 視覚化およびモデリング SDK でサポートされている Visual Studio のエディション
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools, supported Visual Studio editions
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1fdfe698096da53abf28aa583c816d9238810333
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72609344"
---
# <a name="supported-visual-studio-editions-for-visualization--modeling-sdk"></a>Visualization and Modeling SDK に対してサポートされている Visual Studio のエディション

次に示すのは、作成環境と配置環境の [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] でサポートされている Visual Studio のエディションの一覧です。 これらのエディションの詳細については、Microsoft Visual Studio[デベロッパーセンター](http://go.microsoft.com/fwlink/?LinkId=75628)を参照してください。

## <a name="authoring-edition"></a>作成エディション

DSL を定義するには、以下のコンポーネントをインストールしておく必要があります。

|||
|-|-|
|Visual Studio|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|Visual Studio SDK|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|Visual Studio Visualization and Modeling SDK|[http://go.microsoft.com/fwlink/?LinkID=186128](http://go.microsoft.com/fwlink/?LinkID=186128)|

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="deployment-editions"></a>配置エディション

[!INCLUDE[dsl](../modeling/includes/dsl_md.md)] では、作成したドメイン固有言語を配置するために、以下の構成がサポートされています。

- Visual Studio Enterprise

- Visual Studio Professional

- Visual Studio Shell (統合モード) 再頒布可能パッケージの再頒布可能パッケージ

- Visual Studio Shell (分離モード) 再頒布可能パッケージ

> [!NOTE]
> DSL をシェル製品で実行できるようにするには、拡張機能マニフェストで **[サポートされている VS Edition]** フィールドを設定する必要があります。 詳細については、「[ドメイン固有言語ソリューションの配置](msi-and-vsix-deployment-of-a-dsl.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)