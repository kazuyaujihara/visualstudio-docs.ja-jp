---
title: BP_LOCATION_TYPE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_LOCATION_TYPE
helpviewer_keywords:
- BP_LOCATION_TYPE structure
ms.assetid: 0248430a-3b61-4809-87a9-e9b6bb7d1130
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1695c61a829cf1439ed773e48088430f36f8c653
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56715662"
---
# <a name="bplocationtype"></a>BP_LOCATION_TYPE
ブレークポイント要求のブレークポイントの場所の種類を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_BP_LOCATION_TYPE {
    BPLT_NONE               = 0x00000000,
    BPLT_FILE_LINE          = 0x00010000,
    BPLT_FUNC_OFFSET        = 0x00020000,
    BPLT_CONTEXT            = 0x00030000,
    BPLT_STRING             = 0x00040000,
    BPLT_ADDRESS            = 0x00050000,
    BPLT_RESOLUTION         = 0x00060000,
    BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,
    BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,
    BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,
    BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,
    BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,
    BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,
    BPLT_TYPE_MASK          = 0x0000FFFF,
    BPLT_LOCATION_TYPE_MASK = 0xFFFF0000
};
typedef DWORD BP_LOCATION_TYPE;
```

```csharp
public enum enum_BP_LOCATION_TYPE {
    BPLT_NONE               = 0x00000000,
    BPLT_FILE_LINE          = 0x00010000,
    BPLT_FUNC_OFFSET        = 0x00020000,
    BPLT_CONTEXT            = 0x00030000,
    BPLT_STRING             = 0x00040000,
    BPLT_ADDRESS            = 0x00050000,
    BPLT_RESOLUTION         = 0x00060000,
    BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,
    BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,
    BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,
    BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,
    BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,
    BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,
    BPLT_TYPE_MASK          = 0x0000FFFF,
    BPLT_LOCATION_TYPE_MASK = 0xFFFF0000
};
```

## <a name="members"></a>メンバー
BPLT_NONE はブレークポイントの位置を指定しません。

BPLT_FILE_LINE では、ファイルの行として、ブレークポイントの場所の種類を指定します。

BPLT_FUNC_OFFSET では、関数のオフセットとして、ブレークポイントの場所の種類を指定します。

BPLT_CONTEXT では、コンテキストとして、ブレークポイントの場所の種類を指定します。

BPLT_STRING では、文字列として、ブレークポイントの場所の種類を指定します。

BPLT_ADDRESS では、アドレスとして、ブレークポイントの場所の種類を指定します。

BPLT_RESOLUTION では、解決方法として、ブレークポイントの場所の種類を指定します。

BPLT_CODE_FILE_LINE では、ソース コードの行として、ブレークポイントの場所の種類を指定します。

BPLT_CODE_FUNC_OFFSET では、コードの関数のオフセットとして、ブレークポイントの場所の種類を指定します。

BPLT_CODE_CONTEXT では、コードのコンテキストとして、ブレークポイントの場所の種類を指定します。

BPLT_CODE_STRING では、コードの文字列として、ブレークポイントの場所の種類を指定します。

BPLT_CODE_ADDRESS は、コード アドレスとして、ブレークポイントの場所の種類を指定します。

BPLT_DATA_STRING では、データの文字列として、ブレークポイントの場所の種類を指定します。

BPLT_TYPE_MASK を示すビット マスク、ブレークポイントの種類は、値から抽出できるようにします。

BPLT_LOCATION_TYPE_MASK を示すビット マスク、ブレークポイントの場所の種類は、値から抽出できるようにします。

## <a name="remarks"></a>Remarks
パラメーターとして渡される、 [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)メソッド。

ブレークポイントの場所の種類は、ブレークポイントの種類と場所の種類で構成されます。 つまり、ブレークポイントの場所の種類は、ブレークポイントの種類だけではありません (たとえば、 `BPT_CODE`) または場所の種類 (たとえば、 `BPLT_FILE_LINE`)。 現在サポートされているすべてのブレークポイントの場所の種類の定義済み定数は、この列挙体に含まれる (`BPLT_CODE_FILE_LINE`を通じて`BPLT_DATA_STRING`)。

`BPT_CODE` `BPT_DATA`のメンバーである、 [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)列挙体。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)
- [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)
