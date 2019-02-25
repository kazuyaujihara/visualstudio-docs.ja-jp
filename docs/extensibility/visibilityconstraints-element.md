---
title: VisibilityConstraints 要素 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VisibilityConstraints
helpviewer_keywords:
- VSCT XML schema elements, VisibilityConstraints
- VisibilityConstraints element (VSCT XML schema)
ms.assetid: d6dcd314-6fe4-4693-a189-91fa026c7b34
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6c567291f2b91e092afecb264c2b2e0ca1bfd108
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56702578"
---
# <a name="visibilityconstraints-element"></a>VisibilityConstraints 要素
VisibilityConstraints 要素は、コマンドとツールバーのグループの静的な可視性を判断します。 可視性がによって制御される最初の[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]VSPackage を読み込むことがなく、統合開発環境 (IDE) です。

## <a name="syntax"></a>構文

```xml
<VisibilityConstraints>
  <VisibilityConstraint>... </VisibilityConstraint>
  <VisibilityConstraint>... </VisibilityConstraint>
</VisibilityConstraint>
```

## <a name="attributes-and-elements"></a>属性と要素
 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

|属性|説明|
|---------------|-----------------|
|条件|任意。 参照してください[条件付き属性](../extensibility/vsct-xml-schema-conditional-attributes.md)します。|

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[VisibilityItem 要素](../extensibility/visibilityitem-element.md)|コマンドとツールバーの静的な可視性を判断します。|
|[VisibilityConstraints](../extensibility/visibilityconstraints-element.md)|コマンドとツールバーのグループの静的な可視性を判断します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[CommandTable 要素](../extensibility/commandtable-element.md)|IDE に VSPackage を提供するコマンド (たとえば、メニュー項目、メニューのツールバー、およびコンボ ボックスなど) を表すすべての要素を定義します。|

## <a name="example"></a>例

```xml
<VisibilityConstraints>
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"
    context="guidNotViewSourceMode"/>
</VisibilityConstraints>
```

## <a name="see-also"></a>関連項目
- [VisibilityItem 要素](../extensibility/visibilityitem-element.md)
- [Visual Studio コマンド テーブル (します。Vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)