---
title: DBG_ATTRIB_FLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DBG_ATTRIB_FLAGS
helpviewer_keywords:
- DBGPROP_ATTRIB_FLAGS enumerations
ms.assetid: 2f13e601-dadc-476e-a8ec-01c4515082e7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 831d1326d88e70ffaba2cc0c242c55d7325be705
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689331"
---
# <a name="dbgattribflags"></a>DBG_ATTRIB_FLAGS
さまざまな属性について説明します、 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)または[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)インターフェイス。 メンバー、 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)構造体。

## <a name="syntax"></a>構文

```cpp
#define DBG_ATTRIB_NONE                 0x0000000000000000,
#define DBG_ATTRIB_ALL                  0x00000000ffffffff,

// Attributes about the object itself

#define DBG_ATTRIB_OBJ_IS_EXPANDABLE    0x0000000000000001,
#define DBG_ATTRIB_OBJ_HAS_ID           0x0000000000000002,
#define DBG_ATTRIB_OBJ_CAN_HAVE_ID      0x0000000000000004,

// Attributes about the value of the object

#define DBG_ATTRIB_VALUE_READONLY       0x0000000000000010,
#define DBG_ATTRIB_VALUE_ERROR          0x0000000000000020,
#define DBG_ATTRIB_VALUE_SIDE_EFFECT    0x0000000000000040,
#define DBG_ATTRIB_OVERLOADED_CONTAINER 0x0000000000000080,
#define DBG_ATTRIB_VALUE_BOOLEAN        0x0000000000000100,
#define DBG_ATTRIB_VALUE_BOOLEAN_TRUE   0x0000000000000200,
#define DBG_ATTRIB_VALUE_INVALID        0x0000000000000400,
#define DBG_ATTRIB_VALUE_NAT            0x0000000000000800,
#define DBG_ATTRIB_VALUE_AUTOEXPANDED   0x0000000000001000,
#define DBG_ATTRIB_VALUE_TIMEOUT        0x0000000000002000,
#define DBG_ATTRIB_VALUE_RAW_STRING     0x0000000000004000,
#define DBG_ATTRIB_VALUE_CUSTOM_VIEWER  0x0000000000008000,

// Attributes about field access types for the object

#define DBG_ATTRIB_ACCESS_NONE          0x0000000000010000,
#define DBG_ATTRIB_ACCESS_PUBLIC        0x0000000000020000,
#define DBG_ATTRIB_ACCESS_PRIVATE       0x0000000000040000,
#define DBG_ATTRIB_ACCESS_PROTECTED     0x0000000000080000,
#define DBG_ATTRIB_ACCESS_FINAL         0x0000000000100000,
#define DBG_ATTRIB_ACCESS_ALL           0x00000000001f0000,

// Attributes for the storage types of the object

#define DBG_ATTRIB_STORAGE_NONE         0x0000000001000000,
#define DBG_ATTRIB_STORAGE_GLOBAL       0x0000000002000000,
#define DBG_ATTRIB_STORAGE_STATIC       0x0000000004000000,
#define DBG_ATTRIB_STORAGE_REGISTER     0x0000000008000000,
#define DBG_ATTRIB_STORAGE_ALL          0x000000000f000000,

// Attributes for the type modifiers on the object

#define DBG_ATTRIB_TYPE_NONE            0x0000000100000000,
#define DBG_ATTRIB_TYPE_VIRTUAL         0x0000000200000000,
#define DBG_ATTRIB_TYPE_CONSTANT        0x0000000400000000,
#define DBG_ATTRIB_TYPE_SYNCHRONIZED    0x0000000800000000,
#define DBG_ATTRIB_TYPE_VOLATILE        0x0000001000000000,
#define DBG_ATTRIB_TYPE_ALL             0x0000001f00000000,

// Attributes that describe the type of object

#define DBG_ATTRIB_DATA                 0x0000010000000000,
#define DBG_ATTRIB_METHOD               0x0000020000000000,
#define DBG_ATTRIB_PROPERTY             0x0000040000000000,
#define DBG_ATTRIB_CLASS                0x0000080000000000,
#define DBG_ATTRIB_BASECLASS            0x0000100000000000,
#define DBG_ATTRIB_INTERFACE            0x0000200000000000,
#define DBG_ATTRIB_INNERCLASS           0x0000400000000000,
#define DBG_ATTRIB_MOSTDERIVED          0x0000800000000000,
#define DBG_ATTRIB_CHILD_ALL            0x0000ff0000000000,

// Miscellaneous attributes

#define DBG_ATTRIB_MULTI_CUSTOM_VIEWERS 0x0001000000000000

typedef UINT64 DBG_ATTRIB_FLAGS;
```

