---
title: ブレークポイントがヒット ダイアログ ボックスの場合 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.whenbreakpointishit
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
ms.assetid: 476e3d98-cf35-4338-b124-cd0f3010d854
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d4cc3c2366ca20328f591b0661e8c2b3e5af1e45
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717703"
---
# <a name="when-breakpoint-is-hit-dialog-box"></a>[ブレークポイントのヒット時] ダイアログ ボックス
このダイアログ ボックスでは、ブレークポイントにヒットしたときに発生するアクションをカスタマイズできます。

## <a name="uielement-list"></a>UIElement の一覧
 **メッセージを印刷**DebuggerDisplay 構文を使用して、メッセージを出力します。 詳細については、次を参照してください。 [DebuggerDisplay 属性を使用して](../debugger/using-the-debuggerdisplay-attribute.md)します。

 このテキストボックスは、$ADDRESS などの特殊なキーワードもサポートしています。これらのキーワードはキーワード自身が使用することも、DebuggerDisplay 式の中かっこ ({}) 内で使用することもできます。 使用できるキーワードはダイアログ ボックスに一覧表示されます。

 **実行を継続**このコントロールが有効になっている場合にのみ**メッセージを印刷**が選択されています。 このコントロールを選択すると、ブレークポイントにヒットしたときに、これを中断するポイントとしてではなく、プログラムの実行をトレースするためのトレースポイントとして使用できます。

## <a name="see-also"></a>参照
- [ブレークポイントの使用](../debugger/using-breakpoints.md)
- [DebuggerDisplay 属性の使用](../debugger/using-the-debuggerdisplay-attribute.md)