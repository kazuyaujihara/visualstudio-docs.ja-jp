---
title: UML モデリング機能拡張の API リファレンス |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
helpviewer_keywords:
- UML - extending
- UML API
- UML model, API
ms.assetid: 2b2ffe93-c358-4d28-a5e5-3d0474629b58
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 12eadb9844df5da78b11367708fed715f1c13672
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68159672"
---
# <a name="api-reference-for-uml-modeling-extensibility"></a>UML モデリング機能拡張の API リファレンス
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

プログラム コードを記述して、Visual Studio を使用して作成したモデルを読み取ったり、変更したりすることができます。 API リファレンスには、この操作を実行するために役に立つ、特定のクラスに関する情報が掲載されています。 タスク指向の詳細については、下にあるトピックを参照してください。 [UML を拡張モデルと図](../modeling/extend-uml-models-and-diagrams.md)します。 UML モデルをサポートする Visual Studio のバージョンを確認するには、「 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)」を参照してください。  
  
## <a name="assemblies"></a>アセンブリ  
  
|Assembly|実行できる操作|  
|--------------|--------------------------------|  
|Microsoft.VisualStudio.Uml.Interfaces.dll|-読み取りし、IUseCase、IAssociation などのモデル要素を変更します。<br />要素間のリレーションシップを移動します。<br /><br /> 名前空間と型は、UML 仕様で定義されたものに対応しています。|  
|Microsoft.VisualStudio.ArchitectureTools.Extensibility.dll|-モデル要素の新しいインスタンスを作成します。<br />アクセスして、図形と図を変更します。|  
  
## <a name="see-also"></a>関連項目  
 [UML モデルと図を拡張します。](../modeling/extend-uml-models-and-diagrams.md)   
 [Modeling SDK for Visual Studio の API リファレンス](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)
