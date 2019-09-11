---
title: '&lt;deployment&gt;要素 (ClickOnce 配置) |Microsoft ドキュメント'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#subscription
- urn:schemas-microsoft-com:asm.v2#beforeApplicationStartup
- urn:schemas-microsoft-com:asm.v2#deploymentProvider
- urn:schemas-microsoft-com:asm.v2#update
- urn:schemas-microsoft-com:asm.v2#deployment
- urn:schemas-microsoft-com:asm.v2#expiration
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <deployment> element [ClickOnce deployment manifest]
ms.assetid: 4fafa9c2-97a0-4cea-b8fd-9746dca33af4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 988ce0859ab24377395cc4077f9e6fa42e0487a5
ms.sourcegitcommit: 4dfe098ac0df294aad63e6b384d6575980798ca3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70887856"
---
# <a name="ltdeploymentgt-element-clickonce-deployment"></a>&lt;deployment&gt;要素 (ClickOnce 配置)
更新プログラムの配置とシステムへの公開に使用される属性を指定します。

## <a name="syntax"></a>構文

```xml

      <deployment
   install
   minimumRequiredVersion
   mapFileExtensions
   disallowUrlActivation
   trustUrlParameters
>
   <subscription>
         <update>
            <beforeApplicationStartup/>
            <expiration
               maximumAge
               unit
            />
         </update>
   </subscription>
   <deploymentProvider
      codebase
   />
</deployment>
```

## <a name="elements-and-attributes"></a>要素と属性
 `deployment` 要素は必須です。この要素は `urn:schemas-microsoft-com:asm.v2` 名前空間に属します。 要素には、次の属性があります。

| 属性 | 説明 |
|--------------------------| - |
| `install` | 必須。 このアプリケーションが Windows の **[スタート]** メニューと コントロールパネル の **[プログラムの追加と削除]** アプリケーションでプレゼンスを定義するかどうかを指定します。 有効値は `true` または `false` です。 の`false`場合[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 、は常に、このアプリケーションの最新バージョンをネットワークから実行`subscription`し、要素を認識しません。 |
| `minimumRequiredVersion` | 任意。 クライアントで実行できる、このアプリケーションの最小バージョンを指定します。 アプリケーションのバージョン番号が配置マニフェストで指定されたバージョン番号よりも小さい場合、アプリケーションは実行されません。 バージョン番号は、という形式`N.N.N.N`で指定する必要があります。ここ`N`で、は符号なし整数です。 属性が`false`の場合、 `minimumRequiredVersion`を設定することはできません。 `install` |
| `mapFileExtensions` | 任意。 既定値は `false` です。 の`true`場合、配置内のすべてのファイルに .deploy 拡張子が必要です。 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]は、これらのファイルを Web サーバーからダウンロードするとすぐに、この拡張機能を削除します。 を使用[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]してアプリケーションを発行すると、この拡張機能がすべてのファイルに自動的に追加されます。 このパラメーターを使用すると、 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]配置内のすべてのファイルを Web サーバーからダウンロードして、.exe などの "安全でない" 拡張機能で終わるファイルの転送をブロックすることができます。 |
| `disallowUrlActivation` | 任意。 既定値は `false` です。 の`true`場合、インストールされているアプリケーションは、url をクリックするか、Internet Explorer に url を入力することで起動できなくなります。 `install`属性が存在しない場合、この属性は無視されます。 |
| `trustURLParameters` | 任意。 既定値は `false` です。 の`true`場合、アプリケーションに渡されるクエリ文字列パラメーターを URL に含めることができます。コマンドライン引数はコマンドラインアプリケーションに渡されます。 詳細については、「[方法 :オンライン ClickOnce アプリケーションでクエリ文字列の情報を取得する](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)」を参照してください。<br /><br /> 属性が`true`の場合は`trustUrlParameters` 、マニフェストから除外するか、を明示的にに`false`設定する必要があります。 `disallowUrlActivation` |

 要素`deployment`には、次の子要素も含まれます。

