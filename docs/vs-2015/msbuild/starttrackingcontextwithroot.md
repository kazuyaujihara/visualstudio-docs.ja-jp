---
title: StartTrackingContextWithRoot | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
api_name:
- StartTrackingContextWithRoot
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- StartTrackingContextWithRoot
ms.assetid: f6ef2b76-8035-4a14-8195-aa221c46ef48
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 68e80da01a0ab1ad59bbb5bdb06c92c1a11a8ac1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68182322"
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

応答ファイルにルート マーカーを指定し、追跡コンテキストを開始します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `intermediateDirectory`  
 追跡ログを格納するディレクトリ。  
  
 [入力] `taskName`  
 追跡コンテキストを識別します。 この名前はログ ファイル名の作成に使用されます。  
  
 [入力] `rootMarkerResponseFile`  
 ルート マーカーを含む応答ファイルのパス名。 あるコンテキストのすべての追跡をグループ化するためにルート名が使用されます。  
  
## <a name="return-value"></a>戻り値  
 [HRESULT] (<!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->) [SUCCEEDED] (<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->) 追跡コンテキストが作成された場合はビットが設定されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** FileTracker.h  
  
## <a name="see-also"></a>関連項目  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)
