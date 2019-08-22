---
title: CA2310:安全ではないデシリアライザー NetDataContractSerializer を使用しないでください
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
- CA2310
- DoNotUseInsecureDeserializerNetDataContractSerializer
ms.openlocfilehash: 09496fd11945ec4d419cc215569a7436f96d71ec
ms.sourcegitcommit: 673b9364fc9a96b027662dcb4cf5d61cab60ef11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69891152"
---
# <a name="ca2310-do-not-use-insecure-deserializer-netdatacontractserializer"></a>CA2310:安全ではないデシリアライザー NetDataContractSerializer を使用しないでください

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerNetDataContractSerializer|
|CheckId|CA2310|
|Category|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

逆<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType>シリアル化メソッドが呼び出されたか、参照されました。

## <a name="rule-description"></a>規則の説明

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

このルールは<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType> 、逆シリアル化メソッドの呼び出しまたは参照を検索します。 プロパティが制限の種類に設定さ<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>れている場合にのみ逆シリアル化を行うには、この規則を無効にし、代わりに規則[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)と[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)を有効にします。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 可能であれば、代わりにセキュリティで保護されたシリアライザーを使用して、**攻撃者が任意の型を逆シリアル化することを許可しない**でください。 安全性の高いシリアライザーには次のものがあります。
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType>-使用<xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>しないでください。 型リゾルバーを使用する必要がある場合は、逆シリアル化された型を予期されるリストに制限します。
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft Json.NET-TypeNameHandling を使用します。 TypeNameHandling に別の値を使用する必要がある場合は、カスタム ISerializationBinder を使用して、逆シリアル化された型を予期されるリストに制限します。
  - プロトコルバッファー
- シリアル化されたデータの改ざん防止を行います。 シリアル化後に、シリアル化されたデータに暗号署名します。 逆シリアル化する前に、暗号化署名を検証します。 暗号化キーが公開され、キーのローテーションのための設計になっていないことを防止します。
- 逆シリアル化された型を制限します。 カスタム<xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>を実装します。 で<xref:System.Runtime.Serialization.NetDataContractSerializer>逆シリアル化する前<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>に、プロパティをカスタム<xref:System.Runtime.Serialization.SerializationBinder>のインスタンスに設定します。 オーバーライド<xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>されたメソッドで、型が予期しない場合は例外をスローして、逆シリアル化を停止します。
  - 逆シリアル化された型を制限する場合は、この規則を無効にして、 [CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)と[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)の規則を有効にすることをお勧めします。 ルール[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)と[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)は、 <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>逆シリアル化の前にプロパティが常に設定されていることを確認するのに役立ちます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>擬似コードの例

### <a name="violation"></a>違反

```csharp
using System.IO;
using System.Runtime.Serialization;

public class ExampleClass
{
    public object MyDeserialize(byte[] bytes)
    {
        NetDataContractSerializer serializer = new NetDataContractSerializer();
        return serializer.Deserialize(new MemoryStream(bytes));
    }
}
```

```vb
Imports System.IO
Imports System.Runtime.Serialization

Public Class ExampleClass
    Public Function MyDeserialize(bytes As Byte()) As Object
        Dim serializer As NetDataContractSerializer = New NetDataContractSerializer()
        Return serializer.Deserialize(New MemoryStream(bytes))
    End Function
End Class
```

## <a name="related-rules"></a>関連するルール

[CA2311:NetDataContractSerializer を最初に設定せずに逆シリアル化することはできません。](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)

[CA2312:逆シリアル化の前に NetDataContractSerializer が設定されていることを確認する](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)
