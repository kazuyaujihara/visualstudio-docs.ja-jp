---
title: 関数パラメーターおよび戻り値の注釈設定
ms.date: 07/11/2019
ms.topic: conceptual
f1_keywords:
- _Outptr_opt_result_bytebuffer_to_
- _Inout_updates_all_opt_
- _Post_equal_to_
- _Outptr_opt_result_maybenull_
- _Out_writes_bytes_all_
- _Out_writes_all_opt_
- _In_opt_
- _Outptr_
- _Outptr_result_maybenull_
- _Outref_result_bytebuffer_all_maybenull_
- _Inout_updates_opt_z_
- _Inout_updates_z_
- _Out_writes_
- _Out_writes_to_ptr_opt_z_
- _In_reads_to_ptr_opt_
- _Ret_writes_to_maybenull_
- _Outref_result_maybenull_
- _Ret_writes_bytes_
- _Outptr_result_bytebuffer_
- _Out_writes_opt_
- _Inout_updates_bytes_opt_
- _In_z_
- _Inout_updates_to_
- _Ret_maybenull_
- _Ret_writes_bytes_to_
- _Ret_z_
- _COM_Outptr_
- _Ret_maybenull_z_
- _Out_opt_
- _In_reads_opt_z_
- _Outptr_result_bytebuffer_to_
- _Ret_notnull_
- _COM_Outptr_opt_result_maybenull_
- _Inout_updates_to_opt_
- _Inout_updates_
- _Outptr_opt_result_buffer_
- _Outptr_result_buffer_to_
- _Out_writes_to_ptr_opt_
- _Out_writes_bytes_all_opt_
- _Inout_updates_all_
- _Deref_inout_range_
- _Ret_writes_
- _Out_writes_z_
- _Ret_writes_to_
- _Out_writes_to_ptr_z_
- _Out_writes_bytes_to_opt_
- _In_reads_or_z_
- _Inout_updates_bytes_to_
- _In_reads_z_
- _In_opt_z_
- _Outref_result_buffer_maybenull_
- _Ret_range_
- _COM_Outptr_opt_
- _Ouptr_opt_result_maybenull_z_
- _In_reads_opt_
- _Inout_
- _Field_range_
- _Ret_writes_z_
- _Out_writes_to_
- _Out_writes_to_ptr_
- _Inout_opt_z_
- _Outref_
- _Deref_out_range_
- _Outref_result_buffer_
- _Outref_result_buffer_to_
- _Outref_result_bytebuffer_to_maybenull_
- _In_reads_bytes_
- _Outptr_opt_result_buffer_to_
- _Outref_result_buffer_all_
- _Out_writes_bytes_to_
- _Result_zeroonfailure_
- _In_reads_bytes_opt_
- _Outref_result_buffer_to_maybenull_
- _Outref_result_bytebuffer_all_
- _Outref_result_buffer_all_maybenull_
- _Ret_writes_maybenull_z_
- _In_range_
- _Inout_updates_bytes_all_opt_
- _Outref_result_bytebuffer_to_
- _Inout_updates_bytes_to_opt_
- _Pre_equal_to_
- _Ret_writes_bytes_maybenull_
- _COM_Outptr_result_maybenull_
- _Ret_writes_maybenull_
- _Out_writes_bytes_
- _Outptr_opt_
- _Out_writes_opt_z_
- _Outref_result_nullonfailure_
- _Outptr_opt_result_z_
- _Inout_opt_
- _Deref_in_range_
- _Outptr_result_z_
- _In_reads_to_ptr_opt_z_
- _Struct_size_bytes_
- _Outptr_result_nullonfailure_
- _In_
- _Inout_updates_bytes_
- _In_reads_to_ptr_z_
- _Ret_writes_bytes_to_maybenull
- _Outptr_opt_result_nullonfailure_
- _In_reads_to_ptr_
- _Outptr_result_buffer_
- _Out_
- _Outref_result_bytebuffer_maybenull_
- _Outptr_result_maybenull_z_
- _In_reads_
- _Inout_updates_opt_
- _Out_writes_to_opt_
- _Outptr_opt_result_bytebuffer_
- _Out_writes_all_
- _Out_range_
- _Inout_updates_bytes_all_
- _Inout_z_
- _Outref_result_bytebuffer_
- _Result_nullonfailure_
- _Ret_null_
- _Scanf_format_string_
- _Scanf_s_format_string_
- _Printf_format_string_
ms.assetid: 82826a3d-0c81-421c-8ffe-4072555dca3a
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 8f07650e47398b028460776f41557a3f853eaad3
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919614"
---
# <a name="annotating-function-parameters-and-return-values"></a>関数パラメーターおよび戻り値の注釈設定
この記事では、単純な関数パラメーター (スカラー、構造体とクラスへのポインター)、およびほとんどの種類のバッファーに対する注釈の一般的な使用方法について説明します。  この記事では、注釈の一般的な使用パターンについても説明します。 関数に関連するその他の注釈については、「[関数の動作に注釈を付ける](../code-quality/annotating-function-behavior.md)」を参照してください。

