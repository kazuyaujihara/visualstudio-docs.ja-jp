---
title: DISASSEMBLY_FLAGS |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DISASSEMBLY_FLAGS
helpviewer_keywords:
- DISASSEMBLY_FLAGS enumeration
ms.assetid: c1ec5a4d-5d42-4660-932c-7348550140cb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0c4602fa1b8d30e9119bb39e925cf7768ae1cbcf
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56682428"
---
# <a name="disassemblyflags"></a>DISASSEMBLY_FLAGS
逆アセンブリのフラグを指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_DISASSEMBLY_FLAGS {
    DF_DOCUMENTCHANGE     = 0x00000001,
    DF_DISABLED           = 0x00000002,
    DF_INSTRUCTION_ACTIVE = 0x00000004,
    DF_DATA               = 0x00000008,
    DF_HASSOURCE          = 0x00000010,
    DF_DOCUMENT_CHECKSUM  = 0x00000020
};
typedef DWORD DISASSEMBLY_FLAGS;
```

```csharp
public enum enum_DISASSEMBLY_FLAGS {
    DF_DOCUMENTCHANGE     = 0x00000001,
    DF_DISABLED           = 0x00000002,
    DF_INSTRUCTION_ACTIVE = 0x00000004,
    DF_DATA               = 0x00000008,
    DF_HASSOURCE          = 0x00000010,
    DF_DOCUMENT_CHECKSUM  = 0x00000020
};
```

## <a name="members"></a>メンバー
DF_DOCUMENTCHANGE では、この命令は、別のドキュメントは、前のことを示します。

DF_DISABLED では、この命令は実行されないことを示します。

DF_INSTRUCTION_ACTIVE では、この命令は、次の手順を実行するのいずれかのことを示します (あります 1 つ以上)。

DF_DATA では、この命令は、データ (コードではなく) で、実際にあることを示します。

DF_HASSOURCE では、この命令がソースのことを示します。 プロファイルまたはガベージ コレクションのコードなどのいくつかの手順では、対応するソースがあるありません。

示す DF_DOCUMENT_CHECKSUM`bstrDocumentUrl`フィールドには、ドキュメントの URL の後のチェックサム データが含まれています。 「解説」を参照してください、 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)チェックサム データを格納する方法の構造体。

## <a name="remarks"></a>Remarks
として使用される、`dwFlags`のメンバー、 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)構造体。

これらのフラグは、演算と組み合わせることがあります`OR`します。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)
