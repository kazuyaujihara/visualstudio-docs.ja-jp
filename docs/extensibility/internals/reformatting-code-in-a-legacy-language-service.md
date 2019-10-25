---
title: 従来の言語サービスでコードを再フォーマットする |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- reformatting code, supporting in language services [managed package framework]
- language services [managed package framework], reformatting code
ms.assetid: 08bb3375-8fef-4f4e-9efa-0d7333bab0eb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ae48e1b97b5c9194cf3081687ab31ea9f857e6c9
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724752"
---
# <a name="reformatting-code-in-a-legacy-language-service"></a>従来の言語サービスの再フォーマット コード

@No__t_0 ソースコードは、インデントと空白文字の使用を正規化することによって、再フォーマットできます。 これには、各行の先頭にスペースやタブを挿入したり、行の間に新しい行を追加したり、スペースを含むタブまたはタブをスペースに置き換えたりすることができます。

> [!NOTE]
> 改行文字を挿入または削除すると、ブレークポイントやブックマークなどのマーカーに影響を与える可能性がありますが、マーカーには影響しません。

ユーザーは、 **[編集]** メニューの **[詳細設定]** メニューから **[選択内容の書式設定]** または **[ドキュメントの書式]** 設定 を選択して、再フォーマット操作を開始できます。 また、コードスニペットまたは特定の文字が挿入されたときに、再フォーマット操作をトリガーすることもできます。 たとえば、で右中C#かっこを入力すると、一致する左中かっこと終わりかっこの間のすべてが自動的に適切なレベルにインデントされます。

@No__t_0 が [**ドキュメント**の**形式**] コマンドを言語サービスに送信すると、<xref:Microsoft.VisualStudio.Package.ViewFilter> クラスは <xref:Microsoft.VisualStudio.Package.Source> クラスの <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> メソッドを呼び出します。 書式設定をサポートするには、<xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> メソッドをオーバーライドし、独自の書式設定コードを指定する必要があります。

## <a name="enabling-support-for-reformatting"></a>再フォーマットのサポートの有効化

書式設定をサポートするには、VSPackage を登録するときに <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> の `EnableFormatSelection` パラメーターを `true` に設定する必要があります。 これにより、<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableFormatSelection%2A> プロパティが `true` に設定されます。 @No__t_0 メソッドは、このプロパティの値を返します。 True を返した場合、<xref:Microsoft.VisualStudio.Package.ViewFilter> クラスは <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> を呼び出します。

## <a name="implementing-reformatting"></a>再フォーマットの実装

再フォーマットを実装するには、<xref:Microsoft.VisualStudio.Package.Source> クラスからクラスを派生させ、<xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> メソッドをオーバーライドする必要があります。 @No__t_0 オブジェクトは、書式設定するスパンを記述し、<xref:Microsoft.VisualStudio.Package.EditArray> オブジェクトはスパンに加えられた編集を保持します。 このスパンはドキュメント全体であることに注意してください。 ただし、スパンに対して複数の変更が行われる可能性があるため、すべての変更を1回の操作で元に戻す必要があります。 これを行うには、<xref:Microsoft.VisualStudio.Package.CompoundAction> オブジェクトにすべての変更をラップします (このトピックの「CompoundAction クラスの使用」セクションを参照してください)。

### <a name="example"></a>例

次の例では、コンマの後にタブが続く場合、または行の末尾にある場合を除き、すべてのコンマの後にスペースが1つあることを保証します。 行の最後のコンマの後の末尾のスペースが削除されます。 @No__t_0 メソッドからのこのメソッドの呼び出し方法については、このトピックの「CompoundAction クラスの使用」セクションを参照してください。

