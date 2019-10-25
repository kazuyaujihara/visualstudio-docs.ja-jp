---
title: レガシ言語の実装 Service2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- language services [managed package framework], implementing
ms.assetid: 5bcafdc5-f922-48f6-a12e-6c8507a79a05
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 053ca367776c811dd1192814c5f928bb294eefb4
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72727234"
---
# <a name="implementing-a-legacy-language-service"></a>従来の言語サービスの実装
Managed package framework (MPF) を使用して言語サービスを実装するには、<xref:Microsoft.VisualStudio.Package.LanguageService> クラスからクラスを派生させ、次の抽象メソッドとプロパティを実装する必要があります。

- <xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A> メソッド

- <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> メソッド

- <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> メソッド

- <xref:Microsoft.VisualStudio.Package.LanguageService.Name%2A> プロパティ

  これらのメソッドとプロパティの実装の詳細については、以下の該当するセクションを参照してください。

  その他の機能をサポートするために、言語サービスでは、いずれかの MPF 言語サービスクラスからクラスを派生させる必要がある場合があります。たとえば、追加のメニューコマンドをサポートするには、<xref:Microsoft.VisualStudio.Package.ViewFilter> クラスからクラスを派生させ、いくつかのコマンド処理メソッドをオーバーライドする必要があります (詳細については <xref:Microsoft.VisualStudio.Package.ViewFilter> を参照してください)。 @No__t_0 クラスには、さまざまなクラスの新しいインスタンスを作成するために呼び出されるいくつかのメソッドが用意されています。クラスのインスタンスを提供するために、適切な作成方法をオーバーライドします。 たとえば、<xref:Microsoft.VisualStudio.Package.LanguageService> クラスの <xref:Microsoft.VisualStudio.Package.LanguageService.CreateViewFilter%2A> メソッドをオーバーライドして、独自の <xref:Microsoft.VisualStudio.Package.ViewFilter> クラスのインスタンスを返す必要があります。 詳細については、「カスタムクラスのインスタンス化」セクションを参照してください。

  言語サービスでは、さまざまな場所で使用される独自のアイコンを指定することもできます。 たとえば、IntelliSense の入力候補一覧が表示されている場合、リスト内の各項目は、関連付けられているアイコンを持つことができます。また、項目をメソッド、クラス、名前空間、プロパティ、または任意の言語に対して必要なものとしてマークできます。 これらのアイコンは、すべての IntelliSense リスト、**ナビゲーションバー**、および**エラー一覧**タスクウィンドウで使用されます。 詳細については、後述の「言語サービスイメージ」セクションを参照してください。

## <a name="getlanguagepreferences-method"></a>Get言語設定メソッド
 @No__t_0 メソッドは、常に <xref:Microsoft.VisualStudio.Package.LanguagePreferences> クラスの同じインスタンスを返します。 言語サービスに対して追加の設定が不要な場合は、基本 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> クラスを使用できます。 MPF 言語サービスクラスは、少なくとも基本 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> クラスが存在することを前提としています。

### <a name="example"></a>例
 この例は、<xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A> メソッドの一般的な実装を示しています。 この例では、基本 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> クラスを使用します。

```csharp
using Microsoft.VisualStudio.Package;
using Microsoft.VisualStudio.TextManager.Interop;

namespace TestLanguagePackage
{
    public class TestLanguageService : LanguageService
    {
        private LanguagePreferences m_preferences;

        public override LanguagePreferences GetLanguagePreferences()
        {
            if (m_preferences == null)
            {
                m_preferences = new LanguagePreferences(this.Site,
                                                        typeof(TestLanguageService).GUID,
                                                        this.Name );
                m_preferences.Init();
            }
            return m_preferences;
        }
    }
}
```

