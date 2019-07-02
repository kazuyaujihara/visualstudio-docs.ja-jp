---
title: 構造体とクラスに注釈を付ける
ms.date: 06/28/2019
ms.topic: conceptual
f1_keywords:
- _Field_size_bytes_part_
- _Field_size_bytes_full_opt_
- _Field_size_bytes_
- _Field_size_opt_
- _Field_size_part_
- _Field_size_bytes_part_opt_
- _Field_range_
- _Field_size_part_opt_
- _Field_size_
- _Field_size_bytes_opt_
- _Struct_size_bytes_
- _Field_size_bytes_full_
- _Field_size_full_
- _Field_size_full_opt_
- _Field_z_
ms.assetid: b8278a4a-c86e-4845-aa2a-70da21a1dd52
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 35be465064c9524eb0e1339794b6a19b7a595da1
ms.sourcegitcommit: d2b234e0a4a875c3cba09321cdf246842670d872
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2019
ms.locfileid: "67493636"
---
# <a name="annotating-structs-and-classes"></a>構造体とクラスに注釈を付ける

インバリアントのように動作する注釈を使用して構造体とクラスのメンバーに注釈を付けることができます: これらは true に、関数呼び出し、または関数の開始/終了パラメーターまたは結果の値として外側の構造体を含むと見なされます。

## <a name="struct-and-class-annotations"></a>構造体とクラスの注釈

- `_Field_range_(low, high)`

     フィールドがから (包括) の範囲である`low`に`high`します。  等価`_Satisfies_(_Curr_ >= low && _Curr_ <= high)`適切なプリトリガーまたは条件を使用して、注釈付きのオブジェクトに適用します。

- `_Field_size_(size)`, `_Field_size_opt_(size)`, `_Field_size_bytes_(size)`, `_Field_size_bytes_opt_(size)`

     要素 (またはバイト数) とで指定された書き込み可能なサイズのフィールド`size`します。

- `_Field_size_part_(size, count)`, `_Field_size_part_opt_(size, count)`,         `_Field_size_bytes_part_(size, count)`, `_Field_size_bytes_part_opt_(size, count)`

     要素 (またはバイト数) とで指定された書き込み可能なサイズのフィールド`size`、および`count`は読み取り可能なそれらの要素 (バイト単位)。

- `_Field_size_full_(size)`, `_Field_size_full_opt_(size)`, `_Field_size_bytes_full_(size)`, `_Field_size_bytes_full_opt_(size)`

     読み取りと書き込みの両方のサイズの要素 (またはバイト数) とで指定されたフィールド`size`します。

- `_Field_z_`

     Null で終わる文字列フィールドです。

- `_Struct_size_bytes_(size)`

     構造体またはクラスの宣言に適用されます。  指定されているバイト数でその型の有効なオブジェクトを宣言された型よりも大きいでことがあることを示します`size`します。  例:

    ```cpp

    typedef _Struct_size_bytes_(nSize)
    struct MyStruct {
        size_t nSize;
        ...
    };

    ```

     パラメーターのバイト単位のバッファー サイズ`pM`型の`MyStruct *`が表示されます。

    ```cpp
    min(pM->nSize, sizeof(MyStruct))
    ```

## <a name="example"></a>例

```cpp
#include <sal.h>
// For FIELD_OFFSET macro
#include <windows.h>

// This _Struct_size_bytes_ is equivalent to what below _Field_size_ means.
_Struct_size_bytes_(FIELD_OFFSET(MyBuffer, buffer) + bufferSize * sizeof(int))
struct MyBuffer
{
    static int MaxBufferSize;
    
    _Field_z_
    const char* name;
    
    int firstField;

    // ... other fields

    _Field_range_(1, MaxBufferSize)
    int bufferSize;
    _Field_size_(bufferSize)        // Prefered way - easier to read and maintain.
    int buffer[0];
};
```

この例のノート:

- `_Field_z_` は `_Null_terminated_` と同じです。  `_Field_z_` 名前フィールドでは、[名前] フィールドが null で終わる文字列を指定します。
- `_Field_range_` `bufferSize`ことを指定の値`bufferSize`1 内にする必要がありますと`MaxBufferSize`(両端の値)。
- 最終結果、`_Struct_size_bytes_`と`_Field_size_`注釈は同等です。 構造体またはクラスを持つ同様のレイアウトの`_Field_size_`は、以下の参照と相当するものよりも計算があるため、読みやすさと保守、`_Struct_size_bytes_`注釈。 `_Field_size_` サイズのバイトへの変換は必要ありません。 場合、バイト サイズは、唯一のオプションでは、たとえば、void ポインター フィールドの`_Field_size_bytes_`ことができます。 両方`_Struct_size_bytes_`と`_Field_size_`存在は、両方のツールを使用できます。 ツール、2 つの注釈に一致しない場合の対処方法。

## <a name="see-also"></a>関連項目

- [SAL 注釈を使って C/C++ のコード障害を減らす方法](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL について](../code-quality/understanding-sal.md)
- [関数パラメーターおよび戻り値の注釈設定](../code-quality/annotating-function-parameters-and-return-values.md)
- [関数の動作に注釈を付ける](../code-quality/annotating-function-behavior.md)
- [ロック動作に注釈を付ける](../code-quality/annotating-locking-behavior.md)
- [注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [組み込み関数](../code-quality/intrinsic-functions.md)
- [ベスト プラクティスと例](../code-quality/best-practices-and-examples-sal.md)