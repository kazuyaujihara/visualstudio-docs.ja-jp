---
title: T4 インポート ディレクティブ
ms.date: 11/04/2016
ms.topic: reference
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 74181ea3bb086688893749850adb697c75b6eac1
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72606441"
---
# <a name="t4-import-directive"></a>T4 インポート ディレクティブ

Visual Studio T4 テキストテンプレートのコードブロックでは、`import` ディレクティブを使用して、完全修飾名を指定せずに別の名前空間の要素を参照できます。 このディレクティブは、C# の `using` または `imports` の [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)] に相当します。

T4 テキストテンプレートの作成の概要については、「 [T4 テキストテンプレートの作成](../modeling/writing-a-t4-text-template.md)」を参照してください。

## <a name="using-the-import-directive"></a>import ディレクティブの使用

```
<#@ import namespace="namespace" #>
```

 この例では、テンプレート コードで System.IO のメンバーの明示的な名前空間を省略できます。

```
<#@ import namespace="System.IO" #>
<#
   string fileContent = File.ReadAllText("C:\x.txt"); // System.IO.File
#>
The file contains: <#=  fileContent #>
```

## <a name="standard-imports"></a>標準インポート
 次の名前空間は自動的にインポートされるので、この名前空間のインポート ディレクティブを記述する必要はありません。

- `System`

  また、カスタム ディレクティブを使用する場合は、ディレクティブ プロセッサによって一部の名前空間が自動的にインポートされます。

  たとえば、ドメイン固有言語 (DSL) のテンプレートを作成する場合、次の名前空間のインポート ディレクティブを記述する必要はありません。

- `Microsoft.VisualStudio.Modeling`

- DSL の名前空間

## <a name="see-also"></a>参照

- [T4 アセンブリ ディレクティブ](../modeling/t4-assembly-directive.md)