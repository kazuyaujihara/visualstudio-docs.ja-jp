---
title: CommandPlacements 要素 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- CommandPlacements
helpviewer_keywords:
- CommandPlacements element (VSCT XML schema)
- VSCT XML schema elements, CommandPlacements
ms.assetid: 78a5724a-3b9f-4c78-9c0d-8faa3924f81c
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: dbe65cc38bd14d859507d795ce32657f53ca8b44
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58978323"
---
# <a name="commandplacements-element"></a>CommandPlacements 要素
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

CommandPlacements 要素には、CommandPlacement 要素とその他の CommandPlacements グループがグループ化します。  
  
 CommandPlacements 要素は省略可能です。 コマンド、グループ、またはメニューする必要がありますが含まれていない場合、2 次拠点で、.vsct ファイルにこのセクションを含めることはありません。  
  
## <a name="syntax"></a>構文  
  
```  
<CommandPlacements>  
  <CommandPlacement>... </CommandPlacement>  
  <CommandPlacement>... </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|条件|任意。 参照してください[条件付き属性](../extensibility/vsct-xml-schema-conditional-attributes.md)します。|  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|CommandPlacements|CommandPlacement 要素をグループ化し、他の CommandPlacements グループ化します。|  
|[CommandPlacement 要素](../extensibility/commandplacement-element.md)|1 つ以上のグループまたはメニューに含まれるには、ボタン、グループ、およびメニューを使用できます。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[CommandTable 要素](../extensibility/commandtable-element.md)|コマンドを表すすべての要素を定義します。|  
  
## <a name="example"></a>例  
  
```  
<CommandPlacements>  
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"  
    priority="0x0300">  
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>  
  </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="see-also"></a>関連項目  
 [CommandPlacement 要素](../extensibility/commandplacement-element.md)   
 [Visual Studio Command Table (.Vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
