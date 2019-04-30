---
title: エラー :IA64 プロセスの混合モードのデバッグはサポートされていません |Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.interop_unsupported_ia64
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5c4414651249aa7622e7f7be59e6150a4925f1b8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850867"
---
# <a name="error-mixed-mode-debugging-for-ia64-processes-is-unsupported"></a>エラー :IA64 プロセスの混合モードのデバッグはサポートされていません。
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] デバッガーは、Itanium ベースのプロセスでのネイティブ コードとマネージド コードの混合のデバッグをサポートしません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- デバッグのため、32 ビット バージョンのアプリケーションをビルドします。

## <a name="see-also"></a>関連項目
- [Remote Debugging](../debugger/remote-debugging.md)