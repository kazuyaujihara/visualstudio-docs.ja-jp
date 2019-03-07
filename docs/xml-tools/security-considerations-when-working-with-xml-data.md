---
title: XML データを使用するときのセキュリティに関する考慮事項
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: fce2b708-1aef-454f-be59-52b76f359351
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3af91f02b6cc34fcc05b83bb6c09cfd37e8a18ef
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57525467"
---
# <a name="security-considerations-when-working-with-xml-data"></a>XML データを使用する場合のセキュリティに関する考慮事項

このトピックでは、XML エディターや XSLT デバッガーを使用する際に理解する必要があるセキュリティの問題について説明します。

## <a name="xml-editor"></a>XML エディター

 XML エディターは Visual Studio テキスト エディターに基づいています。 XML エディターは通常、<xref:System.Xml> クラスと <xref:System.Xml.Xsl> クラスに依存して XML プロセスを処理します。

-   XSLT 変換は、新しいアプリケーション ドメインで実行されます。 XSLT 変換は*サンド ボックス化された*; XSLT スタイル シートがある場所に基づいて制限されたアクセス許可を決定する、コンピューターのコード アクセス セキュリティ ポリシーを使用する、します。 たとえば、インターネット上にあるスタイル シートは最も制限されたアクセス許可を持ち、ユーザーのハード ディスクにコピーされているスタイル シートは "完全な信頼" で実行されます。

-   <xref:System.Xml.Xsl.XslCompiledTransform> クラスは、XSLT を Microsoft Intermediate Language (MSIL) にコンパイルし、実行時の処理速度を高めるために使用されます。

-   カタログ ファイルで外部の場所を指し示すスキーマは、XML エディターが初めて読み込まれるときに自動的にダウンロードします。 <xref:System.Xml.Schema.XmlSchemaSet> クラスは、スキーマをコンパイルするために使用されます。 XML エディターに付属するカタログ ファイルには、外部のスキーマへのリンクはありません。 ユーザーは、XML エディターでスキーマ ファイルをダウンロードする前に、外部スキーマへの参照を明示的に追加します。 HTTP ダウンロードを使用して無効にできる、**その他のツール オプション**XML エディターのページ。

-   XML エディターを使用して、<xref:System.Net>クラス スキーマをダウンロードするには

## <a name="xslt-debugger"></a>XSLT デバッガー

 XSLT デバッガーは、Visual Studio のマネージド デバッグ エンジンと、<xref:System.Xml> および <xref:System.Xml.Xsl> 名前空間のクラスを使用します。

-   XSLT デバッガーは、それぞれの XSLT 変換をサンドボックスで保護されたアプリケーション ドメインで実行します。 コンピューターのコード アクセスに関するセキュリティ ポリシーを使用し、XSLT スタイル シートが置かれている場所に基づいて、アクセス許可の制限が決定されます。 たとえば、インターネット上にあるスタイル シートは最も制限されたアクセス許可を持ち、ユーザーのハード ディスクにコピーされているスタイル シートは "完全な信頼" で実行されます。

-   XSLT スタイル シートは、<xref:System.Xml.Xsl.XslCompiledTransform> クラスを使用してコンパイルされます。

-   XSLT 式エバリュエーターは、マネージ デバッグ エンジンによって読み込まれます。 マネージ デバッグ エンジンは、すべてのコードがユーザーのローカル コンピューターから実行されることを前提としています。 そのため、<xref:System.Xml.Xsl.XslCompiledTransform> クラスによって XSLT ファイルがユーザーのコンピューターにダウンロードされます。 実行特権で評価が行われる可能性は、制限されたアクセス許可を使用して、新しいアプリケーション ドメインですべての XSLT 変換を実行することにより軽減されます。

## <a name="see-also"></a>関連項目

- [アプリケーション ドメイン](/dotnet/framework/app-domains/application-domains)