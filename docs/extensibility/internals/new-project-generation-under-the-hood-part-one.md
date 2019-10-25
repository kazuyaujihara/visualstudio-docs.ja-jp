---
title: '新しいプロジェクトの生成: 内部、パート 1 |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio], new project dialog
- projects [Visual Studio], new project generation
ms.assetid: 66778698-0258-467d-8b8b-c351744510eb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 41b2b229fe343c9f6d515ba757e4bd976ee7fda5
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72726527"
---
# <a name="new-project-generation-under-the-hood-part-one"></a>新しいプロジェクトの生成: 内部、パート 1
独自のプロジェクトの種類を作成するにはどうすればよいでしょうか。 新しいプロジェクトを作成すると、実際にはどうなるのでしょうか。 では、実際の状況を見てみましょう。

 Visual Studio では、次のようないくつかのタスクが調整されます。

- 使用可能なすべてのプロジェクトの種類のツリーが表示されます。

- プロジェクトの種類ごとにアプリケーションテンプレートの一覧が表示され、1つを選択できます。

- プロジェクト名やパスなど、アプリケーションのプロジェクト情報が収集されます。

- この情報をプロジェクトファクトリに渡します。

- これにより、現在のソリューション内のプロジェクト項目とフォルダーが生成されます。

## <a name="the-new-project-dialog-box"></a>[新しいプロジェクト] ダイアログボックス
 新しいプロジェクトのプロジェクトの種類を選択すると、すべてが開始されます。 まず、 **[ファイル]** メニューの **[新しいプロジェクト]** をクリックします。 **[新しいプロジェクト]** ダイアログボックスが表示され、次のようになります。

 ![[新しいプロジェクト] ダイアログボックス](../../extensibility/internals/media/newproject.gif "NewProject")

 詳しく見てみましょう。 **プロジェクトの種類**ツリーには、作成できるさまざまな種類のプロジェクトが一覧表示されます。 **ビジュアルC#ウィンドウ**などのプロジェクトの種類を選択すると、アプリケーションテンプレートの一覧が表示され、作業を開始できます。 **Visual studio にインストール**されているテンプレートは、visual studio によってインストールされ、コンピューターの任意のユーザーが使用できます。 作成または収集した新しいテンプレートは**マイテンプレート**に追加でき、自分だけが使用できます。

 **Windows アプリケーション**などのテンプレートを選択すると、ダイアログボックスにアプリケーションの種類の説明が表示されます。この場合は、 **Windows ユーザーインターフェイスを使用してアプリケーションを作成するためのプロジェクト**です。

 **[新しいプロジェクト]** ダイアログボックスの下部に、詳細情報を収集するコントロールがいくつか表示されます。 表示されるコントロールはプロジェクトの種類によって異なりますが、一般に、プロジェクト **[名]** テキストボックス、 **[場所]** テキストボックス、関連する **[参照]** ボタン、 **[ソリューション名]** テキストボックス、および**ソリューションの関連する作成ディレクトリが含まれています。** チェックボックスをオンにします。

## <a name="populating-the-new-project-dialog-box"></a>[新しいプロジェクト] ダイアログボックスの設定
 **[新しいプロジェクト]** ダイアログボックスの情報の取得元 ここでは2つのメカニズムが使用されています。そのうちの1つは非推奨とされます。 **[新しいプロジェクト]** ダイアログボックスには、両方のメカニズムから取得した情報がまとめて表示されます。

 古い (非推奨) メソッドでは、システムレジストリエントリと .vsdir ファイルが使用されます。 このメカニズムは、Visual Studio を開いたときに実行されます。 新しいメソッドでは、.vstemplate ファイルを使用します。 たとえば、次のように Visual Studio を初期化すると、このメカニズムが実行されます。

```
devenv /setup
```

 、または

```
devenv /installvstemplates
```

### <a name="project-types"></a>プロジェクトの種類
 **Visual C#** など**の** **プロジェクトの種類**のルートノードの位置と名前は、システムレジストリエントリによって決定されます。 **データベース**や**スマートデバイス**など、子ノードの組織は、対応する .vstemplate ファイルを含むフォルダーの階層をミラー化します。 まずルートノードを見てみましょう。

#### <a name="project-type-root-nodes"></a>プロジェクトの種類のルートノード
 @No__t_0 が初期化されると、システムレジストリキー HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\NewProjectTemplates\TemplateDirs のサブキーを走査して、**プロジェクトの種類**ツリーのルートノードをビルドし、名前を指定します。 この情報は、後で使用するためにキャッシュされます。 TemplateDirs \\ {FAE04EC1-301F-11D3-BF4B-00C04F79EFBC} \\/1 キーを確認します。 各エントリは VSPackage GUID です。 サブキー (/1) の名前は無視されますが、その存在は、これが**プロジェクトの種類**のルートノードであることを示します。 ルートノードには、 **[プロジェクトの種類]** ツリーでの表示を制御するいくつかのサブキーがあります。 それらのいくつかを見てみましょう。

