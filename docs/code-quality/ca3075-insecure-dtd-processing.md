---
title: CA3075:安全ではない DTD の処理
ms.date: 03/18/2019
ms.topic: reference
ms.assetid: 65798d66-7a30-4359-b064-61a8660c1eed
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6de817e3aaecbdd1c89cc2174e91126ea39d99d7
ms.sourcegitcommit: 4d9c54f689416bf1dc4ace058919592482d02e36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58194620"
---
# <a name="ca3075-insecure-dtd-processing"></a>CA3075:安全ではない DTD の処理

|||
|-|-|
|TypeName|InsecureDTDProcessing|
|CheckId|CA3075|
|Category|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

安全ではない <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> インスタンスを使用する場合、または外部エンティティ ソースを参照する場合、パーサーは信頼されていない入力を受け入れ、攻撃者に機密情報を漏えいしてしまう可能性があります。

## <a name="rule-description"></a>規則の説明

*文書型定義 (DTD)* は、  [World Wide Web コンソーシアム (W3C) Extensible Markup Language (XML) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/)で定義されているように、XML パーサーが文書の妥当性を判別する 2 つの方法のうちの 1 つです。 このルールはシーク プロパティとインスタンスの可能性について開発者に警告の信頼されていないデータを受け入れている[情報漏えいが起こる](/dotnet/framework/wcf/feature-details/information-disclosure)脅威または[サービス拒否 (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service)攻撃です。 このルールは、次の場合にトリガーされます。

- <xref:System.Xml.XmlReader> を使用して外部 XML エンティティを解決する <xref:System.Xml.XmlUrlResolver>インスタンスで、DtdProcessing が有効になっている。

- XML で <xref:System.Xml.XmlNode.InnerXml%2A> プロパティが設定されている。

- <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> プロパティは、Parse に設定されます。

- 使用して入力が処理される信頼されていない<xref:System.Xml.XmlResolver>の代わりに<xref:System.Xml.XmlSecureResolver>します。

- <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType>メソッドが呼び出される、安全でないと<xref:System.Xml.XmlReaderSettings>インスタンスまたはすべてのインスタンスがありません。

- <xref:System.Xml.XmlReader> 安全でない既定の設定または値で作成されます。

それぞれの場合、結果は同じ: いずれか、ファイル システムまたはネットワーク共有から XML を処理するマシンから内容が、攻撃者に公開または DTD の処理は、DoS ベクターとして使用できます。

## <a name="how-to-fix-violations"></a>違反の修正方法

- キャッチし、パス情報の漏えいを回避するために適切にすべての XmlTextReader 例外を処理します。

- 使用して、 <xref:System.Xml.XmlSecureResolver> XmlTextReader がアクセスできるリソースを制限します。

- <xref:System.Xml.XmlReader> プロパティを <xref:System.Xml.XmlResolver> null **に設定して、** がどの外部リソースも開けないようにします。

- いることを確認、<xref:System.Data.DataViewManager.DataViewSettingCollectionString%2A?displayProperty=nameWithType>プロパティが、信頼できるソースから割り当てられます。

**.NET 3.5 以前**

- 設定によって信頼されていないソースを扱う場合は、DTD 処理を無効にする、<xref:System.Xml.XmlReaderSettings.ProhibitDtd%2A>プロパティを**true**します。

- XmlTextReader クラスには、完全信頼の継承確認要求があります。

**.NET 4 以降**

- 設定によって信頼されていないソースを扱う場合は、DtdProcessing を有効にしないように、<xref:System.Xml.XmlReaderSettings.DtdProcessing%2A?displayProperty=nameWithType>プロパティを**禁止**または**無視**します。

- すべての InnerXml ケースで、Load() メソッドが XmlReader インスタンスを取ることを確認します。

> [!NOTE]
> このルールは、有効な XmlSecureResolver インスタンスについて誤検知を報告することがあります。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

入力が信頼できるソースからのものとわかっているのでない限り、この警告からのルールを抑制しないでください。

## <a name="pseudo-code-examples"></a>疑似コードの例

### <a name="violation"></a>違反

```csharp
using System.IO;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlSchema schema = XmlSchema.Read(tr, null); // warn
            return schema;
        }
    }
}
```

### <a name="solution"></a>ソリューション

```csharp
using System.IO;
using System.Xml;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlTextReader reader = new XmlTextReader(tr) { DtdProcessing = DtdProcessing.Prohibit };
            XmlSchema schema = XmlSchema.Read(reader , null);
            return schema;
        }
    }
}
```

### <a name="violation"></a>違反

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings();
        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);  // warn
        }
    }
}
```

### <a name="solution"></a>ソリューション

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings()
        {
            DtdProcessing = DtdProcessing.Prohibit
        };

        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);
        }
    }
}
```

### <a name="violations"></a>違反

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseSetInnerXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument() { XmlResolver = null };
            doc.InnerXml = xml; // warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseLoadXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument(){ XmlResolver = null };
            doc.LoadXml(xml); // warn
        }
    }
}
```

### <a name="solution"></a>ソリューション

```csharp
using System.Xml;

public static void TestMethod(string xml)
{
    XmlDocument doc = new XmlDocument() { XmlResolver = null };
    System.IO.StringReader sreader = new System.IO.StringReader(xml);
    XmlReader reader = XmlReader.Create(sreader, new XmlReaderSettings() { XmlResolver = null });
    doc.Load(reader);
}
```

### <a name="violation"></a>違反

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            serializer.Deserialize(stream); // warn
        }
    }
}
```

### <a name="solution"></a>ソリューション

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            XmlReader reader = XmlReader.Create(stream, new XmlReaderSettings() { XmlResolver = null });
            serializer.Deserialize(reader );
        }
    }
}
```

### <a name="violation"></a>違反

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XPathDocument doc = new XPathDocument(path); // warn
        }
    }
}
```

### <a name="solution"></a>ソリューション

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XmlReader reader = XmlReader.Create(path, new XmlReaderSettings() { XmlResolver = null });
            XPathDocument doc = new XPathDocument(reader);
        }
    }
}
```

### <a name="violation"></a>違反

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = new XmlUrlResolver() };
    }
}
```

### <a name="solution"></a>ソリューション

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = null }; // or set to a XmlSecureResolver instance
    }
}
```

### <a name="violations"></a>違反

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod()
        {
            var reader = XmlTextReader.Create(""doc.xml""); //warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            try {
                XmlTextReader reader = new XmlTextReader(path); // warn
            }
            catch { throw ; }
            finally {}
        }
    }
}
```

### <a name="solution"></a>ソリューション

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            XmlReaderSettings settings = new XmlReaderSettings() { XmlResolver = null };
            XmlReader reader = XmlReader.Create(path, settings);
        }
    }
}
```
