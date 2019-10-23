---
title: 登録と選択 (ソース管理 VSPackage) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- registration, source control packages
- source control packages, registration
ms.assetid: 7d21fe48-489a-4f55-acb5-73da64c4e155
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3d6ca60c74ae9956f38418ea6048bb0c8050be2c
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724506"
---
# <a name="registration-and-selection-source-control-vspackage"></a>登録と選択 (ソース管理 VSPackage)
@No__t_0 に公開するには、ソース管理 VSPackage が登録されている必要があります。 複数のソース管理 VSPackage が登録されている場合、ユーザーは適切なタイミングで読み込む VSPackage を選択できます。 Vspackage とその登録方法の詳細については、「 [vspackage](../../extensibility/internals/vspackages.md) 」を参照してください。

## <a name="registering-a-source-control-package"></a>ソース管理パッケージの登録
 ソース管理パッケージは登録されているので、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 環境で検索して、サポートされている機能のクエリを実行できます。 これは、機能またはコマンドが必要な場合、または明示的に要求された場合にのみ、パッケージのインスタンスが作成される遅延読み込みスキームに従っています。

 Vspackage はバージョン固有のレジストリキー HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio \\ に情報を格納し*ます。* ここで、 *x*はメジャーバージョン番号、 *Y*はマイナーバージョン番号です。 この方法では、複数のバージョンの [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] のサイドバイサイドインストールをサポートできます。

 @No__t_0 のユーザーインターフェイス (UI) は、インストールされている複数のソース管理プラグイン (ソース管理アダプターパッケージ経由) とソース管理 Vspackage の間での選択をサポートしています。 アクティブなソース管理プラグインまたは VSPackage は一度に1つしか存在できません。 ただし、以下で説明するように、IDE では、ソリューションベースの自動パッケージスワップメカニズムを使用して、ソース管理プラグインと Vspackage を切り替えることができます。 この選択メカニズムを有効にするために、ソース管理 VSPackage の一部にはいくつかの要件があります。

### <a name="registry-entries"></a>レジストリ エントリ
 ソース管理パッケージには、次の3つのプライベート Guid が必要です。

- パッケージ GUID: これは、ソース管理の実装 (このセクションでは ID_Package と呼ばれます) を含むパッケージの主要な GUID です。

- ソース管理 GUID: これは、Visual Studio ソース管理スタブに登録するために使用されるソース管理 VSPackage の GUID であり、コマンド UI コンテキスト GUID としても使用されます。 ソース管理サービス GUID は、ソース管理 GUID の下に登録されます。 この例では、ソース管理の GUID は ID_SccProvider と呼ばれています。

- ソース管理サービス GUID: これは、Visual Studio によって使用されるプライベートサービス GUID です (このセクションでは SID_SccPkgService と呼ばれます)。 さらに、ソース管理パッケージでは、Vspackage、ツールウィンドウなどの他の Guid を定義する必要があります。

  次のレジストリエントリは、ソース管理 VSPackage によって作成される必要があります。

