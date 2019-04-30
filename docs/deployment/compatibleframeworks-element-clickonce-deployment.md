---
title: '&lt;compatibleFrameworks&gt;要素 (ClickOnce 配置) |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <compatibleFrameworks> element [ClickOnce deployment manifest]
ms.assetid: f6c3ee55-9e65-403d-8664-3ebde872c7d4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 06b96327205369d0280a865b632801edbf199745
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63407861"
---
# <a name="ltcompatibleframeworksgt-element-clickonce-deployment"></a>&lt;compatibleFrameworks&gt;要素 (ClickOnce 配置)
このアプリケーションをインストールして実行できる .NET Framework のバージョンを指定します。

> [!NOTE]
> [*MageUI.exe* ](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)はサポートしていません、`compatibleFrameworks`アプリケーション マニフェストを保存するときに要素を使用して、証明書で署名済みの[ *MageUI.exe*](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)します。 代わりに [*Mage.exe*](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) を使用する必要があります。

## <a name="syntax"></a>構文

```xml
<compatibleFrameworks
      SupportUrl> 
   <framework
      targetVersion
      profile
      supportedRuntime
   /> 
</ compatibleFrameworks>
```

## <a name="elements-and-attributes"></a>要素と属性
 `compatibleFrameworks`配置マニフェストを対象とする要素が必要、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]ランタイムによって提供される[!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)]またはそれ以降。 `compatibleFrameworks`要素は、1 つ以上含まれています。`framework`このアプリケーションが実行できる .NET Framework のバージョンを指定する要素。 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]ランタイムは、最初に、アプリケーションを実行する使用可能な`framework`この一覧にします。

 次の表に、属性を`compatibleFrameworks`要素をサポートしています。

|属性|説明|
|---------------|-----------------|
|`S` `upportUrl`|省略可能です。 推奨される互換性のある .NET Framework バージョンをダウンロードできる URL を指定します。|

## <a name="framework"></a>framework
 必須。 次の表に、属性を`framework`要素をサポートしています。

|属性|説明|
|---------------|-----------------|
|`targetVersion`|必須。 ターゲット .NET Framework のバージョン番号を指定します。|
|`profile`|必須。 ターゲット .NET Framework のプロファイルを指定します。|
|`supportedRuntime`|必須。 .NET Framework を対象に関連付けられているランタイムのバージョン番号を指定します。|

## <a name="remarks"></a>Remarks

## <a name="example"></a>例
 次のコード例は、`compatibleFrameworks`内の要素を[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]配置マニフェスト。 この配置を実行できる、[!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]します。 も実行でき、[!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)]のスーパー セットである、[!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]します。

```xml
<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">
  <framework
      targetVersion="4.0"
      profile="Client"
      supportedRuntime="4.0.30319" />
</compatibleFrameworks>
```

## <a name="see-also"></a>関連項目
- [ClickOnce 配置マニフェスト](../deployment/clickonce-deployment-manifest.md)