## <a name="pointer-parameters"></a>ポインター パラメーター
次の表の注釈については、ポインターパラメーターに注釈を付けると、ポインターが null の場合、アナライザーはエラーを報告します。  これは、ポインターと、ポイントされている任意のデータ項目に適用されます。

**注釈と説明**

- `_In_`

     スカラー、構造体、構造体へのポインター、およびなどの入力パラメーターに注釈を入力します。  単純なスカラーでは、明示的に使用できます。  パラメーターは、事前状態で有効である必要があり、変更されません。

- `_Out_`

     スカラー、構造体、構造体へのポインター、およびなどの出力パラメーターに注釈を記述します。  値で渡されるスカラーなど、値を返すことができないオブジェクトには適用しないでください。  パラメーターは、事前状態では有効である必要はありませんが、事後状態で有効である必要があります。

- `_Inout_`

     関数によって変更されるパラメーターに注釈を設定します。  これは、事前状態と事後状態の両方で有効である必要がありますが、呼び出しの前後に異なる値があると見なされます。 変更可能な値に適用する必要があります。

- `_In_z_`

     入力として使用される、null で終わる文字列へのポインター。  文字列は、事前状態で有効である必要があります。  には`PSTR`、既に正しい注釈があるのバリアントが推奨されています。

- `_Inout_z_`

     変更される null で終わる文字配列へのポインター。  呼び出しの前後で有効である必要がありますが、値は変更されたと見なされます。  Null 終端文字は移動できますが、元の null 終端文字までの要素のみがアクセスされる可能性があります。

- `_In_reads_(s)`

     `_In_reads_bytes_(s)`

     関数によって読み取られる配列へのポインター。  配列はサイズ`s`の要素であり、すべて有効である必要があります。

     バリアント`_bytes_`は、要素の代わりにサイズをバイト単位で示します。 この値は、サイズを要素として表現できない場合にのみ使用してください。  たとえば、文字列`char`では、を`_bytes_`使用`wchar_t`する同様の関数がの場合にのみ、バリアントが使用されます。

- `_In_reads_z_(s)`

     Null で終了し、既知のサイズを持つ配列へのポインター。 Null 終端文字`s`までの要素 (null 終端文字がない場合) は、事前状態で有効である必要があります。  サイズがバイト単位でわかっている場合`s`は、要素のサイズでスケールします。

- `_In_reads_or_z_(s)`

     Null で終わるか、既知のサイズ (またはその両方) を持つ配列へのポインター。 Null 終端文字`s`までの要素 (null 終端文字がない場合) は、事前状態で有効である必要があります。  サイズがバイト単位でわかっている場合`s`は、要素のサイズでスケールします。  ( `strn`ファミリで使用されます)。

