---
title: テスト ソース管理プラグインのガイド |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- plug-ins, source control
- source control [Visual Studio SDK], testing plug-ins
- tests, source control plug-ins
- testing, source control plug-ins
- source control plug-ins, test guide
ms.assetid: 13b74765-0b7c-418e-8cd9-5f2e8db51ae5
caps.latest.revision: 27
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9efe5ffcd0428a11df69e3c80f28fdecaeb99aaf
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60100359"
---
# <a name="test-guide-for-source-control-plug-ins"></a>ソース管理プラグイン向けのテスト ガイド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

このセクションでは、ソース管理プラグインをテストするためのガイダンスを提供します。[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]します。 同様の問題となる可能性がより複雑な領域の一部、最も一般的なテスト領域の広範な概要が表示されます。 この概要はテスト_ケースを網羅するものではありません。  
  
> [!NOTE]
>  いくつかのバグ修正と最新の機能強化[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]既存ソース管理プラグインをしないの以前のバージョンを使用しているときに発生した以前の問題が明らかに IDE[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]します。 場合でも、変更が加えないプラグインの以前のバージョン以降、既存のソース管理プラグインのこのセクションに列挙された領域をテストすることを強くお勧め[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]します。  
  
## <a name="common-preparation"></a>一般的な準備  
 マシン[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]ターゲットのソース管理プラグイン インストールされている必要があります。 同様に構成されている 2 つ目のマシンは、いくつかのテストのソース管理から開く を使用できます。  
  
## <a name="definition-of-terms"></a>用語の定義  
 このテスト ガイドするためには、次の用語の定義を使用します。  
  
 クライアント プロジェクト  
 いずれかのプロジェクトで使用できる型[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]ソース管理の統合をサポートする (たとえば、 [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]、 [!INCLUDE[csprcs](../../includes/csprcs-md.md)]、または[!INCLUDE[vcprvc](../../includes/vcprvc-md.md)])。  
  
 Web プロジェクト (Web project)  
 Web プロジェクトの 4 つの種類があります。ファイル システム、ローカル IIS、リモートのサイトおよび FTP です。  
  
- ファイル システムのプロジェクトは、ローカル パスに作成されますが、インターネット インフォメーション サービス (IIS) には、UNC パスを使用して内部的にアクセスし、クライアント プロジェクトと同様に、IDE 内からソース管理下に置くことができますをインストールする必要はありません。  
  
- ローカル IIS プロジェクト、ローカル コンピューターを指す URL を使用して IIS が同じマシンにインストールされ、アクセスを使用します。  
  
- リモート サイトのプロジェクトは、IIS サービスも作成されますとからではなく、IIS サーバー コンピューターで、ソース管理下にあるそれらの内部で、 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE。  
  
- FTP のプロジェクトは、リモートの FTP サーバーからアクセスしますが、ソース管理下に配置することはできません。  
  
  参加リスト  
  ソリューションまたはプロジェクトをソース管理の別の用語です。  
  
  バージョン ストア  
  ソース管理プラグイン API を通じてアクセスされているソース管理データベース。  
  
## <a name="test-areas-covered-in-this-section"></a>このセクションで説明するテスト区分  
  
- [テスト領域 1:ソース管理から開く/を追加します。](../../extensibility/internals/test-area-1-add-to-open-from-source-control.md)  
  
    - ケース 1 a:ソリューションをソース管理に追加します。  
  
    - ケース 1 b:ソース管理からソリューションを開く  
  
    - ケース 1 c:ソース管理からソリューションを追加します。  
  
- [テスト領域 2:ソース管理から取得します。](../../extensibility/internals/test-area-2-get-from-source-control.md)  
  
- [テスト領域 3:チェック アウト/チェック アウトの取り消し](../../extensibility/internals/test-area-3-check-out-undo-checkout.md)  
  
    - ケース 3:チェック アウト/チェック アウトの取り消し  
  
    - ケース 3 a:チェックアウト  
  
    - ケース 3 b:切断されたチェック アウト  
  
    - ケース 3 c:保存 (QEQS) クエリの編集/クエリ  
  
    - 3d の場合します。サイレント チェック アウト  
  
    - ケース 3 e:チェック アウトを取り消し  
  
- [テスト領域 4:チェックイン](../../extensibility/internals/test-area-4-check-in.md)  
  
    - ケース 4 a:変更された項目  
  
    - ケース 4 b:ファイルを追加します。  
  
    - ケース 4 c:プロジェクトの追加  
  
- [テスト領域 5:ソース管理の変更](../../extensibility/internals/test-area-5-change-source-control.md)  
  
    - ケース 5 a:バインド  
  
    - ケース 5 b:[バインドの解除]  
  
    - ケース 5 c:再バインドします。  
  
- [テスト領域 6:Delete](../../extensibility/internals/test-area-6-delete.md)  
  
- [テスト領域 7:共有](../../extensibility/internals/test-area-7-share.md)  
  
- [テスト領域 8:プラグインの切り替え](../../extensibility/internals/test-area-8-plug-in-switching.md)  
  
    - 大文字と小文字の 8 a:自動の変更  
  
    - 大文字と小文字の 8 b:ソリューションに基づく変更  
  
## <a name="see-also"></a>関連項目  
 [ソース管理プラグイン](../../extensibility/source-control-plug-ins.md)
