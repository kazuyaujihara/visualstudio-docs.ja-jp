---
title: テキスト マネージャーを使用して、グローバル設定を監視する |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - monitor global settings
- editors [Visual Studio SDK], legacy - text manager
ms.assetid: 023e7671-cf65-419c-9bc1-3c4ee92aa436
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 792c566eda53cb8a4703e8ab03982952c518d8e4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58964273"
---
# <a name="using-the-text-manager-to-monitor-global-settings"></a>テキスト マネージャーを使用して、グローバル設定を監視するには
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

コア エディターを実装する場合、エディターのインスタンスがこれらの変更の影響を与えるため、グローバル設定に加えられた変更を監視する必要があります。 変更を追跡するには、テキスト マネージャーによって生成されるイベントをリッスンします。 たとえば、そのドキュメント データ オブジェクトなどのコア エディターでの表示やコンポーネントの動作のグローバル設定を指定するとテキスト マネージャーはこの情報を格納し、影響を受けるすべてのクライアントと通信すること。  
  
## <a name="text-manager-functions"></a>テキストのマネージャーの機能  
 テキスト マネージャーは、さまざまな設定は、次のようにイベントを発生させます。  
  
- バッファーはソース コード管理、かどうか  
  
- ファイル変更通知を登録する方法  
  
- ビューは、特定のバッファーに関連付けられたを追跡する方法  
  
- テキストの色づけの基本設定  
  
- タブとスペースの基本設定  
  
  特定の言語に固有の設定は、テキスト マネージャーによって管理されていません。 各言語サービスでは、これらの設定を管理する必要があります。  
  
  によって、テキスト マネージャーのイベント通知が提供される、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents>インターフェイス。 このインターフェイスを実装して、クライアントでイベントを処理するオブジェクトにはテキスト マネージャーが発生します。 使用してこれらのイベントの登録、<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>テキスト マネージャーのインターフェイス。  
  
## <a name="see-also"></a>関連項目  
 [コア エディター内で](../extensibility/inside-the-core-editor.md)   
 [エディターの機能](http://msdn.microsoft.com/bdac940d-1f14-4019-a01f-fd0bb3dc7198)
