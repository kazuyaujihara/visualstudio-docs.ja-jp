---
title: エディットコンティニュ (ビジュアルC#) |Microsoft Docs
ms.date: 10/11/2017
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Edit and Continue
- Edit and Continue [C#]
- debugging [C#], Edit and Continue
ms.assetid: 591bd1b7-ef10-4d10-817b-3f92ca4be006
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: a4d11875a7ab2ca3f21f364308580a732b7516e6
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72737928"
---
# <a name="edit-and-continue-visual-c"></a>エディット コンティニュ (Visual C#)
 C# のエディット コンティニュを使用すると、デバッグ中に中断モードでコードに変更を加えることができます。 デバッグ セッションを停止したり再開したりしなくても、変更を適用できます。 実行モードでは、ソース エディターは読み取り専用です。

 エディット コンティニュは、デバッグ セッションで行う必要があるほとんどの変更をサポートしますが、いくつか例外があります。 詳細については、「[サポートさC#れているコード変更 (および Visual Basic)](../debugger/supported-code-changes-csharp.md)」を参照してください。

 エディットコンティニュは、Windows 10 の UWP、および .NET Framework 4.6 デスクトップ以降のバージョンを対象とする x86 および x64 アプリでサポートされています (.NET Framework はデスクトップバージョンのみ)。

 > [!NOTE]
 > サポートされていないアプリとプラットフォームには、ASP.NET 5、Silverlight 5、Windows 8.1 があります。

 エディット コンティニュが有効なときは、 **[続行]** 、 **[ステップ]** 、 **[次のステートメントの設定]** などのデバッガー実行コマンドを使用したり、デバッガー ウィンドウで関数の評価を実行したりすると、サポートされている変更が自動的に適用されます。

 詳細については、「[方法: エディットコンティニュを使用C#する ()](../debugger/how-to-use-edit-and-continue-csharp.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [方法 : エディット コンティニュを使用する (C#)](../debugger/how-to-use-edit-and-continue-csharp.md)
- [サポートされてC#いるコード変更 (および Visual Basic)](../debugger/supported-code-changes-csharp.md)
- [XAML を使用した実行中の XAML コードの作成とデバッグ Visual Studio でのホットリロード](../debugger/xaml-hot-reload.md)
