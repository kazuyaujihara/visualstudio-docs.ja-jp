---
title: オブジェクトのカスタム ビューの作成 |Microsoft Docs
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
ms.openlocfilehash: 911f0423184f22919be016691b9333b2f62d1b61
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2019
ms.locfileid: "66744798"
---
# <a name="create-custom-views-of-objects-c-visual-basic-c"></a>オブジェクトのカスタム ビューの作成 (C#、Visual Basic、 C++)
Visual Studio でデバッガーの変数ウィンドウにデータ型を表示する方法をカスタマイズできます。

## <a name="native-code"></a>ネイティブ コード

C++コード、」の説明に従って、Natvis フレームワークを使用してカスタム データ型の展開を追加できます[カスタム ビューの作成C++デバッガーでオブジェクト](/visualstudio/debugger/create-custom-views-of-native-objects)します。 C++/CLI コードも属性を使用して、この記事では、ここで説明します。

## <a name="attributes"></a>属性

C#、Visual Basic、およびC++(C++/CLI コードのみ)、カスタム データを使用するための拡張を追加する<xref:System.Diagnostics.DebuggerTypeProxyAttribute>、<xref:System.Diagnostics.DebuggerDisplayAttribute>と<xref:System.Diagnostics.DebuggerBrowsableAttribute>。

.NET Framework 2.0 のコードでは、Visual Basic は DebuggerBrowsable 属性機能をサポートしていません。 この制限は、.NET Framework の新しいバージョンで解除されています。

## <a name="visualizers"></a>ビジュアライザー

マネージド データ型を表示するには、ビジュアライザーを記述します。 詳細については、「[方法 :ビジュアライザーを記述する](/visualstudio/debugger/create-custom-visualizers-of-data)

## <a name="see-also"></a>関連項目

- [DebuggerDisplay 属性を使用して表示するものをデバッガーに通知します。](../debugger/using-the-debuggerdisplay-attribute.md)
- [DebuggerTypeProxy 属性の使用を表示するには、どのような型をデバッガーに通知します。](../debugger/using-debuggertypeproxy-attribute.md)
- [ウォッチ ウィンドウと [クイック ウォッチ] ウィンドウ](../debugger/watch-and-quickwatch-windows.md)
- [デバッガー表示属性によるデバッグ機能の拡張](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)