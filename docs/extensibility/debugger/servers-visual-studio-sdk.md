---
title: サーバー (Visual Studio SDK) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- servers, debugging
- debugging [Debugging SDK], servers
ms.assetid: 62236d64-7956-448c-9ac3-5528f3edac1d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ebd991a5bb61211a33cc965668c48644bdcf9a27
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66348596"
---
# <a name="servers-visual-studio-sdk"></a>サーバー (Visual Studio SDK)
デバッガーのアーキテクチャで、 *server*:

- ポートおよびポート サプライヤーのコンテナーと、セッション デバッグ マネージャー (SDM) とデバッグ エンジンにポートとポート サプライヤーを通信します。

- 名前で識別し、そのポートとポート サプライヤーを列挙できます。

- によって表される、 [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md)インターフェイスで、Visual Studio (Visual Studio の実行の各インスタンスのサーバーの 1 つのインスタンス) によってのみ実装されます。

## <a name="see-also"></a>関連項目
- [ポート](../../extensibility/debugger/ports.md)
- [ポート サプライヤー](../../extensibility/debugger/port-suppliers.md)
- [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)
- [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md)