---
title: VSIX v3 で拡張機能フォルダー外でのインストール |Microsoft Docs
ms.date: 11/09/2016
ms.topic: conceptual
ms.assetid: 913c3745-8aa9-4260-886e-a05aecfb2225
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2d5fc36c1244edd0988b6b76f8106020369cd90b
ms.sourcegitcommit: da4079f5b6ec884baf3108cbd0519d20cb64c70b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "67852194"
---
# <a name="install-outside-the-extensions-folder"></a>拡張機能フォルダー外でのインストール

拡張機能フォルダーの外部 (バージョン 3) 拡張機能資産を Visual Studio 2017 と VSIX v3 以降をインストールできます。 現時点では、次の場所は、([INSTALLDIR] は、Visual Studio インスタンスのインストール ディレクトリにマップ) の有効なインストール場所として有効になっているは。

* [INSTALLDIR]\MSBuild
* [INSTALLDIR]\Xml\Schemas
* [INSTALLDIR]\Common7\IDE\PublicAssemblies
* [INSTALLDIR]\Licenses
* [INSTALLDIR]\Common7\IDE\ReferenceAssemblies
* [INSTALLDIR]\Common7\IDE\RemoteDebugger
* [INSTALLDIR] \Common7\IDE\VC\VCTargets (Visual Studio 2017 のサポートされている; Visual Studio 2019 の非推奨とのみ以降)

> [!NOTE]
> VSIX 形式は、Visual Studio のインストール フォルダーの構造の外にインストールできます。 

これらのディレクトリへのインストールをサポートするために、VSIX を「インスタンスごとのコンピューターごとの」インストールする必要があります。 これは、extension.vsixmanifest デザイナーで「すべてのユーザー」のチェック ボックスをオンに有効にすることができます。

![すべてのユーザーを確認してください。](media/check-all-users.png)

## <a name="how-to-set-the-installroot"></a>InstallRoot を設定する方法

インストール ディレクトリを設定するには、使用することができます、**プロパティ**Visual Studio のウィンドウ。 たとえば、設定、`InstallRoot`上の場所のいずれかへの参照をプロジェクトのプロパティ。

![ルートのプロパティをインストールします。](media/install-root-properties.png)

これは、いくつかのメタデータが、対応する追加されます`ProjectReference`VSIX プロジェクトの .csproj ファイル内のプロパティ。

```xml
 <ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
        <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
        <Name>ClassLibrary1</Name>
        <InstallRoot>PublicAssemblies</InstallRoot>
 </ProjectReference>
```

> [!NOTE]
> たい場合は、.csproj ファイルを直接編集できます。

## <a name="how-to-set-a-subpath-under-the-installroot"></a>InstallRoot、下のサブパスを設定する方法

下のサブパスをインストールするかかどうか、 `InstallRoot`、設定によって行うことができます、`VsixSubPath`プロパティと同様、`InstallRoot`プロパティ。 たとえばをインストールする、プロジェクト参照の出力する ' [INSTALLDIR]\MSBuild\MyCompany\MySDK\1.0'。 次のように簡単にプロパティ デザイナーを使用しました。

![セットのサブパス](media/set-subpath.png)

対応する .csproj 変更は、次のようになります。

```xml
<ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
       <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
       <Name>ClassLibrary1</Name>
       <InstallRoot>MSBuild</InstallRoot>
       <VSIXSubPath>MyCompany\MySDK\1.0</VSIXSubPath>
</ProjectReference>
```

## <a name="extra-information"></a>追加情報

プロパティのデザイナーの変更; プロジェクトの参照だけに適用されます。設定することができます、`InstallRoot`もプロジェクト内の項目のメタデータ (上記で説明したのと同じ方法を使用)。