- `_Out_writes_(s)`

     `_Out_writes_bytes_(s)`

     関数によって書き込まれる`s`要素の配列 (resp) へのポインター。  配列要素は、事前状態で有効である必要はなく、事後状態で有効な要素の数が指定されていません。  パラメーターの型に注釈がある場合は、事後状態で適用されます。 次に例を示します。

     `typedef _Null_terminated_ wchar_t *PWSTR; void MyStringCopy(_Out_writes_ (size) PWSTR p1,    _In_ size_t size,    _In_ PWSTR p2);`

     この例では、呼び出し元はの`size` `p1`要素のバッファーを提供します。  `MyStringCopy`これらの要素の一部を有効にします。 さらに重要な`_Null_terminated_`のは`PWSTR` 、の`p1`注釈は、が post 状態で null で終了することを意味します。  この方法では、有効な要素の数は引き続き明確に定義されますが、特定の要素数は必要ありません。

     バリアント`_bytes_`は、要素の代わりにサイズをバイト単位で示します。 この値は、サイズを要素として表現できない場合にのみ使用してください。  たとえば、文字列`char`では、を`_bytes_`使用`wchar_t`する同様の関数がの場合にのみ、バリアントが使用されます。

- `_Out_writes_z_(s)`

     要素の配列への`s`ポインター。  要素は、事前状態で有効である必要はありません。  事後の状態では、null 終端文字 (存在する必要がある) を介して要素が有効である必要があります。  サイズがバイト単位でわかっている場合`s`は、要素のサイズでスケールします。

- `_Inout_updates_(s)`

     `_Inout_updates_bytes_(s)`

     配列へのポインター。関数内で読み取りと書き込みの両方を行います。  これはサイズ`s`の要素であり、事前状態と事後状態で有効です。

     バリアント`_bytes_`は、要素の代わりにサイズをバイト単位で示します。 この値は、サイズを要素として表現できない場合にのみ使用してください。  たとえば、文字列`char`では、を`_bytes_`使用`wchar_t`する同様の関数がの場合にのみ、バリアントが使用されます。

- `_Inout_updates_z_(s)`

     Null で終了し、既知のサイズを持つ配列へのポインター。 Null 終端文字 (存在する必要がある) までの要素は、事前状態と事後状態の両方で有効である必要があります。  事後状態の値は、前の状態の値とは異なるものと見なされます。これには、null 終端文字の場所も含まれます。 サイズがバイト単位でわかっている場合`s`は、要素のサイズでスケールします。

- `_Out_writes_to_(s,c)`

     `_Out_writes_bytes_to_(s,c)`

     `_Out_writes_all_(s)`

     `_Out_writes_bytes_all_(s)`

     要素の配列への`s`ポインター。  要素は、事前状態で有効である必要はありません。  事後の状態では、 `c`-th 要素までの要素が有効である必要があります。  サイズがバイト単位でわかっている場合`s`は`c` 、スケールと`_bytes_`要素サイズを使用するか、次のように定義されている variant を使用します。

     `_Out_writes_to_(_Old_(s), _Old_(s))    _Out_writes_bytes_to_(_Old_(s), _Old_(s))`

     つまり、前の状態にあるバッファー `s`に存在するすべての要素は、post 状態で有効です。  例えば:

     `void *memcpy(_Out_writes_bytes_all_(s) char *p1,    _In_reads_bytes_(s) char *p2,    _In_ int s); void * wordcpy(_Out_writes_all_(s) DWORD *p1,     _In_reads_(s) DWORD *p2,    _In_ int s);`

- `_Inout_updates_to_(s,c)`

     `_Inout_updates_bytes_to_(s,c)`

     配列へのポインター。この配列は、関数によって読み取られ、書き込まれます。  これはサイズ`s`の要素であり、すべてが事前状態`c`で有効である必要があり、要素は事後状態で有効である必要があります。

     バリアント`_bytes_`は、要素の代わりにサイズをバイト単位で示します。 この値は、サイズを要素として表現できない場合にのみ使用してください。  たとえば、文字列`char`では、を`_bytes_`使用`wchar_t`する同様の関数がの場合にのみ、バリアントが使用されます。

- `_Inout_updates_z_(s)`

     Null で終了し、既知のサイズを持つ配列へのポインター。 Null 終端文字 (存在する必要がある) までの要素は、事前状態と事後状態の両方で有効である必要があります。  事後状態の値は、前の状態の値とは異なるものと見なされます。これには、null 終端文字の場所も含まれます。 サイズがバイト単位でわかっている場合`s`は、要素のサイズでスケールします。

