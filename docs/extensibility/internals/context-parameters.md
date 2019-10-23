---
title: コンテキストパラメーター |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- wizards, context parameters
- context parameters
ms.assetid: 1a062dcb-8a8f-40dd-bea9-3d10f9448966
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9ea38b79be362f78fcc34161a480597fb0ecce40
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72727556"
---
# <a name="context-parameters"></a>コンテキスト パラメーター
@No__t_0 統合開発環境 (IDE) では、 **[新しいプロジェクト]** 、 **[新しい項目の追加]** 、または **[サブプロジェクトの追加]** ダイアログボックスにウィザードを追加できます。 追加したウィザードは、 **[ファイル]** メニューまたは**ソリューションエクスプローラー**でプロジェクトを右クリックして表示できます。 IDE は、ウィザードの実装にコンテキストパラメーターを渡します。 IDE がウィザードを呼び出すと、コンテキストパラメーターによってプロジェクトの状態が定義されます。

 IDE は、IDE の呼び出しの <xref:Microsoft.VisualStudio.Shell.Interop.VSADDITEMOPERATION> フラグをプロジェクトの <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.AddItem%2A> メソッドに設定することによって、ウィザードを起動します。 設定すると、プロジェクトは、登録されているウィザードの名前または GUID、および IDE によって渡されるその他のコンテキストパラメーターを使用して、`IVsExtensibility::RunWizardFile` メソッドを実行する必要があります。

## <a name="context-parameters-for-new-project"></a>新しいプロジェクトのコンテキストパラメーター

| パラメーター | 説明 |
|-------------------------| - |
| `WizardType` | 登録されたウィザードの種類 (<xref:EnvDTE.Constants.vsWizardNewProject>)、またはウィザードの種類を示す GUID。 @No__t_0 の実装では、ウィザードの GUID は {0F90E1D0-4999-11D1-B6D1-00A0C90F2744} です。 |
| `ProjectName` | 一意の [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] プロジェクト名を表す文字列。 |
| `LocalDirectory` | 作業プロジェクトファイルのローカルの場所。 |
| `InstallationDirectory` | @No__t_0 のディレクトリパスがインストールされています。 |
| `FExclusive` | プロジェクトが開いているソリューションを閉じる必要があることを示すブール型のフラグ。 |
| `SolutionName` | ディレクトリ部分または *.sln*拡張子のないソリューションファイルの名前。 *.Suo*ファイル名も `SolutionName` を使用して作成されます。 この引数が空の文字列でない場合、ウィザードは <xref:EnvDTE._Solution.AddFromTemplate%2A> でプロジェクトを追加する前に、<xref:EnvDTE._Solution.Create%2A> を使用します。 この名前が空の文字列の場合は、<xref:EnvDTE._Solution.Create%2A> を呼び出さずに <xref:EnvDTE._Solution.AddFromTemplate%2A> を使用します。 |
| `Silent` | ウィザードを **[完了**] をクリックしたときにサイレントモードで実行するかどうかを示すブール値 (`TRUE`)。 |

## <a name="context-parameters-for-add-new-item"></a>[新しい項目の追加] のコンテキストパラメーター

| パラメーター | 説明 |
|-------------------------| - |
| `WizardType` | 登録されたウィザードの種類 (<xref:EnvDTE.Constants.vsWizardAddItem>)、またはウィザードの種類を示す GUID。 @No__t_0 の実装では、ウィザードの GUID は {0F90E1D1-4999-11D1-B6D1-00A0C90F2744} です。 |
| `ProjectName` | 一意の [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] プロジェクト名を表す文字列。 |
| `ProjectItems` | 作業中のプロジェクトファイルが格納されているローカルの場所。 |
| `ItemName` | 追加する項目の名前。 この名前は、 **[項目の追加]** ダイアログボックスでユーザーが入力する既定のファイル名またはファイル名のいずれかになります。 この名前は、 *.vsdir*ファイルに設定されているフラグに基づいています。 名前には null 値を指定できます。 |
| `InstallationDirectory` | @No__t_0 のディレクトリパスがインストールされています。 |
| `Silent` | ウィザードを **[完了**] をクリックしたときにサイレントモードで実行するかどうかを示すブール値 (`TRUE`)。 |

## <a name="context-parameters-for-add-sub-project"></a>サブプロジェクトの追加のコンテキストパラメーター

| パラメーター | 説明 |
|-------------------------| - |
| `WizardType` | 登録されたウィザードの種類 (<xref:EnvDTE.Constants.vsWizardAddSubProject>)、またはウィザードの種類を示す GUID。 @No__t_0 の実装では、ウィザードの GUID は {0F90E1D2-4999-11D1-B6D1-00A0C90F2744} です。 |
| `ProjectName` | 一意の [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] プロジェクト名を表す文字列。 |
| `ProjectItems` | ウィザードが動作する `ProjectItems` コレクションへのポインター。 このポインターは、プロジェクト階層の選択に基づいてウィザードに渡されます。 ユーザーは、通常、項目を配置するフォルダーを選択してから、プロジェクトの **[項目の追加]** ダイアログボックスを呼び出します。 |
| `LocalDirectory` | 作業プロジェクトファイルのローカルの場所。 |
| `ItemName` | 追加する項目の名前。 この名前は、 **[項目の追加]** ダイアログボックスでユーザーが入力する既定のファイル名またはファイル名のいずれかになります。 この名前は、 *.vsdir*ファイルに設定されているフラグに基づいています。 名前には null 値を指定できます。 |
| `InstallationDirectory` | @No__t_0 インストールのディレクトリパス。 |
| `Silent` | ウィザードを **[完了**] をクリックしたときにサイレントモードで実行するかどうかを示すブール値 (`TRUE`)。 |

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2>
- [カスタムパラメーター](../../extensibility/internals/custom-parameters.md)
- [ウィザード](../../extensibility/internals/wizards.md)
- [ウィザード (.vsz) ファイル](../../extensibility/internals/wizard-dot-vsz-file.md)
- [ウィザードを起動するためのコンテキストパラメーター](https://msdn.microsoft.com/Library/051a10f4-9e45-4604-b344-123044f33a24)