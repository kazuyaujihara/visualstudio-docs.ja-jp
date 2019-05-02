---
title: '方法: 組み込みの配色可能な項目を使用して、|Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- colorable items
- language services, built-in colorable items
ms.assetid: 5e5f3436-6bad-4fd2-8823-6a30353ba648
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a86361f28eb4c73a65093fc5c80ef15ddf791a77
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63436138"
---
# <a name="how-to-use-built-in-colorable-items"></a>方法: ビルトインの配色可能な項目の使用
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

組み込みの配色可能な項目を使用する前にする必要があります最初に通知する、統合開発環境 (IDE) ここで可能性のあるカスタム独自配色可能な項目を提供していない<xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems>オブジェクト。 言語サービスのレジストリ エントリを設定して行います。  
  
### <a name="to-use-built-in-colorable-items"></a>組み込みの配色可能な項目を使用するには  
  
1. HKEY_LOCAL_MACHINE\VisualStudio\\*X.Y*\Languages\Language サービス\\*言語名*ここで、 *X.Y* のバージョンです[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]と*言語名*名前を指定します、言語の作成という DWORD レジストリ エントリ値`RequestStockColors`します。  
  
2. 設定、`RequestStockColors`レジストリ エントリの値を 1 にします。  
  
     レジストリ エントリを colorizer を作成した後<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>メソッドのメンバーが使用できる、<xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS>エディターによって使用される色の属性の配列を埋めるために列挙します。  
  
    > [!NOTE]
    > カスタムの配色可能な項目を指定する場合は、このレジストリ エントリを設定しないでください。 詳細については、次を参照してください。[カスタム装飾が可能なアイテム](../../extensibility/internals/custom-colorable-items.md)します。  
  
## <a name="see-also"></a>関連項目  
 [構文のカスタム エディターで色分け表示](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [構文の色分け、従来の言語サービス](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [構文の色分けを実装します。](../../extensibility/internals/implementing-syntax-coloring.md)   
 [カスタムの配色可能な項目](../../extensibility/internals/custom-colorable-items.md)   
 [従来の言語サービスの登録](../../extensibility/internals/registering-a-legacy-language-service2.md)
