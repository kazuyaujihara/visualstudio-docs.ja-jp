---
title: '&lt;Signature&gt; 要素 (ClickOnce 配置) |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <Signature> element [ClickOnce deployment manifest]
ms.assetid: c99b07ad-e8ba-43f2-b0d6-3745e7a7c8b3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f69dcec6bbee5358184b74a71274cb26e4de60b3
ms.sourcegitcommit: 8589d85cc10710ef87e6363a2effa5ee5610d46a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2019
ms.locfileid: "72806849"
---
# <a name="ltsignaturegt-element-clickonce-deployment"></a>&lt;Signature&gt; 要素 (ClickOnce 配置)
この配置マニフェストにデジタル署名するために必要な情報が含まれます。

## <a name="syntax"></a>構文

```xml

      <Signature> 
   XML signature information 
</Signature>
```

## <a name="remarks"></a>Remarks
 エンベロープ署名を使用した配置マニフェストへの署名はオプションですが、推奨されます。 XML ファイルに署名する方法の詳細については、「 [http://www.w3.org/TR/xmldsig-core/](https://www.w3.org/TR/xmldsig-core/)」で説明されている World Wide Web コンソーシアムの推奨事項「xml 署名の構文と処理」を参照してください。

 マニフェストに署名する場合は、すべてのファイルに対してハッシュを指定する必要があります。 ハッシュされていないファイルを含むマニフェストに署名することはできません。これは、ハッシュされていないファイルの内容をユーザーが確認できないためです。

## <a name="example"></a>例
 次のコード例は、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] の配置で使用される配置マニフェストの `Signature` 要素を示しています。

```xml
<Signature xmlns="http://www.w3.org/2000/09/xmldsig#">
  <SignedInfo>
    <CanonicalizationMethod Algorithm=
           "http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />
    <SignatureMethod Algorithm=
           "http://www.w3.org/2000/09/xmldsig#rsa-sha1" />
    <Reference URI="">
      <Transforms>
        <Transform Algorithm=
           "http://www.w3.org/2000/09/xmldsig#enveloped-signature" />
      </Transforms>
      <DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />
      <DigestValue>d2z5AE...</DigestValue>
    </Reference>
  </SignedInfo>
  <SignatureValue>
4PHj6SaopoLp...
  </SignatureValue>
  <KeyInfo>
    <X509Data>
      <X509Certificate>
MIIHnTCCBoWgAwIBAgIKJY9+nwAHAAB...
      </X509Certificate>
    </X509Data>
  </KeyInfo>
</Signature>
```

## <a name="see-also"></a>関連項目
- [ClickOnce 配置マニフェスト](../deployment/clickonce-deployment-manifest.md)