## <a name="getscanner-method"></a>GetScanner メソッド
 このメソッドは、トークンとその型およびトリガーを取得するために使用されるライン指向パーサーまたはスキャナーを実装する <xref:Microsoft.VisualStudio.Package.IScanner> オブジェクトのインスタンスを返します。 このスキャナーは、色付けのために <xref:Microsoft.VisualStudio.Package.Colorizer> クラスで使用されます。ただし、より複雑な解析操作に準備としてトークンの種類とトリガーを取得するためにスキャナーを使用することもできます。 @No__t_0 インターフェイスを実装するクラスを指定する必要があります。また、<xref:Microsoft.VisualStudio.Package.IScanner> インターフェイスにすべてのメソッドを実装する必要があります。

### <a name="example"></a>例
 この例は、<xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> メソッドの一般的な実装を示しています。 @No__t_0 クラスは、<xref:Microsoft.VisualStudio.Package.IScanner> インターフェイスを実装します (表示されません)。

```csharp
using Microsoft.VisualStudio.Package;
using Microsoft.VisualStudio.TextManager.Interop;

namespace TestLanguagePackage
{
    public class TestLanguageService : LanguageService
    {
        private TestScanner m_scanner;

        public override IScanner GetScanner(IVsTextLines buffer)
        {
            if (m_scanner == null)
            {
                m_scanner = new TestScanner(buffer);
            }
            return m_scanner;
        }
    }
}
    internal class TestScanner : IScanner
    {
        private IVsTextBuffer m_buffer;
        string m_source;

        public TestScanner(IVsTextBuffer buffer)
        {
            m_buffer = buffer;
        }

        bool IScanner.ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo, ref int state)
        {
            tokenInfo.Type = TokenType.Unknown;
            tokenInfo.Color = TokenColor.Text;
            return true;
        }

        void IScanner.SetSource(string source, int offset)
        {
            m_source = source.Substring(offset);
        }
    }

```

## <a name="parsesource-method"></a>ParseSource メソッド
 さまざまな理由に基づいてソースファイルを解析します。 このメソッドには、特定の解析操作に必要なものを記述する <xref:Microsoft.VisualStudio.Package.ParseRequest> オブジェクトが与えられています。 @No__t_0 メソッドは、トークンの機能とスコープを決定するより複雑なパーサーを呼び出します。 @No__t_0 メソッドは、IntelliSense 操作のサポートと、中かっこの照合に使用されます。 このような高度な操作をサポートしていない場合でも、有効な <xref:Microsoft.VisualStudio.Package.AuthoringScope> オブジェクトを返す必要があります。これにより、<xref:Microsoft.VisualStudio.Package.AuthoringScope> インターフェイスを実装するクラスを作成し、そのインターフェイスにすべてのメソッドを実装する必要があります。 すべてのメソッドから null 値を返すことができますが、<xref:Microsoft.VisualStudio.Package.AuthoringScope> オブジェクト自体を null 値にすることはできません。

### <a name="example"></a>例
 この例では、<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> メソッドと <xref:Microsoft.VisualStudio.Package.AuthoringScope> クラスの最小限の実装を示しています。これにより、言語サービスは、より高度な機能を実際にはサポートせずにコンパイルして機能させることができます。

```csharp
using Microsoft.VisualStudio.Package;
using Microsoft.VisualStudio.TextManager.Interop;

namespace TestLanguagePackage
{
    public class TestLanguageService : LanguageService
    {
        public override AuthoringScope ParseSource(ParseRequest req)
        {
            return new TestAuthoringScope();
        }
    }

    internal class TestAuthoringScope : AuthoringScope
    {
        public override string GetDataTipText(int line, int col, out TextSpan span)
        {
            span = new TextSpan();
            return null;
        }

        public override Declarations GetDeclarations(IVsTextView view,
                                                     int line,
                                                     int col,
                                                     TokenInfo info,
                                                     ParseReason reason)
        {
            return null;
        }

        public override string Goto(VSConstants.VSStd97CmdID cmd, IVsTextView textView, int line, int col, out TextSpan span)
        {
            span = new TextSpan();
            return null;
        }

        public override Methods GetMethods(int line, int col, string name)
        {
            return null;
        }
}
```

