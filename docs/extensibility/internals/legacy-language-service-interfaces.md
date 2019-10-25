---
title: 従来の言語サービスインターフェイス |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IVsLanguageInfo interface
- language services, objects
ms.assetid: 03b2d507-f463-417e-bc22-bdac68eeda52
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 065ef972709ca78b516a9acc5f4a737d2963e4b7
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72726853"
---
# <a name="legacy-language-service-interfaces"></a>従来の言語サービスのインターフェイス
特定のプログラミング言語では、言語サービスのインスタンスは一度に1つしか存在できません。 ただし、1つの言語サービスで複数のエディターを使用できます。

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] では、言語サービスが特定のエディターに関連付けられません。 そのため、言語サービス操作を要求する場合は、適切なエディターをパラメーターとして指定する必要があります。

## <a name="common-interfaces-associated-with-language-services"></a>言語サービスに関連付けられている共通のインターフェイス
 エディターは、適切な VSPackage で <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> を呼び出すことによって、言語サービスを取得します。 この呼び出しで渡されるサービス ID (SID) は、要求されている言語サービスを識別します。

 コア言語サービスインターフェイスは、任意の数の独立したクラスに実装できます。 ただし、一般的な方法は、1つのクラスに次のインターフェイスを実装することです。

- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>

- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems>

- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo>

- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageBlock> (省略可能)

  @No__t_0 インターフェイスは、すべての言語サービスに実装する必要があります。 言語のローカライズされた名前、言語サービスに関連付けられているファイル名拡張子、色計を取得する方法など、言語サービスに関する情報を提供します。

## <a name="additional-language-service-interfaces"></a>追加の言語サービスインターフェイス
 その他のインターフェイスは、言語サービスで提供できます。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] は、テキストバッファーのインスタンスごとに、これらのインターフェイスの個別のインスタンスを要求します。 そのため、これらの各インターフェイスを独自のオブジェクトに実装する必要があります。 次の表は、テキストバッファーインスタンスごとに1つのインスタンスを必要とするインターフェイスを示しています。

|Interface|説明|
|---------------|-----------------|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>|ドロップダウンバーなどのコードウィンドウの表示要素を管理します。 このインターフェイスを取得するには、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> メソッドを使用します。 コードウィンドウごとに <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> が1つあります。|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>|色づけ言語のキーワードと区切り記号。 このインターフェイスを取得するには、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> メソッドを使用します。 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> は、描画時に呼び出されます。 @No__t_0 内で計算集中型の作業を避けるか、パフォーマンスが低下する可能性があります。|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>|IntelliSense パラメーターのヒントを提供します。 言語サービスが、開いているかっこなど、メソッドのデータを表示する必要があることを示す文字を認識すると、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow.SetMethodData%2A> メソッドを呼び出して、言語サービスがパラメーターヒントを表示する準備ができていることをテキストビューに通知します。 次に、テキストビューは、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> インターフェイスのメソッドを使用して言語サービスにコールバックし、ツールヒントを表示するために必要な情報を取得します。|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet>|IntelliSense ステートメント入力候補を提供します。 言語サービスがコンプリートリストを表示する準備ができたら、テキストビューで <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> メソッドを呼び出します。 次に、テキストビューは、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> オブジェクトのメソッドを使用して、言語サービスにコールバックします。|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter>|コマンドハンドラーを使用してテキストビューを変更できるようにします。 @No__t_0 インターフェイスを実装するクラスは、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> インターフェイスも実装する必要があります。 テキストビューでは、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> メソッドに渡される <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> オブジェクトを照会することによって、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> オブジェクトを取得します。 ビューごとに1つの <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> オブジェクトが存在する必要があります。|
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|ユーザーがコードウィンドウに入力するコマンドをインターセプトします。 @No__t_0 の実装からの出力を監視して、カスタムの完了情報とビューの変更を提供する<br /><br /> @No__t_0 オブジェクトをテキストビューに渡すには、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> を呼び出します。|

## <a name="see-also"></a>関連項目
- [従来の言語サービスの開発](../../extensibility/internals/developing-a-legacy-language-service.md)
- [チェック リスト: 従来の言語サービスの作成](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)