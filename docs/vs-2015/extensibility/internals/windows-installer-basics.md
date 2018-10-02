---
title: Windows インストーラーの基本事項 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Installer, VSPackages
- VSPackages, Windows Installer basics
ms.assetid: 497e479b-add8-4644-870a-917f15306b97
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3a15d47971a7f500d1f709dfb248838f84065f21
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47536801"
---
# <a name="windows-installer-basics"></a>Windows インストーラーの基本事項
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[Windows インストーラーの基本事項](https://docs.microsoft.com/visualstudio/extensibility/internals/windows-installer-basics)します。  
  
Windows インストーラーは、Windows インストーラーのコンポーネント (WICs または単なるコンポーネントとも呼ばれます) と呼ばれる単位でこれらのタスクを実行するアプリケーションやユーザーのコンピューター上のソフトウェア製品をアンインストールします。 各 WIC では、インストールと参照カウントの Windows インストーラーを使用してセットアップの基本的な単位を識別する GUID。  
  
 Windows インストーラーの包括的なドキュメントについては、プラットフォーム SDK のトピックを参照してください。 [Windows インストーラー](http://msdn.microsoft.com/library/aa372866.aspx)します。  
  
## <a name="authoring-a-vspackage"></a>VSPackage の作成  
 Windows インストーラーは、Windows インストーラーは、インストール、アンインストール、または製品を修復し、セットアップ ユーザー インターフェイス (UI) を実行する必要がある情報が含まれるインストール パッケージを使用します。 各インストール パッケージには、インストール データベース、概要情報ストリーム、およびインストールのさまざまな部分のデータ ストリームを含む .msi ファイルが含まれています。 インストーラーを使用するには、インストールを作成する必要があります。 インストーラーでは、コンポーネントの概念にインストールを整理し、リレーショナル データベースのインストールに関する情報を格納、ため広範インストール パッケージを作成するプロセスには、次の手順が必要です。  
  
1.  作成、バージョン管理とサイド バイ サイドで戦略をサポートするために、セットアップを計画します。  
  
2.  ユーザーに表示するのには、機能を特定します。  
  
3.  VSPackage と依存関係をコンポーネントに編成します。  
  
4.  情報を含むインストール データベースを設定します。  
  
5.  インストール パッケージを検証します。  
  
 このドキュメントは主に、プロセスの最初と 3 番目の手順を実行します。 これらの手順で、VSPackage の特徴に編成する WICs、バージョン管理とサービスの今後のバージョンに対応する方針をフレームできますので[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]します。 残りの 3 つの手順は、プラットフォーム SDK の Windows インストーラーのドキュメントで詳しく説明します。  
  
## <a name="key-terms"></a>主な用語  
 Windows インストーラー テクノロジに関連する主な用語の定義を次に示します。  
  
 リソース  
 ファイル、レジストリ キー、ショートカット、またはこれにコンピューターにインストールされている可能性があります。 これらのリソースは、Windows インストーラー コンポーネントに論理的にグループ化されます。  
  
 Windows インストーラー component (WIC)  
 インストールがインストールされ、単位としてアンインストールする関連リソースの論理的なグループを表すの基本単位。 Windows インストーラー コンポーネントは、コンポーネントの一意の ID または GUID によって識別されます。 さらに、Windows インストーラーは、その参照は、WIC レベルでカウントを保持します。 最大のバージョン管理の柔軟性を高めるには、特定 WIC に、DLL などの複数のプライマリ リソースを含めます。 識別し、設定、WIC と GUID を指定およびデプロイしても後、は、その構成を変更することはできませんに注意してください。 詳細については、次を参照してください。[アプリケーション コンポーネントを整理する](http://msdn.microsoft.com/library/aa370561.aspx)します。  
  
 パッケージ (再頒布可能パッケージ)  
 このファイルをポイントする .msi ファイルと外部のソース ファイルで構成される展開の単位です。 パッケージには、Windows インストーラーの UI を実行して、インストールまたはアプリケーションをアンインストールする必要があるすべての情報が含まれています。  
  
 .msi ファイル  
 手順と、アプリケーションのインストールに必要なデータを含む COM 構造化ストレージ ファイルです。 すべてのパッケージには、少なくとも 1 つの .msi ファイルが含まれています。 .Msi ファイルには、インストーラー データベース、概要情報のストリームでは、および場合によって、1 つまたは複数の変換および内部のソース ファイルが含まれています。 ファイルをインストールするキャビネットに圧縮し、.msi ファイル内のストリームに格納されているまたは格納されている、圧縮されているか、非圧縮ソース メディア上の .msi ファイルの外部で。 詳細については、次を参照してください。 [Windows インストーラー ファイルの拡張子](http://msdn.microsoft.com/library/aa372842\(VS.85\).aspx)します。  
  
## <a name="windows-installer-rules-enforcement"></a>Windows インストーラー規則の実施  
 2 つの規則のセットでは、セットアップのコンポーネントを使用したリソースのデプロイを確認します。 1 つの規則セットは、インストールの作成者は、2 番目のセットを適用する必要があります、自体には、Windows インストーラーによって管理されます。  
  
> [!NOTE]
>  Windows インストーラーの規則の適用は、.msi ファイルの検証を実行する場合にのみ発生します。 ただし、ベスト プラクティスとして、これらの規則を処理する警告が表示されます。 詳細については、次を参照してください。[インストール データベースを検証する](http://msdn.microsoft.com/library/aa372477\(VS.85\).aspx)と[パッケージの検証](http://msdn.microsoft.com/library/aa370569\(VS.85\).aspx)です。  
  
#### <a name="installer-enforced-rules"></a>インストーラーによって適用される規則  
  
-   指定したコンポーネントのすべてのファイルは、同じディレクトリにインストールする必要があります。 逆に、コンポーネントを分離する個別のフォルダーにインストールされているファイルが属している必要があります。  
  
-   要素ごとの 1 つだけのキーのパスがあります。 キーのパスは、単にファイルまたはレジストリ キーを全体の構成要素を表します。  
  
#### <a name="component-provider-responsibilities"></a>コンポーネント プロバイダーの責任  
  
-   今後のバージョンでは別に出荷可能性がありますを 2 つのリソースは、個別のコンポーネントに存在する必要があります。 これらのリソースは個別に出荷されないは特定が場合にのみ、同じコンポーネントにリソースをグループ化する必要があります。 推奨実際には、すべての主要なリソース (たとえば、Dll) 常に個別の WICs に存在します。 詳細については、次を参照してください。[インストーラー コンポーネントを定義する](http://msdn.microsoft.com/library/aa368269\(VS.85\).aspx)します。  
  
-   バージョン管理されたリソース必要がありますこれまで出荷しない 1 つ以上の WIC でします。  
  
## <a name="see-also"></a>関連項目  
 [コンポーネントのルールが破損するいるとどうなりますか。](http://msdn.microsoft.com/library/aa372795\(VS.85\).aspx)