```csharp
public const int DBG_ATTRIB_NONE                 = 0x0000000000000000,
public const int DBG_ATTRIB_ALL                  = 0x00000000ffffffff,

// Attributes about the object itself

public const int DBG_ATTRIB_OBJ_IS_EXPANDABLE    = 0x0000000000000001,
public const int DBG_ATTRIB_OBJ_HAS_ID           = 0x0000000000000002,
public const int DBG_ATTRIB_OBJ_CAN_HAVE_ID      = 0x0000000000000004,

// Attributes about the value of the object

public const int DBG_ATTRIB_VALUE_READONLY       = 0x0000000000000010,
public const int DBG_ATTRIB_VALUE_ERROR          = 0x0000000000000020,
public const int DBG_ATTRIB_VALUE_SIDE_EFFECT    = 0x0000000000000040,
public const int DBG_ATTRIB_OVERLOADED_CONTAINER = 0x0000000000000080,
public const int DBG_ATTRIB_VALUE_BOOLEAN        = 0x0000000000000100,
public const int DBG_ATTRIB_VALUE_BOOLEAN_TRUE   = 0x0000000000000200,
public const int DBG_ATTRIB_VALUE_INVALID        = 0x0000000000000400,
public const int DBG_ATTRIB_VALUE_NAT            = 0x0000000000000800,
public const int DBG_ATTRIB_VALUE_AUTOEXPANDED   = 0x0000000000001000,
public const int DBG_ATTRIB_VALUE_TIMEOUT        = 0x0000000000002000,
public const int DBG_ATTRIB_VALUE_RAW_STRING     = 0x0000000000004000,
public const int DBG_ATTRIB_VALUE_CUSTOM_VIEWER  = 0x0000000000008000,

// Attributes about field access types for the object

public const int DBG_ATTRIB_ACCESS_NONE          = 0x0000000000010000,
public const int DBG_ATTRIB_ACCESS_PUBLIC        = 0x0000000000020000,
public const int DBG_ATTRIB_ACCESS_PRIVATE       = 0x0000000000040000,
public const int DBG_ATTRIB_ACCESS_PROTECTED     = 0x0000000000080000,
public const int DBG_ATTRIB_ACCESS_FINAL         = 0x0000000000100000,
public const int DBG_ATTRIB_ACCESS_ALL           = 0x00000000001f0000,

// Attributes for the storage types of the object

public const int DBG_ATTRIB_STORAGE_NONE         = 0x0000000001000000,
public const int DBG_ATTRIB_STORAGE_GLOBAL       = 0x0000000002000000,
public const int DBG_ATTRIB_STORAGE_STATIC       = 0x0000000004000000,
public const int DBG_ATTRIB_STORAGE_REGISTER     = 0x0000000008000000,
public const int DBG_ATTRIB_STORAGE_ALL          = 0x000000000f000000,

// Attributes for the type modifiers on the object

public const int DBG_ATTRIB_TYPE_NONE            = 0x0000000100000000,
public const int DBG_ATTRIB_TYPE_VIRTUAL         = 0x0000000200000000,
public const int DBG_ATTRIB_TYPE_CONSTANT        = 0x0000000400000000,
public const int DBG_ATTRIB_TYPE_SYNCHRONIZED    = 0x0000000800000000,
public const int DBG_ATTRIB_TYPE_VOLATILE        = 0x0000001000000000,
public const int DBG_ATTRIB_TYPE_ALL             = 0x0000001f00000000,

// Attributes that describe the type of object

public const int DBG_ATTRIB_DATA                 = 0x0000010000000000,
public const int DBG_ATTRIB_METHOD               = 0x0000020000000000,
public const int DBG_ATTRIB_PROPERTY             = 0x0000040000000000,
public const int DBG_ATTRIB_CLASS                = 0x0000080000000000,
public const int DBG_ATTRIB_BASECLASS            = 0x0000100000000000,
public const int DBG_ATTRIB_INTERFACE            = 0x0000200000000000,
public const int DBG_ATTRIB_INNERCLASS           = 0x0000400000000000,
public const int DBG_ATTRIB_MOSTDERIVED          = 0x0000800000000000,
public const int DBG_ATTRIB_CHILD_ALL            = 0x0000ff0000000000,

// Miscellaneous attributes

public const int DBG_ATTRIB_MULTI_CUSTOM_VIEWERS = 0x0001000000000000
```

