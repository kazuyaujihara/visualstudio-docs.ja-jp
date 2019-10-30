---
title: '方法: マネージコード拡張機能をドキュメントにアタッチする'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- managed code extensions [Office development in Visual Studio], attaching
- documents [Office development in Visual Studio], managed code extensions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8fb212f9c5441d697cfa92feee7dc18fab9270d2
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72985974"
---
# <a name="how-to-attach-managed-code-extensions-to-documents"></a>方法: マネージコード拡張機能をドキュメントにアタッチする
  カスタマイズアセンブリは、既存の Microsoft Office Word 文書または Microsoft Office Excel ブックに添付できます。 ドキュメントまたはブックは、Visual Studio の Microsoft Office プロジェクトおよび開発ツールでサポートされている任意のファイル形式にすることができます。 詳細については、「[ドキュメントレベルのカスタマイズのアーキテクチャ](../vsto/architecture-of-document-level-customizations.md)」を参照してください。

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 カスタマイズを Word または Excel ドキュメントに添付するには、<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> クラスの <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> メソッドを使用します。 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> クラスは Microsoft Office がインストールされていないコンピューターで実行されるように設計されているため、この方法は Microsoft Office 開発に直接関係のないソリューション (コンソールや Windows フォームアプリケーションなど) で使用できます。

> [!NOTE]
> 指定したドキュメントに含まれていないコントロールがコードで想定されている場合、カスタマイズは読み込みに失敗します。

### <a name="to-attach-managed-code-extensions-to-a-document"></a>マネージコード拡張機能をドキュメントにアタッチするには

1. コンソールアプリケーションや Windows フォームプロジェクトなど、Microsoft Office を必要としないプロジェクトでは、VisualStudio への参照を追加してください。 *ServerDocument*と*VisualStudio*アセンブリを実行してください。

2. 次の**Imports**ステートメントまたは**using**ステートメントをコードファイルの先頭に追加します。

     [!code-csharp[Trin_VstcoreDeployment#4](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#4)]
     [!code-vb[Trin_VstcoreDeployment#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#4)]

3. 静的 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> メソッドを呼び出します。

     次のコード例では、<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> オーバーロードを使用します。 このオーバーロードは、ドキュメントの完全パスと、ドキュメントに添付するカスタマイズの配置マニフェストの場所を指定する <xref:System.Uri> を受け取ります。 この例では、 **worddocument1.docx**という名前の Word 文書がデスクトップ上にあり、配置マニフェストが、デスクトップ上にもある**Publish**という名前のフォルダーに配置されていることを前提としています。

     [!code-csharp[Trin_VstcoreDeployment#3](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#3)]
     [!code-vb[Trin_VstcoreDeployment#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#3)]

4. プロジェクトをビルドし、カスタマイズをアタッチするコンピューターでアプリケーションを実行します。 コンピューターには、Visual Studio 2010 Tools for Office Runtime がインストールされている必要があります。

## <a name="see-also"></a>関連項目
- [ServerDocument クラスを使用してサーバー上のドキュメントを管理する](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)
- [方法: マネージコード拡張をドキュメントから削除する](../vsto/how-to-remove-managed-code-extensions-from-documents.md)
- [Office ソリューションのアプリケーションマニフェストと配置マニフェスト](../vsto/application-and-deployment-manifests-in-office-solutions.md)
