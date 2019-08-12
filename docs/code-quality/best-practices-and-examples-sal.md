---
title: ベスト プラクティスと例 (SAL)
ms.date: 11/04/2016
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 478efc77bd1fb14f6241e026cfe280355a90746a
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919444"
---
# <a name="best-practices-and-examples-sal"></a>ベスト プラクティスと例 (SAL)
ここでは、ソースコード注釈言語 (SAL) を最大限に活用し、いくつかの一般的な問題を回避する方法をいくつか紹介します。

## <a name="_in_"></a>\_In\_

関数が要素に書き込むことが想定されている`_Inout_`場合は`_In_`、の代わりにを使用します。 これは、古いマクロから SAL への自動変換の場合に特に関連します。 SAL より前は、多くのプログラマはマクロをコメントとして`IN`使用し`IN_OUT`ていました。このような名前のマクロは、、、、またはこれらの名前のバリアントでし`OUT`た。 これらのマクロを SAL に変換することをお勧めしますが、元のプロトタイプが記述された後にコードが変更されている可能性があり、古いマクロがコードの動作を反映しなくなる可能性があるため、変換する際には注意が必要です。 `OPTIONAL`コメントマクロについては特に注意してください。たとえば、コンマの間違った側など、誤って配置されることがよくあります。

```cpp

// Incorrect
void Func1(_In_ int *p1)
{
    if (p1 == NULL)
        return;

    *p1 = 1;
}

// Correct
void Func2(_Inout_ PCHAR p1)
{
    if (p1 == NULL)
        return;

    *p1 = 1;
}
```

## <a name="_opt_"></a>\_opt\_

呼び出し元が null ポインターを渡すことが許可されてい`_In_`ない場合は`_In_opt_` 、 `_Out_opt_`またはの代わりにまたは`_Out_`を使用します。 これは、パラメーターをチェックする関数に対しても適用され、でない場合は NULL である場合はエラーを返します。 関数によってパラメーターが予期しない NULL としてチェックされ、正常に返されるのは、適切な防御コーディング手法であるということで`_*Xxx*_opt_`はありませんが、パラメーター注釈を省略可能な型 () にすることはできません。

```cpp

// Incorrect
void Func1(_Out_opt_ int *p1)
{
    *p = 1;
}

// Correct
void Func2(_Out_ int *p1)
{
    *p = 1;
}
```

## <a name="_pre_defensive_-and-_post_defensive_"></a>\_防御\_前\_と防御\_後\_\_

関数が信頼境界にある場合は、 `_Pre_defensive_`注釈を使用することをお勧めします。  "防御" 修飾子は、呼び出しの時点で、インターフェイスを厳密に確認する必要があることを示すために、特定の注釈を変更します。ただし、実装本文では、正しくないパラメーターが渡される可能性があると想定する必要があります。 この場合、は`_In_ _Pre_defensive_`信頼境界で推奨されます。これは、呼び出し元が null を渡そうとした場合にエラーが発生し、関数本体は、パラメーターが null であるかのように分析され、先にポインターを逆参照しようとすると、NULL を確認すると、フラグが設定されます。  `_Post_defensive_`注釈は、信頼できるパーティが呼び出し元であると見なされ、信頼されていないコードが呼び出されたコードであるコールバックで使用することもできます。

## <a name="_out_writes_"></a>\_出力\_の書き込み\_

次の例は、の`_Out_writes_`一般的な誤用を示しています。

```cpp

// Incorrect
void Func1(_Out_writes_(size) CHAR *pb,
    DWORD size
);
```

注釈`_Out_writes_`は、バッファーがあることを示します。 最初の`cb`バイトが終了時に初期化されたバイトが割り当てられています。 この注釈は厳密には間違っていないため、割り当てられたサイズを表すと便利です。 ただし、関数によって初期化される要素の数はわかりません。

次の例では、バッファーの初期化された部分の正確なサイズを完全に指定するための3つの正しい方法を示します。

```cpp

// Correct
void Func1(_Out_writes_to_(size, *pCount) CHAR *pb,
    DWORD size,
    PDWORD pCount
);

void Func2(_Out_writes_all_(size) CHAR *pb,
    DWORD size
);

void Func3(_Out_writes_(size) PSTR pb,
    DWORD size
);
```

## <a name="_out_-pstr"></a>\_Out\_ pstr

の`_Out_ PSTR`使用は、ほぼ常に間違っています。 これは、文字バッファーを指す出力パラメーターがあり、それが NULL で終わると解釈されます。

```cpp

// Incorrect
void Func1(_Out_ PSTR pFileName, size_t n);

// Correct
void Func2(_Out_writes_(n) PSTR wszFileName, size_t n);
```

のよう`_In_ PCSTR`な注釈は、一般的で便利です。 の`_In_`前提条件では、null で終わる文字列を認識できるため、null 終了を含む入力文字列を指します。

## <a name="_in_-wchar-p"></a>\_WCHAR\_ * p 内

`_In_ WCHAR* p`1つの文字を指す入力`p`ポインターがあることを示します。 ただし、ほとんどの場合、これは意図した仕様ではない可能性があります。 代わりに、NULL で終わる配列の指定が想定されています。これを行うには`_In_ PWSTR`、を使用します。