## <a name="name-property"></a>Name プロパティ
 このプロパティは、言語サービスの名前を返します。 これは、言語サービスの登録時に指定した名前と同じである必要があります。 この名前は、さまざまな場所で使用されます。最も目立つのは、レジストリへのアクセスに名前が使用される <xref:Microsoft.VisualStudio.Package.LanguagePreferences> クラスです。 このプロパティによって返される名前は、レジストリエントリとキー名のレジストリで使用されるので、ローカライズしないでください。

### <a name="example"></a>例
 この例では、<xref:Microsoft.VisualStudio.Package.LanguageService.Name%2A> プロパティの考えられる1つの実装を示します。 ここでの名前はハードコーディングされていることに注意してください。実際の名前は、言語サービスの登録に使用できるように、リソースファイルから取得する必要があります (「[従来の言語サービスの登録](../../extensibility/internals/registering-a-legacy-language-service1.md)」を参照してください)。

```csharp
using Microsoft.VisualStudio.Package;
using Microsoft.VisualStudio.TextManager.Interop;

namespace TestLanguagePackage
{
    public class TestLanguageService : LanguageService
    {
        public override string Name
        {
            get { return "Test Language"; }
        }
    }
}
```

## <a name="instantiating-custom-classes"></a>カスタムクラスのインスタンス化
 指定されたクラスの次のメソッドは、各クラスの独自のバージョンのインスタンスを提供するようにオーバーライドできます。

### <a name="in-the-languageservice-class"></a>LanguageService クラス内

|メソッド|返されるクラス|説明|
|------------|--------------------|-----------------|
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateCodeWindowManager%2A>|<xref:Microsoft.VisualStudio.Package.CodeWindowManager>|テキストビューへのカスタム追加をサポートします。|
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateDocumentProperties%2A>|<xref:Microsoft.VisualStudio.Package.DocumentProperties>|カスタムドキュメントプロパティをサポートします。|
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A>|<xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars>|**ナビゲーションバー**をサポートする場合は。|
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionFunction%2A>|<xref:Microsoft.VisualStudio.Package.ExpansionFunction>|コードスニペットテンプレート内の関数をサポートする場合は。|
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionProvider%2A>|<xref:Microsoft.VisualStudio.Package.ExpansionProvider>|コードスニペットをサポートする場合は。通常、このメソッドはオーバーライドされません。|
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateParseRequest%2A>|<xref:Microsoft.VisualStudio.Package.ParseRequest>|@No__t_0 構造体のカスタマイズをサポートする場合 (通常、このメソッドはオーバーライドされません)。|
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateSource%2A>|<xref:Microsoft.VisualStudio.Package.Source>|ソースコードの書式設定、コメント文字の指定、およびメソッドシグネチャのカスタマイズをサポートします。|
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateViewFilter%2A>|<xref:Microsoft.VisualStudio.Package.ViewFilter>|追加のメニューコマンドをサポートする場合は。|
|<xref:Microsoft.VisualStudio.Package.Source.GetColorizer%2A>|<xref:Microsoft.VisualStudio.Package.Colorizer>|構文の強調表示をサポートする場合は。通常、このメソッドはオーバーライドされません。|
|<xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A>|<xref:Microsoft.VisualStudio.Package.LanguagePreferences>|言語設定へのアクセスをサポートします。 このメソッドは実装する必要がありますが、基底クラスのインスタンスを返すことができます。|
|<xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A>|<xref:Microsoft.VisualStudio.Package.IScanner>|行のトークンの種類を識別するために使用されるパーサーを提供します。 このメソッドは実装する必要があり、<xref:Microsoft.VisualStudio.Package.IScanner> から派生する必要があります。|
|<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A>|<xref:Microsoft.VisualStudio.Package.AuthoringScope>|ソースファイル全体を通じて機能とスコープを識別するために使用されるパーサーを提供します。 このメソッドは実装する必要があり、<xref:Microsoft.VisualStudio.Package.AuthoringScope> クラスのバージョンのインスタンスを返す必要があります。 サポートするものがすべて、<xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> メソッドから返された <xref:Microsoft.VisualStudio.Package.IScanner> パーサーを必要とする構文の強調表示である場合は、メソッドがすべて null 値を返す <xref:Microsoft.VisualStudio.Package.AuthoringScope> クラスのバージョンを返す以外に、このメソッドで何も実行できません。|

