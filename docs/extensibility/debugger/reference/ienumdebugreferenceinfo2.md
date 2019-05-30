---
title: IEnumDebugReferenceInfo2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugReferenceInfo2
helpviewer_keywords:
- IEnumDebugReferenceInfo2
ms.assetid: 7ed01441-686f-4032-8268-a4c750f19f85
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b664b068ac7cd30a7475ab14bfe1b064c98142c2
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66324402"
---
# <a name="ienumdebugreferenceinfo2"></a>IEnumDebugReferenceInfo2
このインターフェイスの列挙[DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)構造体。

## <a name="syntax"></a>構文

```
IEnumDebugReferenceInfo2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 デバッグ エンジン (DE) は、メモリ内オブジェクトへの参照のサポートの一部として、このインターフェイスを実装します。 参照はサポートされている場合にのみ、このインターフェイスを実装する必要があります。

## <a name="notes-for-callers"></a>呼び出し元のノート
 Visual Studio 呼び出し[EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)このインターフェイスを取得します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IEnumDebugReferenceInfo2`します。

|メソッド|説明|
|------------|-----------------|
|[次へ](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-next.md)|指定した数を取得[DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)列挙体シーケンス内の構造体。|
|[Skip](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-skip.md)|指定した数のスキップ[DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)列挙体シーケンス内の構造体。|
|[Reset](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-reset.md)|先頭に、列挙体シーケンスをリセットします。|
|[Clone](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-clone.md)|現在の列挙子と同じ列挙状態を格納する列挙子を作成します。|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-getcount.md)|数を取得[DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)列挙子内の構造体。|

## <a name="remarks"></a>Remarks
 参照は、プロパティは、名前、種類、およびアドレスは、実質的に型と、アドレス。 参照は、メモリ内に存在するオブジェクトが参照される限り、永続化します。 参照してください[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)の詳細。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)