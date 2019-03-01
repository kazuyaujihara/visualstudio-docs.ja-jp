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
ms.openlocfilehash: 748305683ad8f874c985e2599028152d608ccc84
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56597423"
---
# <a name="create-custom-views-of-objects-c-visual-basic-c"></a>オブジェクトのカスタム ビューの作成 (C#、Visual Basic、C++)
Visual Studio でデバッガーの変数ウィンドウにデータ型を表示する方法をカスタマイズできます。

## <a name="native-code"></a>ネイティブ コード

」の説明に従って、C++ コードの Natvis フレームワークを使用してカスタム データ型の展開を追加することができます[デバッガーでネイティブ オブジェクトのカスタム ビューの作成](/visualstudio/debugger/create-custom-views-of-native-objects)です。 C++/cli、CLI コードも属性を使用して、この記事では、ここで説明します。

## <a name="attributes"></a>属性

C#、Visual Basic、および C++ (C +/cli CLI コードのみ)、カスタム データを使用するための拡張を追加する<xref:System.Diagnostics.DebuggerTypeProxyAttribute>、 <xref:System.Diagnostics.DebuggerDisplayAttribute>、および<xref:System.Diagnostics.DebuggerBrowsableAttribute>します。

[!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] コードでは、Visual Basic は DebuggerBrowsable 属性をサポートしません。 この制限は、.NET Framework の新しいバージョンで解除されています。

## <a name="visualizers"></a>ビジュアライザー

マネージド データ型を表示するには、ビジュアライザーを記述します。 詳細については、次を参照してください。[方法: ビジュアライザーを記述する](/visualstudio/debugger/create-custom-visualizers-of-data)します。

## <a name="see-also"></a>関連項目

- [DebuggerTypeProxy 属性の使用](../debugger/using-debuggertypeproxy-attribute.md)
- [DebuggerDisplay 属性の使用](../debugger/using-the-debuggerdisplay-attribute.md)
- [ウォッチ ウィンドウと [クイック ウォッチ] ウィンドウ](../debugger/watch-and-quickwatch-windows.md)
- [デバッガー表示属性によるデバッグ機能の拡張](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)