| キー名 | Entries |
| - | - |
| `HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\` | (既定値) = rg_sz: {ID_SccProvider} |
| `HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\             {ID_SccProvider}\` | (既定値) = rg_sz: パッケージ > の \<Friendly 名<br /><br /> サービス = rg_sz: {SID_SccPkgService} |
| `HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\             {ID_SccProvider}\               Name\` | (既定値) = rg_sz: # \<Resource ローカライズされた名前の ID ><br /><br /> Package = rg_sz: {ID_Package} |
| `HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SolutionPersistence\             <PackageName>\`<br /><br /> (キー名、`SourceCodeControl` は [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] で既に使用されており、\<PackageName > の選択肢としては使用できないことに注意してください)。 | (既定値) = rg_sz: {ID_Package} |

## <a name="selecting-a-source-control-package"></a>ソース管理パッケージの選択
 いくつかのソース管理プラグイン API ベースのプラグインとソース管理 Vspackage が同時に登録されている可能性があります。 ソース管理プラグインまたは VSPackage を選択するプロセスでは、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] がプラグインまたは VSPackage を適切なタイミングで読み込む必要があります。また、不要なコンポーネントの読み込みが必要になるまで遅延させることができます。 さらに [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] では、メニュー項目、ダイアログボックス、ツールバーなど、他の非アクティブな Vspackage からすべての UI を削除し、アクティブな VSPackage の UI を表示する必要があります。

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] は、次のいずれかの操作が実行されたときに、ソース管理 VSPackage を読み込みます。

- ソリューションが開かれています (ソリューションがソース管理下にある場合)。

   ソース管理下にあるソリューションまたはプロジェクトを開くと、IDE によって、そのソリューションに対して指定されたソース管理 VSPackage が読み込まれます。

- ソース管理 VSPackage のメニューコマンドが実行されます。

  ソース管理 VSPackage は、実際に使用される場合にのみ必要なコンポーネント (遅延読み込みとも呼ばれます) を読み込む必要があります。

### <a name="automatic-solution-based-vspackage-swapping"></a>ソリューションベースの VSPackage の自動スワップ
 ソース**管理カテゴリの下にある**[[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]**オプション**] ダイアログボックスを使用して、ソース管理 vspackage を手動でスワップすることができます。 ソリューションベースの自動パッケージスワップは、特定のソリューションに対して指定されているソース管理パッケージが、そのソリューションを開いたときに自動的にアクティブに設定されることを意味します。 すべてのソース管理パッケージは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetActive%2A> と <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetInactive%2A> を実装する必要があります。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] は、(ソース管理プラグイン API を実装する) ソース管理プラグインとソース管理 Vspackage の両方の切り替えを処理します。

 ソース管理アダプターパッケージは、任意のソース管理プラグイン API ベースのプラグインに切り替えるために使用されます。 中間ソース管理アダプターパッケージに切り替えて、アクティブまたは非アクティブに設定する必要があるソース管理プラグインを特定するプロセスは、ユーザーに対して透過的です。 アダプターパッケージは、任意のソース管理プラグインがアクティブになっている場合、常にアクティブです。 プラグイン DLL を単に読み込んでアンロードするために、2つのソース管理プラグインを切り替える。 ただし、ソース管理 VSPackage に切り替えるには、IDE を操作して適切な VSPackage を読み込む必要があります。

 ソース管理 VSPackage は、ソリューションを開いたときに、VSPackage のレジストリキーがソリューションファイル内にある場合に呼び出されます。 ソリューションが開かれると、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] によってレジストリ値が検索され、適切なソース管理 VSPackage が読み込まれます。 すべてのソース管理 Vspackage には、上記で説明したレジストリエントリが必要です。 ソース管理下にあるソリューションは、特定のソース管理 VSPackage に関連付けられているとマークされています。 ソース管理 Vspackage は、ソリューションベースの VSPackage の自動スワップを有効にするために <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> を実装する必要があります。

### <a name="visual-studio-ui-for-package-selection-and-switching"></a>パッケージの選択と切り替えを行うための Visual Studio UI
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] では、 **[ソース]** 管理 カテゴリの **[オプション]** ダイアログボックスで、ソース管理 VSPackage とプラグインの選択のための UI を提供します。 これにより、ユーザーはアクティブなソース管理プラグインまたは VSPackage を選択できます。 ドロップダウンリストには次のものが含まれます。

- インストールされているすべてのソース管理パッケージ

- インストールされているすべてのソース管理プラグイン

- "None" オプション。ソースコード管理を無効にします。

  アクティブなソース管理の選択肢の UI だけが表示されます。 VSPackage を選択すると、前の VSPackage の UI が非表示になり、新しい ui の UI が表示されます。 アクティブな VSPackage は、ユーザーごとに選択されます。 複数の [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] のコピーを同時に開くと、それぞれのユーザーが異なる active VSPackage を使用する可能性があります。 複数のユーザーが同じコンピューターにログオンしている場合は、各ユーザーがそれぞれ異なる active VSPackage を持つ [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] を開くことができます。 @No__t_0 の複数のインスタンスがユーザーによって閉じられると、最後に開いたソリューションに対してアクティブだったソース管理 VSPackage が既定のソース管理 VSPackage になり、再起動時にアクティブに設定されます。

  以前のバージョンの [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] とは異なり、IDE の再起動は、ソース管理 Vspackage を切り替える唯一の方法ではなくなりました。 VSPackage の選択は自動的に行うことができます。 パッケージを切り替えるには、管理者またはパワーユーザーではなく、Windows ユーザー特権が必要です。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>
- [機能](../../extensibility/internals/source-control-vspackage-features.md)
- [ソース管理プラグインの作成](../../extensibility/internals/creating-a-source-control-plug-in.md)
- [VSPackage](../../extensibility/internals/vspackages.md)