##### <a name="default"></a>(既定)
 これは、ルートノードに名前を指定するローカライズされた文字列のリソース ID です。 文字列リソースは、VSPackage GUID によって選択されたサテライト DLL にあります。

 この例では、VSPackage GUID はです。

 {FAE04EC1-301F-11D3-BF4B-00C04F79EFBC}

 ルートノード (/1) のリソース ID (既定値) は #2345

 隣接するパッケージキーの GUID を調べて SatelliteDll サブキーを調べると、文字列リソースを含むアセンブリのパスを確認できます。

 \<Visual Studio のインストールパス >VC#\、Vcspackag/、dll

 これを確認するには、エクスプローラーを開き、csprojui .dll を Visual Studio ディレクトリにドラッグします。 文字列テーブルは、リソース #2345 にキャプション**ビジュアルC#** があることを示しています。

##### <a name="sortpriority"></a>SortPriority
 これにより、**プロジェクトの種類**ツリーのルートノードの位置が決まります。

 SortPriority REG_DWORD 0x00000014 (20)

 優先順位の値が小さいほど、ツリー内の位置が大きくなります。

##### <a name="developeractivity"></a>DeveloperActivity
 このサブキーが存在する場合、ルートノードの位置は [開発者の設定] ダイアログボックスによって制御されます。 たとえば、オブジェクトに適用された

 DeveloperActivity REG_SZVC#

 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 開発用C#に visual Studio が設定されている場合に、ビジュアルがルートノードになることを示します。 それ以外の場合は、**他の言語**の子ノードになります。

##### <a name="folder"></a>フォルダー
 このサブキーが存在する場合、ルートノードは、指定されたフォルダーの子ノードになります。 使用可能なフォルダーの一覧がキーの下に表示されます。

 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\NewProjectTemplates\PseudoFolders

 たとえば、データベースプロジェクトエントリには、擬似フォルダー内の他のプロジェクトの種類のエントリと一致するフォルダーキーがあります。 そのため、 **[プロジェクトの種類]** ツリーでは、**データベースプロジェクト**は**他の種類のプロジェクト**の子ノードになります。

#### <a name="project-type-child-nodes-and-vstdir-files"></a>プロジェクトの種類の子ノードと vstdir ファイル
 **プロジェクトの種類**ツリー内の子ノードの位置は、projecttemplates フォルダー内のフォルダーの階層に従います。 コンピューターテンプレート (**Visual studio がインストールされているテンプレート**) の場合、一般的な場所は "14.0" です。ユーザーテンプレート (**マイテンプレート**) の場合、一般的な場所は \My Documents \ Common7\IDE\ProjectTemplates\ です。Visual Studio 14.0 \ Templates\projecttemplates に配置 \\。 これら2つの場所からのフォルダー階層は、**プロジェクトの種類**ツリーを作成するためにマージされます。

 Visual Studio のC#開発者向け設定では、 **[プロジェクトの種類]** ツリーは次のようになります。

 ![プロジェクト タイプ](../../extensibility/internals/media/projecttypes.png "ProjectTypes")

 対応する ProjectTemplates フォルダーは次のようになります。

 ![プロジェクトテンプレート](../../extensibility/internals/media/projecttemplates.png "ProjectTemplates")

 **[新しいプロジェクト]** ダイアログボックスが開いたら、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] によって projecttemplates フォルダーがスキャンされ、 **[プロジェクトの種類]** ツリーの構造が再作成され、いくつかの変更が加えられます。

- **プロジェクトの種類**ツリーのルートノードは、アプリケーションテンプレートによって決定されます。

- ノード名はローカライズ可能で、特殊文字を含めることができます。

- 並べ替え順序は変更できます。

##### <a name="finding-the-root-node-for-a-project-type"></a>プロジェクトの種類のルートノードの検索
 Visual Studio が ProjectTemplates フォルダーをトラバースすると、すべての .zip ファイルが開き、.vstemplate ファイルが抽出されます。 .Vstemplate ファイルは、XML を使用してアプリケーションテンプレートを記述します。 詳細については、「[新しいプロジェクトの生成: 内部的にはパート 2](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)」を参照してください。

 @No__t_0ProjectType > タグによって、アプリケーションのプロジェクトの種類が決まります。 たとえば、\CSharp\SmartDevice\WindowsCE\1033\WindowsCE-EmptyProject.zip ファイルには、次のタグを持つ EmptyProject .vstemplate ファイルが含まれています。

