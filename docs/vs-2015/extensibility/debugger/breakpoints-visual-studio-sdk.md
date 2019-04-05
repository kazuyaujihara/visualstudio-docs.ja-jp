---
title: ブレークポイント (Visual Studio SDK) |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- breakpoints
ms.assetid: acfcabed-9f2f-436c-ad18-7ca2f45d631b
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 39c13271bad984291f609ef45505549855bee99f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977412"
---
# <a name="breakpoints-visual-studio-sdk"></a>ブレークポイント (Visual Studio SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

ブレークポイントの 3 種類があります。 保留中、バインド、およびエラー。  
  
 **保留中のブレークポイント A:**  
  
- 1 つまたは複数のプログラム内の 1 つまたは複数のコード コンテキストにブレークポイントをバインドするために必要なすべての情報を格納する抽象化。 毎回、原因を読み込むコードをデバッグ対象のプログラム デバッグ エンジンを確認します保留中のすべてのブレークポイントをバインドできるかどうかを参照してください。  
  
   自体保留中のブレークポイントことはありませんコードにバインドしますではなく収集し、言いますを生成するすべてのバインドされたブレークポイントを含みます。  
  
- によって表される、 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)インターフェイス。  
  
  **バインドされたブレークポイント。**  
  
- ブレークポイントの抽象化に関連付けられているか 1 つのコード コンテキストに制限されます。 バインドされた各ブレークポイントは保留中のブレークポイントへの応答で生成されます。 ただし、保留中のブレークポイントは、複数のバインドされたブレークポイントが生成ことができます。  
  
   コードが読み込まれると、バインドされたブレークポイントはバインドされていないし、破棄されます。  
  
- によって表される、 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)インターフェイス。  
  
  **エラー ブレークポイントの場合:**  
  
- コードのコンテキストに保留中のブレークポイントをバインドするときにエラーを説明するための抽象型です。 エラー、ブレークポイントでは、またはブレークポイント式自体の場所で、いずれかのエラーについて説明します。 詳細については、次を参照してください。[ブレークポイントのバインド](../../extensibility/debugger/binding-breakpoints.md)します。  
  
   ブレークポイントのエラーは、エラーまたは警告のいずれかにできます。  
  
- によって表される、 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)インターフェイス。  
  
## <a name="see-also"></a>関連項目  
 [プログラム](../../extensibility/debugger/programs.md)   
 [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)   
 [コード コンテキスト](../../extensibility/debugger/code-context.md)   
 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)
