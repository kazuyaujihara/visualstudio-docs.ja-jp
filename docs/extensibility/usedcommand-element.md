---
title: Used Command 要素 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 44ea8f27cafb166968f66c53dc68398526e0aa5d
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72718773"
---
# <a name="usedcommand-element"></a>UsedCommand 要素
VSPackage が別の vsct ファイルで定義されているコマンドにアクセスできるようにします。 たとえば、VSPackage が [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] シェルによって定義されている標準の**コピー**コマンドを使用している場合は、コマンドを再実装せずにメニューまたはツールバーに追加できます。

## <a name="syntax"></a>構文

```
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />
```

## <a name="attributes-and-elements"></a>属性および要素
 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

|属性|説明|
|---------------|-----------------|
|guid|必須です。 コマンドを識別する GUID ID ペアの GUID。|
|ID|必須です。 コマンドを識別する GUID ID ペアの ID。|
|条件|省略可能です。 「[条件付き属性](../extensibility/vsct-xml-schema-conditional-attributes.md)」を参照してください。|

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|None||

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[UsedCommands 要素](../extensibility/usedcommands-element.md)|グループ化されたコマンド要素とその他の実行コマンドグループ。|

## <a name="remarks"></a>Remarks
 @No__t_0 要素にコマンドを追加することにより、VSPackage は、VSPackage がコマンドを必要とすることを [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 環境に通知します。 パッケージが必要とするすべてのバージョンおよび構成に含まれていない可能性があるすべてのコマンドに対して、`<UsedCommand>` 要素を追加する必要があります。 たとえば、パッケージがビジュアルC++に固有のコマンドを呼び出すと、コマンドに `<UsedCommand>` 要素を含めない限り、Visual Web Developer のユーザーはこのコマンドを使用できません。

## <a name="example"></a>例

```
<UsedCommands>
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>
</UsedCommands>
```

## <a name="see-also"></a>関連項目
- [UsedCommands 要素](../extensibility/usedcommands-element.md)
- [Visual Studio Command Table (.Vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)