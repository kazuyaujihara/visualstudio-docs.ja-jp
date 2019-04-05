---
title: CA3076:安全ではない XSLT スクリプトの実行
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5f98b022aef49a4d98ad4864793aa55732f8de6c
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55929181"
---
# <a name="ca3076-insecure-xslt-script-execution"></a>CA3076:安全ではない XSLT スクリプトの実行

|||
|-|-|
|TypeName|InsecureXSLTScriptExecution|
|CheckId|CA3076|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

.NET アプリケーションで XSLT (Extensible Stylesheet Language Transformation) を安全ではない方法で実行すると、攻撃者に機密情報を漏えいする可能性のある、信頼されていない URI 参照がプロセッサにより解決されるおそれがあります。そのことは、サービス拒否攻撃やクロスサイト攻撃につながります。 詳細については、[XSLT セキュリティ Considerations(.NET Guide)](/dotnet/standard/data/xml/xslt-security-considerations)を参照してください。

## <a name="rule-description"></a>規則の説明

**XSLT** は、XML データを変換するための W3C (World Wide Web Consortium) 規格です。 XSLT は通常、XML データを HTML、固定長のテキスト、コンマ区切りのテキスト、または別の XML 形式などの他の形式に変換するスタイル シートの書き込みに使用します。 既定では禁止になっていますが、プロジェクトに応じて有効にもできます。

攻撃にさらされないように、このルールはたびにトリガー、XslCompiledTransform します。<xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> インスタンスを安全でない組み合わせを受け取る<xref:System.Xml.Xsl.XsltSettings>と<xref:System.Xml.XmlResolver>、悪意のあるスクリプトの処理をことができます。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 安全ではない XsltSettings 引数を xsltsettings に置き換えます。<xref:System.Xml.Xsl.XsltSettings.Default%2A> または、インスタンスが、ドキュメントの関数とスクリプトの実行を無効な。

- <xref:System.Xml.XmlResolver> 引数を null または <xref:System.Xml.XmlSecureResolver> インスタンスに置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

入力が信頼できるソースからのものとわかっているのでない限り、この警告からのルールを抑制しないでください。

## <a name="pseudo-code-examples"></a>疑似コードの例

### <a name="violation-that-uses-xsltsettingstrustedxslt"></a>違反 XsltSettings.TrustedXslt を使用します。

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
         void TestMethod()
        {
             XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
             var settings = XsltSettings.TrustedXslt;
             var resolver = new XmlUrlResolver();
             xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn
        }
    }
}
```

### <a name="solution-that-uses-xsltsettingsdefault"></a>XsltSettings.Default を使用するソリューション

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        void TestMethod()
        {
            XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
            var settings = XsltSettings.Default;
            var resolver = new XmlUrlResolver();
            xslCompiledTransform.Load("testStylesheet", settings, resolver);
        }
    }
}
```

### <a name="violationmdashdocument-function-and-script-execution-not-disabled"></a>違反&mdash;無効になっていない関数とスクリプトの実行を文書化

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod(XsltSettings settings)
        {
            try
            {
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn
            }
            catch { throw; }
            finally { }
        }
    }
}
```

### <a name="solutionmdashdisable-document-function-and-script-execution"></a>ソリューション&mdash;ドキュメントの関数とスクリプトの実行を無効にします。

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod(XsltSettings settings)
        {
            try
            {
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                settings.EnableDocumentFunction = false;
                settings.EnableScript = false;
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver);
            }
            catch { throw; }
            finally { }
        }
    }
}
```

## <a name="see-also"></a>関連項目

- [XSLT のセキュリティに関する考慮事項 (.NET ガイド)](/dotnet/standard/data/xml/xslt-security-considerations)