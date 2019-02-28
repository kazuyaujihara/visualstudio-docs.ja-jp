---
title: .NET Framework の拡張機能の登録 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 18df04fc706ea716f7c22baa6508930f0f94a6f6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54801467"
---
# <a name="registering-extensions-of-the-net-framework"></a>.NET Framework の拡張機能の登録
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
.NET Framework の特定のバージョンを拡張するアセンブリを開発できます。 アセンブリが Visual Studio の **[参照の追加]** ダイアログ ボックスに表示されるようにするには、そのアセンブリを格納するフォルダーをシステム レジストリに追加する必要があります。  
  
 たとえば、Trey Research 社では、.NET Framework 4 を拡張するライブラリを開発しており、プロジェクトが .NET Framework 4 を対象とするときはそのライブラリ アセンブリが **[参照の追加]** ダイアログ ボックスに表示されるようにするとします。 また、アセンブリは、32 ビット コンピューター上で実行される 32 ビット アセンブリまたは 64 ビット コンピューター上で実行される 64 ビット アセンブリであり、C:\TreyResearch\Extensions4\ フォルダーにインストールされるとします。  
  
 このフォルダーを登録するために使用するキーは、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\ です。 このキーに指定する既定値は、C:\TreyResearch\Extensions4 です。  
  
> [!NOTE]
>  .NET Framework のビルド番号は異なる場合があります。  
  
 32 ビット アセンブリを 64 ビット コンピューターに登録するには、Wow6432 ノードを使用します (例: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\)。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio の統合](../msbuild/visual-studio-integration-msbuild.md)
