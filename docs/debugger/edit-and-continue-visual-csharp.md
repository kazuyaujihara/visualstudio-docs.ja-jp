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
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685366"
---
# <a name="edit-and-continue-visual-c"></a>エディット コンティニュ (Visual C#)
 C# のエディット コンティニュを使用すると、デバッグ中に中断モードでコードに変更を加えることができます。 デバッグ セッションを停止したり再開したりしなくても、変更を適用できます。 実行モードでは、ソース エディターは読み取り専用です。

 エディット コンティニュは、デバッグ セッションで行う必要があるほとんどの変更をサポートしますが、いくつか例外があります。 詳細については、次を参照してください。 [(c# および Visual Basic) のサポートされているコード変更](../debugger/supported-code-changes-csharp.md)します。

 Windows 10、および .NET Framework 4.6 を対象とするアプリが x86 および x64 での UWP でエディット コンティニュはサポートされてデスクトップまたはそれ以降のバージョン (.NET Framework は、デスクトップ バージョンのみ)。

 > [!NOTE]
 > サポートされていないアプリとプラットフォームには、ASP.NET 5、Silverlight 5、および Windows 8.1 が含まれます。

 エディット コンティニュが有効なときは、**[続行]**、**[ステップ]**、**[次のステートメントの設定]** などのデバッガー実行コマンドを使用したり、デバッガー ウィンドウで関数の評価を実行したりすると、サポートされている変更が自動的に適用されます。

 詳細については、次を参照してください。[方法: 使用の編集と続行 (c#)](../debugger/how-to-use-edit-and-continue-csharp.md)します。

## <a name="see-also"></a>関連項目
- [方法 : エディット コンティニュを使用する (C#)](../debugger/how-to-use-edit-and-continue-csharp.md)
- [サポートされているコード変更 (c# および Visual Basic)](../debugger/supported-code-changes-csharp.md)