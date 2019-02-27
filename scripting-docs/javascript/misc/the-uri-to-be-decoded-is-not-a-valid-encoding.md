---
title: デコードする URI はない有効なエンコード |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5025
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 029e0790-ffd1-496d-8700-3b3dbac1b6fd
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 792403a9a53f11431e87115d7a95345e316dc2ac
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56844296"
---
# <a name="the-uri-to-be-decoded-is-not-a-valid-encoding"></a>デコードする URI は正しくエンコードされていません。
不適切な形式の URI (Uniform Resource Identifier) をデコードしようとしました。 Uri がある特殊な構文です。URI で使用するには、ほとんどの英数字以外の文字をエンコードする必要があります。 使用することができます、`encodeURI`と`encodeURIComponent`メソッドから通常の URI を作成する[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]文字列。  
  
 完全な URI は、コンポーネントや区切り文字のシーケンスで構成されます。 一般的な形式です。  
  
```JavaScript  
<Scheme>:<first>/<second>;<third>?<fourth>  
```  
  
 山かっこ内の名前は、コンポーネントを表す、":"、「/」、「;」と"?"予約文字が区切り記号として使用します。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   有効な Uri のみをデコードしようとしていることを確認します。 通常をデコードすることはできません[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]文字列が無効な文字を含めることができます。  
  
## <a name="see-also"></a>関連項目  
 [decodeURI 関数](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeURIComponent 関数](../../javascript/reference/decodeuricomponent-function-javascript.md)