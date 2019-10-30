---
title: VSIX パッケージの構造 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- visual studio extension
- vsix
- packages
ms.assetid: 8b86d62f-c274-4e91-82e0-38cdb9a423d5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d215849036e76cb51080775f5ea55e1eb0b28c56
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72981691"
---
# <a name="anatomy-of-a-vsix-package"></a>VSIX パッケージの構造
VSIX パッケージは、1つまたは複数の Visual Studio 拡張機能を含む *.vsix*ファイルで、visual studio が拡張機能を分類およびインストールするために使用するメタデータと共に使用されます。 このメタデータは、VSIX マニフェストと *[Content_Types] .xml*ファイルに格納されています。 VSIX パッケージには、ローカライズされたセットアップテキストを提供するための*vsixlangpack*ファイルが1つ以上含まれている場合があります。また、依存関係をインストールするための vsix パッケージが追加されている場合もあります。

 VSIX パッケージ形式は、Open パッケージング規約 (OPC) 標準に従います。 パッケージには、バイナリおよびサポートファイルと、 *[Content_Types] .xml*ファイルと *.vsix*マニフェストファイルが含まれています。 1つの VSIX パッケージに、複数のプロジェクトの出力、または独自のマニフェストを持つ複数のパッケージが含まれている場合があります。

> [!NOTE]
> VSIX パッケージに含まれるファイルの名前には、 [\[RFC2396\]](https://www.rfc-editor.org/rfc/rfc2396.txt)で定義されているように、スペースや、Uniform resource IDENTIFIER (URI) で予約されている文字を含めることはできません。

## <a name="the-vsix-manifest"></a>VSIX マニフェスト
 VSIX マニフェストには、インストールする拡張機能に関する情報が含まれており、VSX スキーマに従います。 詳細については、「 [VSIX 拡張機能スキーマ1.0 リファレンス](https://msdn.microsoft.com/library/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)」を参照してください。 VSIX マニフェストの例については、「 [PackageManifest 要素 (root 要素、VSX schema)](https://msdn.microsoft.com/library/f8ae42ba-775a-4d2b-976a-f556e147f187)」を参照してください。

 VSIX マニフェストは、^ .vsix * ファイルに含まれている場合は `extension.vsixmanifest` という名前にする必要があります。

## <a name="the-content"></a>コンテンツ
 VSIX パッケージには、テンプレート、ツールボックスアイテム、Vspackage、または Visual Studio でサポートされているその他の種類の拡張機能が含まれている場合があります。

## <a name="language-packs"></a>言語パック
 VSIX パッケージには、インストール時にローカライズされたテキストを提供するための*vsixlangpack*ファイルが1つ以上含まれている場合があります。 詳細については、「 [VSIX パッケージのローカライズ](../extensibility/localizing-vsix-packages.md)」を参照してください。

## <a name="dependencies-and-references"></a>依存関係と参照
 VSIX パッケージには、参照として他の VSIX パッケージを含めることができます。 これらの他のパッケージにはそれぞれ、独自の VSIX マニフェストが含まれている必要があります。

 依存関係がある拡張機能をユーザーがインストールしようとすると、インストーラーは必要なアセンブリがユーザーシステムにインストールされていることを確認します。 必要なアセンブリが見つからない場合は、**拡張機能と更新プログラム**によって、不足しているアセンブリの一覧が表示されます。

 拡張機能マニフェストに1つ以上の[参照](/previous-versions/visualstudio/visual-studio-2010/dd393687(v=vs.100))要素が含まれている場合、**拡張機能と更新プログラム**によって、各参照のマニフェストがシステムにインストールされている拡張機能と比較され、参照されている拡張機能がまだインストールされていない場合はインストールされます。ら. 以前のバージョンの参照されている拡張機能がインストールされている場合は、新しいバージョンで置き換えられます。

 複数プロジェクトのソリューション内のプロジェクトに、同じソリューション内の別のプロジェクトへの参照が含まれている場合、VSIX パッケージにはそのプロジェクトの依存関係が含まれます。 この動作をオーバーライドするには、内部プロジェクトの参照をクリックし、**プロパティ** ウィンドウで、**VSIX に含まれる出力グループ** プロパティを `BuiltProjectOutputGroup`に設定します。

 参照されたアセンブリのサテライト Dll を VSIX パッケージに含めるには、 **vsix プロパティに含まれる出力グループ**に `SatelliteDllsProjectOutputGroup` を追加します。

## <a name="installation-location"></a>インストール場所
 インストール中、**拡張機能と更新プログラム**によって、 *%LocalAppData%\Microsoft\VisualStudio\14.0\Extensions*の下のフォルダーにある VSIX パッケージの内容が検索されます。

 既定では、 *% Localappdata%* はユーザー固有のディレクトリであるため、インストールは現在のユーザーにのみ適用されます。 ただし、マニフェストの[AllUsers](https://msdn.microsoft.com/library/ac817f50-3276-4ddb-b467-8bbb1432455b)要素を `True`に設定した場合、拡張機能は<em>..\\</em>VisualStudioInstallationFolder<em>\Common7\IDE\Extensions</em>にインストールされ、コンピューターのすべてのユーザーが使用できるようになります。

## <a name="content_typesxml"></a>[Content_Types] .xml
 *[Content_Types] .xml*ファイルは、展開された *.vsix*ファイル内のファイルの種類を識別します。 Visual Studio では、パッケージのインストール時にこのファイルを使用しますが、ファイル自体はインストールしません。 このファイルの詳細については、「 [[Content_types] .xml ファイルの構造](the-structure-of-the-content-types-dot-xml-file.md)」を参照してください。

 Open パッケージング規約 (OPC) 標準では、 *[Content_Types] .xml*ファイルが必要です。 OPC の詳細については、「 [opc: データをパッケージ化するための新しい標準](https://blogs.msdn.microsoft.com/msdnmagazine/2007/08/08/opc-a-new-standard-for-packaging-your-data/)」を参照してください。