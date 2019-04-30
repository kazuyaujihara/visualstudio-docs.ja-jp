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
ms.openlocfilehash: 2fb4d0dfaeb944700757c9ceec222dbd62dab9dd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850683"
---
# <a name="error-mixed-mode-debugging-is-supported-only-when-using-microsoft-net-framework-20-or-greater"></a>エラー :混合モード デバッグは、Microsoft .NET Framework 2.0 以上を使用している場合にのみサポートされます
ネイティブ コードとマネージド コードの混合をデバックするには、[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Version 2.0、3.0、 3.5、または 4 が必要です。 以前のバージョンの [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] を使用した混合モード デバッグはサポートされていません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] を Version 2.0、3.0、3.5、または 4 にアップグレードします。

## <a name="see-also"></a>関連項目
- [Remote Debugging](../debugger/remote-debugging.md)