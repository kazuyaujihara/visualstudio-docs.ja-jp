---
title: EditorConfig での .NET の言語規則
ms.date: 06/17/2019
ms.topic: reference
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- language code style rules [EditorConfig]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 90c080b62be8f3aba128b26aafe9d2b6e30446f5
ms.sourcegitcommit: 32144a09ed46e7223ef7dcab647a9f73afa2dd55
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2019
ms.locfileid: "67586806"
---
# <a name="language-conventions"></a>言語規則

Visual Studio 用の EditorConfig の言語規則は、2 つのカテゴリに分類されます。

- [.NET コード スタイルの設定](#net-code-style-settings)

- [C# コード スタイルの設定](#c-code-style-settings)

> [!TIP]
> 優先するプログラミング言語のコード例を表示するには、ブラウザー ウィンドウの右上隅にある言語ピッカーを使ってそれを選択します。

## <a name="rule-format"></a>規則形式

言語規則のルールには次の一般的な形式があります。

`option_name = value:severity`

各言語の規則では、そのスタイルを優先する場合や状況を指定します。 多くのルールでは、`true` (このスタイルを優先する) または `false` (このスタイルを優先しない) の値が受け付けられます。それ以外では、`when_on_single_line` や `never` などの値が受け付けられます。 ルールの 2 番目の部分では、**重要度**を指定します。

### <a name="severity"></a>重要度

言語規則の重要度では、そのスタイルを強制するレベルを指定します。 次の表に、指定できる重要度の値とその効果をリストします。

重要度 | 効果
:------- | ------
`none` | このルールに違反した場合、ユーザーには何も表示されません。 しかし、コード生成機能により、このスタイルでコードが生成されます。 重大度が `none` のルールが、 **[クイック アクションとリファクタリング]** メニューに表示されることはありません。 ほとんどの場合、これは "無効" または "無視" と見なされます。
`silent` (Visual Studio 2017 バージョン 15.8 以降では `refactoring` も) | このルールに違反した場合、ユーザーには何も表示されません。 しかし、コード生成機能により、このスタイルでコードが生成されます。 重大度が `silent` のルールはクリーンアップに関するものであり、また **[クイック アクションとリファクタリング]** メニューに表示されます。
`suggestion` | このスタイル ルールに違反した場合、修正候補としてユーザーに表示されます。 修正候補は、最初の 2 文字の下に 3 つの灰色のドットとして表示されます。
`warning` | このスタイル ルールに違反した場合、コンパイラの警告が表示されます。
`error` | このスタイル ルールに違反した場合、コンパイラ エラーが表示されます。

## <a name="net-code-style-settings"></a>.NET コード スタイルの設定

このセクションのスタイル ルールは、C# および Visual Basic の両方に適用されます。

- ["This."と "Me." 修飾子](#this-and-me)
   - dotnet\_style\_qualification\_for_field
   - dotnet\_style\_qualification\_for_property
   - dotnet\_style\_qualification\_for_method
   - dotnet\_style\_qualification\_for_event
- [型参照のためのフレームワーク型名の代わりの言語キーワード](#language-keywords)
   - dotnet\_style\_predefined\_type\_for\_locals\_parameters_members
   - dotnet\_style\_predefined\_type\_for\_member_access
- [修飾子の基本設定](#normalize-modifiers)
   - dotnet\_style\_require\_accessibility_modifiers
   - csharp\_preferred\_modifier_order
   - visual\_basic\_preferred\_modifier_order
   - dotnet\_style\_readonly\_field
- [かっこの基本設定](#parentheses-preferences)
   - dotnet\_style\_parentheses\_in\_arithmetic\_binary\_operators
   - dotnet\_style\_parentheses\_in\_other\_binary\_operators
   - dotnet\_style\_parentheses\_in\_other\_operators
   - dotnet\_style\_parentheses\_in\_relational\_binary\_operators
- [式レベル基本設定](#expression-level-preferences)
   - dotnet\_style\_object_initializer
   - dotnet\_style\_collection_initializer
   - dotnet\_style\_explicit\_tuple_names
   - dotnet\_style\_prefer\_inferred\_tuple_names
   - dotnet\_style\_prefer\_inferred\_anonymous\_type\_member_names
   - dotnet\_style\_prefer\_auto\_properties
   - dotnet\_style\_prefer\_is\_null\_check\_over\_reference\_equality\_method
   - dotnet\_style\_prefer\_conditional\_expression\_over\_assignment
   - dotnet\_style\_prefer\_conditional\_expression\_over\_return
- ["null" チェック設定](#null-checking-preferences)
   - dotnet\_style\_coalesce_expression
   - dotnet\_style\_null_propagation

### <a name="this-and-me"></a>"This." 修飾子 と "Me." 修飾子

このスタイル ルールは、フィールド、プロパティ、メソッド、またはイベントに適用できます。 **true** の値は、C# では `this.`、Visual Basic では `Me.` をコード記号の前に付けることを意味します。 **false** の値は、`this.` や `Me.` をコード要素の前に_付けない_ ことを意味します。

これらのルールは、次のように *.editorconfig* ファイルに表示されます。

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_qualification_for_field = false:suggestion
dotnet_style_qualification_for_property = false:suggestion
dotnet_style_qualification_for_method = false:suggestion
dotnet_style_qualification_for_event = false:suggestion
```

#### <a name="dotnetstylequalificationforfield"></a>dotnet\_style\_qualification\_for_field

|||
|-|-|
| **規則の名前** | dotnet_style_qualification_for_field |
| **ルール ID** | IDE0003、IDE0009 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - C# では `this.`、Visual Basic では `Me.` をフィールドの前に付けます<br /><br />`false` - フィールドの前に `this.` または `Me.` を付け "_ません_" |
| **Visual Studio の既定値** | `false:silent` |

コード例:

```csharp
// dotnet_style_qualification_for_field = true
this.capacity = 0;

// dotnet_style_qualification_for_field = false
capacity = 0;
```

```vb
' dotnet_style_qualification_for_field = true
Me.capacity = 0

' dotnet_style_qualification_for_field = false
capacity = 0
```

#### <a name="dotnetstylequalificationforproperty"></a>dotnet\_style\_qualification\_for_property

|||
|-|-|
| **規則の名前** | dotnet_style_qualification_for_property |
| **ルール ID** | IDE0003、IDE0009 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - C# では `this.`、Visual Basic では `Me.` をプロパティの前に付けます<br /><br />`false` - プロパティの前に `this.` または `Me.` を付け "_ません_" |
| **Visual Studio の既定値** | `false:silent` |

コード例:

```csharp
// dotnet_style_qualification_for_property = true
this.ID = 0;

// dotnet_style_qualification_for_property = false
ID = 0;
```

```vb
' dotnet_style_qualification_for_property = true
Me.ID = 0

' dotnet_style_qualification_for_property = false
ID = 0
```

#### <a name="dotnetstylequalificationformethod"></a>dotnet\_style\_qualification\_for_method

|||
|-|-|
| **規則の名前** | dotnet_style_qualification_for_method |
| **ルール ID** | IDE0003、IDE0009 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - C# では `this.`、Visual Basic では `Me.` をメソッドの前に付けます<br /><br />`false` - メソッドの前に `this.` または `Me.` を付け "_ません_" |
| **Visual Studio の既定値** | `false:silent` |

コード例:

```csharp
// dotnet_style_qualification_for_method = true
this.Display();

// dotnet_style_qualification_for_method = false
Display();
```

```vb
' dotnet_style_qualification_for_method = true
Me.Display()

' dotnet_style_qualification_for_method = false
Display()
```

#### <a name="dotnetstylequalificationforevent"></a>dotnet\_style\_qualification\_for_event

|||
|-|-|
| **規則の名前** | dotnet_style_qualification_for_event |
| **ルール ID** | IDE0003、IDE0009 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - C# では `this.`、Visual Basic では `Me.` をイベントの前に付けます<br /><br />`false` - イベントの前に `this.` または `Me.` を付け "_ません_" |
| **Visual Studio の既定値** | `false:silent` |

コード例:

```csharp
// dotnet_style_qualification_for_event = true
this.Elapsed += Handler;

// dotnet_style_qualification_for_event = false
Elapsed += Handler;
```

```vb
' dotnet_style_qualification_for_event = true
AddHandler Me.Elapsed, AddressOf Handler

' dotnet_style_qualification_for_event = false
AddHandler Elapsed, AddressOf Handler
```

### <a name="language-keywords"></a>型参照のためのフレームワーク型名の代わりの言語キーワード

このスタイル ルールは、ローカル変数、メソッド パラメーター、およびクラス メンバーに適用できます。また、型メンバー アクセス式に別個のルールとして適用できます。 **true** の値は、型を表すキーワードを持つ型に対して、型名 (`Int32` など) の代わりに言語キーワード (`int` や `Integer` など) を使用することを意味します。 **false** の値は、言語キーワードの代わりに型名を使用することを意味します。

これらのルールは、次のように *.editorconfig* ファイルに表示されます。

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_predefined_type_for_locals_parameters_members = true:suggestion
dotnet_style_predefined_type_for_member_access = true:suggestion
```

#### <a name="dotnetstylepredefinedtypeforlocalsparametersmembers"></a>dotnet\_style\_predefined\_type\_for\_locals\_parameters_members

|||
|-|-|
| **規則の名前** | dotnet_style_predefined_type_for_locals_parameters_members |
| **ルール ID** | IDE0012 と IDE0014 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - 型を表すキーワードを持つ型に対して、型名の代わりに、ローカル変数、メソッド パラメーター、およびクラス メンバーの言語キーワードを使用します<br /><br />`false` - 言語キーワードの代わりに、ローカル変数、メソッド パラメーター、およびクラス メンバーの型名を使用します |
| **Visual Studio の既定値** | `true:silent` |

コード例:

```csharp
// dotnet_style_predefined_type_for_locals_parameters_members = true
private int _member;

// dotnet_style_predefined_type_for_locals_parameters_members = false
private Int32 _member;
```

```vb
' dotnet_style_predefined_type_for_locals_parameters_members = true
Private _member As Integer

' dotnet_style_predefined_type_for_locals_parameters_members = false
Private _member As Int32
```

#### <a name="dotnetstylepredefinedtypeformemberaccess"></a>dotnet\_style\_predefined\_type\_for\_member_access

|||
|-|-|
| **規則の名前** | dotnet_style_predefined_type_for_member_access |
| **ルール ID** | IDE0013 と IDE0015 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - 型を表すキーワードを持つ型に対して、型名の代わりに、メンバー アクセス式の言語キーワードを使用します<br /><br />`false` - 言語キーワードの代わりに、メンバー アクセス式の型名を使用します |
| **Visual Studio の既定値** | `true:silent` |

コード例:

```csharp
// dotnet_style_predefined_type_for_member_access = true
var local = int.MaxValue;

// dotnet_style_predefined_type_for_member_access = false
var local = Int32.MaxValue;
```

```vb
' dotnet_style_predefined_type_for_member_access = true
Dim local = Integer.MaxValue

' dotnet_style_predefined_type_for_member_access = false
Dim local = Int32.MaxValue
```

### <a name="normalize-modifiers"></a>修飾子の基本設定

このセクションのスタイル ルールは、アクセシビリティ修飾子を必要にする、必要な修飾子の並べ替え順序を指定する、読み取り専用修飾子を必要にするなど、修飾子の基本設定に関するものです。

これらのルールは、次のように *.editorconfig* ファイルに表示されます。

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_require_accessibility_modifiers = always:suggestion
dotnet_style_readonly_field = true:warning

# CSharp code style settings:
[*.cs]
csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async:suggestion

# Visual Basic code style settings:
[*.vb]
visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async:suggestion
```

#### <a name="dotnetstylerequireaccessibilitymodifiers"></a>dotnet\_style\_require\_accessibility_modifiers

|||
|-|-|
| **規則の名前** | dotnet_style_require_accessibility_modifiers |
| **ルール ID** | IDE0040 |
| **該当言語** | C# および Visual Basic |
| **値** | `always` - アクセシビリティ修飾子を指定します。<br /><br />`for_non_interface_members` - パブリック インターフェイス メンバーの場合を除き、アクセシビリティ修飾子を宣言します。 (これは、**always** と同じであり、C# が既定のインターフェイス メソッドを追加する場合の将来の対策のために追加されています)。<br /><br />`never` - アクセシビリティ修飾子を指定しません。<br /><br />`omit_if_default` - 既定の修飾子である場合を除き、アクセシビリティ修飾子を指定することを優先します。 |
| **Visual Studio の既定値** | `for_non_interface_members:silent` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.5 |

コード例:

```csharp
// dotnet_style_require_accessibility_modifiers = always
// dotnet_style_require_accessibility_modifiers = for_non_interface_members
class MyClass
{
    private const string thisFieldIsConst = "constant";
}

// dotnet_style_require_accessibility_modifiers = never
class MyClass
{
    const string thisFieldIsConst = "constant";
}
```

#### <a name="csharppreferredmodifierorder"></a>csharp_preferred_modifier_order

|||
|-|-|
| **規則の名前** | csharp_preferred_modifier_order |
| **ルール ID** | IDE0036 |
| **該当言語** | C# |
| **値** | `public`、`private`、`protected` などの 1 つ以上の C# 修飾子 |
| **Visual Studio の既定値** | `public, private, protected, internal, static, extern, new, virtual, abstract, sealed, override, readonly, unsafe, volatile, async:silent` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.5 |

- このルールが修飾子のリストに設定されている場合は、指定された順序を優先します。
- ファイルでこのルールが省略されている場合は、修飾子の順序を優先しません。

コード例:

```csharp
// csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async
class MyClass
{
    private static readonly int _daysInYear = 365;
}
```

#### <a name="visualbasicpreferredmodifierorder"></a>visual_basic_preferred_modifier_order

|||
|-|-|
| **規則の名前** | visual_basic_preferred_modifier_order |
| **ルール ID** | IDE0036 |
| **該当言語** | Visual Basic |
| **値** | `Partial`、`Private`、`Public` などの 1 つ以上の Visual Basic 修飾子 |
| **Visual Studio の既定値** | `Partial, Default, Private, Protected, Public, Friend, NotOverridable, Overridable, MustOverride, Overloads, Overrides, MustInherit, NotInheritable, Static, Shared, Shadows, ReadOnly, WriteOnly, Dim, Const,WithEvents, Widening, Narrowing, Custom, Async:silent` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.5 |

- このルールが修飾子のリストに設定されている場合は、指定された順序を優先します。
- ファイルでこのルールが省略されている場合は、修飾子の順序を優先しません。

コード例:

```vb
' visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async
Public Class MyClass
    Private Shared ReadOnly daysInYear As Int = 365
End Class
```

#### <a name="dotnetstylereadonlyfield"></a>dotnet_style_readonly_field

|||
|-|-|
| **規則の名前** | dotnet_style_readonly_field |
| **ルール ID** | IDE0044 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - フィールドがインラインまたはコンストラクターの内部でのみ割り当てられている場合は、フィールドを `readonly` (C#) または `ReadOnly` (Visual Basic) でマークする必要があります<br /><br />`false` - フィールドを `readonly` (C#) または `ReadOnly` (Visual Basic) でマークする必要があるかどうかに関して特に規定がないことを指定します |
| **Visual Studio の既定値** | `true:suggestion` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.7 |

コード例:

```csharp
// dotnet_style_readonly_field = true
class MyClass
{
    private readonly int _daysInYear = 365;
}
```

```vb
' dotnet_style_readonly_field = true
Public Class MyClass
    Private ReadOnly daysInYear As Int = 365
End Class
```

### <a name="parentheses-preferences"></a>かっこの基本設定

このセクションのスタイル ルールは、算術演算子、関係演算子、およびその他の 2 項演算子でのかっこの使用を含む、かっこの基本設定に関するものです。

これらのルールは、次のように *.editorconfig* ファイルに表示されます。

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_operators = never_if_unnecessary:silent
```

#### <a name="dotnetstyleparenthesesinarithmeticbinaryoperators"></a>dotnet\_style\_parentheses\_in\_arithmetic\_binary_operators

|||
|-|-|
| **規則の名前** | dotnet_style_parentheses_in_arithmetic_binary_operators |
| **ルール ID** | IDE0047 |
| **該当言語** | C# および Visual Basic |
| **値** | `always_for_clarity` - 算術演算子 (`*`、`/`、`%`、`+`、`-`、`<<`、`>>`、`&`、`^`、`|`) の基本設定を明確にするためにかっこを使用します<br /><br />`never_if_unnecessary` - 算術演算子 (`*`、`/`、`%`、`+`、`-`、`<<`、`>>`、`&`、`^`、`|`) の基本設定が明確な場合はかっこを使用しません |
| **Visual Studio の既定値** | `always_for_clarity:silent` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.8 |

コード例:

```csharp
// dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity
var v = a + (b * c);

// dotnet_style_parentheses_in_arithmetic_binary_operators = never_if_unnecessary
var v = a + b * c;
```

```vb
' dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity
Dim v = a + (b * c)

' dotnet_style_parentheses_in_arithmetic_binary_operators = never_if_unnecessary
Dim v = a + b * c
```

#### <a name="dotnetstyleparenthesesinrelationalbinaryoperators"></a>dotnet\_style\_parentheses\_in\_relational\_binary_operators

|||
|-|-|
| **規則の名前** | dotnet_style_parentheses_in_relational_binary_operators |
| **ルール ID** | IDE0047 |
| **該当言語** | C# および Visual Basic |
| **値** | `always_for_clarity` - 関係演算子 (`>`、`<`、`<=`、`>=`、`is`、`as`、`==`、`!=`) の基本設定を明確にするためにかっこを使用します<br /><br />`never_if_unnecessary` - 関係演算子 (`>`、`<`、`<=`、`>=`、`is`、`as`、`==`、`!=`) の基本設定が明確な場合はかっこを使用しません |
| **Visual Studio の既定値** | `always_for_clarity:silent` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.8 |

コード例:

```csharp
// dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity
var v = (a < b) == (c > d);

// dotnet_style_parentheses_in_relational_binary_operators = never_if_unnecessary
var v = a < b == c > d;
```

```vb
' dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity
Dim v = (a < b) = (c > d)

' dotnet_style_parentheses_in_relational_binary_operators = never_if_unnecessary
Dim v = a < b = c > d
```

#### <a name="dotnetstyleparenthesesinotherbinaryoperators"></a>dotnet\_style\_parentheses\_in\_other\_binary_operators

|||
|-|-|
| **規則の名前** | dotnet_style_parentheses_in_other_binary_operators |
| **ルール ID** | IDE0047 |
| **該当言語** | C# および Visual Basic |
| **値** | `always_for_clarity` - 2 項演算子 (`&&`、`||`、`??`) の基本設定を明確にするためにかっこを使用します<br /><br />`never_if_unnecessary` - 2 項演算子 (`&&`、`||`、`??`) の基本設定が明確な場合はかっこを使用しません |
| **Visual Studio の既定値** | `always_for_clarity:silent` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.8 |

コード例:

```csharp
// dotnet_style_parentheses_in_other_binary_operators = always_for_clarity
var v = a || (b && c);

// dotnet_style_parentheses_in_other_binary_operators = never_if_unnecessary
var v = a || b && c;
```

```vb
' dotnet_style_parentheses_in_other_binary_operators = always_for_clarity
Dim v = a OrElse (b AndAlso c)

' dotnet_style_parentheses_in_other_binary_operators = never_if_unnecessary
Dim v = a OrElse b AndAlso c
```

#### <a name="dotnetstyleparenthesesinotheroperators"></a>dotnet\_style\_parentheses\_in\_other_operators

|||
|-|-|
| **規則の名前** | dotnet_style_parentheses_in_other_operators |
| **ルール ID** | IDE0047 |
| **該当言語** | C# および Visual Basic |
| **値** | `always_for_clarity` - 演算子の優先順位を明確にするためにかっこを使用します<br /><br />`never_if_unnecessary` - 演算子の優先順位が明確な場合はかっこを使用しません |
| **Visual Studio の既定値** | `never_if_unnecessary:silent` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.8 |

コード例:

```csharp
// dotnet_style_parentheses_in_other_operators = always_for_clarity
var v = (a.b).Length;

// dotnet_style_parentheses_in_other_operators = never_if_unnecessary
var v = a.b.Length;
```

```vb
' dotnet_style_parentheses_in_other_operators = always_for_clarity
Dim v = (a.b).Length

' dotnet_style_parentheses_in_other_operators = never_if_unnecessary
Dim v = a.b.Length
```

### <a name="expression-level-preferences"></a>式レベルの基本設定

このセクションのスタイル ルールは式レベル基本設定に関するものです。これには、オブジェクト初期化子、コレクション初期化子、明示的または推論されたタプル名、推定された匿名型が含まれます。

これらのルールは、次のように *.editorconfig* ファイルに表示されます。

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_object_initializer = true:suggestion
dotnet_style_collection_initializer = true:suggestion
dotnet_style_explicit_tuple_names = true:suggestion
dotnet_style_prefer_inferred_tuple_names = true:suggestion
dotnet_style_prefer_inferred_anonymous_type_member_names = true:suggestion
dotnet_style_prefer_auto_properties = true:silent
dotnet_style_prefer_conditional_expression_over_assignment = true:suggestion
dotnet_style_prefer_conditional_expression_over_return = true:suggestion
```

#### <a name="dotnetstyleobjectinitializer"></a>dotnet\_style\_object_initializer

|||
|-|-|
| **規則の名前** | dotnet_style_object_initializer |
| **ルール ID** | IDE0017 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - 可能であれば、オブジェクト初期化子を使用し、オブジェクトを初期化します<br /><br />`false` - オブジェクト初期化子でオブジェクトを初期化 "*しません*" |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// dotnet_style_object_initializer = true
var c = new Customer() { Age = 21 };

// dotnet_style_object_initializer = false
var c = new Customer();
c.Age = 21;
```

```vb
' dotnet_style_object_initializer = true
Dim c = New Customer() With {.Age = 21}

' dotnet_style_object_initializer = false
Dim c = New Customer()
c.Age = 21
```

#### <a name="dotnetstylecollectioninitializer"></a>dotnet\_style\_collection_initializer

|||
|-|-|
| **規則の名前** | dotnet_style_collection_initializer |
| **ルール ID** | IDE0028 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - 可能であれば、コレクション初期化子を使用してコレクションを初期化します<br /><br />`false` - コレクション初期化子でコレクションを初期化 "*しません*" |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// dotnet_style_collection_initializer = true
var list = new List<int> { 1, 2, 3 };

// dotnet_style_collection_initializer = false
var list = new List<int>();
list.Add(1);
list.Add(2);
list.Add(3);
```

```vb
' dotnet_style_collection_initializer = true
Dim list = New List(Of Integer) From {1, 2, 3}

' dotnet_style_collection_initializer = false
Dim list = New List(Of Integer)
list.Add(1)
list.Add(2)
list.Add(3)
```

#### <a name="dotnetstyleexplicittuplenames"></a>dotnet\_style\_explicit\_tuple_names

|||
|-|-|
| **規則の名前** | dotnet_style_explicit_tuple_names |
| **ルール ID** | IDE0033 |
| **該当言語** | C# 7.0+ および Visual Basic 15+ |
| **値** | `true` - ItemX プロパティではなくタプル名を使用します<br /><br />`false` - タプル名ではなく ItemX プロパティを使用します |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// dotnet_style_explicit_tuple_names = true
(string name, int age) customer = GetCustomer();
var name = customer.name;

// dotnet_style_explicit_tuple_names = false
(string name, int age) customer = GetCustomer();
var name = customer.Item1;
```

```vb
 ' dotnet_style_explicit_tuple_names = true
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.name

' dotnet_style_explicit_tuple_names = false
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.Item1
```

#### <a name="dotnetstylepreferinferredtuplenames"></a>dotnet\_style\_prefer\_inferred\_tuple_names

|||
|-|-|
| **規則の名前** | dotnet_style_prefer_inferred_tuple_names |
| **ルール ID** | IDE0037 |
| **該当言語** | C# 7.1+ および Visual Basic 15+ |
| **値** | `true` - 推論されたタプル要素名が優先されます<br /><br />`false` - 明示的なタプル要素名が優先されます |
| **Visual Studio の既定値** | `true:suggestion` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.6 |

コード例:

```csharp
// dotnet_style_prefer_inferred_tuple_names = true
var tuple = (age, name);

// dotnet_style_prefer_inferred_tuple_names = false
var tuple = (age: age, name: name);
```

```vb
' dotnet_style_prefer_inferred_tuple_names = true
Dim tuple = (name, age)

' dotnet_style_prefer_inferred_tuple_names = false
Dim tuple = (name:=name, age:=age)
```

#### <a name="dotnetstylepreferinferredanonymoustypemembernames"></a>dotnet\_style\_prefer\_inferred\_anonymous\_type\_member_names

|||
|-|-|
| **規則の名前** | dotnet_style_prefer_inferred_anonymous_type_member_names |
| **ルール ID** | IDE0037 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - 推論された匿名型のメンバー名が優先されます<br /><br />`false` - 明示的な匿名型のメンバー名が優先されます |
| **Visual Studio の既定値** | `true:suggestion` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.6 |

コード例:

```csharp
// dotnet_style_prefer_inferred_anonymous_type_member_names = true
var anon = new { age, name };

// dotnet_style_prefer_inferred_anonymous_type_member_names = false
var anon = new { age = age, name = name };
```

```vb
' dotnet_style_prefer_inferred_anonymous_type_member_names = true
Dim anon = New With {name, age}

' dotnet_style_prefer_inferred_anonymous_type_member_names = false
Dim anon = New With {.name = name, .age = age}
```

#### <a name="dotnetstylepreferautoproperties"></a>dotnet\_style\_prefer\_auto\_properties

|||
|-|-|
| **規則の名前** | dotnet_style_prefer_auto_properties |
| **ルール ID** | IDE0032 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - プライベート バッキング フィールドを持つプロパティよりも、自動プロパティが優先されます<br /><br />`false` - 自動プロパティよりも、プライベート バッキング フィールドを持つプロパティが優先されます |
| **Visual Studio の既定値** | `true:suggestion` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.7 |

コード例:

```csharp
// dotnet_style_prefer_auto_properties = true
private int Age { get; }

// dotnet_style_prefer_auto_properties = false
private int age;

public int Age
{
    get
    {
        return age;
    }
}
```

```vb
' dotnet_style_prefer_auto_properties = true
Public ReadOnly Property Age As Integer

' dotnet_style_prefer_auto_properties = false
Private _age As Integer

Public ReadOnly Property Age As Integer
    Get
        return _age
    End Get
End Property
```

#### <a name="dotnetstylepreferisnullcheckoverreferenceequalitymethod"></a>dotnet\_style\_prefer\_is\_null\_check\_over\_reference\_equality\_method

|||
|-|-|
| **規則の名前** | dotnet_style_prefer_is_null_check_over_reference_equality_method |
| **ルール ID** | IDE0041 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - `object.ReferenceEquals` より、パターン一致の NULL 検査の使用が優先されます<br /><br />`false` - パターン一致の NULL 検査より `object.ReferenceEquals` が優先されます |
| **Visual Studio の既定値** | `true:suggestion` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.7 |

コード例:

```csharp
// dotnet_style_prefer_is_null_check_over_reference_equality_method = true
if (value is null)
    return;

// dotnet_style_prefer_is_null_check_over_reference_equality_method = false
if (object.ReferenceEquals(value, null))
    return;
```

```vb
' dotnet_style_prefer_is_null_check_over_reference_equality_method = true
If value Is Nothing
    Return
End If

' dotnet_style_prefer_is_null_check_over_reference_equality_method = false
If Object.ReferenceEquals(value, Nothing)
    Return
End If
```

#### <a name="dotnetstylepreferconditionalexpressionoverassignment"></a>dotnet\_style\_prefer\_conditional\_expression\_over_assignment

|||
|-|-|
| **規則の名前** | dotnet_style_prefer_conditional_expression_over_assignment |
| **ルール ID** | IDE0045 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - if-else ステートメントよりも三項条件を使用する割り当てを優先します<br /><br />`false` - 三項条件よりも if-else ステートメントを使用する割り当てを優先します |
| **Visual Studio の既定値** | `true:suggestion` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.8 |

コード例:

```csharp
// dotnet_style_prefer_conditional_expression_over_assignment = true
string s = expr ? "hello" : "world";

// dotnet_style_prefer_conditional_expression_over_assignment = false
string s;
if (expr)
{
    s = "hello";
}
else
{
    s = "world";
}
```

```vb
' dotnet_style_prefer_conditional_expression_over_assignment = true
Dim s As String = If(expr, "hello", "world")

' dotnet_style_prefer_conditional_expression_over_assignment = false
Dim s As String
If expr Then
    s = "hello"
Else
    s = "world"
End If
```

#### <a name="dotnetstylepreferconditionalexpressionoverreturn"></a>dotnet\_style\_prefer\_conditional\_expression\_over_return

|||
|-|-|
| **規則の名前** | dotnet_style_prefer_conditional_expression_over_return |
| **ルール ID** | IDE0046 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - if-else ステートメントよりも三項条件を使用する return ステートメントを優先します<br /><br />`false` - 三項条件よりも if-else ステートメントを使用する return ステートメントを優先します |
| **Visual Studio の既定値** | `true:suggestion` |
| **導入されたバージョン** | Visual Studio 2017 バージョン 15.8 |

コード例:

```csharp
// dotnet_style_prefer_conditional_expression_over_return = true
return expr ? "hello" : "world"

// dotnet_style_prefer_conditional_expression_over_return = false
if (expr)
{
    return "hello";
}
else
{
    return "world";
}
```

```vb
' dotnet_style_prefer_conditional_expression_over_return = true
Return If(expr, "hello", "world")

' dotnet_style_prefer_conditional_expression_over_return = false
If expr Then
    Return "hello"
Else
    Return "world"
End If
```

### <a name="null-checking-preferences"></a>"Null" 検査設定

このセクションのスタイル ルールは、null 検査設定が関係します。

これらのルールは、次のように *.editorconfig* ファイルに表示されます。

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_coalesce_expression = true:suggestion
dotnet_style_null_propagation = true:suggestion
```

#### <a name="dotnetstylecoalesceexpression"></a>dotnet\_style\_coalesce_expression

|||
|-|-|
| **規則の名前** | dotnet_style_coalesce_expression |
| **ルール ID** | IDE0029 |
| **該当言語** | C# および Visual Basic |
| **値** | `true` - 三項演算子検査ではなく null 結合式を使用します<br /><br />`false` - null 結合式ではなく三項演算子検査を使用します |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// dotnet_style_coalesce_expression = true
var v = x ?? y;

// dotnet_style_coalesce_expression = false
var v = x != null ? x : y; // or
var v = x == null ? y : x;
```

```vb
' dotnet_style_coalesce_expression = true
Dim v = If(x, y)

' dotnet_style_coalesce_expression = false
Dim v = If(x Is Nothing, y, x) ' or
Dim v = If(x IsNot Nothing, x, y)
```

#### <a name="dotnetstylenullpropagation"></a>dotnet\_style\_null_propagation

|||
|-|-|
| **規則の名前** | dotnet_style_null_propagation |
| **ルール ID** | IDE0031 |
| **該当言語** | C# 6.0+ および Visual Basic 14+ |
| **値** | `true` - 可能であれば、null 条件演算子を使用します<br /><br />`false` - 可能であれば、三項 null 検査を使用します |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// dotnet_style_null_propagation = true
var v = o?.ToString();

// dotnet_style_null_propagation = false
var v = o == null ? null : o.ToString(); // or
var v = o != null ? o.String() : null;
```

```vb
' dotnet_style_null_propagation = true
Dim v = o?.ToString()

' dotnet_style_null_propagation = false
Dim v = If(o Is Nothing, Nothing, o.ToString()) ' or
Dim v = If(o IsNot Nothing, o.ToString(), Nothing)
```

## <a name="c-code-style-settings"></a>C# コード スタイルの設定

このセクションのスタイル ルールは、C# のみに適用されます。

- [暗黙的な型と明示的な型](#implicit-and-explicit-types)
   - csharp\_style\_var\_for\_built\_in_types
   - csharp\_style\_var\_when\_type\_is_apparent
   - csharp\_style\_var_elsewhere
- [式形式のメンバー](#expression-bodied-members)
   - csharp\_style\_expression\_bodied_methods
   - csharp\_style\_expression\_bodied_constructors
   - csharp\_style\_expression\_bodied_operators
   - csharp\_style\_expression\_bodied_properties
   - csharp\_style\_expression\_bodied_indexers
   - csharp\_style\_expression\_bodied_accessors
- [パターン マッチング](#pattern-matching)
   - csharp\_style\_pattern\_matching\_over\_is\_with\_cast_check
   - csharp\_style\_pattern\_matching\_over\_as\_with\_null_check
- [インライン変数宣言](#inlined-variable-declarations)
   - csharp\_style\_inlined\_variable_declaration
- [式レベル基本設定](#expression-level-preferences)
   - csharp\_prefer\_simple\_default_expression
   - csharp\_style\_deconstructed\_variable_declaration
   - csharp\_style\_pattern\_local\_over\_anonymous_function
- ["null" チェック設定](#null-checking-preferences)
   - csharp\_style\_throw_expression
   - csharp\_style\_conditional\_delegate_call
- [コード ブロック基本設定](#code-block-preferences)
   - csharp\_prefer_braces

### <a name="implicit-and-explicit-types"></a>暗黙的な型と明示的な型

このセクションのスタイル ルールは、変数宣言での [var](/dotnet/csharp/language-reference/keywords/var) キーワードと明示的な型の使用に関するものです。 このルールは、ビルトイン型、型が明らかな場合、および他の場所に個別に適用できます。

*.editorconfig* ファイルの例:

```ini
# CSharp code style settings:
[*.cs]
csharp_style_var_for_built_in_types = true:suggestion
csharp_style_var_when_type_is_apparent = true:suggestion
csharp_style_var_elsewhere = true:suggestion
```

#### <a name="csharpstylevarforbuiltintypes"></a>csharp\_style\_var\_for\_built\_in_types

|||
|-|-|
| **規則の名前** | csharp_style_var_for_built_in_types |
| **ルール ID** | IDE0007、IDE0008 |
| **該当言語** | C#  |
| **値** | `true` - `int` などのビルトイン システム型で変数を宣言する場合に `var` を使用します<br /><br />`false` - `int` などのビルトイン システム型で変数を宣言する場合に `var` ではなく明示的な型を使用します。 |
| **Visual Studio の既定値** | `true:silent` |

コード例:

```csharp
// csharp_style_var_for_built_in_types = true
var x = 5;

// csharp_style_var_for_built_in_types = false
int x = 5;
```

#### <a name="csharpstylevarwhentypeisapparent"></a>csharp\_style\_var\_when\_type\_is_apparent

|||
|-|-|
| **規則の名前** | csharp_style_var_when_type_is_apparent |
| **ルール ID** | IDE0007、IDE0008 |
| **該当言語** | C#  |
| **値** | `true` - 宣言式の右側で型が既に述べられているときに `var` を使用します<br /><br />`false` - 宣言式の右側で型が既に示されているときに `var` ではなく明示的な型を使用します |
| **Visual Studio の既定値** | `true:silent` |

コード例:

```csharp
// csharp_style_var_when_type_is_apparent = true
var obj = new Customer();

// csharp_style_var_when_type_is_apparent = false
Customer obj = new Customer();
```

#### <a name="csharpstylevarelsewhere"></a>csharp\_style\_var_elsewhere

|||
|-|-|
| **規則の名前** | csharp_style_var_elsewhere |
| **ルール ID** | IDE0007、IDE0008 |
| **該当言語** | C#  |
| **値** | `true` - 別のコード スタイル ルールでオーバーライドされない限り、すべての場合に明示的な型ではなく `var` を使用します<br /><br />`false` - 別のコード スタイル ルールでオーバーライドされない限り、すべての場合に `var` ではなく明示的な型を使用します |
| **Visual Studio の既定値** | `true:silent` |

コード例:

```csharp
// csharp_style_var_elsewhere = true
var f = this.Init();

// csharp_style_var_elsewhere = false
bool f = this.Init();
```

### <a name="expression-bodied-members"></a>式形式のメンバー

このセクションのスタイル ルールは、ロジックが単一の式で構成される場合の[式形式のメンバー](/dotnet/csharp/programming-guide/statements-expressions-operators/expression-bodied-members)の使用に関するものです。 このルールは、メソッド、コンストラクター、演算子、プロパティ、インデクサー、およびアクセサーに適用できます。

*.editorconfig* ファイルの例:

```ini
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_methods = false:silent
csharp_style_expression_bodied_constructors = false:silent
csharp_style_expression_bodied_operators = false:silent
csharp_style_expression_bodied_properties = true:suggestion
csharp_style_expression_bodied_indexers = true:suggestion
csharp_style_expression_bodied_accessors = true:suggestion
```

#### <a name="csharpstyleexpressionbodiedmethods"></a>csharp\_style\_expression\_bodied_methods

|||
|-|-|
| **規則の名前** | csharp_style_expression_bodied_methods |
| **ルール ID** | IDE0022 |
| **該当言語** | C# 6.0+  |
| **値** | `true` - メソッドに式形式メンバーを使用します<br /><br />`when_on_single_line` - 単一行になる場合は、メソッドに式形式メンバーを使用します<br /><br />`false` - メソッドにブロック本体を使用します |
| **Visual Studio の既定値** | `false:silent` |

コード例:

```csharp
// csharp_style_expression_bodied_methods = true
public int GetAge() => this.Age;

// csharp_style_expression_bodied_methods = false
public int GetAge() { return this.Age; }
```

#### <a name="csharpstyleexpressionbodiedconstructors"></a>csharp\_style\_expression\_bodied_constructors

|||
|-|-|
| **規則の名前** | csharp_style_expression_bodied_constructors |
| **ルール ID** | IDE0021 |
| **該当言語** | C# 7.0+  |
| **値** | `true` - コンストラクターに式形式メンバーを使用します<br /><br />`when_on_single_line` - 単一行になる場合は、コンストラクターに式形式メンバーを使用します<br /><br />`false` - コンストラクターにブロック本体を使用します |
| **Visual Studio の既定値** | `false:silent` |

コード例:

```csharp
// csharp_style_expression_bodied_constructors = true
public Customer(int age) => Age = age;

// csharp_style_expression_bodied_constructors = false
public Customer(int age) { Age = age; }
```

#### <a name="csharpstyleexpressionbodiedoperators"></a>csharp\_style\_expression\_bodied_operators

|||
|-|-|
| **規則の名前** | csharp_style_expression_bodied_operators |
| **ルール ID** | IDE0023 と IDE0024 |
| **該当言語** | C# 7.0+  |
| **値** | `true` - 演算子に式形式メンバーを使用します<br /><br />`when_on_single_line` - 単一行になる場合は、演算子に式形式メンバーを使用します<br /><br />`false` - 演算子にブロック本体を使用します |
| **Visual Studio の既定値** | `false:silent` |

コード例:

```csharp
// csharp_style_expression_bodied_operators = true
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
    => new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);

// csharp_style_expression_bodied_operators = false
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
{ return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary); }
```

#### <a name="csharpstyleexpressionbodiedproperties"></a>csharp\_style\_expression\_bodied_properties

|||
|-|-|
| **規則の名前** | csharp_style_expression_bodied_properties |
| **ルール ID** | IDE0025 |
| **該当言語** | C# 7.0+  |
| **値** | `true` - プロパティに式形式メンバーを使用します<br /><br />`when_on_single_line` - 単一行になる場合は、プロパティに式形式メンバーを使用します<br /><br />`false` - プロパティにブロック本体を使用します |
| **Visual Studio の既定値** | `true:silent` |

コード例:

```csharp
// csharp_style_expression_bodied_properties = true
public int Age => _age;

// csharp_style_expression_bodied_properties = false
public int Age { get { return _age; }}
```

#### <a name="csharpstyleexpressionbodiedindexers"></a>csharp\_style\_expression\_bodied_indexers

|||
|-|-|
| **規則の名前** | csharp_style_expression_bodied_indexers |
| **ルール ID** | IDE0026 |
| **該当言語** | C# 7.0+  |
| **値** | `true` - インデクサーに式形式メンバーを使用します<br /><br />`when_on_single_line` - 単一行になる場合は、インデクサーに式形式メンバーを使用します<br /><br />`false` - インデクサーにブロック本体を使用します |
| **Visual Studio の既定値** | `true:silent` |

コード例:

```csharp
// csharp_style_expression_bodied_indexers = true
public T this[int i] => _values[i];

// csharp_style_expression_bodied_indexers = false
public T this[int i] { get { return _values[i]; } }
```

#### <a name="csharpstyleexpressionbodiedaccessors"></a>csharp\_style\_expression\_bodied_accessors

|||
|-|-|
| **規則の名前** | csharp_style_expression_bodied_accessors |
| **ルール ID** | IDE0027 |
| **該当言語** | C# 7.0+  |
| **値** | `true` - アクセサーに式形式メンバーを使用します<br /><br />`when_on_single_line` - 単一行になる場合は、アクセサーに式形式メンバーを使用します<br /><br />`false` - アクセサーにブロック本体を使用します |
| **Visual Studio の既定値** | `true:silent` |

コード例:

```csharp
// csharp_style_expression_bodied_accessors = true
public int Age { get => _age; set => _age = value; }

// csharp_style_expression_bodied_accessors = false
public int Age { get { return _age; } set { _age = value; } }
```

### <a name="pattern-matching"></a>パターン マッチング

このセクションのスタイル ルールは、C# での[パターン マッチング](/dotnet/csharp/pattern-matching)の使用に関するものです。

*.editorconfig* ファイルの例:

```ini
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion
```

#### <a name="csharpstylepatternmatchingoveriswithcastcheck"></a>csharp\_style\_pattern\_matching\_over\_is\_with\_cast_check

|||
|-|-|
| **規則の名前** | csharp_style_pattern_matching_over_is_with_cast_check |
| **ルール ID** | IDE0020 |
| **該当言語** | C# 7.0+  |
| **値** | `true` - `is` 式と型キャストの代わりにパターン マッチングを使用します<br /><br />`false` - パターン マッチングの代わりに `is` 式と型キャストを使用します |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// csharp_style_pattern_matching_over_is_with_cast_check = true
if (o is int i) {...}

// csharp_style_pattern_matching_over_is_with_cast_check = false
if (o is int) {var i = (int)o; ... }
```

#### <a name="csharpstylepatternmatchingoveraswithnullcheck"></a>csharp\_style\_pattern\_matching\_over\_as\_with\_null_check

|||
|-|-|
| **規則の名前** | csharp_style_pattern_matching_over_as_with_null_check |
| **ルール ID** | IDE0019 |
| **該当言語** | C# 7.0+  |
| **値** | `true` - `as` 式と null 検査の代わりにパターン マッチングを使用し、何かが特定の型であるか判断します<br /><br />`false` - パターン マッチングの代わりに `as` 式と null 検査を使用し、何かが特定の型であるか判断します |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// csharp_style_pattern_matching_over_as_with_null_check = true
if (o is string s) {...}

// csharp_style_pattern_matching_over_as_with_null_check = false
var s = o as string;
if (s != null) {...}
```

### <a name="inlined-variable-declarations"></a>インライン変数宣言

このスタイル ルールは、`out` 変数がインラインで宣言されるかどうかに関するものです。 C# 7 以降では、別の変数宣言内ではなく、[メソッド呼び出しの引数リスト内で out 変数を宣言](/dotnet/csharp/language-reference/keywords/out-parameter-modifier#calling-a-method-with-an-out-argument)できます。

#### <a name="csharpstyleinlinedvariabledeclaration"></a>csharp\_style\_inlined\_variable_declaration

|||
|-|-|
| **規則の名前** | csharp_style_inlined_variable_declaration |
| **ルール ID** | IDE0018 |
| **該当言語** | C# 7.0+  |
| **値** | `true` - 可能であれば、メソッド呼び出しの引数リスト内で `out` 変数をインラインで宣言します<br /><br />`false` - メソッド呼び出しの前に `out` 変数を宣言します |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// csharp_style_inlined_variable_declaration = true
if (int.TryParse(value, out int i) {...}

// csharp_style_inlined_variable_declaration = false
int i;
if (int.TryParse(value, out i) {...}
```

*.editorconfig* ファイルの例:

```ini
# CSharp code style settings:
[*.cs]
csharp_style_inlined_variable_declaration = true:suggestion
```

### <a name="expression-level-preferences"></a>式レベルの基本設定

このセクションのスタイル ルールは、[既定の式](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference)、分解された変数、匿名関数よりローカル関数を使用するなど、式レベル基本設定に関するものです。

*.editorconfig* ファイルの例:

```ini
# CSharp code style settings:
[*.cs]
csharp_prefer_simple_default_expression = true:suggestion
csharp_style_deconstructed_variable_declaration = true:suggestion
csharp_style_pattern_local_over_anonymous_function = true:suggestion
```

#### <a name="csharpprefersimpledefaultexpression"></a>csharp\_prefer\_simple\_default_expression

このスタイル ルールは、コンパイラが式の型を推定できる場合の、[既定の値式での `default` リテラル](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference)の使用に関するものです。

|||
|-|-|
| **規則の名前** | csharp_prefer_simple_default_expression |
| **ルール ID** | IDE0034 |
| **該当言語** | C# 7.1+  |
| **値** | `true` - `default` を `default(T)` より優先します<br /><br />`false` - `default(T)` を `default` より優先します |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// csharp_prefer_simple_default_expression = true
void DoWork(CancellationToken cancellationToken = default) { ... }

// csharp_prefer_simple_default_expression = false
void DoWork(CancellationToken cancellationToken = default(CancellationToken)) { ... }
```

#### <a name="csharpstyledeconstructedvariabledeclaration"></a>csharp\_style\_deconstructed\_variable_declaration

|||
|-|-|
| **規則の名前** | csharp_style_deconstructed_variable_declaration |
| **ルール ID** | IDE0042 |
| **該当言語** | C# 7.0+  |
| **値** | `true` - 分解された変数宣言を優先します<br /><br />`false` - 変数宣言では分解を優先しません |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// csharp_style_deconstructed_variable_declaration = true
var (name, age) = GetPersonTuple();
Console.WriteLine($"{name} {age}");

(int x, int y) = GetPointTuple();
Console.WriteLine($"{x} {y}");

// csharp_style_deconstructed_variable_declaration = false
var person = GetPersonTuple();
Console.WriteLine($"{person.name} {person.age}");

(int x, int y) point = GetPointTuple();
Console.WriteLine($"{point.x} {point.y}");
```

#### <a name="csharpstylepatternlocaloveranonymousfunction"></a>csharp\_style\_pattern\_local\_over\_anonymous_function

|||
|-|-|
| **規則の名前** | csharp_style_pattern_local_over_anonymous_function |
| **ルール ID** | IDE0039 |
| **該当言語** | C# 7.0+  |
| **値** | `true` - 匿名関数よりローカル関数を優先します<br /><br />`false` - ローカル関数より匿名関数を優先します |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// csharp_style_pattern_local_over_anonymous_function = true
int fibonacci(int n)
{
    return n <= 1 ? 1 : fibonacci(n-1) + fibonacci(n-2);
}

// csharp_style_pattern_local_over_anonymous_function = false
Func<int, int> fibonacci = null;
fibonacci = (int n) =>
{
    return n <= 1 ? 1 : fibonacci(n - 1) + fibonacci(n - 2);
};
```

### <a name="null-checking-preferences"></a>"Null" 検査設定

これらのスタイル ルールは、`throw` 式または `throw` ステートメントの使用や、null チェックを実行するか、[ラムダ式](/dotnet/csharp/lambda-expressions)の呼び出し時に条件付き合体演算子 (`?.`) を使用するかなどの、`null` チェックの構文に関するものです。

*.editorconfig* ファイルの例:

```ini
# CSharp code style settings:
[*.cs]
csharp_style_throw_expression = true:suggestion
csharp_style_conditional_delegate_call = false:suggestion
```

#### <a name="csharpstylethrowexpression"></a>csharp\_style\_throw_expression

|||
|-|-|
| **規則の名前** | csharp_style_throw_expression |
| **ルール ID** | IDE0016 |
| **該当言語** | C# 7.0+  |
| **値** | `true` - `throw` ステートメントの代わりに `throw` 式を使用します<br /><br />`false` - `throw` 式の代わりに `throw` ステートメントを使用します |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// csharp_style_throw_expression = true
this.s = s ?? throw new ArgumentNullException(nameof(s));

// csharp_style_throw_expression = false
if (s == null) { throw new ArgumentNullException(nameof(s)); }
this.s = s;
```

#### <a name="csharpstyleconditionaldelegatecall"></a>csharp\_style\_conditional\_delegate_call

|||
|-|-|
| **規則の名前** | csharp_style_conditional_delegate_call |
| **ルール ID** | IDE0041 |
| **該当言語** | C# 6.0+  |
| **値** | `true` - null チェックを実行する代わりに、ラムダ式の呼び出し時に条件付き合体演算子 (`?.`) を使用します<br /><br />`false` - 条件付き合体演算子 (`?.`) を使用する代わりに、ラムダ式を呼び出す前に null チェックを実行します |
| **Visual Studio の既定値** | `true:suggestion` |

コード例:

```csharp
// csharp_style_conditional_delegate_call = true
func?.Invoke(args);

// csharp_style_conditional_delegate_call = false
if (func != null) { func(args); }
```

### <a name="code-block-preferences"></a>コード ブロックの基本設定

このスタイル ルールは、コード ブロックを囲む中かっこ `{ }` の使用に関するものです。

*.editorconfig* ファイルの例:

```ini
# CSharp code style settings:
[*.cs]
csharp_prefer_braces = true:silent
```

#### <a name="csharppreferbraces"></a>csharp\_prefer\_braces

|||
|-|-|
| **規則の名前** | csharp_prefer_braces |
| **ルール ID** | IDE0011 |
| **該当言語** | C# |
| **値** | `true` - コードが 1 行であっても中かっこを使用します<br /><br />`false` - 中かっこは使用しません (許可されている場合) |
| **Visual Studio の既定値** | `true:silent` |

コード例:

```csharp
// csharp_prefer_braces = true
if (test) { this.Display(); }

// csharp_prefer_braces = false
if (test) this.Display();
```

## <a name="see-also"></a>関連項目

- [書式規則](editorconfig-formatting-conventions.md)
- [名前付け規則](editorconfig-naming-conventions.md)
- [EditorConfig の .NET コーディング規則の設定](editorconfig-code-style-settings-reference.md)