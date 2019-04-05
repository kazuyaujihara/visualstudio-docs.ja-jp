---
title: 状態の永続化のサポート |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- state persistence, managed package framework support
- managed package framework, state persistence support
- state, persistence
ms.assetid: d25866f2-8d1f-477f-8aa5-3af3fbbf6e97
caps.latest.revision: 15
manager: jillfra
ms.openlocfilehash: 6dc542d2e410b79a21e436a1881c06bd3cc4eef8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58978079"
---
# <a name="support-for-state-persistence"></a>状態の永続性のサポート
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 共通オブジェクトの状態を維持することができます。 たとえば、ソリューションとプロジェクトのプロパティに保存され、ソリューションおよびプロジェクト ファイルから復元します。 ユーザー設定にエクスポートし、設定ファイルからインポートします。  
  
 Vspackage は、通常、システム レジストリまたは現在のユーザーまたはコンピューターのアプリケーション データ フォルダーのローカルのストレージに依存します。 整数や文字列などの記憶域を少量の領域を必要とする値は、通常、システム レジストリに格納します。 記憶域は、ビットマップなど、多くの領域を必要とする値は、ファイルに保存されます。 システム レジストリに、ファイルのパスを自体に保存することができます。 永続化メカニズムは、ローカル ストレージにアクセスする権限が必要です。  
  
## <a name="support-for-locating-local-storage"></a>ローカル ストレージを検索するためのサポート  
 <xref:Microsoft.VisualStudio.Shell.Package>クラスは、現在のユーザーまたはコンピューターのシステム レジストリまたはアプリケーション データ フォルダー内の状態情報を検索するためのサポートを提供します。  
  
 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>  
 ローカル コンピューターのレジストリ ルートのパスを返します[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]、たとえば、HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0Exp します。  
  
 ローカル レジストリ ルートがから取得した、<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>サービス。 取得したが使用可能な場合、 <xref:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute> VSPackage の属性です。  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>  
 現在のユーザーの (コンピューター単位) のパスを返しますのレジストリ ルート[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]、たとえば、HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp します。  
  
 ローカル レジストリ ルートがから取得した、<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>サービス。 使用可能な場合は、VSPackage の DefaultLocalRegistryRoot 属性から取得されます。  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserDataPath%2A>  
 共通リポジトリとして機能するディレクトリのパスを返します[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]C:\Documents and Settings などの現在のローミング ユーザーのデータ\\*YourAccountName*\Application Data\Microsoft\VisualStudio\8.0Exp します。  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserLocalDataPath%2A>  
 共通リポジトリとして機能するディレクトリのパスを返します[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]データ、現在の非ローミング ユーザー、たとえば、C:\Documents and Settings\\*YourAccountName*\Local Settings\ApplicationData\Microsoft\VisualStudio\8.0Exp します。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio の状態](../misc/vspackage-state.md)