---
title: IDebugDocumentPosition2::GetFileName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentPosition2::GetFileName
helpviewer_keywords:
- IDebugDocumentPosition2::GetFileName
ms.assetid: d713635e-088f-465b-b26d-00ac971c9e86
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8dc5e6ef5317e24e53215dad8f32bc95ee400762
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62921358"
---
# <a name="idebugdocumentposition2getfilename"></a>IDebugDocumentPosition2::GetFileName
ドキュメントの位置を含むソース ファイルのファイル名を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetFileName( 
   BSTR* pbstrFileName
);
```

```csharp
int GetFileName( 
   out string pbstrFileName
);
```

#### <a name="parameters"></a>パラメーター
 `pbstrFileName`

 [out]ソース ファイルのファイル名を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 ソース ファイルは、(、ソース ファイルが存在しないディスクなど) のファイル名を常に必要ありませんがあります。

## <a name="see-also"></a>関連項目
- [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)