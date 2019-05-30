---
title: ポート サプライヤー |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- port suppliers
- debugging [Debugging SDK], port suppliers
ms.assetid: a8f3db96-1a13-4e93-9ef6-0861880369e0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5909587cbed118d618ea1605c8a169024028adf0
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351473"
---
# <a name="port-suppliers"></a>ポート サプライヤー
デバッガーのアーキテクチャで、*ポート サプライヤー*:

- サーバーに含まれていて、そのサーバーへの要求でポートを提供します。

- 追加し、ポートを含む、サーバーから削除できます。

- これがサーバーに提供されているすべてのポートを列挙できます。

- によって表される、 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)インターフェイスをレジストリを使用して Visual Studio に登録します。 このインターフェイスを呼び出すことによって取得できる[GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)します。

  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 既定のポート サプライヤーと既定のポートを提供します。 カスタム ポートを実装する場合は、実装して、これらのカスタム ポートを指定することも、カスタム ポート サプライヤー必要があります。

## <a name="see-also"></a>関連項目
- [サーバー](../../extensibility/debugger/servers-visual-studio-sdk.md)
- [ポート](../../extensibility/debugger/ports.md)
- [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)
- [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)
- [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)