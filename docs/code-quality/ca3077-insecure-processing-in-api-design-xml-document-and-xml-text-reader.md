---
title: CA3077:API のデザイン、XML ドキュメント、および XML テキスト リーダーでの安全ではない処理
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7f33771b-f3c8-4c02-bef6-f581b623c303
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 68aada736b2a22b623502d8586415dc8024c2622
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237067"
---
# <a name="ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader"></a>CA3077:API のデザイン、XML ドキュメント、および XML テキスト リーダーでの安全ではない処理

|||
|-|-|
|TypeName|InsecureDTDProcessingInAPIDesign|
|CheckId|CA3077|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
XMLDocument と XMLTextReader から派生する API をデザインする場合、 <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A>にご注意ください。  外部エンティティ ソースを参照または解決したり、XML に安全ではない値を設定したりする場合に、安全ではない DTDProcessing インスタンスを使用すると、情報漏えいにつながる可能性があります。

## <a name="rule-description"></a>規則の説明
*文書型定義 (DTD)* は、  [World Wide Web コンソーシアム (W3C) Extensible Markup Language (XML) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/)で定義されているように、XML パーサーが文書の妥当性を判別する 2 つの方法のうちの 1 つです。 このルールは、信頼されていないデータを受け入れてしまうプロパティとインスタンスを検索し、 [サービス拒否 (DoS)](/dotnet/framework/wcf/feature-details/information-disclosure) 攻撃につながる可能性がある潜在的な [Information Disclosure](/dotnet/framework/wcf/feature-details/denial-of-service) の脅威について開発者に警告します。 このルールは、次の場合にトリガーされます。

- <xref:System.Xml.XmlDocument>また<xref:System.Xml.XmlTextReader>はクラスは、DTD 処理に既定の競合回避モジュールの値を使用します。

- XmlDocument または XmlTextReader から派生したクラスにコンストラクターが定義されていない。または <xref:System.Xml.XmlResolver>にセキュリティで保護された値が使用されていない。

## <a name="how-to-fix-violations"></a>違反の修正方法

- パス情報の漏えいを防ぐために、すべての XmlTextReader 例外をキャッチして処理します。

- XmlResolver <xref:System.Xml.XmlSecureResolver>の代わりにを使用して、XmlTextReader がアクセスできるリソースを制限します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
入力が信頼できるソースからのものとわかっているのでない限り、この警告からのルールを抑制しないでください。

## <a name="pseudo-code-examples"></a>疑似コードの例

### <a name="violation"></a>違反

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    class TestClass : XmlDocument
    {
        public TestClass () {} // warn
    }

    class TestClass2 : XmlTextReader
    {
        public TestClass2() // warn
        {
        }
    }
}
```

### <a name="solution"></a>ソリューション

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    class TestClass : XmlDocument
    {
        public TestClass ()
        {
            XmlResolver = null;
        }
    }

    class TestClass2 : XmlTextReader
    {
        public TestClass2()
        {
               XmlResolver = null;
        }
    }
}
```