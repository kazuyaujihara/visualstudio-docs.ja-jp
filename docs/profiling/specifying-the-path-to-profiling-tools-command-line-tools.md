---
title: プロファイル ツールのコマンド ライン ツールへのパスの指定 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 03b11b478ef441dc7a09902a7185bfdf45e20dc3
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "57868951"
---
# <a name="specify-the-path-to-profiling-tools-command-line-tools"></a>プロファイル ツールのコマンド ライン ツールへのパスの指定

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] プロファイリング ツールのコマンド ライン ツールのパスは、PATH 環境変数に追加されません。 32 ビット コンピューターでは、これらのツールは単一のディレクトリ内にあります。 64 ビット コンピューターには、32 ビット バージョンと 64 ビット バージョンの両方のプロファイリング ツールがあります。

## <a name="32-bit-computers"></a>32 ビット コンピューター
::: moniker range=">=vs-2019"
 ネイティブ コード用の Visual Studio プロファイラー API は *VSPerf.dll* にあります。 ヘッダー ファイル *VSPerf.h* とインポート ライブラリ *VSPerf.lib* は、*Microsoft Visual Studio\2019\Team Tools\Performance Tools\PerfSDK* ディレクトリにあります。
::: moniker-end
::: moniker range="vs-2017"
 ネイティブ コード用の Visual Studio プロファイラー API は *VSPerf.dll* にあります。 ヘッダー ファイル *VSPerf.h* とインポート ライブラリ *VSPerf.lib* は、*Microsoft Visual Studio\2017\Team Tools\Performance Tools\PerfSDK* ディレクトリにあります。
::: moniker-end

 マネージド コード用のプロファイラー API は、*Microsoft.VisualStudio.Profiler.dll* にあります。 この DLL は、*Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools* ディレクトリにあります。

## <a name="64-bit-computers"></a>64 ビット コンピューター

64 ビット コンピューターでは、プロファイリングするアプリケーションのターゲット プラットフォームに応じてパスを指定します。

::: moniker range=">=vs-2019"
-   32 ビット アプリケーションの場合、既定のプロファイリング ツール ディレクトリは以下のとおりです。

     (ネイティブ) *Microsoft Visual Studio\2019\Team Tools\Performance Tools\PerfSDK* (マネージド) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

-   64 ビット アプリケーションの場合、既定のプロファイリング ツール ディレクトリは以下のとおりです。

     (ネイティブ) *Microsoft Visual Studio\2019\Team Tools\Performance Tools\x64\PerfSDK* (マネージド) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end

::: moniker range="vs-2017"
-   32 ビット アプリケーションの場合、既定のプロファイリング ツール ディレクトリは以下のとおりです。

     (ネイティブ) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\PerfSDK* (マネージド) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

-   64 ビット アプリケーションの場合、既定のプロファイリング ツール ディレクトリは以下のとおりです。

     (ネイティブ) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\x64\PerfSDK* (マネージド) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end