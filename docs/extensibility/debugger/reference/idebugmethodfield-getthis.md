---
title: IDebugMethodField::GetThis |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::GetThis
helpviewer_keywords:
- IDebugMethodField::GetThis method
ms.assetid: cc235bea-e909-4d8c-ab54-936736c803fc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a3e88f209b506d8baf10a779d282a78122c274fb
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211922"
---
# <a name="idebugmethodfieldgetthis"></a>IDebugMethodField::GetThis
取得、 `this` (`Me`で[!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]) メソッドを含むオブジェクトのポインター。

## <a name="syntax"></a>構文

```cpp
HRESULT GetThis( 
   IDebugClassField** ppClass
);
```

```csharp
int GetThis(
   out IDebugClassField ppClass
);
```

## <a name="parameters"></a>パラメーター
`ppClass`\
[out]返します、 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) "this"ポインターを表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 オブジェクト指向の言語では通常、クラスの現在のインスタンス化への暗黙のポインターです。 これと呼ばれます`this`(C#)/C++ として`Me`で[!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]します。

## <a name="see-also"></a>関連項目
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)