## <a name="subscription"></a>subscription
 任意。 `update`要素を含んでいます。 `subscription`要素に属性がありません。 `subscription`要素が存在しない場合、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションは更新プログラムをスキャンしません。 `install`の属性の `deployment` 要素が `false` の場合、ネットワークから起動される[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションは常に最新のバージョンを使用するため、`subscription`要素は無視されます。

## <a name="update"></a>update
 必須。 この要素は`subscription`要素の子であり、要素`beforeApplicationStartup`また`expiration`は要素で構成されます。 `beforeApplicationStartup`と`expiration`の両方を同じ配置マニフェストで指定することはできません。

 `update`要素に属性がありません。

## <a name="beforeapplicationstartup"></a>beforeApplicationStartup
 任意。 この要素は`update`要素の子であり、属性はありません。 要素が存在する場合、クライアントがオンラインになっ[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]ている場合は、が更新プログラムを確認するときに、アプリケーションがブロックされます。 `beforeApplicationStartup` この要素が存在しない場合[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 、は、最初に`expiration`要素に指定された値に基づいて更新プログラムをスキャンします。 `beforeApplicationStartup`と`expiration`の両方を同じ配置マニフェストで指定することはできません。

## <a name="expiration"></a>expiration
 任意。 この要素は`update`要素の子であり、子はありません。 `beforeApplicationStartup`と`expiration`の両方を同じ配置マニフェストで指定することはできません。 更新プログラムのチェックが行われ、更新されたバージョンが検出されると、既存のバージョンが実行されている間に新しいバージョンがキャッシュされます。 その後、 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションの次回の起動時に、新しいバージョンがインストールされます。

 要素`expiration`は、次の属性をサポートしています。

|属性|説明|
|---------------|-----------------|
|`maximumAge`|必須。 アプリケーションが更新プログラムのチェックを実行する前に、現在の更新プログラムがどのようになるかを指定します。 時間の単位は、 `unit`属性によって決まります。|
|`unit`|必須。 の`maximumAge`時間単位を識別します。 有効な単位`hours`は`days`、、 `weeks`、およびです。|

## <a name="deploymentprovider"></a>deploymentProvider
 .NET Framework 2.0 の場合、配置マニフェストに`subscription`セクションが含まれている場合、この要素は必須です。 .NET Framework 3.5 以降では、この要素は省略可能であり、配置マニフェストが検出されたサーバーとファイルパスに既定で設定されます。

 この要素は `deployment` 要素の子であり、以下の属性があります。

| 属性 | 説明 |
|------------| - |
| `codebase` | 必須。 アプリケーションの[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]更新に使用される配置マニフェストの場所を Uniform Resource Identifier (URI) で識別します。 また、この要素により、CD ベースのインストールの更新プログラムの場所も転送できます。 有効な URI である必要があります。 |

## <a name="remarks"></a>Remarks
 スタートアップ時に更新[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]プログラムをスキャンしたり、起動後に更新プログラムをスキャンしたり、更新プログラムを確認したりしないようにアプリケーションを構成できます。 スタートアップ時に更新プログラムをスキャンするには`beforeApplicationStartup` 、要素が要素`update`の下に存在することを確認します。 スタートアップ後に更新プログラムをスキャンするには`expiration` 、要素の`update`下に要素が存在し、その更新間隔が指定されていることを確認します。

 更新プログラムの確認を無効にする`subscription`には、要素を削除します。 配置マニフェストで更新プログラムをスキャンしないように指定した場合でも、 <xref:System.Deployment.Application.ApplicationDeployment.CheckForUpdate%2A>メソッドを使用して更新プログラムを手動で確認できます。

 DeploymentProvider が更新プログラムにどのように関連しているかの詳細については、「 [ClickOnce の更新方法の選択](../deployment/choosing-a-clickonce-update-strategy.md)」を参照してください。

## <a name="examples"></a>使用例
 次のコード例は、 `deployment` [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]配置マニフェストの要素を示しています。 この例では`deploymentProvider` 、要素を使用して、優先する更新の場所を示しています。

```xml
<deployment install="true" minimumRequiredVersion="2.0.0.0" mapFileExtension="true" trustUrlParameters="true">
    <subscription>
      <update>
        <expiration maximumAge="6" unit="hours" />
      </update>
    </subscription>
    <deploymentProvider codebase="http://www.adatum.com/MyApplication.application" />
  </deployment>
```

## <a name="see-also"></a>関連項目
- [ClickOnce 配置マニフェスト](../deployment/clickonce-deployment-manifest.md)