- `_Out_writes_to_(s,c)`

     `_Out_writes_bytes_to_(s,c)`

     `_Out_writes_all_(s)`

     `_Out_writes_bytes_all_(s)`

     要素の配列への`s`ポインター。  要素は、事前状態で有効である必要はありません。  事後の状態では、 `c`-th 要素までの要素が有効である必要があります。  サイズがバイト単位でわかっている場合`s`は`c` 、スケールと`_bytes_`要素サイズを使用するか、次のように定義されている variant を使用します。

     `_Out_writes_to_(_Old_(s), _Old_(s))    _Out_writes_bytes_to_(_Old_(s), _Old_(s))`

     つまり、前の状態にあるバッファー `s`に存在するすべての要素は、post 状態で有効です。  例えば:

     `void *memcpy(_Out_writes_bytes_all_(s) char *p1,    _In_reads_bytes_(s) char *p2,    _In_ int s); void * wordcpy(_Out_writes_all_(s) DWORD *p1,     _In_reads_(s) DWORD *p2,    _In_ int s);`

- `_Inout_updates_to_(s,c)`

     `_Inout_updates_bytes_to_(s,c)`

     配列へのポインター。この配列は、関数によって読み取られ、書き込まれます。  これはサイズ`s`の要素であり、すべてが事前状態`c`で有効である必要があり、要素は事後状態で有効である必要があります。

     バリアント`_bytes_`は、要素の代わりにサイズをバイト単位で示します。 この値は、サイズを要素として表現できない場合にのみ使用してください。  たとえば、文字列`char`では、を`_bytes_`使用`wchar_t`する同様の関数がの場合にのみ、バリアントが使用されます。

- `_Inout_updates_all_(s)`

     `_Inout_updates_bytes_all_(s)`

     サイズ`s`要素の関数によって読み取られ、書き込まれる配列へのポインター。 次の同等のものとして定義されます。

     `_Inout_updates_to_(_Old_(s), _Old_(s))    _Inout_updates_bytes_to_(_Old_(s), _Old_(s))`

     つまり、前の状態`s`にあるバッファーに存在するすべての要素は、事前状態と事後状態で有効です。

     バリアント`_bytes_`は、要素の代わりにサイズをバイト単位で示します。 この値は、サイズを要素として表現できない場合にのみ使用してください。  たとえば、文字列`char`では、を`_bytes_`使用`wchar_t`する同様の関数がの場合にのみ、バリアントが使用されます。

- `_In_reads_to_ptr_(p)`

     式`p` (つまり、 - からを`p` 減算`_Curr_`) が適切な言語標準で定義されている配列へのポインター。 `_Curr_`  の前`p`の要素は、事前状態で有効である必要があります。

- `_In_reads_to_ptr_z_(p)`

     式`p` ( - つまり、から`p` )が適切な言語標準で定義されている、nullで終わる配列へのポインター。`_Curr_` `_Curr_`  の前`p`の要素は、事前状態で有効である必要があります。

- `_Out_writes_to_ptr_(p)`

     式`p` (つまり、 - からを`p` 減算`_Curr_`) が適切な言語標準で定義されている配列へのポインター。 `_Curr_`  より前`p`の要素は、事前状態で有効である必要はなく、事後状態で有効である必要があります。

- `_Out_writes_to_ptr_z_(p)`

     式`p` ( - つまり、から`p` )が適切な言語標準で定義されている、nullで終わる配列へのポインター。`_Curr_` `_Curr_`  より前`p`の要素は、事前状態で有効である必要はなく、事後状態で有効である必要があります。

## <a name="optional-pointer-parameters"></a>省略可能なポインター パラメーター

ポインターパラメーター注釈にが含ま`_opt_`れている場合は、パラメーターが null である可能性があることを示します。 それ以外の場合、注釈はを含ま`_opt_`ないバージョンと同じように実行されます。 ポインターパラメーター注釈の`_opt_`バリアントの一覧を次に示します。