## <a name="members"></a>メンバー
 DBG_ATTRIB_NONE は属性がないことを示します。

 DBG_ATTRIB_ALL では、すべての属性を示します。

 DBG_ATTRIB_OBJ_IS_EXPANDABLE では、参照またはプロパティが子を持つことを示します。

 DBG_ATTRIB_OBJ_HAS_ID では、このオブジェクトの ID が作成されたことを示します。

 DBG_ATTRIB_OBJ_CAN_HAVE_ID では、このオブジェクトの ID を作成できることを示します。

 DBG_ATTRIB_VALUE_READONLY は、値が読み取り専用であることを示します。

 DBG_ATTRIB_VALUE_ERROR 値がエラーであることを示します。

 DBG_ATTRIB_VALUE_SIDE_EFFECT では、評価に副作用があったことを示します。

 DBG_ATTRIB_OVERLOADED_CONTAINER では、このプロパティはオーバー ロードのコンテナーでは実際にことを示します。

 DBG_ATTRIB_VALUE_BOOLEAN をことを示します値`DEBUG_PROPERTY_INFO::bstrValue`はブール値。

 DBG_ATTRIB_VALUE_BOOLEAN_TRUE をことを示します値`DEBUG_PROPERTY_INFO::bstrValue`はブール値と`TRUE`します。

 DBG_ATTRIB_VALUE_INVALID をことを示します値`DEBUG_PROPERTY_INFO::bstrValue`が無効です。

 DBG_ATTRIB_VALUE_NAT をことを示します値`DEBUG_PROPERTY_INFO::bstrValue`は"*物ではなく*"(NAT)。 NAT では、遅延予測の例外を示す Intel 64 ビット プロセッサのレジスタ フラグについて説明します。

 DBG_ATTRIB_VALUE_AUTOEXPANDED をことを示します値`DEBUG_PROPERTY_INFO::bstrValue`自動拡張がされている可能性があります。

 DBG_ATTRIB_VALUE_TIMEOUT を使用して、評価がタイムアウトしたことを示します。

 DBG_ATTRIB_VALUE_RAW_STRING をことを示します値`DEBUG_PROPERTY_INFO::bstrValue`未加工の文字列で表すことができます。

 DBG_ATTRIB_VALUE_CUSTOM_VIEWER では、このプロパティは、少なくとも 1 つのカスタム ビューアーが関連付けられていることを示します。

 DBG_ATTRIB_ACCESS_NONE を持たないオブジェクトを示す`public`、`private`も`protected`へのアクセスを入力します。

 DBG_ATTRIB_ACCESS_PUBLIC では、パブリック アクセス権を持つオブジェクトを示します。

 DBG_ATTRIB_ACCESS_PRIVATE では、プライベート アクセス権を持つオブジェクトを示します。

 DBG_ATTRIB_ACCESS_PROTECTED では、オブジェクトへのアクセスを保護していることを示します。

 DBG_ATTRIB_ACCESS_FINAL では、最終的なアクセス権を持つオブジェクトを示します。

 アクセス権を抽出する DBG_ATTRIB_ACCESS_ALL マスク属性から`DBG_ATTRIB_FLAGS`します。

 DBG_ATTRIB_STORAGE_NONE では、指定されたストレージ型が存在しないことを示します。

 グローバル ストレージの DBG_ATTRIB_STORAGE_GLOBAL ことを示します。

 静的ストレージの DBG_ATTRIB_STORAGE_STATIC ことを示します。

 レジスタのストレージを DBG_ATTRIB_STORAGE_REGISTER を示します。

 記憶域を抽出する DBG_ATTRIB_STORAGE_ALL マスク属性から`DBG_ATTRIB_FLAGS`します。

 DBG_ATTRIB_TYPE_NONE では、型修飾子がないことを示します。

 DBG_ATTRIB_TYPE_VIRTUAL は、オブジェクトの型が仮想であることを示します。

 DBG_ATTRIB_TYPE_CONSTANT は、オブジェクトの型が定数であることを示します。

 DBG_ATTRIB_TYPE_SYNCHRONIZED では、オブジェクトの型が同期されていることを示します。

 DBG_ATTRIB_TYPE_VOLATILE は、オブジェクトの型が volatile であることを示します。

 属性の型を抽出する DBG_ATTRIB_TYPE_ALL マスク`DBG_ATTRIB_FLAGS`します。

 DBG_ATTRIB_DATA では、このオブジェクトは、データ フィールドであることを示します。

 DBG_ATTRIB_METHOD では、このオブジェクトのメソッドであることを示します。

 DBG_ATTRIB_PROPERTY では、このオブジェクトがプロパティであることを示します。

 DBG_ATTRIB_CLASS は、このオブジェクトがクラスであることを示します。

 DBG_ATTRIB_BASECLASS では、このオブジェクトは、基底クラスであることを示します。

 DBG_ATTRIB_INTERFACE は、このオブジェクトがインターフェイスであることを示します。

 DBG_ATTRIB_INNERCLASS では、このオブジェクトは、内部クラスであることを示します。

 DBG_ATTRIB_MOSTDERIVED では、このオブジェクトがあることを示します '*最も多く派生*'。 用語"*最も多く派生*"オブジェクトの実際の型とその参照の型ではありません。

 マスクを示します DBG_ATTRIB_CHILD_ALL`DBG_ATTRIB_DATA`を通じて`DBG_ATTRIB_MOSTDERIVED`します。

 DBG_ATTRIB_MULTI_CUSTOM_VIEWERS では、オブジェクトが複数のカスタム ビューアーが関連付けられていることを示します。

## <a name="remarks"></a>Remarks

> [!NOTE]
>  この列挙体の値は c# のアセンブリに実際に定義されていません。 代わりに、ソース ファイルに定義をコピーする必要があります。

 これらのフラグは、引数として渡されるときに、オブジェクトの子オブジェクトをフィルター処理にも使用[EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)します。 ビットごとの値を組み合わせることができます`OR`します。

 `DBG_ATTRIB_VALUE_CUSTOM_VIEWER`フラグを示す値を[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]を取得する、 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)からインターフェイス、 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)インターフェイスと呼び出し[GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)カスタム ビューアーの一覧についてはします。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
- [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)