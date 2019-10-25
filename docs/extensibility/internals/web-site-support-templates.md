---
title: Web サイトサポートテンプレート |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- we site projects, templates
ms.assetid: 37173c97-486b-4b3c-8ed3-cf5890c4de23
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aceaa574fa2a0148236f033c610f8c53ca74e635
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721595"
---
# <a name="web-site-support-templates"></a>Web サイト サポートのテンプレート
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] の Web サイトプロジェクトと項目テンプレートを使用すると、新しい Web サイトプロジェクトと項目を最初から作成する必要がなくなり、開発プロセスを高速化する、再利用可能でカスタマイズ可能な Web サイトプロジェクトと項目のスタブが提供されます。 @No__t_0 テンプレートの詳細については、「[プロジェクトと項目テンプレートの作成](../../ide/creating-project-and-item-templates.md)」を参照してください。

## <a name="project-template-folder"></a>プロジェクトテンプレートフォルダー
 Web プロジェクトテンプレートは、通常、[*Visual Studio インストールパス*] \Common7\IDE\ProjectTemplates\Web \\ にインストールされます。各サブフォルダーには、web プログラミング言語の後に名前が付けられます。

## <a name="project-file"></a>プロジェクト ファイル
 @No__t_0 統合開発環境 (IDE) では、テンプレートを適切なプロジェクトの種類にマップする方法として、プロジェクトファイルの拡張子が必要です。 Web プロジェクトにはプロジェクトファイルがないため、テンプレートをプロジェクトの種類にマップするために、ダミーのプロジェクトファイル拡張子 webproj が登録されています。

 必要に応じて、言語名の文字列をテンプレートに追加して、Web プロジェクトシステムで、テンプレートに基づく項目の **[新しい項目の追加]** ダイアログボックスで既定の言語を設定できるようにすることができます。 文字列は、ファイルの最初の行である必要があります。 IntelliSense エンジンの登録で AddItemLanguageName に登録されている名前と、プロジェクトのサブタイプ (.Vstemplate) に登録されている名前の両方に一致する必要があります。 詳細については、「 [Web サイトのサポート属性](../../extensibility/internals/web-site-support-attributes.md)」を参照してください。

 文字列が存在しない場合、Web プロジェクトシステムは、プロジェクトテンプレートによって Web プロジェクトに追加されたページの言語属性とファイル拡張子に基づいて、既定の言語を決定しようとします。

## <a name="project-templates"></a>プロジェクト テンプレート
 Web サイトプロジェクトテンプレートは、 **[ファイル]** メニューの **[新しい web サイト]** コマンドに応答して、新しい web サイトを構築するために使用されます。 現在、3つの Web サイトプロジェクトの種類がサポートされています。

- 空の Web サイトプロジェクト

- Web サイトプロジェクト

- Web サービスプロジェクト

### <a name="empty-web-site-projects"></a>空の Web サイトプロジェクト
 これらのファイルは、**空の Web サイト**コマンドに応答して新しい空の web サイトを作成します。このコマンドは、 **[ファイル]**  >  **[新しい web サイト]** を選択した後で利用できます。

- EmptyWeb .vstemplate

     新しい空の Web サイトを作成するためのガイドとなるテンプレートファイル。

- EmptyWeb. webproj

     このファイルは、プロジェクトテンプレートシステムの成果物です。 これは、EmptyWeb .vstemplate ファイル内のプロジェクトファイル参照を満たしています。

### <a name="web-site-projects"></a>Web サイトプロジェクト
 これらのファイルは、 **ASP.NET Web サイト**コマンドに応答して新しい web サイトを作成します。これは、[**ファイル** > **新しい web サイト**] を選択した後に使用できます。

- Default.aspx

     新しい Web サイトの既定のホームページ。 Language 属性は codebehind 言語を指定し、CodeFile 属性はこのページに関連付けられている codebehind コードを含む依存ファイルを指定します。

- Default.aspx。*拡張機能*

     既定のホームページの分離コードを格納する依存ファイル。 このファイルの*拡張子*は、分離コードの言語によって決まります。

- web.config

     ルートの web サイト構成ファイル。

- WebApplication .vstemplate

     Web サイトソリューションの内容を決定し、App_Data フォルダーを強制的に作成するテンプレートファイル。

- WebApplication. webproj

     このファイルは、プロジェクトテンプレートシステムの成果物です。 これは、WebApplication ファイル内のプロジェクトファイル参照を満たしています。

### <a name="web-service-projects"></a>Web サービスプロジェクト
 これらのファイルは、 **ASP.NET Web Service**コマンドに応答して新しい web サイトを作成します。これは、[**ファイル** > **新しい web サイト**] を選択した後で使用できます。

- サービス .asmx

     新しい Web サービスの HTML ページ。 Language 属性は codebehind 言語を指定し、CodeBehind 属性はこのサービスに関連付けられている codebehind コードを含む依存ファイルを指定します。