||||
|-|-|-|
|`_In_opt_`<br /><br /> `_Out_opt_`<br /><br /> `_Inout_opt_`<br /><br /> `_In_opt_z_`<br /><br /> `_Inout_opt_z_`<br /><br /> `_In_reads_opt_`<br /><br /> `_In_reads_bytes_opt_`<br /><br /> `_In_reads_opt_z_`|`_Out_writes_opt_`<br /><br /> `_Out_writes_opt_z_`<br /><br /> `_Inout_updates_opt_`<br /><br /> `_Inout_updates_bytes_opt_`<br /><br /> `_Inout_updates_opt_z_`<br /><br /> `_Out_writes_to_opt_`<br /><br /> `_Out_writes_bytes_to_opt_`<br /><br /> `_Out_writes_all_opt_`<br /><br /> `_Out_writes_bytes_all_opt_`|`_Inout_updates_to_opt_`<br /><br /> `_Inout_updates_bytes_to_opt_`<br /><br /> `_Inout_updates_all_opt_`<br /><br /> `_Inout_updates_bytes_all_opt_`<br /><br /> `_In_reads_to_ptr_opt_`<br /><br /> `_In_reads_to_ptr_opt_z_`<br /><br /> `_Out_writes_to_ptr_opt_`<br /><br /> `_Out_writes_to_ptr_opt_z_`|

## <a name="output-pointer-parameters"></a>出力のポインター パラメーター
出力ポインターパラメーターは、パラメーターとポイント先の位置を明確に区別するために特別な表記を必要とします。

**注釈と説明**

- `_Outptr_`

   パラメーターを null にすることはできません。また、post 状態では、ポイント先の場所を null にすることはできず、有効である必要があります。

- `_Outptr_opt_`

   パラメーターは null でもかまいませんが、post 状態では、ポイント先の場所を null にすることはできず、有効である必要があります。

- `_Outptr_result_maybenull_`

   パラメーターを null にすることはできません。また、状態を示す位置を null にすることもできます。

- `_Outptr_opt_result_maybenull_`

   パラメーターは null にすることができます。また、状態を示す位置を null にすることもできます。

  次の表では、注釈の意味をさらに修飾するために、注釈名に追加の部分文字列が挿入されています。  さまざまな部分文字列`_z`は`_COM_` `_buffer_`、 `_to_` `_bytebuffer_`、、、、およびです。

> [!IMPORTANT]
> 注釈を付けているインターフェイスが COM である場合は、これらの注釈の COM 形式を使用します。 COM 注釈は、他の型インターフェイスと一緒に使用しないでください。

**注釈と説明**

- `_Outptr_result_z_`

   `_Outptr_opt_result_z_`

   `_Outptr_result_maybenull_z_`

   `_Ouptr_opt_result_maybenull_z_`

   返されたポインターに`_Null_terminated_`は注釈があります。

- `_COM_Outptr_`

   `_COM_Outptr_opt_`

   `_COM_Outptr_result_maybenull_`

   `_COM_Outptr_opt_result_maybenull_`

   返されたポインターには COM セマンティクスがあるため`_On_failure_` 、返されたポインターが null であることを示す事後条件が発生します。

- `_Outptr_result_buffer_(s)`

   `_Outptr_result_bytebuffer_(s)`

   `_Outptr_opt_result_buffer_(s)`

   `_Outptr_opt_result_bytebuffer_(s)`

   返されたポインターは、サイズ`s`要素またはバイトの有効なバッファーを指しています。

- `_Outptr_result_buffer_to_(s, c)`

   `_Outptr_result_bytebuffer_to_(s, c)`

   `_Outptr_opt_result_buffer_to_(s,c)`

   `_Outptr_opt_result_bytebuffer_to_(s,c)`

   返されたポインターは、1つ目`s` `c`が有効なサイズ要素またはバイトのバッファーを指しています。

  特定のインターフェイスの規則では、出力パラメーターが失敗時に nullified されることを前提としています。  明示的な COM コードを除き、次の表のフォームを使用することをお勧めします。  COM コードの場合は、前のセクションで示した対応する COM フォームを使用します。

  **注釈と説明**

- `_Result_nullonfailure_`

   他の注釈を変更します。 関数が失敗した場合、結果は null に設定されます。

- `_Result_zeroonfailure_`

   他の注釈を変更します。 関数が失敗した場合、結果は0に設定されます。

