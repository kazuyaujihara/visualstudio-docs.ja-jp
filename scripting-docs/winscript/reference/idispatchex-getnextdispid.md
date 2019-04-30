---
title: IDispatchEx::GetNextDispID | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.GetNextDispID
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetNextDispID method
ms.assetid: 8263d441-85ee-47f4-bdba-fbf2ad07e85f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d964a8744f1f0a28704dd0a1d5e0fd2e67aab1c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62997347"
---
# <a name="idispatchexgetnextdispid"></a>IDispatchEx::GetNextDispID

オブジェクトのメンバーを列挙します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetNextDispID(
   DWORD grfdex,
   DISPID id,
   DISPID *pid
);
```

## <a name="parameters"></a>パラメーター

`grfdex`\
項目のセットが列挙を決定します。 次の値の組み合わせを指定できます。

|[値]|説明|
|-----------|-------------|
|fdexEnumDefault|要求は、オブジェクトは、既定の要素を列挙します。 オブジェクトは任意の要素のセットを列挙するために許可します。|
|fdexEnumAll|要求は、オブジェクトがすべての要素を列挙します。 オブジェクトは任意の要素のセットを列挙するために許可します。|

`id`\
現在のメンバーを識別します。 GetNextDispID では、この後に、列挙内の項目を取得します。 この識別子を取得するのにには、GetDispID または GetNextDispID 以前の呼び出しを使用します。 最初の項目の最初の識別子を取得するのにには、DISPID_STARTENUM 値を使用します。

`pid`\
列挙体の次の項目の識別子を受信するように DISPID 変数のアドレス。

によってメンバーが削除された場合`DeleteMemberByName`または`DeleteMemberByDispID`、`DISPID`の有効なままにする必要がある`GetNextDispID`します。

## <a name="return-value"></a>戻り値

次のいずれかの値を返します。

|||
|-|-|
|`S_OK`|成功。|
|`S_FALSE`|列挙が行われます。|

## <a name="example"></a>例

```cpp
   HRESULT hr;
   BSTR bstrName;
   DISPID dispid;
   IDispatchEx *pdex;

   // Assign to pdex
   hr = pdex->GetNextDispID(fdexEnumAll, DISPID_STARTENUM, &dispid);
   while (hr == NOERROR)
   {
      hr = pdex->GetMemberName(dispid, &bstrName);
      if (!wcscmp(bstrName, OLESTR("Bar")))
      {
         SysFreeString(bstrName);
         return TRUE;
      }
      SysFreeString(bstrName);
      hr = pdex->GetNextDispID(fdexEnumAll, dispid, &dispid);
   }
```

## <a name="see-also"></a>関連項目

- [IDispatchEx インターフェイス](../../winscript/reference/idispatchex-interface.md)
- [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)
- [IDispatchEx::DeleteMemberByName](../../winscript/reference/idispatchex-deletememberbyname.md)
- [IDispatchEx::DeleteMemberByDispID](../../winscript/reference/idispatchex-deletememberbydispid.md)