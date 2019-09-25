---
title: CA2312:NetDataContractSerializer.Binder を設定してから逆シリアル化してください
ms.date: 05/01/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
f1_keywords:
- CA2312
- EnsureNetDataContractSerializerBinderIsSetBeforeDeserializing
ms.openlocfilehash: 03d3e6c4f5e7a3cf4da9f998b75260df522e019f
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237698"
---
# <a name="ca2312-ensure-netdatacontractserializerbinder-is-set-before-deserializing"></a>CA2312:NetDataContractSerializer.Binder を設定してから逆シリアル化してください

|||
|-|-|
|TypeName|EnsureNetDataContractSerializerBinderIsSetBeforeDeserializing|
|CheckId|CA2312|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

逆シリアル化メソッドが呼び出されたか<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> 、または参照されましたが、プロパティが null である可能性があります。 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType>

## <a name="rule-description"></a>規則の説明

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

このルールは<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType> 、が null の場合に、 <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>逆シリアル化メソッドの呼び出しまたは参照を検索します。 <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>プロパティに関係なく、を使用し<xref:System.Runtime.Serialization.NetDataContractSerializer>て逆シリアル化を許可しない場合は、この rule と[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)を無効にして、rule [CA2310](ca2310-do-not-use-insecure-deserializer-netdatacontractserializer.md)を有効にします。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 可能であれば、代わりにセキュリティで保護されたシリアライザーを使用して、**攻撃者が任意の型を逆シリアル化することを許可しない**でください。 安全性の高いシリアライザーには次のものがあります。
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType>-使用<xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>しないでください。 型リゾルバーを使用する必要がある場合は、逆シリアル化された型を予期されるリストに制限します。
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft Json.NET-TypeNameHandling を使用します。 TypeNameHandling に別の値を使用する必要がある場合は、カスタム ISerializationBinder を使用して、逆シリアル化された型を予期されるリストに制限します。
  - プロトコル バッファー
- シリアル化されたデータの改ざん防止を行います。 シリアル化後に、シリアル化されたデータに暗号署名します。 逆シリアル化する前に、暗号化署名を検証します。 暗号化キーが公開され、キーのローテーションのための設計になっていないことを防止します。
- 逆シリアル化された型を制限します。 カスタム<xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>を実装します。 で<xref:System.Runtime.Serialization.NetDataContractSerializer>逆シリアル化する前<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>に、プロパティをカスタム<xref:System.Runtime.Serialization.SerializationBinder>のインスタンスに設定します。 オーバーライド<xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>されたメソッドで、型が予期しない場合は例外をスローして、逆シリアル化を停止します。
  - すべてのコードパス<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>にプロパティが設定されていることを確認します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>擬似コードの例

### <a name="violation"></a>違反

```csharp
using System;
using System.IO;
using System.Runtime.Serialization;

[DataContract]
public class BookRecord
{
    [DataMember]
    public string Title { get; set; }

    [DataMember]
    public string Author { get; set; }

    [DataMember]
    public int PageCount { get; set; }

    [DataMember]
    public AisleLocation Location { get; set; }
}

[DataContract]
public class AisleLocation
{
    [DataMember]
    public char Aisle { get; set; }

    [DataMember]
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public NetDataContractSerializer Serializer { get; set; }

    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) this.Serializer.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization

<DataContract()>
Public Class BookRecord
    <DataMember()>
    Public Property Title As String

    <DataMember()>
    Public Property Author As String

    <DataMember()>
    Public Property Location As AisleLocation
End Class

<DataContract()>
Public Class AisleLocation
    <DataMember()>
    Public Property Aisle As Char

    <DataMember()>
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Property Serializer As NetDataContractSerializer

    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(Me.Serializer.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

### <a name="solution"></a>ソリューション

```csharp
using System;
using System.IO;
using System.Runtime.Serialization;

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

[DataContract]
public class BookRecord
{
    [DataMember]
    public string Title { get; set; }

    [DataMember]
    public string Author { get; set; }

    [DataMember]
    public int PageCount { get; set; }

    [DataMember]
    public AisleLocation Location { get; set; }
}

[DataContract]
public class AisleLocation
{
    [DataMember]
    public char Aisle { get; set; }

    [DataMember]
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        NetDataContractSerializer serializer = new NetDataContractSerializer();
        serializer.Binder = new BookRecordSerializationBinder();
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) serializer.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization

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

<DataContract()>
Public Class BookRecord
    <DataMember()>
    Public Property Title As String

    <DataMember()>
    Public Property Author As String

    <DataMember()>
    Public Property Location As AisleLocation
End Class

<DataContract()>
Public Class AisleLocation
    <DataMember()>
    Public Property Aisle As Char

    <DataMember()>
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Dim serializer As NetDataContractSerializer = New NetDataContractSerializer()
        serializer.Binder = New BookRecordSerializationBinder()
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(serializer.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

## <a name="related-rules"></a>関連するルール

[CA2310:セキュリティで保護されていないデシリアライザー NetDataContractSerializer を使用しない](ca2310-do-not-use-insecure-deserializer-netdatacontractserializer.md)

[CA2311:NetDataContractSerializer を最初に設定せずに逆シリアル化することはできません。](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)
