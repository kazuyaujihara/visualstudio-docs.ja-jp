---
title: Idiaframedata::get_lengthprolog |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_lengthProlog method
ms.assetid: 5f042ff1-e74e-430a-be34-d2cf1b18eff2
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1542435d38f4b528c52ecc648ad6ef8f79378bd5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963668"
---
# <a name="idiaframedatagetlengthprolog"></a>IDiaFrameData::get_lengthProlog
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

プロローグ コード ブロック内のバイト数を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_lengthProlog (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]プロローグ コードのバイト数を返します。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 プロローグ コードは、レジスタの保持し、CPU の状態を設定し、関数のスタックを確立する命令のシーケンスです。  
  
## <a name="see-also"></a>関連項目  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
