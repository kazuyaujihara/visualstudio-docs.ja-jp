---
title: 従来の言語サービスでのアウトライン |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- outlining
- language services [managed package framework], outlining
- outlining, supporting in language services [managed package framework]
ms.assetid: 7b5578b4-a20a-4b94-ad4c-98687ac133b9
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a6b2ba55a2e77a1f7261812a181ad780c2ef2b71
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72726176"
---
# <a name="outlining-in-a-legacy-language-service"></a>従来の言語サービスのアウトライン
アウトラインを使用すると、複雑なプログラムを概要やアウトラインに折りたたむことができます。 たとえば、でC#は、すべてのメソッドを1つの行に折りたたんで、メソッドのシグネチャのみを表示できます。 また、構造体とクラスを折りたたんで、構造体とクラスの名前のみを表示することもできます。 1つのメソッドの内部では、`foreach`、`if`、`while` などのステートメントの最初の行のみを表示することにより、複雑なロジックを折りたたんでフロー全体を表示することができます。

 従来の言語サービスは VSPackage の一部として実装されていますが、言語サービス機能を実装するための新しい方法として、MEF 拡張機能を使用することをお勧めします。 詳細については、「[チュートリアル: アウトライン](../../extensibility/walkthrough-outlining.md)」を参照してください。

> [!NOTE]
> できるだけ早く新しいエディター API の使用を開始することをお勧めします。 これにより、言語サービスのパフォーマンスが向上し、エディターの新機能を利用できるようになります。

## <a name="enabling-support-for-outlining"></a>アウトラインのサポートを有効にする
 自動アウトラインを有効にするには、`AutoOutlining` レジストリエントリを1に設定します。 自動アウトラインでは、隠し領域を識別してアウトライングリフを表示するために、ファイルの読み込み時または変更時にソース全体の解析が設定されます。 アウトラインは、ユーザーが手動で制御することもできます。

 @No__t_0 レジストリエントリの値は、<xref:Microsoft.VisualStudio.Package.LanguagePreferences> クラスの <xref:Microsoft.VisualStudio.Package.LanguagePreferences.AutoOutlining%2A> プロパティを使用して取得できます。 @No__t_0 レジストリエントリは、<xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 属性の名前付きパラメーターを使用して初期化できます (詳細について[は、「従来の言語サービスの登録](../../extensibility/internals/registering-a-legacy-language-service1.md)」を参照してください)。

## <a name="the-hidden-region"></a>非表示領域
 アウトラインを提供するには、言語サービスが非表示領域をサポートしている必要があります。 これらは、展開または折りたたむことができるテキストの範囲です。 非表示の領域は、標準の言語シンボル (中かっこなど) またはカスタムシンボルで区切ることができます。 たとえば、にC#は、非表示の領域を区切る `#region` / `#endregion` ペアがあります。

 非表示の領域は、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> インターフェイスとして公開されている非表示の領域マネージャーによって管理されます。

 アウトラインでは、非表示領域を <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenRegion> インターフェイスに使用し、非表示領域のスパン、現在の表示状態、およびスパンが折りたたまれているときに表示されるバナーを格納します。

 言語サービスパーサーは、<xref:Microsoft.VisualStudio.Package.AuthoringSink.AddHiddenRegion%2A> メソッドを使用して、非表示領域の既定の動作を持つ新しい非表示領域を追加します。一方、<xref:Microsoft.VisualStudio.Package.AuthoringSink.AddHiddenRegion%2A> メソッドでは、アウトラインの外観と動作をカスタマイズできます。 非表示の領域が非表示の領域セッションに与えられると、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] は言語サービスの非表示領域を管理します。

 非表示の領域セッションが破棄されるタイミングを判断する必要がある場合、非表示の領域を変更する場合、または特定の非表示領域が表示されるようにする必要がある場合は、<xref:Microsoft.VisualStudio.Package.Source> クラスからクラスを派生させ、適切なメソッド、<xref:Microsoft.VisualStudio.Package.Source.OnBeforeSessionEnd%2A>、<xref:Microsoft.VisualStudio.Package.Source.OnHiddenRegionChange%2A>、および <xref:Microsoft.VisualStudio.Package.Source.MakeBaseSpanVisible%2A> をそれぞれオーバーライドする必要があります。

### <a name="example"></a>例
 中かっこのすべてのペアに対して非表示の領域を作成する簡単な例を次に示します。 この言語では、中かっこの照合が提供され、照合する中かっこには少なくとも中かっこ ({と}) が含まれていることを前提としています。 この方法は、説明を目的としたものです。 完全な実装では、<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> のケースを完全に処理できます。 この例では、<xref:Microsoft.VisualStudio.Package.LanguagePreferences.AutoOutlining%2A> 設定を一時的に `true` に設定する方法も示しています。 別の方法として、言語パッケージの `ProvideLanguageServiceAttribute` 属性に `AutoOutlining` 名前付きパラメーターを指定することもできます。

 この例でC#は、コメント、文字列、およびリテラルの規則を前提としています。

```csharp
using Microsoft.VisualStudio.Package;
using Microsoft.VisualStudio.TextManager.Interop;

namespace MyLanguagePackage
{

    public class MyLanguageService : LanguageService
    {
        private LanguagePreferences m_preferences;

        public override LanguagePreferences  GetLanguagePreferences()
        {
            if (m_preferences == null)
            {
                m_preferences = new LanguagePreferences(this.Site,
                                                        typeof(MyLanguageService).GUID,
                                                        Name);
                m_preferences.Init();
                // Temporarily enabled auto-outlining
                m_preferences.AutoOutlining = true;
            }
            return m_preferences;
        }

        public override AuthoringScope  ParseSource(ParseRequest req)
        {
            Source source = (Source) this.GetSource(req.FileName);
            switch (req.Reason)
            {
               case ParseReason.HighlightBraces:
               case ParseReason.MatchBraces:
               case ParseReason.MemberSelectAndHighlightBraces:
                  if (source.Braces != null)
                  {
                      foreach (TextSpan[] brace in source.Braces)
                      {
                         if (brace.Length == 2)
                         {
                             if (req.Sink.HiddenRegions == true
                                   && source.GetText(brace[0]).Equals("{")
                                   && source.GetText(brace[1]).Equals("}"))
                             {
                                //construct a TextSpan of everything between the braces
                                TextSpan hideSpan = new TextSpan();
                                hideSpan.iStartIndex = brace[0].iStartIndex;
                                hideSpan.iStartLine = brace[0].iStartLine;
                                hideSpan.iEndIndex = brace[1].iEndIndex;
                                hideSpan.iEndLine = brace[1].iEndLine;
                                req.Sink.ProcessHiddenRegions = true;
                                req.Sink.AddHiddenRegion(hideSpan);
                             }
                             req.Sink.MatchPair(brace[0], brace[1], 1);
                         }
                         else if (brace.Length >= 3)
                             req.Sink.MatchTriple(brace[0], brace[1], brace[2], 1);
                  }
        }
                   break;
               default:
                   break;
      }
            // Must always return a valid AuthoringScope object.
            return new MyAuthoringScope();
        }
    }
}
```

## <a name="see-also"></a>関連項目
- [従来の言語サービスの特徴](../../extensibility/internals/legacy-language-service-features1.md)
- [従来の言語サービスの登録](../../extensibility/internals/registering-a-legacy-language-service1.md)