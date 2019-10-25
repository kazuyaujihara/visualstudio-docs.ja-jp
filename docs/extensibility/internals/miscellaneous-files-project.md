---
title: その他のファイルプロジェクト |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- files, adding existing files to solutions
- Miscellaneous Files project
- Solution Items folder
- files, opening with Miscellaneous Files project
ms.assetid: 93a278a8-d4f4-400b-8945-4f1b0a2b5bac
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c46126507ef9bb293bd0fa6771f53343ad6206f7
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72726679"
---
# <a name="miscellaneous-files-project"></a>その他のファイル プロジェクト
ユーザーがプロジェクト項目を開くと、IDE はその他のファイルプロジェクトに、ソリューション内のプロジェクトのメンバーではないすべての項目を割り当てます。

 プロジェクトは、ユーザーがプロジェクト項目を開いたときにどのエディターが使用されるかを決定するうえで重要な役割を果たします。 プロジェクトは、プロジェクト固有のエディターまたは標準エディターを使用して、特定のファイルを開くように設計できます。

 プロジェクト固有のエディターでは、通常、ユーザーが特別な知識を持っているか、またはプロジェクトから特殊なインターフェイスを使用している必要があります。 詳細については、「[方法: プロジェクト固有のエディターを開く](../../extensibility/how-to-open-project-specific-editors.md)」を参照してください。

 標準エディターでは、任意のプロジェクトで特定の拡張機能の任意のファイルを開くことができます。 ユーザーは、プロジェクトのために [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] テキストエディターなどの一部の標準エディターをカスタマイズできますが、公開文字は保持されます。 標準エディターは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> メソッドを使用して作成されます。

 ソリューション内のプロジェクトがプロジェクト項目を開くことができない場合、IDE には、任意のファイルを開く "その他のファイル" プロジェクトと呼ばれる特別なプロジェクトが用意されています。

 この特別なプロジェクトでは、プロジェクトのコンテキストの外部でファイルを開くことができます。 @No__t_0 メソッドの処理中、その他のファイルプロジェクトは常に低優先度で応答します。 そのため、その他のファイルプロジェクトは常に、ファイルを開くことができる優先度の高いプロジェクトに対して生成されます。

 その他のファイルプロジェクトでは、ユーザーが **[新しいプロジェクト]** ダイアログボックスを使用して明示的に作成する必要はありません。 また、その他のファイルプロジェクトでは、プロジェクトメンバーの一覧は永続的には管理されません。 また、オプションの機能を使用して、各ユーザーが最近使用したファイルの一覧を記録します。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument>
- <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY>
- [方法: プロジェクト固有のエディターを開く](../../extensibility/how-to-open-project-specific-editors.md)
- [方法: 標準のエディターを開く](../../extensibility/how-to-open-standard-editors.md)
- [プロジェクト テンプレートとプロジェクト項目テンプレートの追加](../../extensibility/internals/adding-project-and-project-item-templates.md)
- [プロジェクト テンプレートとプロジェクト項目テンプレートの追加](../../extensibility/internals/adding-project-and-project-item-templates.md)