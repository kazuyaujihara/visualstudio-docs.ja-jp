---
title: エディット コンティニュ (Visual c#) |Microsoft Docs
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
ms.openlocfilehash: 972ad0d772eee9b876f43bc3e2fcd032d4b7e0ab
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62851008"
---
# <a name="edit-and-continue-visual-c"></a>エディット コンティニュ (Visual C#)
 C# のエディット コンティニュを使用すると、デバッグ中に中断モードでコードに変更を加えることができます。 デバッグ セッションを停止したり再開したりしなくても、変更を適用できます。 実行モードでは、ソース エディターは読み取り専用です。

 エディット コンティニュは、デバッグ セッションで行う必要があるほとんどの変更をサポートしますが、いくつか例外があります。 詳細については、次を参照してください。 [(c# および Visual Basic) のサポートされているコード変更](../debugger/supported-code-changes-csharp.md)します。

 Windows 10、および .NET Framework 4.6 を対象とするアプリが x86 および x64 での UWP でエディット コンティニュはサポートされてデスクトップまたはそれ以降のバージョン (.NET Framework は、デスクトップ バージョンのみ)。

 > [!NOTE]
 > サポートされていないアプリとプラットフォームには、ASP.NET 5、Silverlight 5、および Windows 8.1 が含まれます。

 エディット コンティニュが有効なときは、**[続行]**、**[ステップ]**、**[次のステートメントの設定]** などのデバッガー実行コマンドを使用したり、デバッガー ウィンドウで関数の評価を実行したりすると、サポートされている変更が自動的に適用されます。

 詳細については、「[方法 :エディット コンティニュを使用する (C#)](../debugger/how-to-use-edit-and-continue-csharp.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [方法: エディット コンティニュを使用する (C#)](../debugger/how-to-use-edit-and-continue-csharp.md)
- [サポートされているコード変更 (C# および Visual Basic)](../debugger/supported-code-changes-csharp.md)