### <a name="in-the-source-class"></a>ソースクラス内

|メソッド|返されるクラス|説明|
|------------|--------------------|-----------------|
|<xref:Microsoft.VisualStudio.Package.Source.CreateCompletionSet%2A>|<xref:Microsoft.VisualStudio.Package.CompletionSet>|IntelliSense 入力候補一覧の表示をカスタマイズする場合 (通常はオーバーライドされません)。|
|<xref:Microsoft.VisualStudio.Package.Source.CreateErrorTaskItem%2A>|<xref:Microsoft.VisualStudio.Package.DocumentTask>|エラー一覧タスク一覧のマーカーをサポートするには、具体的には、ファイルを開いてエラーの原因となった行にジャンプする以外にも機能がサポートされます。|
|<xref:Microsoft.VisualStudio.Package.Source.CreateMethodData%2A>|<xref:Microsoft.VisualStudio.Package.MethodData>|IntelliSense パラメーターヒントの表示をカスタマイズするために使用します。|
|<xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A>|<xref:Microsoft.VisualStudio.Package.CommentInfo>|コメントコードをサポートします。|
|<xref:Microsoft.VisualStudio.Package.Source.CreateAuthoringSink%2A>|<xref:Microsoft.VisualStudio.Package.AuthoringSink>|解析操作中に情報を収集します。|

### <a name="in-the-authoringscope-class"></a>AuthoringScope クラス内

|メソッド|返されるクラス|説明|
|------------|--------------------|-----------------|
|<xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDeclarations%2A>|<xref:Microsoft.VisualStudio.Package.Declarations>|メンバーや型などの宣言の一覧を提供します。 このメソッドは実装する必要がありますが、null 値を返すことができます。 このメソッドが有効なオブジェクトを返す場合、オブジェクトは、使用しているバージョンの <xref:Microsoft.VisualStudio.Package.Declarations> クラスのインスタンスである必要があります。|
|<xref:Microsoft.VisualStudio.Package.AuthoringScope.GetMethods%2A>|<xref:Microsoft.VisualStudio.Package.Methods>|指定されたコンテキストのメソッドシグネチャの一覧を提供します。 このメソッドは実装する必要がありますが、null 値を返すことができます。 このメソッドが有効なオブジェクトを返す場合、オブジェクトは、使用しているバージョンの <xref:Microsoft.VisualStudio.Package.Methods> クラスのインスタンスである必要があります。|

## <a name="language-service-images"></a>言語サービスのイメージ
 言語サービス全体で使用されるアイコンの一覧を指定するには、<xref:Microsoft.VisualStudio.Package.LanguageService> クラスの <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> メソッドをオーバーライドし、アイコンを含む <xref:System.Windows.Forms.ImageList> を返します。 基本 <xref:Microsoft.VisualStudio.Package.LanguageService> クラスは、アイコンの既定のセットを読み込みます。 アイコンが必要な場所に正確なイメージインデックスを指定するので、独自のイメージリストをどのように配置するかは、ユーザーによって異なります。

