---
title: LocalizedDescription 要素 (VSIX 言語パックのスキーマ) |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
ms.assetid: 766a1732-bbaf-4875-b276-feb42169633a
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9e626e532c462199d38ddb3f1044bab25d389995
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972274"
---
# <a name="localizeddescription-element-vsix-language-pack-schema"></a>LocalizedDescription 要素 (VSIX 言語パックのスキーマ)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

必須。 拡張機能のローカライズされた説明を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
<LocalizedDescription>Localized description of the extension</LocalizedDescription>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|なし||  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|なし||  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[VSIX LanguagePack 要素](../extensibility/vsixlanguagepack-element-vsix-language-pack-schema.md)|必須。 VSIX 言語パックのルート要素を提供します。|  
  
## <a name="text-value"></a>テキスト値  
 必須。 ターゲット言語で拡張機能の説明テキスト。  
  
## <a name="element-information"></a>要素情報  
  
|                 |                                                           |
|-----------------|-----------------------------------------------------------|
|    名前空間    | http://schemas.microsoft.com/developer/vsx-schema-lp/2010 |
|   スキーマ名   |                 VSIX 言語パックのスキーマ                 |
| 検証ファイル |                VSIXLanguagePackSchema.xsd                 |
|  空にすることができます。   |                      利用不可                       |
  
## <a name="see-also"></a>関連項目  
 [VSX 言語パックのスキーマ リファレンス](../extensibility/vsx-language-pack-schema-reference.md)   
 [VSIX パッケージのローカライズ](../extensibility/localizing-vsix-packages.md)   
 [VSIX 拡張機能スキーマ 1.0 リファレンス](http://msdn.microsoft.com/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)
