---
title: SupportsCodeSeparation 要素 (Visual Studio テンプレート) |Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SupportsCodeSeparation
helpviewer_keywords:
- SupportsCodeSeparation element [Visual Studio Templates]
- <SupportsCodeSeparation> element [Visual Studio Templates]
ms.assetid: 8112aac8-a269-40e5-b92b-9b9a6ff5a542
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9e68516a798bcd4d1437ab504c09b4cc529eb889
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72719425"
---
# <a name="supportscodeseparation-element-visual-studio-templates"></a>SupportsCodeSeparation 要素 (Visual Studio テンプレート)
**[新しい項目の追加]** ダイアログボックスで **[別のファイルにコードを配置]** する チェックボックスをオンにするかどうかを指定します。

 \<VSTemplate > \<TemplateData > \<SupportsCodeSeparation >

## <a name="syntax"></a>構文

```
<SupportsCodeSeparation> true/false </SupportsCodeSeparation>
```

## <a name="attributes-and-elements"></a>属性および要素
 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性
 なし。

### <a name="child-elements"></a>子要素
 なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|必須の要素です。<br /><br /> テンプレートを分類し、 **[新しいプロジェクト]** ダイアログボックスまたは **[新しい項目]** ダイアログボックスでの表示方法を定義します。|

## <a name="text-value"></a>テキスト値
 テキスト値が必要です。

 テキストは `true` または `false` のいずれかである必要があります。 **[新しい項目の追加]** ダイアログボックスで **[別のファイルにコードを配置]** する チェックボックスがオンになっているかどうかを示します。

## <a name="remarks"></a>Remarks
 `SupportsCodeSeparation` は、省略可能な要素です。 既定値は `false`です。

 @No__t_0 要素は、Web 項目テンプレートでのみ使用できます。

 コードの分離または分離コードページモデルを使用すると、マークアップを1つのファイルに保持し、プログラミングコードを別のファイルに保持できます。 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] およびその他の .NET 言語では、このモデルを使用します。

## <a name="example"></a>例
 次の例では、[**コードを別のファイルに配置**する] オプションを指定します。

```
<VSTemplate Version="3.0.0" Type="Project"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>
    <TemplateData>
        <Name>MyWebProjecStarterKit</Name>
        <Description>A simple Web template</Description>
        <Icon>icon.ico</Icon>
        <ProjectType>Web</ProjectType>
        <ProjectSubType>CSharp</ProjectSubType>
        <DefaultName>WebSite</DefaultName>
        <SupportsCodeSeparation>true</SupportsCodeSeparation>
    </TemplateData>
    <TemplateContent>
        <Project File="WebApplication.webproj">
            <ProjectItem>icon.ico</ProjectItem>
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>
            <ProjectItem>Default.aspx.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>関連項目
- [Visual Studio テンプレート スキーマ参照](../extensibility/visual-studio-template-schema-reference.md)
- [プロジェクトと項目テンプレートの作成](../ide/creating-project-and-item-templates.md)