### <a name="images-used-in-intellisense-completion-lists"></a>IntelliSense 入力候補一覧で使用されるイメージ
 IntelliSense 入力候補一覧の場合、イメージインデックスは <xref:Microsoft.VisualStudio.Package.Declarations> クラスの <xref:Microsoft.VisualStudio.Package.Declarations.GetGlyph%2A> メソッドの各項目に対して指定されます。イメージインデックスを指定する場合は、オーバーライドする必要があります。 @No__t_0 メソッドから返される値は、<xref:Microsoft.VisualStudio.Package.CompletionSet> クラスコンストラクターに指定されたイメージリストのインデックスであり、<xref:Microsoft.VisualStudio.Package.LanguageService> クラスの <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> メソッドから返されたイメージリストと同じです (で使用するイメージリストを変更でき @no__別のイメージリストを指定するために <xref:Microsoft.VisualStudio.Package.Source> クラスの <xref:Microsoft.VisualStudio.Package.Source.CreateCompletionSet%2A> メソッドをオーバーライドする場合は、t_4)。

### <a name="images-used-in-the-navigation-bar"></a>ナビゲーションバーで使用されるイメージ
 **ナビゲーションバー**には、型とメンバーの一覧が表示されます。クイックナビゲーションでは、アイコンを表示できます。 これらのアイコンは、<xref:Microsoft.VisualStudio.Package.LanguageService> クラスの <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> メソッドから取得され、**ナビゲーションバー**専用にオーバーライドすることはできません。 コンボボックス内の各項目に使用されるインデックスは、コンボボックスを表すリストが <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> クラスの <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> メソッドに入力されるときに指定されます (「[従来の言語サービスでのナビゲーションバーのサポート](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)」を参照してください)。 これらのイメージのインデックスは、通常はバージョンの <xref:Microsoft.VisualStudio.Package.Declarations> クラスを使用してパーサーから取得されます。 インデックスがどのように取得されるかは、ユーザーによって異なります。

### <a name="images-used-in-the-error-list-task-window"></a>[エラー一覧タスク] ウィンドウで使用されるイメージ
 @No__t_0 メソッドパーサー ([従来の言語サービスパーサーとスキャナーを](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)参照) がエラーを検出し、そのエラーを <xref:Microsoft.VisualStudio.Package.AuthoringSink> クラスの <xref:Microsoft.VisualStudio.Package.AuthoringSink.AddError%2A> メソッドに渡すたびに、**エラー一覧**タスクウィンドウでエラーが報告されます。 アイコンは、タスクウィンドウに表示される各項目に関連付けることができ、そのアイコンは、<xref:Microsoft.VisualStudio.Package.LanguageService> クラスの <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> メソッドから返されたものと同じイメージリストから取得されます。 MPF クラスの既定の動作では、エラーメッセージと共に画像が表示されません。 ただし、<xref:Microsoft.VisualStudio.Package.Source> クラスからクラスを派生させ、<xref:Microsoft.VisualStudio.Package.Source.CreateErrorTaskItem%2A> メソッドをオーバーライドすることによって、この動作をオーバーライドできます。 このメソッドでは、新しい <xref:Microsoft.VisualStudio.Package.DocumentTask> オブジェクトを作成します。 オブジェクトを返す前に、<xref:Microsoft.VisualStudio.Package.DocumentTask> オブジェクトの <xref:Microsoft.VisualStudio.Shell.Task.ImageIndex%2A> プロパティを使用して、イメージのインデックスを設定できます。 これは、次の例のようになります。 @No__t_0 は、すべてのアイコンを一覧表示し、この例に固有の列挙型であることに注意してください。 言語サービスでアイコンを識別する方法が異なる場合があります。

```csharp
using Microsoft.VisualStudio.Package;
using Microsoft.VisualStudio.Shell;
using Microsoft.VisualStudio.TextManager.Interop;

namespace TestLanguagePackage
{
    class TestSource : Source
    {
        public override DocumentTask CreateErrorTaskItem(
            TextSpan          span,
            string            filename,
            string            message,
            TaskPriority      priority,
            TaskCategory      category,
            MARKERTYPE        markerType,
            TaskErrorCategory errorCategory)
        {
            DocumentTask taskItem = base.CreateErrorTaskItem(
                                           span,
                                           filename,
                                           message,
                                           priority,
                                           category,
                                           markerType,
                                           errorCategory);
            if (errorCategory == TaskErrorCategory.Error)
            {
                taskItem.ImageIndex = TestIconImageIndex.Error;
            }
            return taskItem;
        }
    }
}
```

