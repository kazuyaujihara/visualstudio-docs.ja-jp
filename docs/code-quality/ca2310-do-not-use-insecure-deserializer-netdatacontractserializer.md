---
title: CA2310:NetDataContractSerializer の安全でないデシリアライザーを使用しないでください。
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
ms.openlocfilehash: e4af6bbfbd7e14b99f39ffa0adb5d1117c200d9a
ms.sourcegitcommit: db30651dc0ce4d0b274479b23a6bd102a5559098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135430"
---
# <a name="ca2310-do-not-use-insecure-deserializer-netdatacontractserializer"></a>CA2310:NetDataContractSerializer の安全でないデシリアライザーを使用しないでください。

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerNetDataContractSerializer|
|CheckId|CA2310|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

A<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType>逆シリアル化メソッドが呼び出されるか参照します。

## <a name="rule-description"></a>規則の説明

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

このルールは、検索<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType>メソッドの呼び出しまたは参照を逆シリアル化します。 場合にのみ逆シリアル化する場合、<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>プロパティが型を制限し、このルールを無効にする、ルールを有効化[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)と[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)代わりにします。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 可能であれば、代わりに、セキュリティで保護されたシリアライザーを使用し、**攻撃者を任意の型を逆シリアル化の指定を許可しない**します。 安全なシリアライザーによっては、次のとおりです。
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -使用しないでください<xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>します。 型競合回避モジュールを使用する必要があります、予想されるリストを逆シリアル化された型を制限します。
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft Json.NET - TypeNameHandling.None を使用します。 TypeNameHandling を別の値を使用する必要がありますがある場合は、カスタム ISerializationBinder での予期される一覧に逆シリアル化された型を制限します。
  - Protocol Buffers
- シリアル化されたデータの耐タンパー性を確認します。 シリアル化後に、シリアル化されたデータを暗号で署名します。 逆シリアル化する前に、暗号化署名を検証します。 公開暗号化キーとキーのローテーションの設計を保護します。
- 逆シリアル化された型を制限します。 カスタムの実装<xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>します。 逆シリアル化する前に<xref:System.Runtime.Serialization.NetDataContractSerializer>、設定、<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>プロパティ、カスタムのインスタンスを<xref:System.Runtime.Serialization.SerializationBinder>します。 オーバーライドされた<xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>メソッド、型が、予想される場合は例外をスローします。
- 逆シリアル化された型を制限する場合は、このルールを無効にし、ルールを有効にすることがある[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)と[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)します。 ルール[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)と[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)ことを確認するヘルプ、<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>プロパティは常に逆シリアル化する前に設定します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>疑似コードの例

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

[CA2311:最初の設定 NetDataContractSerializer.Binder せずシリアル化を解除できません。](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)

[CA2312:NetDataContractSerializer.Binder が逆シリアル化する前に設定してください。](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)
