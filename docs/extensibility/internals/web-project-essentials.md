---
title: Web プロジェクトの Essentials |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- web projects, essentials
ms.assetid: ca2f4e43-322c-4431-8680-52da846940bc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5f3d3069d8cc539deeda7c9d44f8d1cbf27e8821
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721671"
---
# <a name="web-project-essentials"></a>Web プロジェクトの基本情報
Web プロジェクトでは、Web アプリケーションを作成します。 Web プロジェクトを使用して、スマート Web ページを含む Web アプリケーションを作成できます。 スマート Web ページには、Web ページをオンデマンドでレンダリングするサーバー側コードがあります。

 @No__t_0 や [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] などの従来のプログラミング言語を使用して、ユーザーから情報を収集して処理したり、データベースに格納したりするためのスマート Web ページを作成できます。

- 分離コードモデルは、ファイル拡張子が .aspx または .asmx の Web ページに依存ソースコードファイルを関連付けます。 たとえば、hello .aspx は、依存するソースコードファイル hello.aspx.cs を持つ場合があります。

- スマート Web ページに関連付けられているサーバー側のコードは、Web サイトの/bin フォルダーにある実行可能ファイルにコンパイルされます。

- 特定の Web ページに関連付けられていないヘルパークラスなどの追加のソースコードファイルは、Web サイトのコードフォルダーにあります。

  - Web サイトプロジェクト (WSP) では、スマート Web ページごとに1つの実行可能ファイルが生成されます。 その他の実行可能ファイルは、/appcode フォルダー内の任意のソースコードファイルから生成されます。

  - Web アプリケーションプロジェクト (WAP) は、すべてのスマート Web ページのコード、および/appcode フォルダー内のすべてのソースファイルを組み合わせた1つの実行可能ファイルを生成します。

- Web プロジェクトのソリューションファイルは、Web サイト自体とは別に配置されます。 既定では、ソリューションファイルは \Documents と Settings \\ にあります。*アカウント*\My Documents \\ *\<Visual Studio # # # # >* 、*web サイト*\\ ます。

  > [!NOTE]
  > ソリューションファイルを Web サイトと共に保持する場合は、そのファイルを移動して再度開きます。

- ソリューションファイルのない Web サイトを Visual Studio に開いた場合は、新しいソリューションファイルが自動的に生成されます。

- Web プロジェクトにはプロジェクトファイルがありません。 プロジェクト情報は、ソリューションファイル、web.config ファイル、およびその他の場所に格納されます。

- グローバルプロパティを Web プロジェクトに追加すると、Web プロジェクトソリューションフォルダーにストレージファイルが自動的に作成されます。

- スマート Web ページは、ページディレクティブまたは \<script runat = "server" > タグを使用して、サーバー側のプログラミング言語に関連付けることができます。

- また、Web ページには、任意のスクリプト言語で記述されたクライアント側スクリプトブロックをいくつでも含めることができます。

- Web サイトプロジェクトシステムは、プロジェクトと項目テンプレートを追加し、[!INCLUDE[vwprvw](../../extensibility/internals/includes/vwprvw_md.md)] プロジェクトに登録することによって実装されます。

- WAP システムはプロジェクトのサブタイプとして実装されます。プロジェクトのフレーバーとも呼ばれます。 Wap システムを作成するために、[!INCLUDE[vwprvw](../../extensibility/internals/includes/vwprvw_md.md)] プロジェクトは WAP サブタイプによって flavored されます。 プロジェクトのサブタイプの詳細については、「[プロジェクトのサブ](../../extensibility/internals/project-subtypes.md)タイプ」を参照してください。

- スマート Web ページは、HTML とサーバー側プログラミング言語を組み合わせたものです。 サーバー側の言語は、含まれる言語と呼ばれます。 含まれている言語をサポートするには、Web プロジェクトシステムがインターフェイスの <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> ファミリを実装する必要があります。

  - エディターで含まれている言語をサポートするには、HTML 言語サービスが、含まれている言語サービスに含まれる言語コードの表示を延期する必要があります。

  - エラーマーカー (赤の squigglies) は、常にコードエディターのプライマリバッファーに作成する必要があります。

## <a name="see-also"></a>関連項目
- [Web プロジェクト](../../extensibility/internals/web-projects.md)