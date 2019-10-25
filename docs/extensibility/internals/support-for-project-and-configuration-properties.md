---
title: プロジェクトおよび構成プロパティのサポート |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project properties, supporting with Visual Studio SDK
- configuration properties, supporting with Visual Studio SDK
ms.assetid: 9fcfaa0f-7b41-4b68-82ec-7a151dca5d7e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8bf0581eee4fade779d89143f4633f1b87d3ce0f
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72723153"
---
# <a name="support-for-project-and-configuration-properties"></a>プロジェクトおよび構成プロパティのサポート
@No__t_1 統合開発環境 (IDE) の **[プロパティ]** ウィンドウでは、プロジェクトと構成のプロパティを表示できます。 ユーザーがアプリケーションのプロパティを設定できるように、独自のプロジェクトの種類のプロパティページを提供できます。

 **ソリューションエクスプローラー**でプロジェクトノードを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックすると、プロジェクトと構成のプロパティを含むダイアログボックスを開くことができます。 これらの言語から派生した [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] および [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]、およびプロジェクトの種類では、このダイアログボックスは、 [[全般] ([オプション] ダイアログボックス-[環境](../../ide/reference/general-environment-options-dialog-box.md)]) のタブ付きページとして表示されます。 詳細については、「[ビルド内にありません: チュートリアル: プロジェクトC#および構成プロパティを公開する」 ()](https://msdn.microsoft.com/library/d850d63b-25e2-4505-9f3d-eb038d7c1d0e)を参照してください。

 プロジェクト用の Managed Package Framework (MPFProj) には、新しいプロジェクトシステムを作成および管理するためのヘルパークラスが用意されています。 ソースコードとコンパイルの手順については、「 [MPF For Projects-Visual Studio 2013](https://github.com/tunnelvisionlabs/MPFProj10)」を参照してください。

## <a name="persistence-of-project-and-configuration-properties"></a>プロジェクトおよび構成プロパティの永続化
 プロジェクトと構成のプロパティは、プロジェクトの種類に関連付けられたファイル名拡張子を持つプロジェクトファイルに保存されます (.csproj、.vbproj、myproj など)。 言語プロジェクトでは、通常、プロジェクトファイルを生成するためにテンプレートファイルを使用します。 ただし、プロジェクトの種類とテンプレートを関連付けるには、実際にいくつかの方法があります。 詳細については、「テンプレートディレクトリの説明」 (を参照してください[。Vsdir) ファイル](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)。

 プロジェクトと構成のプロパティは、テンプレートファイルに項目を追加することによって作成されます。 これらのプロパティは、このテンプレートを使用するプロジェクトの種類を使用して作成されたプロジェクトで使用できます。 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] プロジェクトと MPFProj は両方とも、テンプレートファイルの "[ビルド内にありません: MSBuild の概要](/previous-versions/visualstudio/visual-studio-2008/ms171452(v=vs.90))" スキーマを使用します。 これらのファイルには、構成ごとに PropertyGroup セクションがあります。 通常、プロジェクトのプロパティは、構成引数が null 文字列に設定されている最初の PropertyGroup セクションに保存されます。

 次のコードは、基本的な MSBuild プロジェクトファイルの開始を示しています。

```
<Project MSBuildVersion="2.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
    <Name>SomeProjectSix</Name>
    <SchemaVersion>2.0</SchemaVersion>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Debug' ">
    <Optimize>false</Optimize>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <Optimize>true</Optimize>
```

 このプロジェクトファイルの `<Name>` と `<SchemaVersion>` はプロジェクトのプロパティであり、`<Optimize>` は構成プロパティです。

 プロジェクトファイルのプロジェクトおよび構成プロパティを永続化するのはプロジェクトの役割です。

> [!NOTE]
> プロジェクトで永続化を最適化するには、既定値とは異なるプロパティ値のみを保持します。

## <a name="support-for-project-and-configuration-properties"></a>プロジェクトおよび構成プロパティのサポート
 @No__t_0 クラスは、プロジェクトと構成のプロパティページを実装します。 @No__t_0 の既定の実装では、汎用プロパティグリッド内のユーザーにパブリックプロパティを提供します。 @No__t_0 メソッドは、プロジェクトのプロパティグリッドの `SettingsPage` から派生したクラスを選択します。 @No__t_0 メソッドは、構成プロパティグリッドの `SettingsPage` から派生したクラスを選択します。 適切なプロパティページを選択するには、プロジェクトの種類でこれらのメソッドをオーバーライドする必要があります。

 @No__t_0 クラスと `Microsoft.VisualStudio.Package.ProjectNode` クラスは、次のメソッドを提供してプロジェクトと構成のプロパティを保持します。

- `Microsoft.VisualStudio.Package.ProjectNode.GetProjectProperty` および `Microsoft.VisualStudio.Package.ProjectNode.SetProjectProperty` プロジェクトのプロパティを保持します。

- `Microsoft.VisualStudio.Package.SettingsPage.GetConfigProperty` および `Microsoft.VisualStudio.Package.SettingsPage.SetConfigProperty` 構成プロパティを保持します。

  > [!NOTE]
  > @No__t_0 クラスと `Microsoft.VisualStudio.Package.ProjectNode` クラスの実装では、`Microsoft.Build.BuildEngine` (MSBuild) メソッドを使用して、プロジェクトファイルからプロジェクトと構成のプロパティを取得および設定します。

  @No__t_0 から派生するクラスは `Microsoft.VisualStudio.Package.SettingsPage.ApplyChanges` を実装し、プロジェクトファイルのプロジェクトまたは構成プロパティを永続化するために `Microsoft.VisualStudio.Package.SettingsPage.BindProperties` する必要があります。

## <a name="provideobjectattribute-and-registry-path"></a>属性とレジストリパス
 @No__t_0 から派生したクラスは、Vspackage 間で共有されるように設計されています。 VSPackage が `SettingsPage` から派生したクラスを作成できるようにするには、`Microsoft.VisualStudio.Shell.Package` から派生したクラスに `Microsoft.VisualStudio.Shell.ProvideObjectAttribute` を追加します。

 [!code-csharp[VSSDKSupportProjectConfigurationProperties#1](../../extensibility/internals/codesnippet/CSharp/support-for-project-and-configuration-properties_1.cs)]
 [!code-vb[VSSDKSupportProjectConfigurationProperties#1](../../extensibility/internals/codesnippet/VisualBasic/support-for-project-and-configuration-properties_1.vb)]

 属性がアタッチされている VSPackage は、重要ではありません。 VSPackage が [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] に登録されると、作成可能な任意のオブジェクトのクラス id (CLSID) が登録され、<xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry.CreateInstance%2A> の呼び出しによって作成されるようになります。

 作成できるオブジェクトのレジストリパスは、<xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>、単語、CLSID、およびオブジェクトの種類の guid を組み合わせることによって決定されます。 @No__t_0 クラスの guid が {3c693da2-5bca-49b3-bd95-ffe0a39dd723} で、UserRegistryRoot が HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp の場合、レジストリパスは HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\ になります。8.0 exp \ CLSID \\ {3c693da2-5bca-49b3-bd95-ffe0a39dd723}。

## <a name="project-and-configuration-property-attributes-and-layout"></a>プロジェクトおよび構成プロパティの属性とレイアウト
 @No__t_0、<xref:System.ComponentModel.DisplayNameAttribute>、および <xref:System.ComponentModel.DescriptionAttribute> 属性によって、一般的なプロパティページのプロジェクトおよび構成プロパティのレイアウト、ラベル付け、および説明が決まります。 これらの属性によって、オプションのカテゴリ、表示名、および説明がそれぞれ決まります。

> [!NOTE]
> 同等の属性、SRCategory、LocDisplayName、および Srcategory では、ローカライズに文字列リソースを使用し、[プロジェクトの Visual Studio 2013 に対して MPF](https://github.com/tunnelvisionlabs/MPFProj10)で定義されています。

 次のコードがあるとします。

 [!code-vb[VSSDKSupportProjectConfigurationProperties#2](../../extensibility/internals/codesnippet/VisualBasic/support-for-project-and-configuration-properties_2.vb)]
 [!code-csharp[VSSDKSupportProjectConfigurationProperties#2](../../extensibility/internals/codesnippet/CSharp/support-for-project-and-configuration-properties_2.cs)]

 @No__t_0 構成プロパティは、構成 プロパティページの **マイカテゴリ** カテゴリの  **Config プロパティ**として表示されます。 このオプションが選択されている場合は、説明パネルに " **My description**" という説明が表示されます。

## <a name="see-also"></a>関連項目
- [プロパティ ページの追加と削除](../../extensibility/adding-and-removing-property-pages.md)
- [プロジェクト](../../extensibility/internals/projects.md)
- [テンプレート ディレクトリの説明 (.Vsdir) ファイル](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)
