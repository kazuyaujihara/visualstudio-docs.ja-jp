---
title: UML コンポーネント図の要素のプロパティ |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.teamarch.componentdiagram.shapes.properties
helpviewer_keywords:
- component diagrams, properties
- UML, element properties
ms.assetid: fa0a9460-6675-4642-aa00-50f8719a892d
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c7f3f30d08fb62defec5e783da286e968a6b17c9
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63444434"
---
# <a name="properties-of-elements-on-uml-component-diagrams"></a>UML コンポーネント図の要素のプロパティ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

UML コンポーネント図の各要素には、プロパティがあります。 要素のプロパティを表示するには、図、または要素を右クリックして**UML モデル エクスプ ローラー**し**プロパティ**します。 プロパティが表示されます、**プロパティ**ウィンドウ。  
  
> [!NOTE]
> このトピックでは、UML コンポーネント図の要素のプロパティについて説明します。 UML コンポーネント図を読み取る方法の詳細については、次を参照してください。 [UML コンポーネント図。Reference](../modeling/uml-component-diagrams-reference.md)」(UML クラス図: リファレンス) を参照してください。 UML コンポーネント図を描画する方法の詳細については、次を参照してください。 [UML コンポーネント図。ガイドライン](../modeling/uml-component-diagrams-guidelines.md)します。  
  
## <a name="properties-of-elements"></a>要素のプロパティ  
  
|プロパティ|既定値|要素|説明|  
|--------------|-------------|-------------|-----------------|  
|**Name**|既定名|すべて|要素を指定します。|  
|**修飾名**|Namespace::名前|すべて|要素を一意に指定します。<br /><br /> コンポーネントまたは型の名前に、要素を格納するパッケージの修飾名がプレフィックスとして付けられます。<br /><br /> パートまたはポートの名前に、要素を所有するコンポーネントの修飾名がプレフィックスとして付けられます。|  
|**作業項目**|関連付けなし|すべて|この要素に関連付けられている作業項目の数。 作業項目に関連付けるを参照してください。[モデル要素をリンクし、作業項目](../modeling/link-model-elements-and-work-items.md)します。|  
|**説明**|(なし)|すべて|ここに、要素に関する一般的なメモを作成できます。|  
|**色**|(型の既定値)|コンポーネント、パート、委譲、パート アセンブリ|シェイプの色。 他のプロパティとは異なり、これはシェイプに表示されるモデル要素ではなく、シェイプの色です。|  
|**直接インスタンス化します。**|True|コンポーネント|コンポーネントは設計の成果物としてのみ存在します。 実行時には、そのパートのみ存在します。|  
|**抽象型**|False|コンポーネント|コンポーネント定義は、他のコンポーネントを特化できる汎化としてのみ使用できます。|  
|**可視性**|Public|コンポーネント、パート、ポート|**パブリック**- グローバルに参照できます。<br /><br /> **パッケージ**- パッケージ内で参照できます。<br /><br /> **プライベート**- 所有コンポーネント内で参照できます。<br /><br /> **保護されている**- 所有者から派生したコンポーネントを参照できます。|  
|**Type**|作成時の型|パート<br /><br /> ポート|パートの型はコンポーネントまたはクラスです。<br /><br /> ポートの型はインターフェイスです。|  
|**多重度**|1|パート<br /><br /> ポート|親コンポーネントの一部を構成する指定された型のインスタンスの数を示します。<br /><br /> `1` - 1 個。<br /><br /> `0..1` - 1 個またはなし。<br /><br /> `*` - 任意の数のコレクション。<br /><br /> `n..m` - n ～ m 個のインスタンスのコレクション。|  
|**動作します。**|False|ポート|true の場合、このポートへのメッセージは、コンポーネントの一部として (そのパートではなく) 記述されるアクティビティまたは操作で処理されます。|  
|**サービスは、します。**|False|ポート|true の場合、このポートはこのコンポーネントの発行されたインターフェイスの一部です。|  
|**LinkedPackage**|モデル|ダイアグラム|この図に追加された要素の既定の名前空間。|  
  
## <a name="see-also"></a>関連項目  
 [UML ユース ケース図: 参照](../modeling/uml-use-case-diagrams-reference.md)   
 [UML ユース ケース図: ガイドライン](../modeling/uml-use-case-diagrams-guidelines.md)