```cpp

// Incorrect
void Func1(_In_ WCHAR* wszFileName);

// Correct
void Func2(_In_ PWSTR wszFileName);
```

NULL 終了の適切な指定が一般的ではありません。 次の例`STR`に示すように、適切なバージョンを使用して型を置き換えます。

```cpp

// Incorrect
BOOL StrEquals1(_In_ PCHAR p1, _In_ PCHAR p2)
{
    return strcmp(p1, p2) == 0;
}

// Correct
BOOL StrEquals2(_In_ PSTR p1, _In_ PSTR p2)
{
    return strcmp(p1, p2) == 0;
}
```

## <a name="_out_range_"></a>\_範囲\_外\_

パラメーターがポインターであり、ポインターによってポイントされている要素の値の範囲を表す場合は、の`_Deref_out_range_` `_Out_range_`代わりにを使用します。 次の例では、* pcbFilled つぶしの範囲を指定しています。 pcbFilled つぶされていません。

```cpp

// Incorrect
void Func1(
    _Out_writes_bytes_to_(cbSize, *pcbFilled) BYTE *pb,
    DWORD cbSize,
    _Out_range_(0, cbSize) DWORD *pcbFilled
);

// Correct
void Func2(
    _Out_writes_bytes_to_(cbSize, *pcbFilled) BYTE *pb,
    DWORD cbSize,
    _Deref_out_range_(0, cbSize) _Out_ DWORD *pcbFilled
);
```

`_Deref_out_range_(0, cbSize)`は、から`_Out_writes_to_(cbSize,*pcbFilled)`推論できるため、一部のツールでは厳密には必須ではありませんが、完全を期すためにここに示します。

## <a name="wrong-context-in-_when_"></a>When の\_コンテキストが正しくありません\_

もう1つの一般的な誤りは、事前条件の事後評価を使用することです。 次の例では`_Requires_lock_held_` 、は前提条件です。

```cpp

// Incorrect
_When_(return == 0, _Requires_lock_held_(p->cs))
int Func1(_In_ MyData *p, int flag);

// Correct
_When_(flag == 0, _Requires_lock_held_(p->cs))
int Func2(_In_ MyData *p, int flag);
```

式`result`が、事前状態では使用できない状態の後の値を参照しています。

## <a name="true-in-_success_"></a>成功し\_た場合は TRUE\_

戻り値が0以外の場合に関数が成功し`return != 0`た場合は、では`return == TRUE`なく成功条件としてを使用します。 0以外のは、コンパイラがに対し`TRUE`て提供する実際の値と等価であるとは限りません。 の`_Success_`パラメーターは式で、次の式は等価として評価さ`return != 0`れます`return != FALSE`。、 `return` 、、およびは、 `return != false`パラメーターも比較もありません。

```cpp

// Incorrect
_Success_(return == TRUE, _Acquires_lock_(*lpCriticalSection))
BOOL WINAPI TryEnterCriticalSection(
  _Inout_ LPCRITICAL_SECTION lpCriticalSection
);

// Correct
_Success_(return != 0, _Acquires_lock_(*lpCriticalSection))
BOOL WINAPI TryEnterCriticalSection(
  _Inout_ LPCRITICAL_SECTION lpCriticalSection
);
```

## <a name="reference-variable"></a>参照変数

参照変数の場合、以前のバージョンの SAL では、暗黙的なポインターを注釈のターゲットとして使用`__deref`し、参照変数に関連付けられている注釈にを追加する必要があります。 このバージョンはオブジェクト自体を使用するため、追加`_Deref_`のを必要としません。

```cpp

// Incorrect
void Func1(
    _Out_writes_bytes_all_(cbSize) BYTE *pb,
    _Deref_ _Out_range_(0, 2) _Out_ DWORD &cbSize
);

// Correct
void Func2(
    _Out_writes_bytes_all_(cbSize) BYTE *pb,
    _Out_range_(0, 2) _Out_ DWORD &cbSize
);
```

## <a name="annotations-on-return-values"></a>戻り値に関する注釈

次の例は、戻り値の注釈における一般的な問題を示しています。

```cpp

// Incorrect
_Out_opt_ void *MightReturnNullPtr1();

// Correct
_Ret_maybenull_ void *MightReturnNullPtr2();
```

この例では`_Out_opt_` 、は、前提条件の一部としてポインターが NULL である可能性があることを示しています。 ただし、事前条件を戻り値に適用することはできません。 この場合、正しい注釈は`_Ret_maybenull_`です。

## <a name="see-also"></a>関連項目

[Sal 注釈を使用した CC++ /コード障害](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
の軽減[sal](../code-quality/understanding-sal.md)
[関数のパラメーターと戻り値](../code-quality/annotating-function-parameters-and-return-values.md)
の注釈[関数の動作](../code-quality/annotating-function-behavior.md)
の注釈付け[構造体とクラス](../code-quality/annotating-structs-and-classes.md)
に注釈を付けて、注釈が[組み込み関数](../code-quality/intrinsic-functions.md)
[に適用されるタイミングと場所を指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)する[ロック動作](../code-quality/annotating-locking-behavior.md)
に注釈を付ける