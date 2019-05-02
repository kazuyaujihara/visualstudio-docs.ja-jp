---
title: RegPkg パッケージ登録のトラブルシューティング |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: troubleshooting
helpviewer_keywords:
- RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 241975e475252a18d5e5a91c6e8c4fb40c067a95
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441181"
---
# <a name="troubleshooting-regpkg-package-registration"></a>RegPkg パッケージ登録のトラブルシューティング
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

> [!NOTE]
> .Pkgdef ファイルを使用する Visual Studio でパッケージを登録することをお勧めです。 これにより、拡張機能の配置、システム レジストリにアクセスする必要はありません。 Pkgdef ファイルを使用して作成された、 [CreatePkgDef ユーティリティ](../../extensibility/internals/createpkgdef-utility.md)します。  
  
 RegPkg でを使用してパッケージを登録する[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]、RegPkg パッケージに適しているのバージョンを使用する必要があります。  
  
## <a name="regpkg-versions-related-to-package-versions"></a>パッケージのバージョンに関連する RegPkg バージョン  
 RegPkg の 2 つのバージョンがあります。 1 つのバージョンが含まれている[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]します。 使用して、次のアセンブリのいずれかによって作成されたパッケージを登録するのにには、このバージョンを使用します。  
  
1. Microsoft.VisualStudioShell.9.0.dll  
  
2. Microsoft.VisualStudioShell.10.0.dll  
  
3. Microsoft.VisualStudioShell.11.0.dll  
  
   以前の Microsoft.VisualStudio.Shell.dll assembly を使用して作成されたパッケージを登録することはできません。  
  
   RegPkg の以前のバージョンでは、Microsoft.VisualStudio.Shell.dll assembly を使用して作成されたパッケージを登録できます。 ただし、そのアセンブリのそれ以降のバージョンを使用してビルドされたパッケージを登録することはできません。  
  
## <a name="see-also"></a>関連項目  
 [製品のリリース](../../misc/releasing-a-visual-studio-integration-product.md)
