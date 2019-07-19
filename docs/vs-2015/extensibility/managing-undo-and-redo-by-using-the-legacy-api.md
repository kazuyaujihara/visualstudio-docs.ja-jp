---
title: 元に戻したり、レガシ API を使用して再実行の管理 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7c2133c75b32e56c1a054740bd829bd04cac97cc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194370"
---
# <a name="managing-undo-and-redo-by-using-the-legacy-api"></a>レガシ API を使用した元に戻すとやり直しの管理
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

エディターでは、ユーザーがコードを変更するときに、最近の変更内容を反転できるように元に戻す操作をサポートする必要があります。 ほとんどのエディターでは実装[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]、[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]統合開発環境 (IDE) によって自動的に提供元に戻す機能を持つことができます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: 元に戻すの管理を実装する](../extensibility/how-to-implement-undo-management.md)  
 エディターの 1 つまたは複数のビューで元に戻す機能を提供します。  
  
 [方法: 元に戻すスタックをクリアする](../extensibility/how-to-clear-the-undo-stack.md)  
 元に戻すスタックをクリアする方法について説明します。  
  
 [方法: リンクされた元に戻すの管理を使用する](../extensibility/how-to-use-linked-undo-management.md)  
 エディターには、リンク元に戻す管理が組み込まれています。  
  
## <a name="reference"></a>参照  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>  
 複数のビューをサポートしているのため元に戻す管理を提供します。  
  
## <a name="related-sections"></a>関連項目
