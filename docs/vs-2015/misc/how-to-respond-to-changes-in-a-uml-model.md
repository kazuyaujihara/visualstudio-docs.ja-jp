---
title: '方法: UML モデルの変更に対応 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
ms.assetid: f0300371-9cac-4def-a3f5-7d7b62dcd6f3
caps.latest.revision: 3
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4d012e3a8c8ef2a3848c4f602bb92e344550f1e1
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63434984"
---
# <a name="how-to-respond-to-changes-in-a-uml-model"></a>方法: UML モデルの変更に対応します。
Visual Studio の UML モデルで変更が生じたときに実行されるコードを作成できます。 このコードは、ユーザーが直接行った変更にも、他の Visual Studio 拡張機能による変更にも同様に応答します。 UML モデルをサポートする Visual Studio のバージョンを確認するには、「 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)」を参照してください。  
  
> [!WARNING]
> これらの手法は、UML API ではサポートされていません。 将来のバージョンの Visual Studio では機能しなくなる可能性があります。  
  
 サンプル コードについては、「 [UML:イベントと規則を使用して UML モデルの変更に応答](http://code.msdn.microsoft.com/UML-Responding-to-changes-c024cd4b)  
  
## <a name="see-also"></a>関連項目  
 [UML モデル内を移動します。](../modeling/navigate-the-uml-model.md)   
 [イベント ハンドラーには、モデルの外部で変更が反映されるまでください。](../modeling/event-handlers-propagate-changes-outside-the-model.md)   
 [サンプル: Color by Stereotype](http://go.microsoft.com/fwlink/?LinkId=213841)