---
title: マイコードのみ | を使用したユーザーコードのデバッグMicrosoft Docs
ms.date: 02/13/2019
ms.topic: conceptual
ms.assetid: 0f0df097-bbaf-46ad-9ad1-ef5f40435079
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c1d474b388dd8f116eb53febb8a472d4c5b8150
ms.sourcegitcommit: 08c144d290da373df841f04fc799e3133540a541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72535998"
---
# <a name="debug-only-user-code-with-just-my-code"></a>マイコードのみでユーザーコードのみをデバッグする

*マイコードのみ*は、システム、フレームワーク、およびその他の非ユーザーコードの呼び出しを自動的にステップオーバーする、Visual Studio のデバッグ機能です。 **[呼び出し履歴]** ウィンドウでは、マイコードのみによってこれらの呼び出しが **[外部コード]** フレームに折りたたまれます。

.NET、、および JavaScript のC++プロジェクトではマイコードのみの動作が異なります。

## <a name="BKMK_Enable_or_disable_Just_My_Code"></a>"マイ コードのみ" の有効/無効の切り替え

ほとんどのプログラミング言語では、マイコードのみは既定で有効になっています。

- Visual Studio でマイコードのみを有効または無効にするには、 **[ツール]**  >  **[オプション]** (または**デバッグ** > **オプション**>) の [**デバッグ** > **全般**] で、 **[マイコードのみを有効にする]** をオンまたはオフにします。

![[オプション] ダイアログボックスでマイコードのみを有効にする](../debugger/media/dbg_justmycode_options.png "[マイ コードのみを有効にする]")

> [!NOTE]
> [**マイコードのみを有効に**する] は、すべての言語のすべての Visual Studio プロジェクトに適用されるグローバル設定です。

## <a name="just-my-code-debugging"></a>マイ コードのみデバッグ

