---
title: インストールされているコードスニペットの一覧を取得する (レガシ) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- snippets, retrieving list
- code snippets, retrieving list
- GetSnippets method
ms.assetid: 7d142f8b-35b1-44c4-a13e-f89f6460c906
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 072827bbb9676ba49df5ccd69f329ea9b04c78b2
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721656"
---
# <a name="walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation"></a>チュートリアル: インストールされているコード スニペットの一覧の取得 (従来の実装)
コードスニペットは、メニューコマンド (インストールされているコードスニペットの一覧を選択できる) を使用するか、IntelliSense の入力候補一覧からスニペットのショートカットを選択することにより、ソースバッファーに挿入できるコードの一部です。

 @No__t_0 メソッドは、特定の言語 GUID のすべてのコードスニペットを取得します。 これらのスニペットのショートカットは、IntelliSense の入力候補一覧に挿入できます。

 Managed package framework (MPF) 言語サービスでコードスニペットを実装する方法の詳細については[、「従来の言語サービスでのコードスニペットのサポート](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)」を参照してください。

### <a name="to-retrieve-a-list-of-code-snippets"></a>コードスニペットの一覧を取得するには

1. 次のコードは、特定の言語のコードスニペットの一覧を取得する方法を示しています。 結果は <xref:Microsoft.VisualStudio.TextManager.Interop.VsExpansion> 構造体の配列に格納されます。 このメソッドは、静的 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> メソッドを使用して、<xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager> サービスから <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> インターフェイスを取得します。 ただし、VSPackage に指定されたサービスプロバイダーを使用して、<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> メソッドを呼び出すこともできます。

    ```csharp
    using System;
    using System.Collections;
    using System.Runtime.InteropServices;
    using Microsoft.VisualStudio.Package;
    using Microsoft.VisualStudio.Shell;
    using Microsoft.VisualStudio.TextManager.Interop;

    [Guid("00000000-0000-0000-0000-000000000000")] //create a new GUID for the language service
    namespace TestLanguage
    {
        class TestLanguageService : LanguageService
        {
            private void GetSnippets(Guid languageGuid,
                                     ref ArrayList expansionsList)
            {
                IVsTextManager textManager = (IVsTextManager)Package.GetGlobalService(typeof(SVsTextManager));
                if (textManager != null)
                {
                    IVsTextManager2 textManager2 = (IVsTextManager2)textManager;
                    if (textManager2 != null)
                    {
                        IVsExpansionManager expansionManager = null;
                        textManager2.GetExpansionManager(out expansionManager);
                        if (expansionManager != null)
                        {
                            // Tell the environment to fetch all of our snippets.
                            IVsExpansionEnumeration expansionEnumerator = null;
                            expansionManager.EnumerateExpansions(languageGuid,
                            0,     // return all info
                            null,    // return all types
                            0,     // return all types
                            1,     // include snippets without types
                            0,     // do not include duplicates
                            out expansionEnumerator);
                            if (expansionEnumerator != null)
                            {
                                // Cache our expansions in a VsExpansion array
                                uint count   = 0;
                                uint fetched = 0;
                                VsExpansion expansionInfo = new VsExpansion();
                                IntPtr[] pExpansionInfo   = new IntPtr[1];

                                // Allocate enough memory for one VSExpansion structure. This memory is filled in by the Next method.
                                pExpansionInfo[0] = Marshal.AllocCoTaskMem(Marshal.SizeOf(expansionInfo));

                                expansionEnumerator.GetCount(out count);
                                for (uint i = 0; i < count; i++)
                                {
                                    expansionEnumerator.Next(1, pExpansionInfo, out fetched);
                                    if (fetched > 0)
                                    {
                                        // Convert the returned blob of data into a structure that can be read in managed code.
                                        expansionInfo = (VsExpansion)Marshal.PtrToStructure(pExpansionInfo[0], typeof(VsExpansion));

                                        if (!String.IsNullOrEmpty(expansionInfo.shortcut))
                                        {
                                            expansionsList.Add(expansionInfo);
                                        }
                                    }
                                }
                                Marshal.FreeCoTaskMem(pExpansionInfo[0]);
                            }
                        }
                    }
                }
            }
        }
    }
    ```

### <a name="to-call-the-getsnippets-method"></a>GetSnippets メソッドを呼び出すには

1. 次のメソッドは、解析操作の完了時に `GetSnippets` メソッドを呼び出す方法を示しています。 @No__t_0 メソッドは、<xref:Microsoft.VisualStudio.Package.ParseReason> 理由で開始された解析操作の後に呼び出されます。

> [!NOTE]
> @No__t_0 配列の一覧は、パフォーマンス上の理由からキャッシュされます。 スニペットへの変更は、言語サービスが停止および再読み込みされるまで (たとえば、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] を停止して再起動することによって)、一覧には反映されません。

```csharp
class TestLanguageService : LanguageService
{
    private ArrayList expansionsList;

    public override void OnParseComplete(ParseRequest req)
    {
        if (this.expansionsList == null)
        {
            this.expansionsList = new ArrayList();
            GetSnippets(this.GetLanguageServiceGuid(),
                ref this.expansionsList);
        }
    }
}
```

### <a name="to-use-the-snippet-information"></a>スニペット情報を使用するには

1. 次のコードは、`GetSnippets` メソッドによって返されるスニペット情報の使用方法を示しています。 @No__t_0 メソッドは、コードスニペットの一覧を設定するために使用される解析の理由に応じて、パーサーから呼び出されます。 これは、完全な解析が初めて実行された後に行われます。

     @No__t_0 メソッドは、後でコンプリートリストに表示される宣言の一覧を作成します。

     @No__t_0 クラスには、入力候補一覧と宣言の種類に表示できるすべての情報が含まれています。

    ```csharp
    class TestAuthoringScope : AuthoringScope
    {
        public void AddDeclarations(TestDeclaration declaration)
        {
            if (m_declarations == null)
                m_declarations = new List<TestDeclaration>();
            m_declarations.Add(declaration);
         }
    }
    class TestDeclaration
    {
        private string m_name;
        private string m_description;
        private string m_type;

        public TestDeclaration(string name, string desc, string type)
        {
            m_name = name;
            m_description = desc;
            m_type = type;
        }

    class TestLanguageService : LanguageService
    {
        internal void AddSnippets(ref TestAuthoringScope scope)
        {
            if (this.expansionsList != null && this.expansionsList.Count > 0)
            {
                int count = this.expansionsList.Count;
                for (int i = 0; i < count; i++)
                {
                    VsExpansion expansionInfo = (VsExpansion)this.expansionsList[i];
                    scope.AddDeclaration(new TestDeclaration(expansionInfo.title,
                         expansionInfo.description,
                         "snippet"));
                }
            }
        }
    }

    ```

## <a name="see-also"></a>関連項目
- [従来の言語サービスでのコード スニペットのサポート](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)