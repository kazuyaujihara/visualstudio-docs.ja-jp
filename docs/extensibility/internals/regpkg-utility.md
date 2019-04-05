---
title: RegPkg ユーティリティ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- regpkg, registration utility
- registration, regpkg utility
ms.assetid: 1683ee18-59d1-4bab-a674-dd00dd960de3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6b9b07bc801e687da9ce93968dbac59966328484
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56619239"
---
# <a name="regpkg-utility"></a>RegPkg ユーティリティ
> [!NOTE]
>  .Pkgdef ファイルを使用する Visual Studio でパッケージを登録することをお勧めです。 これにより、拡張機能の配置、VSIX 展開の要件であるシステム レジストリにアクセスする必要はありません。 Pkgdef ファイルを使用して作成された、 [CreatePkgDef ユーティリティ](../../extensibility/internals/createpkgdef-utility.md)します。 Visual Studio パッケージの配置の詳細については、[Visual Studio 拡張機能の配布](../../extensibility/shipping-visual-studio-extensions.md)を参照してください。

 RegPkg.exe ユーティリティによる VSPackage の登録[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]して展開用に準備します。 VSPackage 開発中にバック グラウンドでこのユーティリティを使用します。 ビルドして、実験用ハイブで VSPackage を実行できるように、ビルド プロセスの一部として実行されます。

 RegPkg は、複数の形式でシステム レジストリのスクリプトを生成できます。 .Msi プロジェクトや Windows Installer XML Toolset ファイルなどの展開プロジェクトでこれらのスクリプトを組み込むことができます。

 RegPkg.exe は通常\< *Visual Studio SDK インストール パス*> \VisualStudioIntegration\Tools\Bin\RegPkg.exe します。 RegPkg は、この構文を次に示します。

```
RegPkg [/root:<root>] [/regfile:<regfile>] [/rgsfile:<rgsfile> [/rgm]] [/vrgfile:<vrgfile>] [/codebase | /assembly] [/unregister] AssemblyPath
```

 指定された名前の/root:root 実行の登録

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ルート。

 /regfile:FileName、レジストリを更新するのではなく、.reg ファイルを作成します。  /Vrgfile または/rgsfile/wixfile では使用できません。

 /rgsfile:FileName には、レジストリを更新するのではなく、.rgs ファイルが作成されます。  /Vrgfile または/regfile/wixfile では使用できません。

 /vrgfile:FileName には、レジストリを更新するのではなく、.vrg ファイルが作成されます。  /Regfile または/rgsfile/wixfile では使用できません。

 /rgm は、rgs ファイルだけでなく .rgm ファイルを作成します。  /Rgsfile と組み合わせる必要があります。

 /wixfile:FileName には、レジストリを更新するのではなく、Windows Installer XML ツールセットと互換性のあるファイルが作成されます。  /Regfile または/rgsfile/vrgfile では使用できません。

 /コードベースのアセンブリではなく、コードベースで強制的に登録します。

 コードベースではなく、アセンブリと/assembly 強制的に登録します。

 /Unregisters このパッケージの登録を解除します。  使用することはできません。

 /regfile または/vrgfile または/rgsfile または/wixfile します。

## <a name="see-also"></a>関連項目
- [VSPackage](../../extensibility/internals/vspackages.md)
- [RegPkg パッケージ登録のトラブルシューティング](../../extensibility/internals/troubleshooting-regpkg-package-registration.md)