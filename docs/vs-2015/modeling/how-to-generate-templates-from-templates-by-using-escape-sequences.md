---
title: '方法: エスケープ シーケンスを使用してテンプレートからテンプレートを生成します |。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, generating templates from templates
ms.assetid: 4126156a-7cea-48b8-925e-7790806cfe6c
caps.latest.revision: 37
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4a3ddd7896732c5b87c5b6bd2032c27fffd96a41
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546623"
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>方法: エスケープ シーケンスを使用してテンプレートからテンプレートを生成する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

別のテキスト テンプレートを作成するテキスト出力として生成されたテキスト テンプレートを作成することができます。 これを行うには、テキスト テンプレートのタグを区切るためにエスケープ シーケンスを使用する必要があります。 エスケープ シーケンスを使用しない場合、生成されたテキスト テンプレートが定義済みの意味になります。 テキスト テンプレートでのエスケープ シーケンスの使用の詳細については、次を参照してください。[テキスト テンプレートでのエスケープ シーケンスの使用](../modeling/using-escape-sequences-in-text-templates.md)  
  
### <a name="to-generate-a-text-template-from-within-a-text-template"></a>テキスト テンプレート内でテキスト テンプレートを生成するには  
  
- 別のテキスト テンプレート ファイル内で、ディレクティブ、ステートメント、式、クラス機能といった必要なマークアップ タグをテキスト テンプレート内で作成するためにエスケープ文字として、バックスラッシュ (\\) を使用します。  
  
    ```  
    \<#@ directive \#>  
    \<# statement \#>  
    \<#= expression \#>  
    \<#+ classfeature \#>  
    ```  
  
## <a name="example"></a>例  
 次の例では、エスケープ文字を使用して、テキスト テンプレートからテキスト テンプレートを生成します。 `output` ディレクティブは、変換先ファイルのテキスト テンプレート ファイルの種類 (.tt) を設定します。  
  
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
  
 生成されたテキスト出力は、テキスト テンプレートです。  
  
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
