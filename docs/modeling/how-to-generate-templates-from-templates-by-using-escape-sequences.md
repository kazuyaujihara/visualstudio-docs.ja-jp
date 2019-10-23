---
title: テンプレートからテンプレートを生成するためにエスケープシーケンスを使用する
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, generating templates from templates
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1a9afe2670bb086627407a9f1bc674edfc2fe354
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72605466"
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>方法: エスケープ シーケンスを使用してテンプレートからテンプレートを生成する
生成されたテキストの出力として別のテキストテンプレートを作成するテキストテンプレートを作成できます。 そのためには、エスケープシーケンスを使用してテキストテンプレートタグを記述する必要があります。 エスケープシーケンスを使用しない場合、生成されたテキストテンプレートには定義済みの意味があります。 テキストテンプレートでのエスケープシーケンスの使用の詳細については、「[テキストテンプレートでのエスケープシーケンスの使用](../modeling/using-escape-sequences-in-text-templates.md)」を参照してください。

### <a name="to-generate-a-text-template-from-within-a-text-template"></a>テキストテンプレート内からテキストテンプレートを生成するには

- エスケープ文字として円記号 (\\) を使用して、テキストテンプレート内でディレクティブ、ステートメント、式、およびクラス機能のために必要なマークアップタグを別のテキストテンプレートファイルに生成します。

    ```
    \<#@ directive \#>
    \<# statement \#>
    \<#= expression \#>
    \<#+ classfeature \#>
    ```

## <a name="example"></a>例
 次の例では、エスケープ文字を使用してテキストテンプレートからテキストテンプレートを生成します。 @No__t_0 ディレクティブは、コピー先のファイルの種類をテキストテンプレートファイルの種類 (.tt) に設定します。

```csharp
\<#@ output extension=".tt" \#>
\<#@ assembly name="System.Xml.dll" \#>
\<#@ import namespace="System.Xml" \#>
\<#
XmlDocument xDoc = new XmlDocument();
//System.Diagnostics.Debugger.Break();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes != null)
    {
       foreach (XmlAttribute attr in attributes)
       {\#>
           \<#= attr.Name \#>
       \<#}
     }
\#>
```

 生成されたテキスト出力はテキストテンプレートです。

```
<#@ output extension=".tt" #>
<#@ assembly name="System.Xml.dll" #>
<#@ import namespace="System.Xml" #>
<#
XmlDocument xDoc = new XmlDocument();
//System.Diagnostics.Debugger.Break();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes != null)
    {
       foreach (XmlAttribute attr in attributes)
       {#>
           <#= attr.Name #>
       <#}
     }
#>
```