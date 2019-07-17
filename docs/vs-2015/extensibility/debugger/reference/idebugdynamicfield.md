---
title: IDebugDynamicField |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugDynamicField
helpviewer_keywords:
- IDebugDynamicField interface
ms.assetid: caffbd95-7596-4714-84b1-b964e89a78bb
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 41cf0e397834f337863baa46abb4e6bbccee98ad
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198506"
---
# <a name="idebugdynamicfield"></a>IDebugDynamicField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このインターフェイスは、変数の型を表します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugDynamicField : IDebugField  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 このインターフェイスは、シンボル プロバイダーによって実行時に判断できる任意の型の基本クラスとして実装されます。 これはマネージ コードのみです。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 このインターフェイスより専門的なインターフェイスの派生元の基本クラスを表します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序メソッド  
 このインターフェイスから継承されたもの以外の任意のメソッドで提供されない`IDebugField`します。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: sh.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [シンボルプロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