## <a name="the-default-image-list-for-a-language-service"></a>言語サービスの既定のイメージリスト
 基本 MPF 言語サービスクラスに用意されている既定のイメージリストには、より一般的な言語要素に関連付けられている多数のアイコンが含まれています。 これらのアイコンの多くは、パブリック、内部、友人、保護、プライベート、およびショートカットのアクセス概念に対応する6つのバリエーションのセットにまとめられています。 たとえば、メソッドがパブリック、保護、プライベートのいずれであるかに応じて、異なるアイコンを使用できます。

 次の列挙体では、各アイコンセットの一般的な名前を指定し、関連付けられているインデックスを指定します。 たとえば、列挙体に基づいて、保護されたメソッドのイメージインデックスを `(int)IconImageIndex.Method + (int)IconImageIndex.AccessProtected` として指定できます。 この列挙体の名前は、必要に応じて変更できます。

```csharp
public enum IconImageIndex
        {
            // access types
            AccessPublic = 0,
            AccessInternal = 1,
            AccessFriend = 2,
            AccessProtected = 3,
            AccessPrivate = 4,
            AccessShortcut = 5,

            Base = 6,
            // Each of the following icon type has 6 versions,
            //corresponding to the access types
            Class = Base + 0,
            Constant = Base + 1,
            Delegate = Base + 2,
            Enumeration = Base + 3,
            EnumMember = Base + 4,
            Event = Base + 5,
            Exception = Base + 6,
            Field = Base + 7,
            Interface = Base + 8,
            Macro = Base + 9,
            Map = Base + 10,
            MapItem = Base + 11,
            Method = Base + 12,
            OverloadedMethod = Base + 13,
            Module = Base + 14,
            Namespace = Base + 15,
            Operator = Base + 16,
            Property = Base + 17,
            Struct = Base + 18,
            Template = Base + 19,
            Typedef = Base + 20,
            Type = Base + 21,
            Union = Base + 22,
            Variable = Base + 23,
            ValueType = Base + 24,
            Intrinsic = Base + 25,
            JavaMethod = Base + 26,
            JavaField = Base + 27,
            JavaClass = Base + 28,
            JavaNamespace = Base + 29,
            JavaInterface = Base + 30,
            // Miscellaneous icons with one icon for each type.
            Error = 187,
            GreyedClass = 188,
            GreyedPrivateMethod = 189,
            GreyedProtectedMethod = 190,
            GreyedPublicMethod = 191,
            BrowseResourceFile = 192,
            Reference = 193,
            Library = 194,
            VBProject = 195,
            VBWebProject = 196,
            CSProject = 197,
            CSWebProject = 198,
            VB6Project = 199,
            CPlusProject = 200,
            Form = 201,
            OpenFolder = 202,
            ClosedFolder = 203,
            Arrow = 204,
            CSClass = 205,
            Snippet = 206,
            Keyword = 207,
            Info = 208,
            CallBrowserCall = 209,
            CallBrowserCallRecursive = 210,
            XMLEditor = 211,
            VJProject = 212,
            VJClass = 213,
            ForwardedType = 214,
            CallsTo = 215,
            CallsFrom = 216,
            Warning = 217,
        }
```

## <a name="see-also"></a>関連項目
- [従来の言語サービスの実装](../../extensibility/internals/implementing-a-legacy-language-service1.md)
- [従来の言語サービスの概要](../../extensibility/internals/legacy-language-service-overview.md)
- [従来の言語サービスの登録](../../extensibility/internals/registering-a-legacy-language-service1.md)
- [従来の言語サービスのパーサーとスキャナー](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)