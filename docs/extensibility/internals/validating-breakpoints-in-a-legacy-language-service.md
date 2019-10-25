---
title: 従来の言語サービスでブレークポイントを検証する |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- breakpoint validation
- language services [managed package framework], breakpoint validation
ms.assetid: a7e873cd-dfe1-474f-bda5-fd7532774b15
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e7c46473610c96779d0c54e06e82cf884216b13b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722019"
---
# <a name="validating-breakpoints-in-a-legacy-language-service"></a>従来の言語サービスでのブレークポイントの検証
ブレークポイントは、デバッガーで実行されている特定の時点でプログラムの実行を停止する必要があることを示します。 ブレークポイントの有効な場所を構成する内容についての情報がエディターに含まれていないため、ソースファイル内の任意の行にブレークポイントを設定できます。 デバッガーを起動すると、マークされているすべてのブレークポイント (保留中のブレークポイントと呼ばれます) が、実行中のプログラム内の適切な場所にバインドされます。 同時に、有効なコードの場所をマークするようにブレークポイントが検証されます。 たとえば、コメントのブレークポイントは無効です。これは、ソースコード内のその場所にコードがないためです。 デバッガーは無効なブレークポイントを無効にします。

 言語サービスは表示されているソースコードを認識しているため、デバッガーを起動する前にブレークポイントを検証できます。 @No__t_0 メソッドをオーバーライドして、ブレークポイントの有効な位置を指定するスパンを返すことができます。 デバッガーが起動されてもブレークポイントの位置は検証されますが、ユーザーにはデバッガーが読み込まれるのを待たずに無効なブレークポイントが通知されます。

## <a name="implementing-support-for-validating-breakpoints"></a>ブレークポイントの検証のサポートの実装

- @No__t_0 メソッドには、ブレークポイントの位置が指定されます。 実装では、位置が有効であるかどうかを判断し、ブレークポイントの位置に関連付けられているコードを識別するテキスト範囲を返すことによってこれを示す必要があります。

- 場所が有効である場合は <xref:Microsoft.VisualStudio.VSConstants.S_OK> を返し、有効でない場合は <xref:Microsoft.VisualStudio.VSConstants.S_FALSE> を返します。

- ブレークポイントが有効な場合、テキスト範囲はブレークポイントと共に強調表示されます。

- ブレークポイントが無効である場合は、エラーメッセージがステータスバーに表示されます。

### <a name="example"></a>例
 この例では、<xref:Microsoft.VisualStudio.Package.LanguageService.ValidateBreakpointLocation%2A> メソッドの実装を示します。このメソッドは、指定された位置にあるコード (存在する場合) を取得するためにパーサーを呼び出します。

 この例では、テキスト範囲を検証する <xref:Microsoft.VisualStudio.Package.AuthoringSink> クラスに `GetCodeSpan` メソッドを追加し、それが有効なブレークポイントの位置である場合は `true` を返すことを前提としています。

```csharp
using Microsoft VisualStudio;
using Microsoft.VisualStudio.Package;
using Microsoft.VisualStudio.TextManager.Interop;

namespace TestLanguagePackage
{
    class TestLanguageService : LanguageService
    {
        public override int ValidateBreakpointLocation(IVsTextBuffer buffer,
                                                       int line,
                                                       int col,
                                                       TextSpan[] pCodeSpan)
        {
            int retval = VSConstants.S_FALSE;
            if (pCodeSpan != null)
            {
                // Initialize span to current line by default.
                pCodeSpan[0].iStartLine = line;
                pCodeSpan[0].iStartIndex = col;
                pCodeSpan[0].iEndLine = line;
                pCodeSpan[0].iEndIndex = col;
            }

            if (buffer != null)
            {
                IVsTextLines textLines = buffer as IVsTextLines;
                if (textLines != null)
                {
                    Source src = this.GetSource(textLines);
                    if (src != null)
                    {
                        TokenInfo tokenInfo = new TokenInfo();
                        string text = src.GetText();
                        ParseRequest req = CreateParseRequest(src,
                                                              line,
                                                              col,
                                                              tokenInfo,
                                                              text,
                                                              src.GetFilePath(),
                                                              ParseReason.CodeSpan,
                                                              null);
                        req.Scope = this.ParseSource(req);
                        TestAuthoringSink sink = req.Sink as TestAuthoringSink;

                        TextSpan span = new TextSpan();
                        if (sink.GetCodeSpan(out span))
                        {
                            pCodeSpan[0] = span;
                            retval = VSConstants.S_OK;
                        }
                    }
                }
            }
            return retval;
        }
    }
}
```

## <a name="see-also"></a>関連項目
- [従来の言語サービスの特徴](../../extensibility/internals/legacy-language-service-features1.md)