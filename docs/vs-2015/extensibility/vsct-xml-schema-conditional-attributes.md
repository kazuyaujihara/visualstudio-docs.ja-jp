---
title: VSCT XML スキーマの条件付き属性 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, conditional attributes
- conditional attributes (VSCT XML schema)
ms.assetid: 754d4f32-319b-44c9-915f-f7c60e53222e
caps.latest.revision: 6
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6294ee8027b61840149096561efc91b8a4a3c3ec
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62422162"
---
# <a name="vsct-xml-schema-conditional-attributes"></a>VSCT XML スキーマの条件付き属性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

条件付き属性は、すべてのリストとアイテムに適用可能性があります。 論理演算子およびシンボルの拡張の式は、true または false に評価されます。 True の場合、結果の出力で、関連付けられているリストまたは項目が含まれます。  
  
 その他のトークンの拡張や定数に対してトークンの展開をテストできます。 知り関数は、値が存在しない場合でも、特定の名前が定義されているかどうかをテストに使用されます。  
  
 Condition 属性がリストに適用されると、条件は、リスト内のすべての子要素に適用されます。 子要素自体に条件属性が含まれている場合、その条件が結合親式 AND 演算によって。  
  
 True の場合、値 1、'1' および 'true' に評価して 0、'0' および 'false' が false として評価されます。  
  
## <a name="operators"></a>演算子  
 次の演算子は、条件付きの式の評価に使用できます。  
  
|演算子|定義|  
|--------------|----------------|  
|(,)|グループ化|  
|!|論理 NOT|  
|\<, >, \<=, >=, ==, !=|関係と比較|  
|と、呼び出し|ブール型|  
|または|ブール型|  
  
## <a name="examples"></a>使用例  
  
```  
<Menu Condition="Defined(DEBUG)" …  
</Menu>  
  
<Menu Condition="%(SKU_MODE) = 'Demo'" …  
</Menu>  
  
<Menus Condition="Defined(DEBUG)">  
    <Menu …  
    </Menu>  
</Menus>  
  
<Menus Condition="Defined(DEMO_SKU)">  
    <Menus Condition="!Defined(DEBUG)">  
        <Menu …  
        </Menu>  
    </Menus>  
  
    <Menu …  
    </Menu>  
</Menus>  
  
<Menus Condition="(Defined(DEMO_SKU) or Defined(SAMPLE_SKU))   
and !Defined(DEBUG)">  
    <Menu …  
    </Menu>  
</Menus>  
```  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio Command Table (.Vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