- 処理. *番号*

     サービスクラスを実装する依存ファイル。 このファイルの*拡張子*は、分離コードの言語によって決まります。

- web.config

- ルートの web サイト構成ファイル。

- WebService. .vstemplate

     Web サイトソリューションの内容を決定し、App_Data および App_Code フォルダーを強制的に作成するテンプレートファイル。 サービス。*拡張*ファイルが App_Code フォルダーにコピーされます。

- WebService. webproj

     このファイルは、プロジェクトテンプレートシステムの成果物です。 これは、WebService ファイル内のプロジェクトファイル参照を満たしています。

## <a name="project-item-template-folder"></a>プロジェクト項目テンプレートフォルダー
 Web プロジェクト項目テンプレートは、通常、[*Visual Studio インストールパス*] \Common7\IDE\ItemTemplates\Web \\ にインストールされます。各サブフォルダーには、web プログラミング言語の後に名前が付けられます。

## <a name="project-item-templates"></a>プロジェクト項目テンプレート
 **[既存項目の追加]** コマンドに応答して web サイトに新しい web ページを追加するには、web サイトプロジェクト項目テンプレートを使用します。 現在、次の種類の Web ページがサポートされています。

- 新しいクラス

- 新しい HTML ページ

- 新しい Web フォーム

- 新しいマスターページ

### <a name="new-class"></a>新しいクラス
 このテンプレートは、 **[新しいクラスの追加]** コマンドに応答して、空のクラスを定義する新しいソースファイルを作成します。

- クラス。 *番号*

     空のクラスを実装するソースファイル。 このファイルの*拡張子*は、分離コードの言語によって決まります。

- クラス .vstemplate

     ソースファイルを作成し、その内容を決定するテンプレートファイル。

### <a name="new-html-page"></a>新しい HTML ページ
 このテンプレートは、 **[新しい HTML ページの追加]** コマンドに応答して新しい Web ページを作成します。

- HTMLPage .htm

     Web ページの開始コンテンツ。 この Web ページには、通常、関連付けられている codebehind 依存ファイルがありません。 関連付けられた分離コードファイルを使用してスマートページを作成するには、代わりに Web フォームテンプレートを使用します。

- HTMLPage .vstemplate

     Web ページを作成し、その内容を決定するテンプレートファイル。

### <a name="new-webform"></a>新しい Web フォーム
 このテンプレートは、 **[新しい Web フォームの追加]** コマンドに応答して新しいスマート web ページを作成します。

 依存する分離コードソースファイルを作成するには、[**コードを別のファイルに配置**する] を選択します。 それ以外の場合は、空のスクリプトブロックを持つ Web ページが1つ作成され、依存ファイルをフックする \<% Page% > ディレクティブはありません。

 選択したマスターページのコンテンツページを作成するには、 **[マスターページの選択]** を選択します。

- Web フォーム .aspx

     Web ページの開始コンテンツ。 この Web ページには、関連付けられている codebehind 依存ファイルがありません。

- WebForm_cb

     Web ページの開始コンテンツ。 この Web ページには、関連付けられた codebehind 依存ファイルがあります。

- 分離コード. *番号*

     Web フォームクラスを実装する依存ファイル。 このファイルの*拡張子*は、分離コードの言語によって決まります。

- ContentPage

     コンテンツページとしての Web ページの開始コンテンツ。 この Web ページには、関連付けられている codebehind 依存ファイルがありません。

- ContentPage_cb

     コンテンツページとしての Web ページの開始コンテンツ。 この Web ページには、関連付けられた codebehind 依存ファイルがあります。

- Web フォーム .vstemplate

     新しい web ページの内容とその依存ファイル (存在する場合) を決定するテンプレートファイル。

### <a name="new-master-page"></a>新しいマスターページ
 このテンプレートは、 **[新しいマスターページの追加]** コマンドに応答して新しいマスターページを作成します。

 依存する分離コードソースファイルを作成するには、[**コードを別のファイルに配置**する] を選択します。 それ以外の場合は、空のスクリプトブロックを持つ1つの Web ページが作成され、依存ファイルをフックするための \<% Page% > ディレクティブはありません。

- マスターマスター

     マスターページの開始コンテンツ。 このマスターページには、関連付けられた codebehind 依存ファイルがありません。

- MasterPage_cb

     マスターページの開始コンテンツ。 このマスターページには、関連付けられた codebehind 依存ファイルがあります。

- 分離コード.*拡張機能*

     マスターページクラスを実装する依存ファイル。 このファイルの*拡張子*は、分離コードの言語によって決まります。

- //.Vstemplate

     新しいマスターページの内容とその依存ファイル (存在する場合) を決定するテンプレートファイル。

## <a name="see-also"></a>関連項目
- [Web サイト サポート](../../extensibility/internals/web-site-support.md)