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
manager: markl
ms.workload:
- multiple
ms.openlocfilehash: 1bb0e8bdbb2bd62fa637b9cecce64adf98f71013
ms.sourcegitcommit: 535ef05b1e553f0fc66082cd2e0998817eb2a56a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72016052"
---
# <a name="annotating-function-behavior"></a>関数の動作に注釈を付ける
[関数のパラメーターと戻り値](../code-quality/annotating-function-parameters-and-return-values.md)に注釈を付けるだけでなく、関数全体のプロパティに注釈を設定することもできます。

## <a name="function-annotations"></a>関数の注釈
次の注釈は、関数全体に適用され、どのように動作するか、またはどのように動作するかを説明します。

|Annotation|説明|
|----------------|-----------------|
|`_Called_from_function_class_(name)`|スタンドアロン専用ではありません。代わりに、@no__t 0 の注釈と共に使用する述語です。 詳細については、「[注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)」を参照してください。<br /><br /> @No__t-0 パラメーターは任意の文字列であり、一部の関数の宣言で @no__t 1 の注釈にも表示されます。  `_Called_from_function_class_` は、現在分析されている関数が、`name` と同じ値を持つ `_Function_class_` を使用して注釈が付けられている場合は0以外の値を返します。それ以外の場合は0を返します。|
|`_Check_return_`|戻り値に注釈を指定し、呼び出し元がそれを検査する必要があることを示します。 関数が void コンテキストで呼び出された場合、チェッカーはエラーを報告します。|
|`_Function_class_(name)`|@No__t-0 パラメーターは、ユーザーが指定する任意の文字列です。  これは、他の名前空間とは異なる名前空間に存在します。 関数、関数ポインター、または-最も便利な関数ポインター型は、1つまたは複数の関数クラスに属しているものとして指定できます。|
|`_Raises_SEH_exception_`|常に @no__t 0 および @no__t 1 の条件に従って構造化例外ハンドラー (SEH) 例外を発生させる関数に注釈を適用します。 詳細については、「[注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)」を参照してください。|
|`_Maybe_raises_SEH_exception_`|必要に応じて、@no__t 0 および @no__t 1 の条件に従って SEH 例外を発生させる可能性がある関数に注釈を適用します。|
|`_Must_inspect_result_`|戻り値、パラメーター、および globals を含む、すべての出力値に注釈を指定します。  アナライザーは、注釈付きオブジェクトの値がその後検査されない場合にエラーを報告します。 "検査" は、条件式で使用されるか、出力パラメーターまたはグローバルに割り当てられるか、またはパラメーターとして渡されるかを示します。  戻り値の場合、`_Must_inspect_result_` は `_Check_return_` を意味します。|
|`_Use_decl_annotations_`|は、ヘッダー内の注釈のリストの代わりに、関数定義 (関数本体とも呼ばれます) で使用できます。  @No__t-0 が使用されている場合、同じ関数のスコープ内ヘッダーに表示される注釈は、@no__t 1 の注釈を持つ定義にも存在するかのように使用されます。|

## <a name="successfailure-annotations"></a>成功または失敗の注釈
関数が失敗する場合があります。関数が成功すると、結果が不完全になるか、結果と異なる可能性があります。  次の一覧の注釈は、エラーの動作を表現する方法を示しています。  これらの注釈を使用するには、成功したかどうかを判断するために有効にする必要があります。したがって、@no__t 0 の注釈が必要です。  @No__t-0 と `HRESULT` には既に @no__t 2 つの注釈が組み込まれていることに注意してください。ただし、`NTSTATUS` または `HRESULT` で独自の `_Success_` 注釈を指定すると、組み込みの注釈がオーバーライドされます。

|Annotation|説明|
|----------------|-----------------|
|`_Always_(anno_list)`|@No__t-0 と同じです。つまり、`anno_list` の注釈は、関数が成功したかどうかにかかわらず適用されます。|
|`_On_failure_(anno_list)`|@No__t-0 を使用して、明示的に、または typedef の `_Return_type_success_` を暗黙的に指定することによって関数に注釈を付ける場合にのみ使用されます。 @No__t 0 の注釈が関数パラメーターまたは戻り値に存在する場合、`anno_list` (キリスト) の各注釈は `_When_(!expr, anno)` としてコード化されているかのように動作します。ここで、`expr` は、必須の `_Success_` 注釈のパラメーターです。 つまり、すべての事後条件に対する `_Success_` の暗黙的な適用は、`_On_failure_` には適用されません。|
|`_Return_type_success_(expr)`|Typedef に適用できます。 この型を返し、明示的に @no__t 0 を持たないすべての関数に `_Success_(expr)` があるかのように注釈が付けられていることを示します。 `_Return_type_success_` は、関数または関数ポインター typedef では使用できません。|
|`_Success_(expr)`|`expr` は、右辺値を生成する式です。 関数の宣言または定義に @no__t 0 の注釈が存在する場合、関数および事後条件の各注釈 (`anno`) は、`_When_(expr, anno)` としてコーディングされているかのように動作します。 @No__t 0 の注釈は、パラメーターや戻り値の型ではなく、関数でのみ使用できます。 関数には最大で1つの @no__t 0 の注釈を指定できます。また、`_When_`、`_At_`、または `_Group_` にすることはできません。 詳細については、「[注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)」を参照してください。|

## <a name="see-also"></a>関連項目

- [SAL 注釈を使って C/C++ のコード障害を減らす方法](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL について](../code-quality/understanding-sal.md)
- [関数パラメーターおよび戻り値の注釈設定](../code-quality/annotating-function-parameters-and-return-values.md)
- [構造体とクラスに注釈を付ける](../code-quality/annotating-structs-and-classes.md)
- [ロック動作に注釈を付ける](../code-quality/annotating-locking-behavior.md)
- [注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [組み込み関数](../code-quality/intrinsic-functions.md)
- [ベスト プラクティスと例](../code-quality/best-practices-and-examples-sal.md)