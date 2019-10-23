---
title: CRT デバッグライブラリの使用 |Microsoft Docs
ms.date: 10/03/2019
ms.topic: conceptual
f1_keywords:
- c.debug.runtime
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /DEBUG linker option [C++]
- crtdbg.h file
- debug library
- MDd compiler option [C++]
- libraries, CRT debug library
- MTd compiler option [C++]
- LDd compiler function [C++]
- /MTd compiler option [C++]
- /MDd compiler option [C++]
- debugging [CRT], CRT debug library
- DEBUG linker option [C++]
- /LDd compiler function [C++]
ms.assetid: 464de16b-4215-4787-9bfa-921aaff9d9f4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c7e58f65f174c549f6992e9218d7ad692634e20d
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72435876"
---
# <a name="crt-debug-library-use"></a>CRT デバッグ ライブラリの使用方法
C ランタイム ライブラリには、広範なデバッグ支援機能が用意されています。 CRT デバッグライブラリの1つを使用するには、 [/debug](/cpp/build/reference/debug-generate-debug-info)にリンクし、 **/mdd**、 **/MTd**、または **/LDd**を使用してコンパイルする必要があります。

## <a name="remarks"></a>Remarks
 CRT のデバッグに使用する主な定義とマクロは、CRTDBG.h ヘッダー ファイルに記述されています。

 CRT デバッグ ライブラリの関数は、デバッグ情報 ([/Z7、/Zd、/Zi、/ZI (デバッグ情報の形式)](/cpp/build/reference/z7-zi-zi-debug-information-format)) を含んだ状態で、最適化されずにコンパイルされています。 渡されるパラメーターを検証するためのアサート ステートメントを含む関数もあり、これらの関数のソース コードは公開されています。 このソース コードを利用すると、CRT 関数をステップ実行して、その関数が正常に動作しているかを確認したり、パラメーターやメモリ状態が不正でないかどうかを検証したりできます。 一部の CRT 技術については権利が保有されており、例外処理、浮動小数点数、その他いくつかのルーチンのソース コードは公開されていません。

 使用できる各種ランタイム ライブラリの詳細については、[C ランタイム ライブラリ](/cpp/c-runtime-library/crt-library-features)に関するページを参照してください。

## <a name="see-also"></a>参照

- [CRT のデバッグ技術](../debugger/crt-debugging-techniques.md)
- [/MD、/MT、/LD (ランタイム ライブラリの使用)](/cpp/build/reference/md-mt-ld-use-run-time-library)
