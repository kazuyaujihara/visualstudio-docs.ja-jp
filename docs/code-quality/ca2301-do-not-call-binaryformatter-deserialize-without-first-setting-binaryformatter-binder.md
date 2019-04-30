---
title: CA2301:最初に BinaryFormatter.Binder を設定しないで BinaryFormatter.Deserialize を呼び出さないでください
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
ms.openlocfilehash: d90ed71c1d5ca4cbfdcf8e500e1d176519a2fdff
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541572"
---
# <a name="ca2301-do-not-call-binaryformatterdeserialize-without-first-setting-binaryformatterbinder"></a>CA2301:最初に BinaryFormatter.Binder を設定しないで BinaryFormatter.Deserialize を呼び出さないでください

|||
|-|-|
|TypeName|DoNotCallBinaryFormatterDeserializeWithoutFirstSettingBinaryFormatterBinder|
|CheckId|CA2301|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

A<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>逆シリアル化メソッドが呼び出されるかせずに参照、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>プロパティ セット。

## <a name="rule-description"></a>規則の説明

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

このルールは、検索<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>メソッドの呼び出しまたは参照を逆シリアル化時に<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>がないその<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>設定します。 逆シリアル化を禁止する場合<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>に関係なく、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>プロパティでは、このルールを無効にして[CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)、ルールを有効にして[CA2300](ca2300-do-not-use-insecure-deserializer-binaryformatter.md)します。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 可能であれば、代わりに、セキュリティで保護されたシリアライザーを使用し、**攻撃者を任意の型を逆シリアル化の指定を許可しない**します。 安全なシリアライザーによっては、次のとおりです。
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -使用しないでください<xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>します。 型競合回避モジュールを使用する必要があります、予想されるリストを逆シリアル化された型を制限します。
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - NewtonSoft Json.NET - TypeNameHandling.None を使用します。 TypeNameHandling を別の値を使用する必要がありますがある場合は、カスタム ISerializationBinder での予期される一覧に逆シリアル化された型を制限します。
  - Protocol Buffers
- シリアル化されたデータの耐タンパー性を確認します。 シリアル化後に、シリアル化されたデータを暗号で署名します。 逆シリアル化する前に、暗号化署名を検証します。 公開される暗号化キーを保護し、キーのローテーションのための設計。
- 逆シリアル化された型を制限します。 カスタムの実装<xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>します。 逆シリアル化する前に<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>、設定、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>プロパティ、カスタムのインスタンスを<xref:System.Runtime.Serialization.SerializationBinder>します。 オーバーライドされた<xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>し、メソッド、型が予想される場合は例外をスローします。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

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
    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        BinaryFormatter formatter = new BinaryFormatter();
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
    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Dim formatter As BinaryFormatter = New BinaryFormatter()
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(formatter.Deserialize(ms), BookRecord)
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
            throw new ArgumentException("Unexpected type", nameof(typeName));
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
            Throw New ArgumentException("Unexpected type", NameOf(typeName))
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

[CA2302:BinaryFormatter.Binder は BinaryFormatter.Deserialize を呼び出す前に設定してください。](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)