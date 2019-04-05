---
title: ClickOnce キャッシュの概要 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce deployemtn
- ClickOnce applications, cache
- ClickOnce deployment, cache
ms.assetid: e379921e-9ef1-4326-bbf3-53ba67925526
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 58ea758ea10e2c58ff123a2bc991f14191db0aa1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977413"
---
# <a name="clickonce-cache-overview"></a>ClickOnce キャッシュの概要
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

すべて[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]、アプリケーションはオンラインでホストされているまたはローカルにインストールされるかどうか、内のクライアント コンピューターに保存されて、[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]アプリケーション*キャッシュ*します。 A[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]キャッシュは現在のユーザーの Documents and Settings フォルダーの設定をローカル ディレクトリの下の隠しディレクトリのファミリです。 このキャッシュは、アセンブリ、構成ファイル、アプリケーションとユーザー設定、およびデータ ディレクトリを含む、アプリケーションのすべてのファイルを保持します。 キャッシュはアプリケーションのデータ ディレクトリを最新バージョンに移行するためも担当します。 データ移行の詳細については、次を参照してください。[ローカルへのアクセスとリモート データには、ClickOnce アプリケーション](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)します。  
  
 アプリケーションの記憶域用の 1 つの場所を提供することで[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]ユーザーから、アプリケーションの物理的なインストールの管理作業を引き継ぎます。 アセンブリとすべてのアプリケーション データ ファイルを保持することでアプリケーションの分離にも役立ちますをキャッシュし、その個々 のバージョンを互いから分離します。 たとえば、アップグレード、[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]アプリケーションでは、バージョンとそのデータ リソースをキャッシュに独自のディレクトリに付属します。  
  
## <a name="cache-storage-quota"></a>キャッシュの記憶域のクォータ  
 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] オンラインでホストされているアプリケーションに占有できる領域の量のサイズを制限するクォータによって制限されますが、[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]キャッシュします。 キャッシュ サイズはすべてのユーザーのオンライン アプリケーションに適用されます。1 つの部分的に信頼された、オンライン アプリケーションでは、クォータの容量の半分を占有しているに制限されます。 インストールされているアプリケーションでは、キャッシュのサイズによる制限はありませんし、キャッシュ制限としてはカウントされません。 すべての[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]のみ現在のバージョンと以前にインストールされたバージョン、アプリケーション、キャッシュが保持されます。  
  
 既定では、クライアント コンピューターがある 250 MB の記憶域のオンライン[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]アプリケーション。 データ ファイルは、この制限にカウントされません。 システム管理者を拡大または HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment\OnlineAppQuotaInKB、DWORD 値は、レジストリ キーを変更することで特定のクライアント コンピューターでは、このクォータを削減できます。キャッシュ サイズ (キロバイト単位) を表現するとします。 たとえば、50 mb のキャッシュ サイズを減らす、この値を 51200 を変更します。  
  
## <a name="see-also"></a>関連項目  
 [ClickOnce アプリケーションにおけるローカル データおよびリモート データへのアクセス](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)
