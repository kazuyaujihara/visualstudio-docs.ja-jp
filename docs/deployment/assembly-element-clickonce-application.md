---
title: '&lt;アセンブリ&gt;要素 (ClickOnce アプリケーション) |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assembly> element [ClickOnce application manifest]
ms.assetid: 51410569-10f9-4c0a-96b5-d39185edbefc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6b629243920021adc3833f43f268f05638029dc7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62900761"
---
# <a name="ltassemblygt-element-clickonce-application"></a>&lt;アセンブリ&gt;要素 (ClickOnce アプリケーション)
アプリケーション マニフェストの最上位要素。

## <a name="syntax"></a>構文

```xml

      <assembly
   manifestVersion
/>
```

## <a name="elements-and-attributes"></a>要素と属性
 `assembly`要素はルート要素でありが必要です。 その最初の構成要素である必要があります、`assemblyIdentity`要素。 マニフェストの要素は、次の名前空間のいずれかである必要があります。

 `urn:schemas-microsoft-com:asm.v1`

 `urn:schemas-microsoft-com:asm.v2`

 `http://www.w3.org/2000/09/xmldsig#`

 アセンブリの子要素は、これらの名前空間を継承またはタグ付けによってもあります。

 `assembly` 要素には、次の属性があります。

|属性|説明|
|---------------|-----------------|
|`manifestVersion`|必須。 `manifestVersion`に属性を設定する必要があります`1.0`します。|

## <a name="example"></a>例
 次のコード例を示しています、`assembly`に対するアプリケーション マニフェスト内の要素を[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーション。 このコード例で示されている例の一部は、 [ClickOnce アプリケーション マニフェスト](../deployment/clickonce-application-manifest.md)します。

```xml
<asmv1:assembly
  xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"
  manifestVersion="1.0"
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"
  xmlns="urn:schemas-microsoft-com:asm.v2"
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"
  xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1">
```

## <a name="see-also"></a>関連項目
- [ClickOnce アプリケーション マニフェスト](../deployment/clickonce-application-manifest.md)
- [\<アセンブリ > 要素](../deployment/assembly-element-clickonce-deployment.md)
