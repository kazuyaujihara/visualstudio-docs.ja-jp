---
title: 要素の定義 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- VSCT XML schema elements, Define
- Define element (VSCT XML schema)
ms.assetid: 5aee74e3-de41-4dc6-9618-93e158af56dd
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8cc543a07176f307641c53a2ef3e132881821ce7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68162157"
---
# <a name="define-element"></a>Define 要素
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

シンボルの名前と値のペアを定義します。 このシンボルは、条件付き属性によって評価されることができます。 詳細については、次を参照してください。[条件付き属性](../extensibility/vsct-xml-schema-conditional-attributes.md)します。 参照してください、[要素をシンボル](../extensibility/symbols-element.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
<Define name="Mode" value="Standard" />  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|name|必須。 シンボルの名前。<br /><br /> 名前 =「モード」|  
|値|必須。 シンボルの値です。<br /><br /> 値 ="Standard"|  
|条件|任意。 詳細については、次を参照してください。[条件付き属性](../extensibility/vsct-xml-schema-conditional-attributes.md)します。|  
  
### <a name="child-elements"></a>子要素  
 なし。  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[CommandTable 要素](../extensibility/commandtable-element.md)|統合開発環境 (IDE) には、VSPackage を提供するコマンドを表すすべての要素を定義します。 たとえば、メニュー項目、メニューのツールバー、およびコンボ ボックス。|  
  
## <a name="example"></a>例  
  
```  
<Define name="DEMO_UI"/>  
<Define name="MODE" value="Standard"/>  
```  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio Command Table (.Vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
