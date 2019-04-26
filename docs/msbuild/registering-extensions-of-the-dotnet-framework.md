---
title: .NET Framework の拡張機能の登録 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: f1e780a67ee419a8cae661570802e5d85081f1fd
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63445811"
---
# <a name="register-extensions-of-the-net-framework"></a>.NET Framework の拡張機能の登録
.NET Framework の特定のバージョンを拡張するアセンブリを開発できます。 アセンブリが Visual Studio の **[参照の追加]** ダイアログ ボックスに表示されるようにするには、そのアセンブリを格納するフォルダーをシステム レジストリに追加する必要があります。

 たとえば、Trey Research 社では、.NET Framework 4 を拡張するライブラリを開発しており、プロジェクトが .NET Framework 4 を対象とするときはそのライブラリ アセンブリが **[参照の追加]** ダイアログ ボックスに表示されるようにするとします。 また、アセンブリは、32 ビット コンピューター上で実行される 32 ビット アセンブリまたは 64 ビット コンピューター上で実行される 64 ビット アセンブリであり、*C:\TreyResearch\Extensions4\\* フォルダーにインストールされるとします。

 このフォルダーを登録するために使用するキーは、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\** です。 このキーに指定する既定値は、**C:\TreyResearch\Extensions4** です。

> [!NOTE]
> .NET Framework のビルド番号は異なる場合があります。

 32 ビット アセンブリを 64 ビット コンピューターに登録するには、Wow6432 ノードを使用します (例:**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\**)。

### <a name="see-also"></a>関連項目
- [Visual Studio の統合](../msbuild/visual-studio-integration-msbuild.md)