- `_Outptr_result_nullonfailure_`

   関数が成功した場合、返されるポインターは有効なバッファーを指します。関数が失敗した場合は null を指します。 この注釈は、省略可能なパラメーターに対してのみ使用されます。

- `_Outptr_opt_result_nullonfailure_`

   関数が成功した場合、返されるポインターは有効なバッファーを指します。関数が失敗した場合は null を指します。 この注釈は省略可能なパラメーターのためのものです。

- `_Outref_result_nullonfailure_`

   関数が成功した場合、返されるポインターは有効なバッファーを指します。関数が失敗した場合は null を指します。 この注釈は、参照パラメーターを対象としています。

## <a name="output-reference-parameters"></a>出力の参照パラメーター

参照パラメーターの一般的な使用方法は、出力パラメーター用です。  単純な出力参照パラメーター (など) の`int&`場合`_Out_` 、は正しいセマンティクスを提供します。  ただし、出力値がポインターの場合 (たとえば`int *&`)、のような`_Outptr_ int **`同等のポインター注釈は、正しいセマンティクスを提供しません。  ポインター型の出力参照パラメーターのセマンティクスを簡潔に表現するには、次の複合注釈を使用します。

**注釈と説明**

- `_Outref_`

     結果は、事後の状態で有効である必要があります。 null にすることはできません。

- `_Outref_result_maybenull_`

     結果は事後状態で有効である必要がありますが、事後状態では null である可能性があります。

- `_Outref_result_buffer_(s)`

     結果は、事後の状態で有効である必要があります。 null にすることはできません。 は、サイズ`s`要素の有効なバッファーを指します。

- `_Outref_result_bytebuffer_(s)`

     結果は、事後の状態で有効である必要があります。 null にすることはできません。 サイズ`s`バイトの有効なバッファーを指しています。

- `_Outref_result_buffer_to_(s, c)`

     結果は、事後の状態で有効である必要があります。 null にすることはできません。 は、要素の`s`バッファーを指します。最初`c`の要素は有効です。

- `_Outref_result_bytebuffer_to_(s, c)`

     結果は、事後の状態で有効である必要があります。 null にすることはできません。 `s` 最初`c`のが有効なバイトのバッファーを指します。

- `_Outref_result_buffer_all_(s)`

     結果は、事後の状態で有効である必要があります。 null にすることはできません。 有効なバッファーサイズ`s`の有効な要素を指しています。

- `_Outref_result_bytebuffer_all_(s)`

     結果は、事後の状態で有効である必要があります。 null にすることはできません。 有効な要素のバイト`s`の有効なバッファーを指しています。

- `_Outref_result_buffer_maybenull_(s)`

     結果は事後状態で有効である必要がありますが、事後状態では null である可能性があります。 は、サイズ`s`要素の有効なバッファーを指します。

- `_Outref_result_bytebuffer_maybenull_(s)`

     結果は事後状態で有効である必要がありますが、事後状態では null である可能性があります。 サイズ`s`バイトの有効なバッファーを指しています。

- `_Outref_result_buffer_to_maybenull_(s, c)`

     結果は事後状態で有効である必要がありますが、事後状態では null である可能性があります。 は、要素の`s`バッファーを指します。最初`c`の要素は有効です。

- `_Outref_result_bytebuffer_to_maybenull_(s,c)`

     結果は事後状態で有効である必要がありますが、post 状態では null である可能性があります。 `s` 最初`c`のが有効なバイトのバッファーを指します。

- `_Outref_result_buffer_all_maybenull_(s)`

     結果は事後状態で有効である必要がありますが、post 状態では null である可能性があります。 有効なバッファーサイズ`s`の有効な要素を指しています。

- `_Outref_result_bytebuffer_all_maybenull_(s)`

     結果は事後状態で有効である必要がありますが、post 状態では null である可能性があります。 有効な要素のバイト`s`の有効なバッファーを指しています。

## <a name="return-values"></a>戻り値

関数の戻り値はパラメーターに`_Out_`似ていますが、逆参照のレベルが異なるため、結果へのポインターの概念を考慮する必要はありません。  次の注釈について、戻り値は注釈付きオブジェクト (スカラー、構造体へのポインター、またはバッファーへのポインター) です。 これらの注釈は、対応する`_Out_`注釈と同じセマンティクスを持ちます。

