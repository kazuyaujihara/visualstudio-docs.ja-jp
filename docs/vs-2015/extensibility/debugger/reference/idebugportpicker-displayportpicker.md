---
title: IDebugPortPicker::DisplayPortPicker |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- DisplayPortPicker
- IDebugPortPicker::DisplayPortPicker
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3dd9317a73800a3886a5a807e9e28b0c24b2301c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963986"
---
# <a name="idebugportpickerdisplayportpicker"></a>IDebugPortPicker::DisplayPortPicker
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

ユーザーがポートを選択できる指定されたダイアログ ボックスが表示されます。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT DisplayPortPicker(  
   HWND hwndParentDialog,  
   BSTR* pbstrPortId  
);  
```  
  
```csharp  
public int DisplayPortPicker(  
   int hwndParentDialog,  
   out string pbstrPortId  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hwndParentDialog`  
 [in]親ダイアログ ボックスのハンドル。  
  
 `pbstrPortId`  
 [out]ポート id 文字列。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。 戻り値`S_FALSE`(または戻り値の`S_OK`で、`BSTR`に設定`NULL`)、ユーザーがクリックされたことを示します**キャンセル**します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)