```
<ProjectType>CSharp</ProjectType>
```

 @No__t_0ProjectType の > タグで、ProjectTemplates フォルダーのサブフォルダーではなく、**プロジェクトの種類**ツリーのアプリケーションのルートノードが決定されます。 この例では、Windows CE アプリケーションが**ビジュアルC#** ルートノードの下に表示されます。また、WindowsCE フォルダーを visual basic フォルダーに移動した場合でも、Windows CE アプリケーションは**ビジュアルC#** ルートの下に表示されます。ノード.

##### <a name="localizing-the-node-name"></a>ノード名のローカライズ
 Visual Studio が ProjectTemplates フォルダーをトラバースすると、検出されたすべての vstdir ファイルが調べられます。 Vstdir ファイルは、 **[新しいプロジェクト]** ダイアログボックスでのプロジェクトの種類の外観を制御する XML ファイルです。 Vstdir ファイルで、\<LocalizedName > タグを使用して、 **[プロジェクトの種類]** ノードに名前を付けます。

 たとえば、\CSharp\Database\TemplateIndex.vstdir ファイルには次のタグが含まれています。

```
<LocalizedName Package="{462b036f-7349-4835-9e21-bec60e989b9c}" ID="4598"/>
```

 これにより、ルートノードに名前を指定するローカライズされた文字列 (この場合は**データベース**) のサテライト DLL とリソース ID が決まります。 ローカライズされた名前には、 **.net**などのフォルダー名に使用できない特殊文字を含めることができます。

 @No__t_0LocalizedName > タグが存在しない場合、プロジェクトの種類にはフォルダー自体**SmartPhone2003**が付けられます。

##### <a name="finding-the-sort-order-for-a-project-type"></a>プロジェクトの種類の並べ替え順序の検索
 プロジェクトの種類の並べ替え順序を決定するために、vstdir ファイルは \<SortOrder > タグを使用します。

 たとえば、\CSharp\Windows\Windows.vstdir ファイルには次のタグが含まれています。

```
<SortOrder>5</SortOrder>
```

 \CSharp\Database\TemplateIndex.vstdir ファイルには、より大きな値を持つタグがあります。

```
<SortOrder>5000</SortOrder>
```

 @No__t_0SortOrder > タグの数値が小さいほど、ツリー内の位置が大きくなり、 **[プロジェクトの種類]** ツリーの **[データベース]** ノードよりも**Windows**ノードが大きくなります。

 プロジェクトの種類に \<SortOrder > タグが指定されていない場合は \<SortOrder > 仕様を含むプロジェクトの種類に従ってアルファベット順に表示されます。

 [マイドキュメント] フォルダー (**マイテンプレート**) には、vstdir ファイルがないことに注意してください。 ユーザーアプリケーションプロジェクトの種類の名前はローカライズされていないため、アルファベット順に表示されます。

#### <a name="a-quick-review"></a>クイックレビュー
 **[新しいプロジェクト]** ダイアログボックスを変更し、新しいユーザープロジェクトテンプレートを作成してみましょう。

1. 14.0 \ Common7\IDE\ProjectTemplates\CSharp フォルダーに MyProjectNode サブフォルダーを追加します。

2. 任意のテキストエディターを使用して、MyProjectNode フォルダーに MyProject ファイルを作成します。

3. 次の行を vstdir ファイルに追加します。

   ```
   <TemplateDir Version="1.0.0">
       <SortOrder>6</SortOrder>
   </TemplateDir>
   ```

4. Vstdir ファイルを保存して閉じます。

5. 任意のテキストエディターを使用して、MyProjectNode フォルダーに MyProject ファイルを作成します。

6. 次の行を .vstemplate ファイルに追加します。

   ```
   <VSTemplate Version="2.0.0" Type="Project" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
       <TemplateData>
           <ProjectType>CSharp</ProjectType>
       </TemplateData>
   </VSTemplate>
   ```

7. .Vstemplate ファイルを保存し、エディターを閉じます。

8. .Vstemplate ファイルを新しい圧縮された MyProjectNode\MyProject.zip フォルダーに送信します。

9. Visual Studio のコマンドウィンドウで、次のように入力します。

    ```
    devenv /installvstemplates
    ```

   Visual Studio を開きます。

10. **[新しいプロジェクト]** ダイアログボックスを開き、**ビジュアルC#** プロジェクトノードを展開します。

    ![MyProjectNode](../../extensibility/internals/media/myprojectnode.png "MyProjectNode")

    **Myprojectnode**は、Windows ノードの直下にC#あるビジュアルの子ノードとして表示されます。

## <a name="see-also"></a>関連項目
- [新しいプロジェクトの生成: 内部、パート 2](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)