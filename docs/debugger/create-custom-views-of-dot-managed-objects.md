---
title: オブジェクトのカスタムビューを作成する |Microsoft Docs
ms.date: 01/08/2019
ms.topic: conceptual
f1_keywords:
- vs.debug.data.elements
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- data types, custom
- custom data types
- managed code, custom data types
- autoexp.dat file
- mcee_cs.dat file
- debugger, expanding data types
- mcee_mc.dat file
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 36e875bc8101bc8a1b0eb1bec6671c76e3b0c9b2
ms.sourcegitcommit: 8a3545329a58e446672181cfed2083f850e1ad14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71814299"
---
# <a name="create-custom-views-of-objects-c-visual-basic-f-ccli"></a>オブジェクトのカスタムビューの作成C#(、Visual Basic F#、 C++、/cli)
Visual Studio でデバッガーの変数ウィンドウにデータ型を表示する方法をカスタマイズできます。

## <a name="attributes"></a>属性

、 C#、Visual Basic F# C++ (C++/cli コードのみ) では、<xref:System.Diagnostics.DebuggerTypeProxyAttribute>、<xref:System.Diagnostics.DebuggerDisplayAttribute>、および @no__t を使用して、カスタムデータの展開を追加できます。

.NET Framework 2.0 コードでは、Visual Basic はデバッガ参照可能属性をサポートしていません。 この制限は、.NET Framework の新しいバージョンで解除されています。

## <a name="visualizers"></a>ビジュアライザー

マネージド データ型を表示するには、ビジュアライザーを記述します。 詳細については、「[方法 :ビジュアライザーを記述する](/visualstudio/debugger/create-custom-visualizers-of-data)

> [!NOTE]
> コードC++の場合、「[デバッガーでのオブジェクトのカスタムビューの作成C++ ](/visualstudio/debugger/create-custom-views-of-native-objects)」で説明されているように、Natvis フレームワークを使用してカスタムデータ型の展開を追加できます。

## <a name="see-also"></a>関連項目

- [デバッガ Display 属性を使用して、表示する内容をデバッガーに通知します](../debugger/using-the-debuggerdisplay-attribute.md)
- [Debugger Typeproxy 属性を使用して表示する型をデバッガーに通知する](../debugger/using-debuggertypeproxy-attribute.md)
- [ウォッチ ウィンドウと [クイック ウォッチ] ウィンドウ](../debugger/watch-and-quickwatch-windows.md)
- [デバッガー表示属性によるデバッグ機能の拡張](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)
