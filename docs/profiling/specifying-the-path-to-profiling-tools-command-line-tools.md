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
ms.openlocfilehash: 48ac65ef8fb7a67783a3c9c5a9652accf86821fc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62979836"
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
- 32 ビット アプリケーションの場合、既定のプロファイリング ツール ディレクトリは以下のとおりです。

     (ネイティブ) *Microsoft Visual Studio\2019\Team Tools\Performance Tools\PerfSDK* (マネージド) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

- 64 ビット アプリケーションの場合、既定のプロファイリング ツール ディレクトリは以下のとおりです。

     (ネイティブ) *Microsoft Visual Studio\2019\Team Tools\Performance Tools\x64\PerfSDK* (マネージド) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end

::: moniker range="vs-2017"
- 32 ビット アプリケーションの場合、既定のプロファイリング ツール ディレクトリは以下のとおりです。

     (ネイティブ) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\PerfSDK* (マネージド) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

- 64 ビット アプリケーションの場合、既定のプロファイリング ツール ディレクトリは以下のとおりです。

     (ネイティブ) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\x64\PerfSDK* (マネージド) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end