---
title: エンコードする URI に無効な文字が含まれています |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5024
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a3f0fdbb-8d4b-41ae-a396-43dfc9483760
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f2f9111acf656bf882a3d506fe95b8361f3693ff
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63006209"
---
# <a name="the-uri-to-be-encoded-contains-an-invalid-character"></a>エンコードする URI は無効な文字を含んでいます。
URI (Uniform Resource Identifier) として文字列をエンコードしようとしましたが、無効な文字が含まれています。 ほとんどの文字は Uri に変換する文字列内で有効ですが、一部の Unicode 文字のシーケンスはできません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- エンコードする文字列には、有効な Unicode シーケンスだけが含まれていることを確認します。 完全な URI は、コンポーネントや区切り文字のシーケンスで構成されます。 山かっこ内の名前は、コンポーネントを表す、":"、「/」、「;」と"?"予約文字が区切り記号として使用します。 一般的な形式です。  
  
    ```JavaScript  
    <Scheme>:<first>/<second>;<third>?<fourth>  
    ```  
  
## <a name="see-also"></a>関連項目  
 [encodeURI 関数](../../javascript/reference/encodeuri-function-javascript.md)   
 [encodeURIComponent 関数](../../javascript/reference/encodeuricomponent-function-javascript.md)