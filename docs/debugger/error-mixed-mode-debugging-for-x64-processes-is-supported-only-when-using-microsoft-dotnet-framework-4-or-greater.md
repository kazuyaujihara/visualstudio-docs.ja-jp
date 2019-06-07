---
title: エラー :混合モードの x64 プロセスがサポートされるは、Microsoft .NET Framework 4 を使用している場合にのみデバッグ以上 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 9ef0daf5fd28bd829edcdce412839b03ed8347bf
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2019
ms.locfileid: "66745432"
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>エラー :x64 プロセスの混合モード デバッグは、Microsoft .NET Framework 4 以上を使用している場合にのみサポートされます
64 ビット プロセスで、混合ネイティブおよびマネージ コードをデバッグするには、.NET Framework version 4 が必要です。 .NET Framework 4 より前のバージョンと 64 ビット プロセスの混合モードのデバッグはサポートされていません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- 次のいずれかの操作を実行します。

  - バージョン 4、.NET Framework にアップグレードします。

  - デバッグのため、32 ビット バージョンのアプリケーションをビルドします。

## <a name="see-also"></a>関連項目
- [Remote Debugging](../debugger/remote-debugging.md)