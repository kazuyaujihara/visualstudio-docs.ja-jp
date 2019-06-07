---
title: エラー :混合モード デバッグは Microsoft .NET Framework 2.0 を使用する場合にのみ以上サポート |Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.interop_unsupported_to_old
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
ms.openlocfilehash: 0fd30fb1b181224b61b96670553ef5aa6ff0f721
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2019
ms.locfileid: "66745278"
---
# <a name="error-mixed-mode-debugging-is-supported-only-when-using-microsoft-net-framework-20-or-greater"></a>エラー :混合モード デバッグは、Microsoft .NET Framework 2.0 以上を使用している場合にのみサポートされます
ネイティブおよびマネージの混合コードをデバッグするには、.NET Framework version 2.0、3.0 が必要です。 3.5、または 4 が必要です。 混合モードの .NET Framework の旧バージョンとデバッグがサポートされていません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- .NET Framework をバージョン 2.0、3.0、3.5、または 4.0 にアップグレードします。

## <a name="see-also"></a>関連項目
- [Remote Debugging](../debugger/remote-debugging.md)