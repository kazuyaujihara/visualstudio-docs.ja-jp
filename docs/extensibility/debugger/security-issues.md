---
title: セキュリティの問題 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5f68db1a4c6fb3ea2a7f9542c1a9d2d313359554
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689214"
---
# <a name="security-issues"></a>セキュリティの問題
Visual Studio を使用してプログラムをデバッグするために必要なアクセス許可は、開発者がプログラムの実行に必要なものと同じです。 これは、ほとんどの場合、リモート デバッグが含まれます。 インターネット インフォメーション サービスなどの他のサービスに関連するいくつかの状況より高いレベルのアクセス許可を必要があります。

 Visual Studio の実行中に、プロセス デバッグ マネージャー (PDM) は、ローカル コンピューター上のデバッグ プロセスを追跡します。 リモートでというプログラム*msvsmon.exe*リモート デバッグを処理し、PDM を使用できるようにするために開発者が開始します。 (*msvsmon.exe*サービスではないと、そのコンピューターにリモート デバッグを有効にするのには手動で開始する必要があります)。ときに Visual Studio (または*msvsmon.exe*) が実行されていないプロセスが追跡されなかったデバッグします。

 開発者は、特別なアクセス許可なしで開始したプログラムをデバッグできます。 開発者は、その他の人が同じセキュリティ グループのメンバーである場合は、他のユーザーによって開始されたプロセスをデバッグもできます。 また、リモート デバッグを有効にするのには、リモート コンピューターに必要なファイルをコピーし、起動にのみ必要な*msvsmon.exe*します。 詳細については、[リモート デバッグ](../../debugger/remote-debugging.md)を参照してください。

## <a name="see-also"></a>関連項目
- [タスクのデバッグ](../../extensibility/debugger/debugging-tasks.md)
- [プロセス デバッグ マネージャー](../../extensibility/debugger/process-debug-manager.md)
- [リモート デバッグ](../../debugger/remote-debugging.md)
