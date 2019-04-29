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
ms.openlocfilehash: 1423cbcfcae53948f7b9c9cd52eb90f57251bc24
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62851057"
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>エラー :x64 プロセスの混合モード デバッグは、Microsoft .NET Framework 4 以上を使用している場合にのみサポートされます
ネイティブ コードとマネージド コードの混合を 64 プロセスでデバックするには、[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Version 4 が必要です。 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Version 4 より前のバージョンを使用した 64 ビット プロセスの混合モード デバッグはサポートされません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- 次のいずれかの操作を実行します。

  - [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] を Version 4 にアップグレードします。

  - デバッグのため、32 ビット バージョンのアプリケーションをビルドします。

## <a name="see-also"></a>関連項目
- [Remote Debugging](../debugger/remote-debugging.md)