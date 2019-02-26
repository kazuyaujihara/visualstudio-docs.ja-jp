---
title: FRAMEINFO_FLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- FRAMEINFO_FLAGS
helpviewer_keywords:
- FRAMEINFO_FLAGS enumeration
ms.assetid: 41578062-8455-412a-9d8b-1e1e9dc8d52e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 54bb93fa6f88c02731691728bceacdd4a5fe2036
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694349"
---
# <a name="frameinfoflags"></a>FRAMEINFO_FLAGS
スタック フレーム オブジェクトを取得する情報を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_FRAMEINFO_FLAGS {
    FIF_FUNCNAME              = 0x00000001,
    FIF_RETURNTYPE            = 0x00000002,
    FIF_ARGS                  = 0x00000004,
    FIF_LANGUAGE              = 0x00000008,
    FIF_MODULE                = 0x00000010,
    FIF_STACKRANGE            = 0x00000020,
    FIF_FRAME                 = 0x00000040,
    FIF_DEBUGINFO             = 0x00000080,
    FIF_STALECODE             = 0x00000100,
    FIF_ANNOTATEDFRAME        = 0x00000200,
    FIF_DEBUG_MODULEP         = 0x00000400,
    FIF_FUNCNAME_FORMAT       = 0x00001000,
    FIF_FUNCNAME_RETURNTYPE   = 0x00002000,
    FIF_FUNCNAME_ARGS         = 0x00004000,
    FIF_FUNCNAME_LANGUAGE     = 0x00008000,
    FIF_FUNCNAME_MODULE       = 0x00010000,
    FIF_FUNCNAME_LINES        = 0x00020000,
    FIF_FUNCNAME_OFFSET       = 0x00040000,
    FIF_FUNCNAME_ARGS_TYPES   = 0x00100000,
    FIF_FUNCNAME_ARGS_NAMES   = 0x00200000,
    FIF_FUNCNAME_ARGS_VALUES  = 0x00400000,
    FIF_FUNCNAME_ARGS_ALL     = 0x00700000,
    FIF_ARGS_TYPES            = 0x01000000,
    FIF_ARGS_NAMES            = 0x02000000,
    FIF_ARGS_VALUES           = 0x04000000,
    FIF_ARGS_ALL              = 0x07000000,
    FIF_ARGS_NOFORMAT         = 0x08000000,
    FIF_ARGS_NO_FUNC_EVAL     = 0x10000000,
    FIF_FILTER_NON_USER_CODE  = 0x20000000,
    FIF_ARGS_NO_TOSTRING      = 0x40000000,
    FIF_DESIGN_TIME_EXPR_EVAL = 0x80000000
};
typedef DWORD FRAMEINFO_FLAGS;
```

```csharp
public enum enum_FRAMEINFO_FLAGS {
    FIF_FUNCNAME              = 0x00000001,
    FIF_RETURNTYPE            = 0x00000002,
    FIF_ARGS                  = 0x00000004,
    FIF_LANGUAGE              = 0x00000008,
    FIF_MODULE                = 0x00000010,
    FIF_STACKRANGE            = 0x00000020,
    FIF_FRAME                 = 0x00000040,
    FIF_DEBUGINFO             = 0x00000080,
    FIF_STALECODE             = 0x00000100,
    FIF_ANNOTATEDFRAME        = 0x00000200,
    FIF_DEBUG_MODULEP         = 0x00000400,
    FIF_FUNCNAME_FORMAT       = 0x00001000,
    FIF_FUNCNAME_RETURNTYPE   = 0x00002000,
    FIF_FUNCNAME_ARGS         = 0x00004000,
    FIF_FUNCNAME_LANGUAGE     = 0x00008000,
    FIF_FUNCNAME_MODULE       = 0x00010000,
    FIF_FUNCNAME_LINES        = 0x00020000,
    FIF_FUNCNAME_OFFSET       = 0x00040000,
    FIF_FUNCNAME_ARGS_TYPES   = 0x00100000,
    FIF_FUNCNAME_ARGS_NAMES   = 0x00200000,
    FIF_FUNCNAME_ARGS_VALUES  = 0x00400000,
    FIF_FUNCNAME_ARGS_ALL     = 0x00700000,
    FIF_ARGS_TYPES            = 0x01000000,
    FIF_ARGS_NAMES            = 0x02000000,
    FIF_ARGS_VALUES           = 0x04000000,
    FIF_ARGS_ALL              = 0x07000000,
    FIF_ARGS_NOFORMAT         = 0x08000000,
    FIF_ARGS_NO_FUNC_EVAL     = 0x10000000,
    FIF_FILTER_NON_USER_CODE  = 0x20000000,
    FIF_ARGS_NO_TOSTRING      = 0x40000000,
    FIF_DESIGN_TIME_EXPR_EVAL = 0x80000000
};
```

## <a name="members"></a>メンバー
FIF_FUNCNAME 初期化/使用、`m_bstrFuncName`フィールド。

FIF_RETURNTYPE 初期化/使用、`m_bstrReturnType`フィールド。

FIF_ARGS 初期化/使用、`m_bstrArgs`フィールド。

FIF_LANGUAGE 初期化/使用、`m_bstrLanguage`フィールド。

FIF_MODULE 初期化/使用、`m_bstrModule`フィールド。

FIF_STACKRANGE 初期化/使用、`m_addrMin`と`m_addrMax`(スタックの範囲) フィールド。

FIF_FRAME 初期化/使用、`m_pFrame`フィールド。

FIF_DEBUGINFO 初期化/使用、`m_fHasDebugInfo`フィールド。

FIF_STALECODE 初期化/使用、`m_fStaleCode`フィールド。

FIF_ANNOTATEDFRAME 初期化/使用、`m_fAnnotatedFrame`フィールド。

FIF_DEBUG_MODULEP 初期化/使用、`m_pModule`フィールド。

FIF_FUNCNAME_FORMAT は、関数名を書式設定します。 結果が返されます、`m_bstrFunName`フィールドおよびないその他のフィールドに入力されます。

FIF_FUNCNAME_RETURNTYPE が戻り値の型を追加、`m_bstrFuncName`フィールド。

FIF_FUNCNAME_ARGS 追加の引数、`m_bstrFuncName`フィールド。

FIF_FUNCNAME_LANGUAGE する言語の追加、`m_bstrFuncName`フィールド。

FIF_FUNCNAME_MODULE にモジュール名の追加、`m_bstrFuncName`フィールド。

FIF_FUNCNAME_LINES に追加する行の数、`m_bstrFuncName`フィールド。

FIF_FUNCNAME_OFFSET に追加、`m_bstrFuncName`場合に、行の先頭からのバイト オフセットをフィールド`FIF_FUNCNAME_LINES`を指定します。 場合`FIF_FUNCNAME_LINES`が指定されていないか、行番号が使用できない場合は、バイト単位のオフセットを関数の開始から追加します。

FIF_FUNCNAME_ARGS_TYPES が各関数の引数の型を追加、`m_bstrFuncName`フィールド。

FIF_FUNCNAME_ARGS_NAMES に追加する各関数の引数の名前、`m_bstrFuncName`フィールド。

FIF_FUNCNAME_ARGS_VALUES が各関数の引数の値を追加、`m_bstrFuncName`フィールド。

FIF_FUNCNAME_ARGS_ALL 型、名、およびすべての引数の値を追加、`m_bstrFuncName`フィールド。

FIF_ARGS_TYPES 引数の型が取得されて書式設定します。

FIF_ARGS_NAMES 引数名が取得されて書式設定します。

FIF_ARGS_VALUES 引数の値が取得されて書式設定します。

FIF_ARGS_ALL を取得し、形式、種類、名、およびすべての引数の値。

フォーマットされていない FIF_ARGS_NOFORMAT では、引数には、ことを指定します (たとえば、引数リストをかっこで囲むの開閉の追加もしない引数間の区切り記号を追加) します。

引数の値を取得するときに、FIF_ARGS_NO_FUNC_EVAL では、関数の評価に (プロパティ) ことを指定しますを使用しない必要があります。

FIF_FILTER_NON_USER_CODE デバッグ エンジンでは、含まれていないために、非ユーザー コード フレームをフィルター処理します。

FIF_ARGS_NO_TOSTRING 許可しない`ToString()`関数の評価または関数の引数を返すときに書式設定します。

FIF_DESIGN_TIME_EXPR_EVAL フレーム情報は、ホスト プロセスではなく、ホストされるアプリケーション ドメインから取得する必要があります。

## <a name="remarks"></a>Remarks
これらのフラグに渡される、 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)と[GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)メソッドで初期化するフィールドを示す、 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)構造体または構造体。

これらのフラグは、のどのフィールドを示すためにも使用、 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)構造が返されるときに構造体が使用し、無効です。 これらの値は、演算と組み合わせることがあります`OR`します。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)
- [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)