|||
|-|-|
|`_Ret_z_`<br /><br /> `_Ret_writes_(s)`<br /><br /> `_Ret_writes_bytes_(s)`<br /><br /> `_Ret_writes_z_(s)`<br /><br /> `_Ret_writes_to_(s,c)`<br /><br /> `_Ret_writes_maybenull_(s)`<br /><br /> `_Ret_writes_to_maybenull_(s)`<br /><br /> `_Ret_writes_maybenull_z_(s)`|`_Ret_maybenull_`<br /><br /> `_Ret_maybenull_z_`<br /><br /> `_Ret_null_`<br /><br /> `_Ret_notnull_`<br /><br /> `_Ret_writes_bytes_to_`<br /><br /> `_Ret_writes_bytes_maybenull_`<br /><br /> `_Ret_writes_bytes_to_maybenull_`|

## <a name="format-string-parameters"></a>書式指定文字列パラメーター

- `_Printf_format_string_`パラメーターが`printf`式で使用する書式指定文字列であることを示します。

     **例**

    ```cpp
    int MyPrintF(_Printf_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwprintf(format, args);
           va_end(args);
           return ret;
    }
    ```

- `_Scanf_format_string_`パラメーターが`scanf`式で使用する書式指定文字列であることを示します。

     **例**

    ```cpp
    int MyScanF(_Scanf_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwscanf(format, args);
           va_end(args);
           return ret;
    }
    ```

- `_Scanf_s_format_string_`パラメーターが`scanf_s`式で使用する書式指定文字列であることを示します。

     **例**

    ```cpp
    int MyScanF_s(_Scanf_s_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwscanf_s(format, args);
           va_end(args);
           return ret;
    }
    ```

## <a name="other-common-annotations"></a>その他の一般的な注釈

**注釈と説明**

- `_In_range_(low, hi)`

     `_Out_range_(low, hi)`

     `_Ret_range_(low, hi)`

     `_Deref_in_range_(low, hi)`

     `_Deref_out_range_(low, hi)`

     `_Deref_inout_range_(low, hi)`

     `_Field_range_(low, hi)`

     パラメーター、フィールド、または結果は、から`low`までの範囲内にあります (を`hi`含む)。  注釈付きオブジェクトに適切な状態または状態の条件と共に適用されると同じです。`_Satisfies_(_Curr_ >= low && _Curr_ <= hi)`

    > [!IMPORTANT]
    > 名前には "in" と "out" が含まれてい`_In_`ます`_Out_`が、とのセマンティクスはこれらの注釈には適用**されません**。

- `_Pre_equal_to_(expr)`

     `_Post_equal_to_(expr)`

     注釈付きの値は`expr`正確にです。  注釈付きオブジェクトに適切な状態または状態の条件と共に適用されると同じです。`_Satisfies_(_Curr_ == expr)`

- `_Struct_size_bytes_(size)`

     構造体またはクラスの宣言に適用されます。  この型の有効なオブジェクトが、で`size`指定されたバイト数を使用して、宣言された型よりも大きくなる可能性があることを示します。  例えば:

     `typedef _Struct_size_bytes_(nSize) struct MyStruct {    size_t nSize;    ... };`

     次に、型`pM` `MyStruct *`のパラメーターのバッファーサイズ (バイト単位) を次のように取得します。

     `min(pM->nSize, sizeof(MyStruct))`

## <a name="related-resources"></a>関連資料

[コード分析チームのブログ](http://go.microsoft.com/fwlink/?LinkId=251197)

## <a name="see-also"></a>関連項目

- [SAL 注釈を使って C/C++ のコード障害を減らす方法](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL について](../code-quality/understanding-sal.md)
- [関数の動作に注釈を付ける](../code-quality/annotating-function-behavior.md)
- [構造体とクラスに注釈を付ける](../code-quality/annotating-structs-and-classes.md)
- [ロック動作に注釈を付ける](../code-quality/annotating-locking-behavior.md)
- [注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [組み込み関数](../code-quality/intrinsic-functions.md)
- [ベスト プラクティスと例](../code-quality/best-practices-and-examples-sal.md)