---
title: C++ 用の CTest を使用する方法
ms.date: 05/01/2019
ms.topic: conceptual
ms.author: mblome
manager: jillfra
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: fddb32ce75bf587ee78ca172fd4de2c31237a331
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65225944"
---
# <a name="how-to-use-ctest-for-c-in-visual-studio-2017-and-later"></a>Visual Studio 2017 以降で C++ 用の CTest を使用する方法

CMake (CTest を含む) は、**C++ によるデスクトップ開発**ワークロードのコンポーネントとして Visual Studio IDE に既定で統合されています。 それをご自分のコンピューターにインストールする必要がある場合、Visual Studio Installer プログラムを開き、**[C++ によるデスクトップ開発]** ボタンをクリックし、**[変更]** をクリックします。 ワークロード コンポーネントの一覧の下にある [[Visual C++ 用の CMake ツール]](/cpp/ide/cmake-tools-for-visual-cpp) をオンにします。

## <a name="to-write-tests"></a>テストを記述するには

Visual Studio の CMake サポートでは、Visual Studio プロジェクト システムを必要としません。 したがって、任意の CMake 環境の場合と同様に、CTest テストを記述して構成します。 Visual Studio での CMake 使用の詳細については、[Visual C++ 用の CMake ツール](/cpp/ide/cmake-tools-for-visual-cpp)に関する記事を参照してください。

## <a name="to-run-tests"></a>テストを実行するには

CTest は**テスト エクスプローラー**に完全に統合され、Google 単体テスト フレームワークと Boost 単体テスト フレームワークの両方もサポートしています。 これらのフレームワークは、**C++ によるデスクトップ開発**ワークロードにコンポーネントとして既定で含まれています。 ただし、Visual Studio の以前のバージョンからプロジェクトをアップグレードする場合は、Visual Studio インストーラー プログラムを使用してこれらのフレームワークをインストールする必要があります。

次の図は、Google テスト フレームワークを使用して実行した CTest の結果を示しています。

![Visual Studio での Google Test Framework による CTest](media/ctest-test-explorer.png)

CTest を使用するが、Google アダプターまたは Boost アダプターを使用していない場合、結果は、個別のテスト方法レベルではなく、CTest レベルで表示されます。 CTest 専用実行可能ファイルのデバッグとステップ実行を行うことができますが、個々のテストのスタック トレースはサポートされません。

次の図は、Google テスト フレームワークを使用して実行した CTest の結果を示しています。

![Visual Studio 2017 での Google Test Framework による CTest](media/ctest-test-explorer.png)

CTest を使用するが、Google アダプターまたは Boost アダプターを使用していない場合、結果は、個別のテスト方法レベルではなく、CTest レベルで表示されます。 CTest 専用実行可能ファイルのデバッグとステップ実行を行うことができますが、個々のテストのスタック トレースはサポートされません。

## <a name="see-also"></a>関連項目

- [C/C++ 用の単体テストの記述](writing-unit-tests-for-c-cpp.md)