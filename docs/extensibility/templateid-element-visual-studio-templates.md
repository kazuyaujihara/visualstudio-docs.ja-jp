---
title: TemplateID 要素 (Visual Studio テンプレート) |Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateID
helpviewer_keywords:
- <TemplateID> element [Visual Studio Templates]
- TemplateID element [Visual Studio Templates]
ms.assetid: 6ca24b4e-0325-4a9e-855e-0cbbe7361d8f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c0e404921d1ed74db2a1f23117242f49a07206c2
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72718740"
---
# <a name="templateid-element-visual-studio-templates"></a>TemplateID 要素 (Visual Studio テンプレート)
[Templategroupid](../extensibility/templategroupid-element-visual-studio-templates.md)要素によって項目テンプレートのグループに分類される項目テンプレートの識別子を指定します。

 \<VSTemplate > \<TemplateData > \<TemplateID >

## <a name="syntax"></a>構文

```
<TemplateID> ... </TemplateID>
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
 @No__t_1 要素によって項目テンプレートのグループに分類される項目テンプレートの識別子を表す `string`。

## <a name="remarks"></a>Remarks
 `TemplateID` は、省略可能な要素です。

 .Vstemplate ファイルで `TemplateID` 要素が省略されている場合、 [Name](../extensibility/name-element-visual-studio-templates.md)要素がテンプレートの識別子として使用されます。

 @No__t_0 要素の値は、プロジェクトシステムの登録 (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\Projects \\) と共に使用して、 **[新しい項目の追加]** ダイアログボックスに表示されるテンプレートをフィルター処理します。

## <a name="see-also"></a>関連項目
- [Visual Studio テンプレート スキーマ参照](../extensibility/visual-studio-template-schema-reference.md)
- [プロジェクトと項目テンプレートの作成](../ide/creating-project-and-item-templates.md)