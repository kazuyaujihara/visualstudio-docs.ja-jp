---
title: 相互運用機能アセンブリの登録コマンドハンドラー |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- interop assemblies, command handlers
- command handling with interop assemblies, registering
ms.assetid: 303cd399-e29d-4ea1-8abe-5e0b59c12a0c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cbc0d162a11df034bec4d1f357ef8abd106da401
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724689"
---
# <a name="registering-interop-assembly-command-handlers"></a>相互運用機能アセンブリ コマンド ハンドラーの登録
VSPackage は、統合開発環境 (IDE: integrated development environment) がコマンドを適切にルーティングできるように [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] に登録する必要があります。

 レジストリを更新するには、手動で編集するか、レジストラー (.rgs) ファイルを使用します。 詳細については、「 [Creating Registrar Scripts](/cpp/atl/creating-registrar-scripts)」を参照してください。

 Managed Package Framework (MPF) は、<xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> クラスを通じてこの機能を提供します。

- [コマンドテーブル形式の参照](https://msdn.microsoft.com/library/09e9c6ef-9863-48de-9483-d45b7b7c798f)リソースは、アンマネージサテライト UI dll にあります。

## <a name="command-handler-registration-of-a-vspackage"></a>VSPackage のコマンドハンドラーの登録
 ユーザーインターフェイス (UI) ベースのコマンドのハンドラーとして機能する VSPackage には、VSPackage `GUID` の後に、という名前のレジストリエントリが必要です。 このレジストリエントリは、VSPackage の UI リソースファイルとそのファイル内の menu リソースの場所を指定します。 レジストリエントリ自体は、HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio \\ *\<Version >* ] の下にあります。 *\<Version >* は、9.0 などの [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] のバージョンです。

> [!NOTE]
> HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio \\ *\<Version >* のルートパスは、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] シェルの初期化時に代替ルートでオーバーライドできます。 ルートパスの詳細については、「 [Windows インストーラーを使用した Vspackage のインストール](../../extensibility/internals/installing-vspackages-with-windows-installer.md)」を参照してください。

### <a name="the-ctmenu-resource-registry-entry"></a>CTMENU リソースレジストリエントリ
 レジストリエントリの構造は次のとおりです。

```
HKEY_LOCAL_MACHINE\Software\VisualStudio\<Version>\
  Menus\
    <GUID> = <Resource Information>
```

 \<*GUID*> は、{VSPackage} という形式の、XXXXXXXXX} の `GUID` です。

 *\<Resource 情報 >* は、コンマで区切られた3つの要素で構成されます。 これらの要素の順序は次のとおりです。

 *リソース DLL > へ*の \< パス、\<*メニューリソース ID*>、\<*メニューバージョン*>

 次の表では、> \<*リソース情報*のフィールドについて説明します。

| 要素 | 説明 |
|---------------------------| - |
| *リソース DLL への \< パス*> | これは、メニューリソースを含むリソース DLL への完全なパスです。これは、VSPackage のリソース DLL が使用されることを示します。これは、VSPackage 自体が登録されている Packages サブキーで指定されています。<br /><br /> 慣例として、このフィールドは空白にしておきます。 |
| \<*メニューリソース ID* > | これは、 [VSPackage ファイルからコンパイルされた](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)のすべての UI 要素を含む、`CTMENU` リソースのリソース ID です。 |
| \<*メニューバージョン*> | これは、`CTMENU` リソースのバージョンとして使用される番号です。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] は、この値を使用して、`CTMENU` リソースの内容をすべての `CTMENU` リソースのキャッシュと再マージする必要があるかどうかを判断します。 Devenv のセットアップコマンドを実行すると、再マージがトリガーされます。<br /><br /> この値は、最初に1に設定し、`CTMENU` リソースのすべての変更の後、再マージが発生する前にインクリメントする必要があります。 |

### <a name="example"></a>例
 いくつかのリソースエントリの例を次に示します。

```
HKEY_LOCAL_MACHINE\Software\VisualStudio\9.0Exp\
  Menus\
    {019971D6-4685-11D2-B48A-0000F87572EB} = ,1, 10
    {1b027a40-8f43-11d0-8d11-00a0c91bc942} = , 10211, 3
```

## <a name="see-also"></a>関連項目
- [VSPackage でユーザー インターフェイス要素を追加する方法](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [相互運用機能アセンブリを使用するコマンドとメニュー](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)