---
title: 関数の動作に注釈を付ける
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _On_failure_
- _Return_type_success_
- _Always_
- _Maybe_raises_SEH_exception_
- _Raises_SEH_exception_
- _Called_from_function_class_
- _Function_class_
- _Must_inspect_result_
- _Success_
- _Check_return_
- _Use_decl_annotations_
ms.assetid: c0aa268d-6fa3-4ced-a8c6-f7652b152e61
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: c7ff2551f3a99bf13909f9db3b1659482246e957
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919623"
---
# <a name="annotating-function-behavior"></a>関数の動作に注釈を付ける
[関数のパラメーターと戻り値](../code-quality/annotating-function-parameters-and-return-values.md)に注釈を付けるだけでなく、関数全体のプロパティに注釈を設定することもできます。

## <a name="function-annotations"></a>関数の注釈
次の注釈は、関数全体に適用され、どのように動作するか、またはどのように動作するかを説明します。

|注釈|説明|
|----------------|-----------------|
|`_Called_from_function_class_(name)`|スタンドアロン専用ではありません。代わりに、 `_When_`注釈と共に使用する述語です。 詳細については、「[注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)」を参照してください。<br /><br /> パラメーターは、一部の関数の宣言内の`_Function_class_`注釈にも含まれる任意の文字列です。 `name`  `_Called_from_function_class_`現在分析されている関数が、と`_Function_class_` `name`同じ値を持つを使用して注釈を付けられている場合は0以外の値を返します。それ以外の場合は0を返します。|
|`_Check_return_`|戻り値に注釈を指定し、呼び出し元がそれを検査する必要があることを示します。 関数が void コンテキストで呼び出された場合、チェッカーはエラーを報告します。|
|`_Function_class_(name)`|`name`パラメーターは、ユーザーが指定する任意の文字列です。  これは、他の名前空間とは異なる名前空間に存在します。 関数、関数ポインター、または-最も便利な関数ポインター型は、1つまたは複数の関数クラスに属しているものとして指定できます。|
|`_Raises_SEH_exception_`|常に構造化例外ハンドラー (SEH) 例外を発生させる関数に注釈を`_When_`適用`_On_failure_`します。 詳細については、「[注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)」を参照してください。|
|`_Maybe_raises_SEH_exception_`|必要に応じて、および条件に`_When_`従って`_On_failure_` SEH 例外を発生させる可能性がある関数に注釈を適用します。|
|`_Must_inspect_result_`|戻り値、パラメーター、および globals を含む、すべての出力値に注釈を指定します。  アナライザーは、注釈付きオブジェクトの値がその後検査されない場合にエラーを報告します。 "検査" は、条件式で使用されるか、出力パラメーターまたはグローバルに割り当てられるか、またはパラメーターとして渡されるかを示します。  戻り値の場合`_Must_inspect_result_` 、 `_Check_return_`はを意味します。|
|`_Use_decl_annotations_`|は、ヘッダー内の注釈のリストの代わりに、関数定義 (関数本体とも呼ばれます) で使用できます。  を`_Use_decl_annotations_`使用する場合、同じ関数のスコープ内ヘッダーに表示される注釈は、 `_Use_decl_annotations_`注釈を持つ定義内にも存在するかのように使用されます。|

## <a name="successfailure-annotations"></a>成功または失敗の注釈
関数が失敗する場合があります。関数が成功すると、結果が不完全になるか、結果と異なる可能性があります。  次の一覧の注釈は、エラーの動作を表現する方法を示しています。  これらの注釈を使用するには、成功したかどうかを判断するために有効にする必要があります。したがって、 `_Success_`注釈が必要です。  `_Success_` `HRESULT` `NTSTATUS`とには既に注釈が組み込まれています。ただし、またはで`_Success_`独自の注釈を指定すると、組み込みの注釈がオーバーライドされます。 `HRESULT` `NTSTATUS`

|注釈|説明|
|----------------|-----------------|
|`_Always_(anno_list)`|と同じです`anno_list` 。つまり、関数が成功したかどうかにかかわらず、内の注釈が適用`anno_list _On_failure_(anno_list)`されます。|
|`_On_failure_(anno_list)`|が、明示的に`_Success_` 、または typedef `_Return_type_success_`上で暗黙的にまたは暗黙的に関数に注釈を付けるためにも使用される場合にのみ使用されます。 `expr` `anno_list` `_When_(!expr, anno)`関数パラメーターまたは戻り値に`_Success_`注釈が存在する場合、(キリスト) の各注釈はとしてコード化されているかのように動作します。ここで、は必要な注釈のパラメーターです。 `_On_failure_` これは、すべての事後条件`_Success_`に対する暗黙のアプリケーションがに`_On_failure_`適用されないことを意味します。|
|`_Return_type_success_(expr)`|Typedef に適用できます。 この型を返し、明示的`_Success_`に指定されていないすべての関数は`_Success_(expr)`、のように注釈が付けられていることを示します。 `_Return_type_success_`は、関数または関数ポインター typedef では使用できません。|
|`_Success_(expr)`|`expr`右辺値を生成する式です。 関数宣言または定義に`anno` `_When_(expr, anno)`注釈が存在する場合、関数および事後条件に対する各注釈()は、としてコード化されているかのように`_Success_`動作します。 `_Success_`注釈は、パラメーターや戻り値の型ではなく、関数でのみ使用できます。 関数には最大1つ`_Success_`の注釈を指定できます。また`_When_`、 `_At_`、、または`_Group_`には指定できません。 詳細については、「[注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)」を参照してください。|

## <a name="see-also"></a>関連項目

- [SAL 注釈を使って C/C++ のコード障害を減らす方法](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL について](../code-quality/understanding-sal.md)
- [関数パラメーターおよび戻り値の注釈設定](../code-quality/annotating-function-parameters-and-return-values.md)
- [構造体とクラスに注釈を付ける](../code-quality/annotating-structs-and-classes.md)
- [ロック動作に注釈を付ける](../code-quality/annotating-locking-behavior.md)
- [注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [組み込み関数](../code-quality/intrinsic-functions.md)
- [ベスト プラクティスと例](../code-quality/best-practices-and-examples-sal.md)