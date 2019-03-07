---
title: XSLT コードをデバッグする方法
ms.date: 03/05/2019
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 23e108e476bfa9cb3ce699a16c77eb3520ed4785
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526387"
---
# <a name="debugging-xslt"></a>XSLT のデバッグ

Visual Studio での XSLT コードをデバッグすることができます。 XSLT デバッガーのブレークポイントの設定、XSLT 実行状態の表示をサポートしにします。 XSLT スタイル シートや XSLT アプリケーションをデバッグする XSLT デバッガーを使用できます。

ステップ イン、ステップ オーバー、または、コードからステップによって、一度に 1 行のコードを実行できます。 XSLT デバッガーのコードのステップ実行機能を使用するためのコマンドは、デバッガー、他の Visual Studio の場合と同じです。

デバッグを開始すると、XSLT デバッガーのウィンドウが開き、入力ドキュメントと XSLT 出力が表示されます。

> [!NOTE]
> XSLT デバッガーには、Visual Studio の Enterprise edition ではできるだけです。

## <a name="debug-from-the-xml-editor"></a>XML エディターからのデバッグします。

スタイル シートまたはエディターで開き、入力 XML ファイルのいずれかがある場合は、デバッガーを起動することができます。 これにより、スタイル シートを設計するようにデバッグできます。

1. Visual Studio で、スタイル シートまたは XML ファイルを開きます。

1. 選択**XSLT のデバッグの開始**から、 **XML**メニューまたはキーを押して**Alt**+**f5 キーを押して**。

## <a name="debug-from-an-app-that-uses-xslt"></a>XSLT を使用するアプリをデバッグします。

アプリケーションのデバッグ中に XSLT にステップ インすることができます。 キーを押すと**F11**上、<xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=fullName>呼び出し、デバッガーが XSLT コードにステップ インできます。

> [!NOTE]
> <xref:System.Xml.Xsl.XslTransform> クラスから XSLT へのステップ インは、サポートされていません。 デバッグ中の XSLT へのステップ インをサポートしている XSLT プロセッサは、<xref:System.Xml.Xsl.XslCompiledTransform> クラスだけです。

### <a name="to-start-debugging-an-xslt-application"></a>XSLT アプリケーションのデバッグを開始するには

1. <xref:System.Xml.Xsl.XslCompiledTransform> オブジェクトをインスタンス化するときに、コード内で `enableDebug` パラメーターを `true` に設定します。 この設定によって、コードがコンパイルされるときにデバッグ情報を作成するように XSLT プロセッサに指示します。

1. キーを押して**F11** XSLT コードにステップ インします。

   新しいドキュメント ウィンドウに XSLT スタイル シートが読み込まれ、XSLT デバッガーが起動します。

   または、ブレーク ポイントをスタイル シートに追加し、アプリケーションを実行することもできます。

### <a name="example"></a>例

C# XSLT プログラムの例を次に示します。 この例は、XSLT のデバッグを有効にする方法を示しています。

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Xsl;

namespace ConsoleApplication
{
  class Program
  {
    private const string sourceFile = @"c:\data\xsl_files\books.xml";
    private const string stylesheet = @"c:\data\xsl_files\below-average.xsl";
    private const string outputFile = @"c:\data\xsl_files\output.xml";

    static void Main(string[] args)
    {
      // Enable XSLT debugging.
      XslCompiledTransform xslt = new XslCompiledTransform(true);

      // Compile the style sheet.
      xslt.Load(stylesheet)

      // Execute the XSLT transform.
      FileStream outputStream = new FileStream(outputFile, FileMode.Append);
      xslt.Transform(sourceFile, null, outputStream);
    }
  }
}
```

## <a name="xslt-profiler"></a>XSLT プロファイラー

[XSLT プロファイラー](../xml-tools/xslt-profiler.md)はにより、開発者は、計測、評価、および詳細な XSLT パフォーマンス レポートを作成して XSLT コード内のパフォーマンスに関連する問題を特定するツールです。 詳細については、次を参照してください。 [XSLT プロファイラー](../xml-tools/xslt-profiler.md)します。

## <a name="see-also"></a>関連項目

- [チュートリアル: XSLT スタイル シートをデバッグします。](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)
- [最初に、Visual Studio デバッガーについてください。](../debugger/debugger-feature-tour.md)
- [デバッグの基礎: ブレークポイント](../debugger/using-breakpoints.md)