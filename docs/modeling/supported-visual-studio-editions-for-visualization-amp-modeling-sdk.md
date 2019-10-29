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
ms.openlocfilehash: efe452f059d7184e1f7c87fddd6bdc6c213ece8a
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72983725"
---
# <a name="supported-visual-studio-editions-for-visualization--modeling-sdk"></a>Visualization and Modeling SDK に対してサポートされている Visual Studio のエディション

次に示すのは、作成環境と配置環境の [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] でサポートされている Visual Studio のエディションの一覧です。 これらのエディションの詳細については、Microsoft Visual Studio[デベロッパーセンター](https://visualstudio.microsoft.com/)を参照してください。

## <a name="authoring-edition"></a>作成エディション

DSL を定義するには、以下のコンポーネントをインストールしておく必要があります。

|||
|-|-|
|Visual Studio|[http://go.microsoft.com/fwlink/?LinkId=185579](https://visualstudio.microsoft.com/)|
|Visual Studio SDK|[http://go.microsoft.com/fwlink/?LinkId=185580](/azure/devops/integrate/index?view=azure-devops&viewFallbackFrom=vsts)|
|Visual Studio Visualization and Modeling SDK|[http://go.microsoft.com/fwlink/?LinkID=186128](https://code.msdn.microsoft.com/Visualization-and-Modeling-313535db)|

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