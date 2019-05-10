---
title: IDebugProgramNode2::GetHostMachineName_V7 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramNode2::GetHostMachineName
helpviewer_keywords:
- IDebugProgramNode2::GetHostMachineName_V7
- IDebugProgramNode2::GetHostMachineNameIDebugProgramNode2::GetHostMachineName
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 09919ed73afc9115feffd1f828e9e8d14d1eae79
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457797"
---
# <a name="idebugprogramnode2gethostmachinenamev7"></a>IDebugProgramNode2::GetHostMachineName_V7

> [!Note]
> 非推奨とされます。 使用しないでください。

## <a name="syntax"></a>構文

```cpp
HRESULT GetHostMachineName_V7 (
   BSTR* pbstrHostMachineName
);
```

```csharp
int GetHostMachineName_V7 (
   out string pbstrHostMachineName
);
```

## <a name="parameters"></a>パラメーター

`pbstrHostMachineName`\

 [out]プログラムが実行されているマシンの名前を返します。

## <a name="return-value"></a>戻り値

実装は常に返す必要があります`E_NOTIMPL`します。

## <a name="remarks"></a>Remarks

> [!WARNING]
> Visual Studio 2005 の時点でこのメソッドは使用されなくと常に返す必要があります`E_NOTIMPL`します。

## <a name="see-also"></a>関連項目

- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)