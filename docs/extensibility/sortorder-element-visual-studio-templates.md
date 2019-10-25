---
title: 順序の要素 (Visual Studio テンプレート) |Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SortOrder
helpviewer_keywords:
- SortOrder element [Visual Studio Templates]
- <SortOrder> element [Visual Studio Templates]
ms.assetid: 151932c1-f08a-4f78-a8d0-bd2f32211a9c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2875bcb4583c1d2ec47a935d1a8bb4f0de109a92
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72719925"
---
# <a name="sortorder-element-visual-studio-templates"></a>SortOrder 要素 (Visual Studio テンプレート)
**[新しいプロジェクト]** ダイアログボックスまたは **[新しい項目の追加]** ダイアログボックスに表示されるテンプレートを、同じカテゴリの他のテンプレートの中に配置するために使用される値を指定します。

 \<VSTemplate > \<TemplateData > \<SortOrder >

## <a name="syntax"></a>構文

```
<SortOrder> ... </SortOrder>
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|必須の要素です。<br /><br /> テンプレートをカテゴリに分類し、 **[新しいプロジェクト]** ダイアログ ボックス、または **[新しい項目の追加]** ダイアログ ボックスでどのように表示させるかを定義します。|

## <a name="text-value"></a>テキスト値
 テキスト値が必要です。

 並べ替え順序の値を表す `integer`。

## <a name="remarks"></a>Remarks
 `SortOrder` は、省略可能な要素です。 既定値は100で、すべての値は10の倍数である必要があります。

 @No__t_0 要素は、ユーザーが作成したテンプレートでは無視されます。 ユーザーが作成したすべてのテンプレートはアルファベット順に並べ替えられます。

 並べ替え順序の値が低いテンプレートは、 **[新しいプロジェクト]** ダイアログボックスまたは **[新しい項目の追加]** ダイアログボックスで、並べ替え順の値が大きいテンプレートよりも前に表示されます。

## <a name="example"></a>例
 次の例は、標準 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] クラステンプレートのメタデータを示しています。

```
<VSTemplate Type="Item" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyClass</Name>
        <Description>My custom C# class template.</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <SortOrder>290</SortOrder>
        <DefaultName>MyClass</DefaultName>
    </TemplateData>
    <TemplateContent>
        <ProjectItem>MyClass.cs</ProjectItem>
    </TemplateContent>
</VSTemplate>
```

 この例では、`SortOrder` 要素は比較的高いです。 他の [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 項目テンプレートは `290` よりも低い `SortOrder` 値を持つ可能性があり、 **[新しい項目]** ダイアログボックスではこのテンプレートの前に表示されます。

## <a name="see-also"></a>関連項目
- [Visual Studio テンプレート スキーマ参照](../extensibility/visual-studio-template-schema-reference.md)
- [プロジェクトと項目テンプレートの作成](../ide/creating-project-and-item-templates.md)