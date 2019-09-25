---
title: '&lt;dependency&gt;要素 (ClickOnce アプリケーション) |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#osVersionInfo
- urn:schemas-microsoft-com:asm.v2#os
- http://www.w3.org/2000/09/xmldsig#Transform
- urn:schemas-microsoft-com:asm.v2#dependency
- http://www.w3.org/2000/09/xmldsig#DigestValue
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
- http://www.w3.org/2000/09/xmldsig#DigestMethod
- http://www.w3.org/2000/09/xmldsig#Transforms
- urn:schemas-microsoft-com:asm.v2#hash
- urn:schemas-microsoft-com:asm.v2#dependentAssembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- manifests [ClickOnce], dependency element
- <dependency> element [ClickOnce application manifest]
ms.assetid: 09d6a1e0-60f8-4fbd-843b-8e49ee3115a3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3aa949aa2f8e718ab0209c54a0ea2160c042a4eb
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71252492"
---
# <a name="ltdependencygt-element-clickonce-application"></a>&lt;dependency&gt;要素 (ClickOnce アプリケーション)
アプリケーションに必要なプラットフォームまたはアセンブリの依存関係を識別します。

## <a name="syntax"></a>構文

```xml

      <dependency>
   <dependentOS
      supportURL
      description
   >
      <osVersionInfo>
         <os
            majorVersion
            minorVersion
            buildNumber
            servicePackMajor
            servicePackMinor
            productType
            suiteType
         />
      </osVersionInfo>
   </dependentOS>
   <dependentAssembly
      dependencyType
      allowDelayedBinding
      group
      codeBase
      size
   >
      <assemblyIdentity
         name
         version
         processorArchitecture
         language
      >
         <hash>
            <dsig:Transforms>
               <dsig:Transform
                  Algorithm
            />
            </dsig:Transforms>
            <dsig:DigestMethod />
            <dsig:DigestValue>
            </dsig:DigestValue>
    </hash>

      </assemblyIdentity>
   </dependentAssembly>
</dependency>
```

## <a name="elements-and-attributes"></a>要素と属性
 `dependency`要素が必要です。 同じアプリケーションマニフェストにの複数`dependency`のインスタンスが存在する場合があります。

 `dependency`要素には属性がなく、には次の子要素が含まれています。

### <a name="dependentos"></a>依存関係 Entos
 任意。 `osVersionInfo`要素を含んでいます。 要素`dependentOS` `dependency`と`dependentAssembly`要素は相互に排他的です。一方またはもう一方は要素に対して存在する必要がありますが、両方を指定することはできません。

 `dependentOS`では、次の属性がサポートされています。

|属性|説明|
|---------------|-----------------|
|`supportUrl`|任意。 依存プラットフォームのサポート URL を指定します。 この URL は、必要なプラットフォームが見つかった場合にユーザーに表示されます。|
|`description`|任意。 人間が判読できる形式で、 `dependentOS`要素によって記述されるオペレーティングシステムについて説明します。|

### <a name="osversioninfo"></a>osVersionInfo
 必須です。 この要素は `dependentOS` 要素の子であり、 `os` 要素を含んでいます。 この要素には属性はありません。

### <a name="os"></a>os
 必須です。 この要素は `osVersionInfo` 要素の子です。 この要素には、次の属性があります。

|属性|説明|
|---------------|-----------------|
|`majorVersion`|必須です。 OS のメジャーバージョン番号を指定します。|
|`minorVersion`|必須です。 OS のマイナーバージョン番号を指定します。|
|`buildNumber`|必須です。 OS のビルド番号を指定します。|
|`servicePackMajor`|必須です。 OS の Service Pack メジャー番号を指定します。|
|`servicePackMinor`|任意。 OS の Service Pack マイナー番号を指定します。|
|`productType`|任意。 製品の種類の値を識別します。 有効な値は `server`、`workstation`、`domainController` です。 たとえば、Windows 2000 Professional の場合、この属性値は`workstation`になります。|
|`suiteType`|任意。 システムで使用可能な製品スイート、またはシステムの構成の種類を識別します。 有効な値は、`backoffice`、`blade`、`datacenter`、`enterprise`、`home`、`professional`、`smallbusiness`、`smallbusinessRestricted`、および `terminal` です。 たとえば、Windows 2000 Professional の場合、この属性値は`professional`になります。|

### <a name="dependentassembly"></a>dependentAssembly
 任意。 `assemblyIdentity`要素を含んでいます。 要素`dependentOS` `dependency`と`dependentAssembly`要素は相互に排他的です。一方またはもう一方は要素に対して存在する必要がありますが、両方を指定することはできません。

 `dependentAssembly`には次の属性があります。

| 属性 | 説明 |
|-----------------------| - |
| `dependencyType` | 必須です。 依存関係の種類を指定します。 有効値は `preprequisite` または `install` です。 アセンブリは、 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションの一部としてインストールされます。 `install` [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] `prerequisite`アプリケーションをインストールする前に、アセンブリがグローバルアセンブリキャッシュ (GAC) に存在している必要があります。 |
| `allowDelayedBinding` | 必須です。 実行時にアセンブリをプログラムによって読み込むことができるかどうかを指定します。 |
| `group` | 任意。 属性がに`install`設定されている場合、は、要求時にのみインストールされるアセンブリの名前付きグループを指定します。 `dependencyType` 詳細については、「[チュートリアル:デザイナーを使用して必要に応じて ClickOnce 配置 API でアセンブリをダウンロードする](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md)」を参照してください。<br /><br /> に`framework`設定され、 `dependencyType`属性がに`prerequisite`設定されている場合、は、アセンブリを .NET Framework の一部として指定します。 .NET Framework 4 以降のバージョンにインストールする場合、このアセンブリのグローバル assemby キャッシュ (GAC) はチェックされません。 |
| `codeBase` | 属性がに`dependencyType` `install`設定されている場合に必要です。 依存アセンブリへのパス。 絶対パス、またはマニフェストのコードベースを基準とした相対パスのいずれかを指定できます。 このパスは、アセンブリマニフェストが有効であるために有効な URI である必要があります。 |
| `size` | 属性がに`dependencyType` `install`設定されている場合に必要です。 依存アセンブリのサイズ (バイト単位)。 |

