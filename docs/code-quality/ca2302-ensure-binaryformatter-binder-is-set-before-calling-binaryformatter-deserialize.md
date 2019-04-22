---
title: CA2302:BinaryFormatter.Deserialize を呼び出す前に BinaryFormatter.Binder が設定されていることを確認します
ms.date: 04/05/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fb997d8184ea9459b46eee95bfe2863e8c1c6ed0
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59367290"
---
# <a name="ca2302-ensure-binaryformatterbinder-is-set-before-calling-binaryformatterdeserialize"></a>CA2302:BinaryFormatter.Deserialize を呼び出す前に BinaryFormatter.Binder が設定されていることを確認します

|||
|-|-|
|TypeName|EnsureBinaryFormatterBinderIsSetBeforeCallingBinaryFormatterDeserialize|
|CheckId|CA2302|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

A<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>逆シリアル化メソッドが呼び出されるか、参照されていると、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>プロパティを null にすることがあります。

## <a name="rule-description"></a>規則の説明

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

このルールは、検索<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>メソッドの呼び出しまたは参照を逆シリアル化時に<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>ときにその<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>が null でいます。 逆シリアル化を禁止する場合<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>に関係なく、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>プロパティでは、このルールを無効にして[CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)、ルールを有効にして[CA2300](ca2300-do-not-use-insecure-deserializer-binaryformatter.md)します。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 可能であれば、代わりに、セキュリティで保護されたシリアライザーを使用し、**攻撃者を任意の型を逆シリアル化の指定を許可しない**します。 安全なシリアライザーによっては、次のとおりです。
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -使用しないでください<xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>します。 型競合回避モジュールを使用する必要がありますがする必要があります、予想されるリストを逆シリアル化された型が制限されます。
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - NewtonSoft Json.NET - TypeNameHandling.None を使用します。 TypeNameHandling を別の値を使用する必要がありますがある場合は、予想されるリストに、逆シリアル化された型を制限する必要があります。
  - Protocol Buffers
- シリアル化されたデータの改ざんを作成します。 シリアル化後に、シリアル化されたデータを暗号で署名します。 逆シリアル化する前に、暗号化署名を検証します。 公開される暗号化キーを保護する必要があり、キーのローテーションを設計する必要があります。
- 逆シリアル化された型を制限します。 カスタムの実装<xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>します。 逆シリアル化する前に<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>、設定、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>プロパティ、カスタムのインスタンスを<xref:System.Runtime.Serialization.SerializationBinder>します。 オーバーライドされた<xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>し、メソッド、型が予想される場合は例外をスローします。
  - すべてのコード パスがいることを確認、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>プロパティ セット。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

- 入力が信頼されていることがわかっている場合、この規則による警告を抑制するのには安全です。 時間の経過と共に変更することがあります、アプリケーションの信頼の境界とデータ フローを検討してください。
- 上の予防策のいずれかを取得した場合、この警告を抑制するのには安全です。

## <a name="pseudo-code-examples"></a>疑似コードの例

### <a name="violation"></a>違反

```csharp
using System;
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;

[Serializable]
public class BookRecord
{
    public string Title { get; set; }
    public string Author { get; set; }
    public int PageCount { get; set; }
    public AisleLocation Location { get; set; }
}

[Serializable]
public class AisleLocation
{
    public char Aisle { get; set; }
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public BinaryFormatter Formatter { get; set; }

    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) this.Formatter.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization.Formatters.Binary

<Serializable()>
Public Class BookRecord
    Public Property Title As String
    Public Property Author As String
    Public Property Location As AisleLocation
End Class

<Serializable()>
Public Class AisleLocation
    Public Property Aisle As Char
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Property Formatter As BinaryFormatter

    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(Me.Formatter.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

### <a name="solution"></a>ソリューション
```csharp
using System;
using System.IO;
using System.Runtime.Serialization;
using System.Runtime.Serialization.Formatters.Binary;

public class BookRecordSerializationBinder : SerializationBinder
{
    public override Type BindToType(string assemblyName, string typeName)
    {
        // One way to discover expected types is through testing deserialization
        // of **valid** data and logging the types used.

        ////Console.WriteLine($"BindToType('{assemblyName}', '{typeName}')");

        if (typeName == "BookRecord" || typeName == "AisleLocation")
        {
            return null;
        }
        else
        {
            throw new ArgumentException("Unexpected type", "typeName");
        }
    }
}

[Serializable]
public class BookRecord
{
    public string Title { get; set; }
    public string Author { get; set; }
    public int PageCount { get; set; }
    public AisleLocation Location { get; set; }
}

[Serializable]
public class AisleLocation
{
    public char Aisle { get; set; }
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        BinaryFormatter formatter = new BinaryFormatter();
        formatter.Binder = new BookRecordSerializationBinder();
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) formatter.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization
Imports System.Runtime.Serialization.Formatters.Binary

Public Class BookRecordSerializationBinder
    Inherits SerializationBinder

    Public Overrides Function BindToType(assemblyName As String, typeName As String) As Type
        ' One way to discover expected types is through testing deserialization
        ' of **valid** data and logging the types used.

        'Console.WriteLine($"BindToType('{assemblyName}', '{typeName}')")

        If typeName = "BinaryFormatterVB.BookRecord" Or typeName = "BinaryFormatterVB.AisleLocation" Then
            Return Nothing
        Else
            Throw New ArgumentException("Unexpected type", "typeName")
        End If
    End Function
End Class

<Serializable()>
Public Class BookRecord
    Public Property Title As String
    Public Property Author As String
    Public Property Location As AisleLocation
End Class

<Serializable()>
Public Class AisleLocation
    Public Property Aisle As Char
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Dim formatter As BinaryFormatter = New BinaryFormatter()
        formatter.Binder = New BookRecordSerializationBinder()
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(formatter.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

## <a name="related-rules"></a>関連するルール

[CA2300:安全でないデシリアライザー BinaryFormatter を使用しないでください。](ca2300-do-not-use-insecure-deserializer-binaryformatter.md)

[CA2301:最初の設定 BinaryFormatter.Binder せず BinaryFormatter.Deserialize を呼び出さないでください。](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)