```csharp
using Microsoft.VisualStudio.Package;
using Microsoft VisualStudio.TextManager.Interop;

namespace MyLanguagePackage
{
    class MySource : Source
    {
        private void DoFormatting(EditArray mgr, TextSpan span)
        {
            // Make sure there is one space after every comma unless followed
            // by a tab or comma is at end of line.
            IVsTextLines pBuffer = GetTextLines();
            if (pBuffer != null)
            {
                int    startIndex = span.iStartIndex;
                int    endIndex   = 0;
                string line       = "";
                // Loop over all lines in span
                for (int i = span.iStartLine; i <= span.iEndLine; i++)
                {
                    if (i < span.iEndLine)
                    {
                        pBuffer.GetLengthOfLine(i, out endIndex);
                    }
                    else
                    {
                        endIndex = span.iEndIndex;
                    }
                    pBuffer.GetLineText(i, startIndex, i, endIndex, out line);

                    if (line.Length > 0)
                    {
                        int index = 0;
                        // Loop over all commas in line
                        while ((index = line.IndexOf(',', index)) != -1)
                        {
                            int spaceIndex = index + 1;
                            // Determine how many spaces after comma
                            while (spaceIndex < line.Length && line[spaceIndex] == ' ')
                            {
                                ++spaceIndex;
                            }

                            int      spaceCount      = spaceIndex - (index + 1);
                            string   replacementText = " ";
                            bool     fDoEdit         = true;
                            TextSpan editTextSpan    = new TextSpan();

                            editTextSpan.iStartLine  = i;
                            editTextSpan.iEndLine    = i;
                            editTextSpan.iStartIndex = index + 1;

                            if (spaceIndex == line.Length)
                            {
                                if (spaceCount > 0)
                                {
                                    // Delete spaces after a comma at end of line
                                    editTextSpan.iEndIndex = spaceIndex;
                                    replacementText = "";
                                }
                                else
                                {
                                    // Otherwise, do not add spaces if comma is
                                    // at end of line.
                                    fDoEdit = false;
                                }
                            }
                            else if (spaceCount == 0)
                            {
                                if (spaceIndex < line.Length && line[spaceIndex] == '\t')
                                {
                                    // Do not insert space if a tab follows
                                    // a comma.
                                    fDoEdit = false;
                                }
                                else
                                {
                                    // No space after comma so add a space.
                                    editTextSpan.iEndIndex = index + 1;
                                }
                            }
                            else if (spaceCount > 1)
                            {
                                // More than one space after comma, replace
                                // with a single space.
                                editTextSpan.iEndIndex = spaceIndex;
                            }
                            else
                            {
                                // Single space after a comma and not at end
                                // of the line, leave it alone.
                                fDoEdit = false;
                            }
                            if (fDoEdit)
                            {
                                // Add edit operation
                                mgr.Add(new EditSpan(editTextSpan, replacementText));
                            }
                            index = spaceIndex;
                        }
                    }
                    startIndex = 0; // All subsequent lines start at 0
                }
                // Apply all edits
                mgr.ApplyEdits();
            }
        }
    }
}
```

## <a name="using-the-compoundaction-class"></a>CompoundAction クラスの使用

コードのセクションで実行されるすべての再フォーマットは、1回の操作で元に戻す必要があります。 これは <xref:Microsoft.VisualStudio.Package.CompoundAction> クラスを使用して実現できます。 このクラスは、テキストバッファーに対する一連の編集操作を1つの編集操作にラップします。

### <a name="example"></a>例

@No__t_0 クラスを使用する方法の例を次に示します。 @No__t_0 方法の例については、このトピックの「書式設定のサポートの実装」セクションの例を参照してください。

```csharp
using Microsoft.VisualStudio.Package;
using Microsoft VisualStudio.TextManager.Interop;

namespace MyLanguagePackage
{
    class MySource : Source
    {
        public override void ReformatSpan(EditArray mgr, TextSpan span)
        {
            string description = "Reformat code";
            CompoundAction ca = new CompoundAction(this, description);
            using (ca)
            {
                ca.FlushEditActions();      // Flush any pending edits
                DoFormatting(mgr, span);    // Format the span
            }
        }
    }
}
```

## <a name="see-also"></a>関連項目

- [従来の言語サービスの特徴](legacy-language-service-features1.md)