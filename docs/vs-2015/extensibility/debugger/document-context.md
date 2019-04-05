---
title: コンテキストのドキュメント |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 96d5e3e34a6827e7871b053501c61e9c4c98ae26
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972290"
---
# <a name="document-context"></a>ドキュメント コンテキスト
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 、デバッグ、**ドキュメント コンテキスト**:  
  
-   ソース ファイル内の位置を表します。 ソース ファイルが存在していない可能性がある言語では、ドキュメントのコンテキストは、通常、実行時環境で生成されるドキュメント内の位置を識別します。 たとえば、スクリプト エンジンでは、スクリプトからドキュメントを生成する可能性があります。 詳細については、次を参照してください。[ドキュメントの位置](../../extensibility/debugger/document-position.md)します。  
  
-   コードのコンテキストに対応するソース ドキュメント内の位置をについて説明します。 シンボルのハンドラーは、コードのコンテキストをコンパイラまたはインタープリターによって生成される情報を使用して、ドキュメントのコンテキストにマップします。  
  
-   によって実装される、 [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md)インターフェイス。  
  
## <a name="see-also"></a>関連項目  
 [コード コンテキスト](../../extensibility/debugger/code-context.md)   
 [シンボル プロバイダー](../../extensibility/debugger/symbol-provider.md)   
 [シンボルプロバイダーのインターフェイス](../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [デバッガー コンテキスト](../../extensibility/debugger/debugger-contexts.md)