### <a name="assemblyidentity"></a>assemblyIdentity
 必須です。 この要素は `dependentAssembly` 要素の子であり、以下の属性があります。

|属性|説明|
|---------------|-----------------|
|`name`|必須です。 アプリケーションの名前を識別します。|
|`version`|必須です。 アプリケーションのバージョン番号を次の形式で指定します。`major.minor.build.revision`|
|`publicKeyToken`|任意。 アプリケーションまたはアセンブリに署名するときに使用する公開キーの`SHA-1`ハッシュ値の最後の8バイトを表す16文字の16進数文字列を指定します。 カタログの署名に使用される公開キーは、2048ビット以上である必要があります。|
|`processorArchitecture`|任意。 プロセッサを指定します。 有効な値は`x86` 、32ビット`I64` windows の場合は、64ビット版の場合はです。|
|`language`|任意。 アセンブリの2つの部分言語コード (EN-US など) を識別します。|

### <a name="hash"></a>hash
 要素は、 `assemblyIdentity`要素の省略可能な子です。 `hash` `hash` 要素に属性はありません。

 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]は、アプリケーション内のすべてのファイルのアルゴリズムハッシュをセキュリティチェックとして使用して、展開後にファイルが変更されていないことを確認します。 `hash`要素が含まれていない場合、このチェックは実行されません。 そのため、要素`hash`を省略することは推奨されません。

### <a name="dsigtransforms"></a>dsig:Transforms
 要素は、 `hash`要素の必須の子です。 `dsig:Transforms` `dsig:Transforms` 要素に属性はありません。

### <a name="dsigtransform"></a>dsig:Transform
 要素は、 `dsig:Transforms`要素の必須の子です。 `dsig:Transform` `dsig:Transform` 要素には、次の属性があります。

| 属性 | 説明 |
|-------------| - |
| `Algorithm` | このファイルのダイジェストの計算に使用されるアルゴリズム。 現在、で使用され[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]て`urn:schemas-microsoft-com:HashTransforms.Identity`いる値はのみです。 |

### <a name="dsigdigestmethod"></a>dsig: DigestMethod
 要素は、 `hash`要素の必須の子です。 `dsig:DigestMethod` `dsig:DigestMethod` 要素には、次の属性があります。

| 属性 | 説明 |
|-------------| - |
| `Algorithm` | このファイルのダイジェストの計算に使用されるアルゴリズム。 現在、で使用され[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]て`http://www.w3.org/2000/09/xmldsig#sha1`いる値はのみです。 |

### <a name="dsigdigestvalue"></a>dsig:DigestValue
 要素は、 `hash`要素の必須の子です。 `dsig:DigestValue` `dsig:DigestValue` 要素に属性はありません。 テキスト値は、指定されたファイルの計算済みハッシュです。

## <a name="remarks"></a>コメント
 アプリケーションで使用されるすべてのアセンブリには`dependency` 、対応する要素が必要です。 依存アセンブリには、プラットフォームアセンブリとしてグローバルアセンブリキャッシュにプレインストールする必要があるアセンブリは含まれません。

## <a name="example"></a>例
 次のコード例は`dependency` 、 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションマニフェストの要素を示しています。 このコード例は、 [ClickOnce アプリケーションマニフェスト](../deployment/clickonce-application-manifest.md)トピック用に用意されている、より大きな例の一部です。

```xml
<dependency>
  <dependentOS>
    <osVersionInfo>
      <os
        majorVersion="4"
        minorVersion="10"
        buildNumber="0"
        servicePackMajor="0" />
    </osVersionInfo>
  </dependentOS>
</dependency>
<dependency>
  <dependentAssembly
    dependencyType="preRequisite"
    allowDelayedBinding="true">
    <assemblyIdentity
      name="Microsoft.Windows.CommonLanguageRuntime"
      version="4.0.20506.0" />
  </dependentAssembly>
</dependency>

<dependency>
  <dependentAssembly
    dependencyType="install"
    allowDelayedBinding="true"
    codebase="MyApplication.exe"
    size="4096">
    <assemblyIdentity
      name="MyApplication"
      version="1.0.0.0"
      language="neutral"
      processorArchitecture="x86" />
    <hash>
      <dsig:Transforms>
        <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />
      </dsig:Transforms>
      <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />
      <dsig:DigestValue>DpTW7RzS9IeT/RBSLj54vfTEzNg=</dsig:DigestValue>
    </hash>
  </dependentAssembly>
</dependency>
```

## <a name="see-also"></a>関連項目
- [ClickOnce アプリケーション マニフェスト](../deployment/clickonce-application-manifest.md)
- [\<dependency > 要素](../deployment/dependency-element-clickonce-deployment.md)