---
title: '方法: ビジュアライザーをインストール |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1a75386844e3653a4dbf791980737f8d339072c4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963106"
---
# <a name="how-to-install-a-visualizer"></a>方法: ビジュアライザーをインストールする
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

作成したビジュアライザーは、インストールして初めて [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] で使用できるようになります。 ビジュアライザーのインストールは簡単です。  
  
> [!NOTE]
>  **ストア**アプリ、標準のテキストのみ HTML、XML、および JSON ビジュアライザーがサポートされています。 カスタム (ユーザーが作成した) ビジュアライザーはサポートされていません。  
  
### <a name="to-install-a-visualizer"></a>ビジュアライザーをインストールするには  
  
1.  作成したビジュアライザーを含むダイナミック リンク ライブラリ (DLL: Dynamic Link Library) を探します。  
  
2.  DLL を次のいずれかの場所にコピーします。  
  
    -   *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`  
  
    -   `My Documents\` *VisualStudioVersion* `\Visualizers`  
  
3.  マネージド ビジュアライザーをリモート デバッグで使用するには、DLL をリモート コンピューター上の同じパスにコピーします。  
  
4.  デバッグ セッションを再開します。  
  
## <a name="see-also"></a>関連項目  
 [カスタム ビジュアライザーを作成する](../debugger/create-custom-visualizers-of-data.md)   
 [方法: ビジュアライザーを記述する](../debugger/how-to-write-a-visualizer.md)
