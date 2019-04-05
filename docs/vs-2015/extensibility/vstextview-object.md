---
title: VSTextView オブジェクト |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VSTextView
helpviewer_keywords:
- VSTextView object, reference
- views [Visual Studio SDK], reference
ms.assetid: 78272ddc-9718-4c65-a94e-a44a2e8d54f4
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e8ed14761b77e3469b2c19d0e9fd2ff3732bb72d
ms.sourcegitcommit: 447f2174bdecdd471d8a8e11c19554977db620a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2019
ms.locfileid: "59002111"
---
# <a name="vstextview-object"></a>VSTextView オブジェクト
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

テキスト ビューは、ユーザーを表示し、テキスト バッファーの Unicode テキストを編集できるウィンドウです。 基本的には、ビューは、ほとんどのユーザーではこれをエディターとして参照します。 ビューは、バッファーからさまざまなテキスト レイヤー (ワード ラップ、アウトラインのテキスト) で区切られた、ため、ビューは、バッファー内のテキストの正確な表現には保証されません。 テキスト ビューの詳細については、次を参照してください[レガシ API を使用してテキスト ビューにアクセスする。](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
  
 次の表は、インターフェイス、<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>オブジェクト。  
  
|Interface|説明|  
|---------------|-----------------|  
|[IDropSource](/windows/desktop/api/oleidl/nn-oleidl-idropsource)|標準の OLE インターフェイス。|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget>|標準の OLE インターフェイス。|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite>|標準の OLE インターフェイス。|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|標準の OLE インターフェイス。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|複合アクション (元に戻す/やり直しの 1 つの単位にグループ化アクション) を作成できます。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|管理すると、ビューにアクセスするには、基本的なメソッドを提供します。 `IVsTextView` スレッド セーフです。|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|作成し、ウィンドウ ペインを管理します。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|テキスト レイヤーとやり取りします。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsThreadSafeTextView>|別のスレッドから、ビューに対する操作を実行します。|  
  
## <a name="see-also"></a>関連項目  
 [図の編集](http://msdn.microsoft.com/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)   
 [VSTextBuffer オブジェクト](../extensibility/vstextbuffer-object.md)   
 [レガシ API を使用するテキスト ビューへのアクセス](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)
