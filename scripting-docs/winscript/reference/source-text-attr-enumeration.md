---
title: SOURCE_TEXT_ATTR 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SOURCE_TEXT_ATTR constants
ms.assetid: 459384b0-1463-4841-a2b3-a993207163bf
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1dd0bbf08b6ddfdcfbffa494fdda9842004839b0
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573006"
---
# <a name="source_text_attr-enumeration"></a>SOURCE_TEXT_ATTR 列挙型
ソース テキストの単一文字の属性を記述します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum enum_SOURCE_TEXT_ATTR{    SOURCETEXT_ATTR_KEYWORD    = 0x0001,    SOURCETEXT_ATTR_COMMENT    = 0x0002,    SOURCETEXT_ATTR_NONSOURCE    = 0x0004,    SOURCETEXT_ATTR_OPERATOR   = 0x0008,    SOURCETEXT_ATTR_NUMBER    = 0x0010,    SOURCETEXT_ATTR_STRING    = 0x0020,    SOURCETEXT_ATTR_FUNCTION_START  = 0x0040};  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|[値]|説明|  
|------------|-----------|-----------------|  
|SOURCETEXT_ATTR_KEYWORD|0x0001|この文字は、VBScript キーワード `While` など、言語キーワードの一部です。|  
|SOURCETEXT_ATTR_COMMENT|0x0002|この文字は、コメントブロックの一部です。|  
|SOURCETEXT_ATTR_NONSOURCE|0x0004|文字は、コンパイルされた言語のソーステキストの一部ではありません。 たとえば、スクリプトブロックを囲む HTML です。|  
|SOURCETEXT_ATTR_OPERATOR|0x0008|文字は言語演算子の一部です。 たとえば、算術演算子 **+** です。|  
|SOURCETEXT_ATTR_NUMBER|0x0010|文字は、言語の数値定数の一部です。  たとえば、定数3.14159 です。|  
|SOURCETEXT_ATTR_STRING|0x0020|文字は、言語文字列定数の一部です。 たとえば、"Hello World" という文字列があるとします。|  
|SOURCETEXT_ATTR_FUNCTION_START|0x0040|文字は、関数ブロックの開始を示します。|  
  
## <a name="remarks"></a>Remarks  
 通常、`IDebugDocumentHost::GetScriptTextAttributes`、`IActiveScriptDebug::GetScriptletTextAttributes`、および `IActiveScriptDebug::GetScriptTextAttributes` の各メソッドは、次の場合を除き、文字ごとに1つのテキスト属性を返します。  
  
- GETATTRTYPE_DEPSCAN フラグが設定されています。この場合、メソッドは SOURCETEXT_ATTR_IDENTIFIER および SOURCETEXT_ATTR_MEMBERLOOKUP フラグを返すことができます。  
  
- GETATTRFLAG_THIS フラグが設定されています。この場合、メソッドは SOURCETEXT_ATTR_THIS フラグを返すことができます。  
  
- GETATTRFLAG_HUMANTEXT フラグが設定されています。この場合、メソッドは SOURCETEXT_ATTR_HUMANTEXT フラグを返す可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)