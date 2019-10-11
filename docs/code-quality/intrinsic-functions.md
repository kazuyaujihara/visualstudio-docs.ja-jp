---
title: 組み込み関数
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _String_length_
- _Param_
- _Curr_
- _Old_
- _Nullterm_length_
- _Inexpressible_
ms.assetid: adf29f8c-89fd-4a5e-9804-35ac83e1c457
author: mikeblome
ms.author: mblome
manager: markl
ms.workload:
- multiple
ms.openlocfilehash: e5b754f32edb86d10b4dd722ea7c6486f8179af6
ms.sourcegitcommit: 535ef05b1e553f0fc66082cd2e0998817eb2a56a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72018738"
---
# <a name="intrinsic-functions"></a>組み込み関数
SAL 内の式は、C/C++式にすることができます。これは、副作用のない式であることを示します。たとえば、+ +、--,、関数の呼び出しすべてにこのコンテキストでの副作用があります。  ただし、SAL には、関数に似たオブジェクトや、SAL 式で使用できる予約済みのシンボルがいくつか用意されています。 これらは*組み込み関数*と呼ばれます。

## <a name="general-purpose"></a>General Purpose
次のているか関数注釈は、SAL の一般的なユーティリティを提供します。

|Annotation|説明|
|----------------|-----------------|
|`_Curr_`|現在注釈が付けられているオブジェクトのシノニム。  @No__t 0 の注釈が使用されている場合、`_Curr_` は `_At_` の最初のパラメーターと同じです。  それ以外の場合は、パラメーター、または注釈が構文的に関連付けられている関数/戻り値全体を指定します。|
|`_Inexpressible_(expr)`|入力データセットをスキャンして選択したメンバーをカウントすることによって計算された場合など、注釈式を使用して、バッファーのサイズが複雑すぎて表すことができない状況を表します。|
|`_Nullterm_length_(param)`|`param` は、バッファー内の要素の数の最大値ですが、null 終端文字は含まれません。 非集計の非 void 型の任意のバッファーに適用できます。|
|`_Old_(expr)`|前提条件で評価された場合、`_Old_` は入力値 `expr` を返します。  事後条件で評価されると、前提条件で評価された値 `expr` が返されます。|
|`_Param_(n)`|関数の @no__t 0 番目のパラメーター (1 から `n`、`n`) がリテラル整数定数です。 パラメーターにという名前が付けられている場合、この注釈は名前によってパラメーターにアクセスするのと同じです。 **注:**  `n` は、省略記号で定義された位置指定パラメーターを参照することも、名前が使用されない関数プロトタイプで使用することもできます。|
|`return`|関数の戻りC++値を示すには、SAL 式で C/予約済みキーワード `return` を使用できます。  この値は post 状態でのみ使用できます。これは、事前状態で使用するための構文エラーです。|

## <a name="string-specific"></a>文字列固有
次の組み込み関数注釈を使用すると、文字列を操作できます。 これらの4つの関数は、null 終端文字の前に見つかった型の要素の数を返すために、同じ目的を果たします。 違いは、参照される要素のデータの種類です。 文字で構成されていない null で終わるバッファーの長さを指定する場合は、前のセクションの @no__t 0 の注釈を使用します。

|Annotation|説明|
|----------------|-----------------|
|`_String_length_(param)`|`param` は文字列内の要素の数ですが、null 終端文字は含まれません。 この注釈は、文字型の文字列用に予約されています。|
|`strlen(param)`|`param` は文字列内の要素の数ですが、null 終端文字は含まれません。 この注釈は、文字配列で使用するために予約されており、C ランタイム関数[strlen ()](/cpp/c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l)に似ています。|
|`wcslen(param)`|`param` は、null 終端文字までの文字列内の要素の数です (ただし、は含まれません)。 この注釈は、ワイド文字配列で使用するために予約されており、C ランタイム関数[wcslen ()](/cpp/c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l)に似ています。|

## <a name="see-also"></a>関連項目

- [SAL 注釈を使って C/C++ のコード障害を減らす方法](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL について](../code-quality/understanding-sal.md)
- [関数パラメーターおよび戻り値の注釈設定](../code-quality/annotating-function-parameters-and-return-values.md)
- [関数の動作に注釈を付ける](../code-quality/annotating-function-behavior.md)
- [構造体とクラスに注釈を付ける](../code-quality/annotating-structs-and-classes.md)
- [ロック動作に注釈を付ける](../code-quality/annotating-locking-behavior.md)
- [注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [ベスト プラクティスと例](../code-quality/best-practices-and-examples-sal.md)