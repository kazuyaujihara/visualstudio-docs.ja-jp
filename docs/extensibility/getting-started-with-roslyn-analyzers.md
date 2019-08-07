---
title: Roslyn アナライザーを使用したはじめにMicrosoft Docs
ms.date: 04/02/2018
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 21b2d77d8c038988fa77293280c9ff7ad38cc82e
ms.sourcegitcommit: 90c3187d804ad7544367829d07ed4b47d3f8a72d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "68822343"
---
# <a name="get-started-with-roslyn-analyzers"></a>Roslyn アナライザーを使ってみる

Visual Studio のプロジェクトベースのコードアナライザーを使用すると、API の作成者は、NuGet パッケージの一部としてドメイン固有のコード分析を行うことができます。 これらのアナライザーは .NET Compiler Platform (コードネーム "Roslyn") を備えているので、行を完了する前に入力したコードに警告を生成することができます (問題を検出するためのコードのビルドを待機する必要はありません)。 また、アナライザーは、Visual Studio 電球のプロンプトを使用してコードを自動的に修正することもできます。これにより、コードをすぐにクリーンアップできます。

## <a name="get-started"></a>作業開始

[Roslyn アナライザーの概要](../code-quality/roslyn-analyzers-overview.md)

[チュートリアル: 最初のアナライザーとコード修正を記述する](/dotnet/csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix)

[コード修正の追加のチュートリアル:アナライザーの問題についてユーザーの修正プログラムを提供する](https://msdn.microsoft.com/magazine/dn904670.aspx)

[リアルワールド Roslyn アナライザー](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) 。[話す](https://channel9.msdn.com/events/Build/2015/3-725)こともできます。

[3種類のアナライザーにグループ化された GitHub のいくつかの例](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

## <a name="see-also"></a>関連項目

- [.NET compiler platform パッケージバージョンリファレンス](roslyn-version-support.md)
- [GitHub OSS サイトに関するその他のドキュメント](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [Roslyn アナライザーで実装された FxCop 規則](../code-quality/fxcop-rule-port-status.md)