デバッグセッション中に、 **[モジュール]** ウィンドウには、デバッガーがマイコードとして扱うコードモジュール (ユーザーコード) と、シンボルの読み込み状態が表示されます。 詳細については、「[デバッガーがアプリにアタッチする方法を理解する](../debugger/debugger-tips-and-tricks.md#modules_window)」を参照してください。

![[モジュール] ウィンドウのユーザーコード](../debugger/media/dbg_justmycode_module.png "[モジュール] ウィンドウのユーザーコード")

**[呼び出し履歴]** ウィンドウまたは **[タスク]** ウィンドウで、マイコードのみ非ユーザーコードが `[External Code]` というラベルが付いた、淡色表示の注釈付きコードフレームに折りたたまれます。

![[呼び出し履歴] ウィンドウの外部コードフレーム](../debugger/media/dbg_justmycode_externalcode.png "外部コードフレーム")

>[!TIP]
>**モジュール**、**呼び出し履歴**、**タスク**、またはその他のほとんどのデバッグウィンドウを開くには、デバッグセッションである必要があります。 デバッグ中に、[**デバッグ** > **ウィンドウ**] で、開くウィンドウを選択します。

<a name="BKMK_Override_call_stack_filtering"></a>折りたたまれた **[外部コード]** フレームでコードを表示するには、**呼び出し履歴**または**タスク**ウィンドウを右クリックし、コンテキストメニューから **[外部コードの表示]** を選択します。 展開された外部コード行は、 **[外部コード**] フレームを置き換えます。

![[呼び出し履歴] ウィンドウに外部コードを表示する](../debugger/media/dbg_justmycode_showexternalcode.png "[外部コードの表示]")

> [!NOTE]
> [**外部コードの表示]** は、ユーザーが開いているすべての言語のすべてのプロジェクトに適用される、現在のユーザープロファイラー設定です。

**[呼び出し履歴]** ウィンドウで展開されている外部コード行をダブルクリックすると、ソースコード内の呼び出し元のコード行が緑色で強調表示されます。 Dll またはその他のモジュールが見つからないか、読み込まれていない場合、[シンボルまたはソースが見つかりません] ページが表示されることがあります。

## <a name="BKMK__NET_Framework_Just_My_Code"></a>.NET マイコードのみ

.NET プロジェクトでは、マイコードのみがシンボル ( *.pdb*) ファイルとプログラムの最適化を使用して、ユーザーコードと非ユーザーコードを分類します。 .NET デバッガーは、最適化されたバイナリと読み込ま*れていない .pdb*ファイルを非ユーザーコードと見なします。

次の3つのコンパイラ属性は、.NET デバッガーがユーザーコードと見なされる内容にも影響します。

- <xref:System.Diagnostics.DebuggerNonUserCodeAttribute> は、適用されているコードがユーザーコードではないことをデバッガーに通知します。
- <xref:System.Diagnostics.DebuggerHiddenAttribute> は、"マイ コードのみ" がオフになっていても、コードをデバッガーから見えないようにするための属性です。
- <xref:System.Diagnostics.DebuggerStepThroughAttribute> は、コードにステップインするのではなく、適用されているコードをステップ実行するようにデバッガーに指示します。

.NET デバッガーでは、他のすべてのコードがユーザーコードであると見なされます。

.NET のデバッグ中:

- コードをユーザーコードの次の行にステップオーバーして、ユーザーコード以外のステップに**ステップイン**(または**F11**)  >  するには、**デバッグ**を実行します。
- ユーザーコード以外のコードがユーザーコードの次の行に実行されるときに、**デバッグ** > **ステップアウト**(または**Shift** +**F11**) を実行します。

それ以上のユーザーコードがない場合、デバッグは終了するか、別のブレークポイントにヒットするか、エラーをスローします。

<a name="BKMK_NET_Breakpoint_behavior"></a>デバッガーが非ユーザーコードで中断した場合 (たとえば、**デバッグ** >  使用して、ユーザーコード以外で**中断**します)、 **[ソースなし]** ウィンドウが表示されます。 次に、**デバッグ** > **ステップ**コマンドを使用して、ユーザーコードの次の行に進むことができます。

非ユーザーコードでハンドルされない例外が発生した場合、デバッガーは例外が生成されたユーザーコード行で中断します。

例外に対して初回例外が有効になっている場合は、呼び出し元のユーザーコード行がソースコードで緑色で強調表示されます。 **[呼び出し履歴]** ウィンドウに、 **[外部コード]** というラベルの付いた注釈付きフレームが表示されます。

## <a name="BKMK_C___Just_My_Code"></a>C++ での "マイ コードのみ"

Visual Studio 2017 バージョン15.8 以降では、コードステップのマイコードのみもサポートされています。 この機能では、 [/JMC (マイコードのみのデバッグ)](/cpp/build/reference/jmc)コンパイラスイッチを使用する必要もあります。 スイッチは、プロジェクトでC++既定で有効になっています。 マイコードのみでの**呼び出し履歴**ウィンドウとコールスタックのサポートでは、/JMC スイッチは必要ありません。

<a name="BKMK_CPP_User_and_non_user_code"></a>ユーザーコードとして分類するには、ユーザーコードを含むバイナリの PDB がデバッガーによって読み込まれている必要があります ( **[モジュール]** ウィンドウを使用してこれを確認します)。

**[呼び出し履歴]** ウィンドウなどの呼び出し履歴の動作の場合、のC++マイコードのみは、これらの関数のみを*非ユーザーコード*と見なします。

- シンボル ファイル内に除去されたソース情報がある関数。
- シンボル ファイルがスタック フレームに対応するソース ファイルがないことを示す関数。
- *.Natjmc ファイル \** で指定された関数は、 *%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers*フォルダーにあります。

コードのステッピング動作では、 C++のマイコードのみは、これらの関数のみを*非ユーザーコード*と見なします。

- 対応する PDB ファイルがデバッガーに読み込まれていないの関数。
- *.Natjmc ファイル \** で指定された関数は、 *%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers*フォルダーにあります。

> [!NOTE]
> マイコードのみでコードのステップ実行をC++サポートするには、Visual Studio 15.8 Preview 3 以降の MSVC コンパイラを使用してコードをコンパイルし、/JMC コンパイラスイッチを有効にする必要があります (既定では有効になっています)。 詳細については、「[呼び出し履歴とコードのステップ実行動作のC++カスタマイズ](#BKMK_CPP_Customize_call_stack_behavior)」およびこの[ブログ投稿](https://devblogs.microsoft.com/cppblog/announcing-jmc-stepping-in-visual-studio/)を参照してください。 以前のコンパイラを使用してコンパイルされたコードの場合、 *.natstepfilter*ファイルは、マイコードのみに依存しないコードステップをカスタマイズする唯一の方法です。 「[ステップC++実行動作のカスタマイズ](#BKMK_CPP_Customize_stepping_behavior)」を参照してください。

<a name="BKMK_CPP_Stepping_behavior"></a>デバッグC++中:

- コードをユーザーコードの次の行にステップオーバーして、ユーザーコード以外のステップに**ステップイン**(または**F11**)  >  するには、**デバッグ**を実行します。
- ユーザーコード以外のコードがユーザーコードの次の行に実行されるときに、**デバッグ** > **ステップアウト**(または**Shift** +**F11**) を実行します。

それ以上のユーザーコードがない場合、デバッグは終了するか、別のブレークポイントにヒットするか、エラーをスローします。

デバッガーが非ユーザーコードで中断した場合 (たとえば、**デバッグ** >  使用して、非ユーザーコードで**中断**して一時停止した場合)、ユーザーコード以外でステップ実行が続行されます。

デバッガーが例外にヒットした場合は、例外が発生したときに、ユーザーコードか非ユーザーコードかにかかわらず、デバッガーは停止します。 **[例外設定]** ダイアログボックスの**ユーザーが処理できない**オプションは無視されます。

### <a name="BKMK_CPP_Customize_call_stack_behavior"></a>呼び出しC++履歴とコードのステップ実行動作をカスタマイズする

プロジェクトでは、.natjmc ファイル \* で指定することにより、 **[呼び出し履歴]** ウィンドウが非ユーザーコードとして扱うモジュール、ソースファイル、および関数を指定できます。 C++ このカスタマイズは、最新のコンパイラを使用している場合のコードステップにも適用されます ( [ C++マイコードのみ](#BKMK_CPP_User_and_non_user_code)を参照してください)。

- Visual Studio コンピューターのすべてのユーザーの非ユーザー コードを指定するには、 *%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers* フォルダーに *.natjmc* ファイルを追加します。
- 個々のユーザーに対して非ユーザーコードを指定するには、.natjmc ファイルを *%USERPROFILE%\My Documents \\ < Visual Studio version \> \ ビジュアライザー*フォルダーに追加し*ます*。

*.Natjmc*ファイルは、次の構文を持つ XML ファイルです。

```xml
<?xml version="1.0" encoding="utf-8"?>
<NonUserCode xmlns="http://schemas.microsoft.com/vstudio/debugger/jmc/2015">

  <!-- Modules -->
  <Module Name="ModuleSpec" />
  <Module Name="ModuleSpec" Company="CompanyName" />

  <!-- Files -->
  <File Name="FileSpec"/>

  <!-- Functions -->
  <Function Name="FunctionSpec" />
  <Function Name="FunctionSpec" Module ="ModuleSpec" />
  <Function Name="FunctionSpec" Module ="ModuleSpec" ExceptionImplementation="true" />

</NonUserCode>

```

 **Module 要素の属性**

|属性|説明|
|---------------|-----------------|
|`Name`|必須です。 モジュールの完全パス。 Windows のワイルドカード文字 `?` (0 または1文字) と `*` (0 個以上の文字) を使用できます。 たとえば、オブジェクトに適用された<br /><br /> `<Module Name="?:\3rdParty\UtilLibs\*" />`<br /><br /> では、ドライブの *\3rdParty\UtilLibs* 内のすべてのモジュールを外部コードとして扱うことをデバッガーに指示します。|
|`Company`|省略可能です。 実行可能ファイルに埋め込まれているモジュールを発行する会社の名前。 この属性を使用して、モジュールのあいまいさを解消することができます。|

 **File 要素の属性**

|属性|説明|
|---------------|-----------------|
|`Name`|必須です。 外部コードとして扱うソース ファイルの完全パス。 パスを指定するときに Windows のワイルドカード文字、`?` および `*` を使用できます。|

 **Function 要素の属性**

|属性|説明|
|---------------|-----------------|
|`Name`|必須です。 外部コードとして扱う関数の完全修飾名。|
|`Module`|省略可能です。 関数を含むモジュールの名前または完全パス。 この属性を使用して、同じ名前の関数のあいまいさを解消することができます。|
|`ExceptionImplementation`|`true` に設定すると、この関数ではなく、例外をスローした関数が呼び出し履歴に表示されます。|

### <a name="BKMK_CPP_Customize_stepping_behavior"></a>マイコードのみC++設定とは関係なく、ステップ実行動作をカスタマイズする

プロジェクトC++では、 *.natstepfilter ファイル \** で非ユーザーコードとして一覧表示することによって、ステップオーバーする関数を指定できます。 *.Natstepfilter ファイル \** に一覧表示されている関数は、マイコードのみの設定に依存していません。

- すべてのローカル Visual Studio ユーザーに対して非ユーザーコードを指定するには、 *.natstepfilter*ファイルを *%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers*フォルダーに追加します。
- 個々のユーザーに対して非ユーザーコードを指定するには、.natstepfilter ファイルを *%USERPROFILE%\My Documents \\ < Visual Studio version \> \ ビジュアライザー*フォルダーに追加し*ます*。

*.Natstepfilter*ファイルは、次の構文を持つ XML ファイルです。

```xml
<?xml version="1.0" encoding="utf-8"?>
<StepFilter xmlns="http://schemas.microsoft.com/vstudio/debugger/natstepfilter/2010">
    <Function>
        <Name>FunctionSpec</Name>
        <Action>StepAction</Action>
    </Function>
    <Function>
        <Name>FunctionSpec</Name>
        <Module>ModuleSpec</Module>
        <Action>StepAction</Action>
    </Function>
</StepFilter>

```

|要素|説明|
|-------------|-----------------|
|`Function`|必須です。 1 つ以上の関数を非ユーザー関数として指定します。|
|`Name`|必須です。 一致を照合する完全な関数名を指定する ECMA-262 書式の正規表現。 (例:<br /><br /> `<Name>MyNS::MyClass.*</Name>`<br /><br /> は、`MyNS::MyClass` のすべてのメソッドが非ユーザー コードと見なされることをデバッガーに知らせます。 一致照合では、大文字と小文字が区別されます。|
|`Module`|省略可能です。 関数を含むモジュールへの完全パスを指定する ECMA-262 書式の正規表現。 一致では、大文字と小文字を区別しません。|
|`Action`|必須です。 大文字と小文字が区別される以下のいずれかの値です。<br /><br /> `NoStepInto`-関数をステップオーバーするようにデバッガーに指示します。<br /> `StepInto`-関数にステップインするようにデバッガーに指示し、一致する関数の他の `NoStepInto` をオーバーライドします。|

## <a name="BKMK_JavaScript_Just_My_Code"></a>JavaScript での "マイ コードのみ"

<a name="BKMK_JS_User_and_non_user_code"></a>JavaScript の "マイ コードのみ" では、以下のいずれかの方法でコードを分類することによって、ステップ実行と呼び出し履歴表示が制御されます。

|||
|-|-|
|**MyCode**|ユーザーが所有および制御するユーザー コード。|
|**LibraryCode**|定期的に使用するライブラリからの非ユーザーコードと、アプリが正しく機能するために依存している (例: WinJS や jQuery)。|
|**UnrelatedCode**|アプリで所有していない非ユーザーコード。アプリが正しく機能するために依存していません。 たとえば、広告を表示する広告 SDK には、関連性のないコードが考えられます。 UWP プロジェクトでは、HTTP または HTTPS URI からアプリに読み込まれるコードも、非関連コードと見なされます。|

JavaScript デバッガーは、コードをユーザーまたは非ユーザーとして次の順序で分類します。

1. 既定の分類。
   - ホストから提供された `eval` 関数に文字列を渡すことによって実行されるスクリプトは**Mycode**です。
   - 文字列を `Function` コンストラクターに渡すことによって実行されるスクリプトは**Librarycode**です。
   - WinJS や Azure SDK などのフレームワーク参照のスクリプトは、 **Librarycode**です。
   - @No__t_0、`setImmediate`、または `setInterval` 関数に文字列を渡すことによって実行されるスクリプトは、非関連性の**コード**です。

2. *%VSInstallDirectory%\JavaScript\JustMyCode\mycode.default.wwa.json*ファイル内のすべての Visual Studio JavaScript プロジェクトに対して指定された分類。

3. 現在のプロジェクトの*mycode. json*ファイル内の分類。

分類の各手順で、前の手順はオーバーライドされます。

他のコードはすべて、**MyCode** として分類されます。

既定の分類を変更し、特定のファイルと Url をユーザーコードまたは非ユーザーコードとして分類することができます。そのためには、 *mycode*という名前の*Json*ファイルを JavaScript プロジェクトのルートフォルダーに追加します。 「 [JavaScript マイコードのみをカスタマイズ](#BKMK_JS_Customize_Just_My_Code)する」を参照してください。

<a name="BKMK_JS_Stepping_behavior"></a>JavaScript のデバッグ中:

- 関数が非ユーザーコードの場合、**デバッグ** > **ステップイン**(または**F11**) は**デバッグ** > **ステップオーバー** (または**F10**) と同様に動作します。
- ステップが非ユーザー (**librarycode**または**Un関連性**のあるコード) コードで始まる場合、ステップ実行は一時的にマイコードのみが有効になっていないかのように動作します。 ユーザーコードに戻ると、マイコードのみのステップ実行が再度有効になります。
- ユーザーコードのステップで現在の実行コンテキストを離れると、デバッガーは次に実行されたユーザーコード行で停止します。 たとえば、コールバックが **LibraryCode** コードで実行されると、デバッガーはユーザー コードの次の行が実行されるまで続行されます。
- **[ステップアウト]** (または**Shift** +**F11**) は、ユーザーコードの次の行で停止します。

それ以上のユーザーコードがない場合、デバッグは終了するか、別のブレークポイントにヒットするか、エラーをスローします。

コードに設定されたブレークポイントは常にヒットしますが、コードは分類されます。

- @No__t_0 キーワードが**Librarycode**で発生した場合、デバッガーは常に中断します。
- @No__t_0 キーワードが非関連性**コード**で発生した場合、デバッガーは停止しません。

<a name="BKMK_JS_Exception_behavior"></a>**Mycode**または**librarycode**コードでハンドルされない例外が発生した場合、デバッガーは常に中断します。

ハンドルされない例外が非関連性**コード**で発生し、 **Mycode**または**librarycode**が呼び出し履歴にある場合、デバッガーは中断します。

例外に対して初回例外が有効になっていて、 **librarycode**または非関連性**コード**で例外が発生した場合は、次のようになります。

- 例外が処理される場合、デバッガーは中断されません。
- 例外が処理されない場合、デバッガーは中断します。

### <a name="BKMK_JS_Customize_Just_My_Code"></a>JavaScript マイコードのみをカスタマイズする

1つの JavaScript プロジェクトのユーザーコードと非ユーザーコードを分類するには、 *mycode*という名前の*json*ファイルをプロジェクトのルートフォルダーに追加します。

このファイルの仕様によって、既定の分類と*mycode. wwa. json*ファイルがオーバーライドされます。 *Mycode の json*ファイルでは、すべてのキーと値のペアを一覧表示する必要はありません。 **Mycode**、 **Library**、および**無関係**の値は、空の配列にすることができます。

*Mycode. json*ファイルは、次の構文を使用します。

```json
{
    "Eval" : "Classification",
    "Function" : "Classification",
    "ScriptBlock" : "Classification",
    "MyCode" : [
        "UrlOrFileSpec",
        . . .
        "UrlOrFileSpec"
    ],
    "Libraries" : [
        "UrlOrFileSpec",
        . .
        "UrlOrFileSpec"
    ],
    "Unrelated" : [
        "UrlOrFileSpec",
        . . .
        "UrlOrFileSpec"
    ]
}

```

**Eval、Function、および ScriptBlock**

**Eval**、**Function**、および **ScriptBlock** のキーと値のペアで、動的に生成されたコードを分類する方法が決まります。

|||
|-|-|
|**Eval**|ホスト提供の `eval` 関数に文字列を渡すことで実行されるスクリプト。 既定では、Eval スクリプトは **MyCode** として分類されます。|
|**Function**|`Function` コンストラクターに文字列を渡すことで実行されるスクリプト。 既定では、Function スクリプトは **LibraryCode** として分類されます。|
|**ScriptBlock**|`setTimeout`、`setImmediate`、または `setInterval` 関数に文字列を渡すことで実行されるスクリプト。 既定では、ScriptBlock スクリプトは **UnrelatedCode** として分類されます。|

以下のいずれかのキーワードに値を変更できます。

- `MyCode` では、スクリプトが **MyCode** として分類されます。
- `Library` では、スクリプトが **LibraryCode** として分類されます。
- `Unrelated` では、スクリプトが **UnrelatedCode** として分類されます。

**MyCode、Libraries、および Unrelated**

**MyCode**、**Libraries**、および **Unrelated** のキーと値のペアでは、分類に含める URL またはファイルを指定します。

|||
|-|-|
|**MyCode**|**MyCode** として分類される URL またはファイルの配列。|
|**Libraries**|**LibraryCode** として分類される URL またはファイルの配列。|
|**Unrelated**|**UnrelatedCode** として分類される URL またはファイルの配列。|

URL またはファイルの文字列には、0個以上の文字に一致する1つ以上の `*` 文字を指定できます。 `*` は、正規表現 `.*` と同じです。
