---
title: コンテキストのドキュメント |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d15e53d29adc04a82274ebd456027d15b0e41703
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345708"
---
# <a name="document-context"></a>ドキュメントのコンテキスト
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 、デバッグ、*ドキュメント コンテキスト*:

- ソース ファイル内の位置を表します。 ソース ファイルが存在していない可能性がある言語では、ドキュメントのコンテキストは、通常、実行時環境で生成されるドキュメント内の位置を識別します。 たとえば、スクリプト エンジンでは、スクリプトからドキュメントを生成する可能性があります。 詳細については、次を参照してください。[位置を文書化](../../extensibility/debugger/document-position.md)します。

- コードのコンテキストに対応するソース ドキュメント内の位置をについて説明します。 シンボルのハンドラーは、コードのコンテキストをコンパイラまたはインタープリターによって生成される情報を使用して、ドキュメントのコンテキストにマップします。

- によって実装される、 [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md)インターフェイス。

## <a name="see-also"></a>関連項目
- [コード コンテキスト](../../extensibility/debugger/code-context.md)
- [シンボル プロバイダー](../../extensibility/debugger/symbol-provider.md)
- [シンボルプロバイダーのインターフェイス](../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [デバッガー コンテキスト](../../extensibility/debugger/debugger-contexts.md)