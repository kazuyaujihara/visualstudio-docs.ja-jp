---
title: エディターでの従来のインターフェイス |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy
ms.assetid: 741d45f5-0ea3-4614-972a-8728fe054e07
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8483068ae03c9a57fc67b528393e5d6830c3ec33
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973892"
---
# <a name="legacy-interfaces-in-the-editor"></a>エディターでのレガシー インターフェイス
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio エディターは、従来のインターフェイスからアクセスできます。 Visual Studio SDK と呼ばれるアダプタが含まれています。 *shim*、これらの新しいエディターと対話するインターフェイスを有効にします。 ただし、新しいエディターの API を使用して従来のコードを更新することをお勧めします。 コードのパフォーマンスが向上し、Windows Presentation Foundation (WPF) と Managed Extensibility Framework (MEF) などの新しいテクノロジを使用することができます。  
  
## <a name="related-topics"></a>関連トピック  
  
|タイトル|説明|  
|-----------|-----------------|  
|[レガシ コードをエディターに適合させる](../extensibility/adapting-legacy-code-to-the-editor.md)|新しいエディターにコードを改変する方法について説明します。|  
|[エディター アダプターの新規または変更された動作](../extensibility/new-or-changed-behavior-with-editor-adapters.md)|エディターの以前のバージョンの動作のエディターのアダプターの違いについて説明します。|  
|[コア エディターの内部](../extensibility/inside-the-core-editor.md)|エディターの以前のバージョンのさまざまなコンポーネントをについて説明します。|  
|[レガシ API を使用するコア エディターのインスタンス化](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)|従来の API を使用して、コア エディターのインスタンスを作成する方法について説明します。|  
|[エディター ファクトリ](../extensibility/editor-factories.md)|従来の API でエディター ファクトリを使用する方法について説明します。|  
|[方法: エディターのファイルの種類を登録します。](../extensibility/how-to-register-editor-file-types.md)|エディターにファイル名拡張子をリンクする方法について説明します。|  
|[チュートリアル: コア エディターを作成してエディター ファイルの種類を登録します。](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)|コア エディターを作成して、ファイル名拡張子をリンクする方法について説明します。|  
|[方法: エディターのコンテキストを提供します。](../extensibility/how-to-provide-context-for-editors.md)|エディターのコンテキストを提供する方法について説明します。|  
|[言語サービスとコア エディター](../extensibility/language-services-and-the-core-editor.md)|言語サービスとエディター間の相互作用をについて説明します。|  
|[レガシ API を使用するテキスト バッファーへのアクセス](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)|従来の API を使用して、テキスト バッファーにアクセスする方法について説明します。|  
|[レガシ API を使用するテキスト ビューへのアクセス](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)|従来の API を使用して、テキスト ビューにアクセスする方法について説明します。|  
|[レガシ API を使用するコード ウィンドウのカスタマイズ](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)|従来の API を使用してコード ウィンドウをカスタマイズする方法について説明します。|  
|[レガシ API を使用するテキスト レイヤーへのアクセス](../extensibility/accessing-text-layers-by-using-the-legacy-api.md)|従来の API を使用してテキストの異なる層にアクセスする方法について説明します。|  
|[レガシ API でのテキスト マーカーの使用](../extensibility/using-text-markers-with-the-legacy-api.md)|従来の API を使用してテキスト マーカーを追加する方法について説明します。|  
|[レガシ API を使用するエディター コントロールおよびメニューのカスタマイズ](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)|従来の API を使用して、エディター コントロールをカスタマイズする方法について説明します。|  
|[レガシ API を使用した元に戻すとやり直しの管理](../extensibility/managing-undo-and-redo-by-using-the-legacy-api.md)|元に戻すを管理し、従来の API を使用して再実行する方法について説明します。|  
|[方法: 検索の実装とメカニズムを置換](../extensibility/how-to-implement-the-find-and-replace-mechanism.md)|検索の管理し、従来の API を使用して置き換える方法について説明します。|  
|[方法: ファイル変更通知を抑制します。](../extensibility/how-to-suppress-file-change-notifications.md)|従来の API を使用して、ファイル変更通知を抑制する方法について説明します。|  
|[カスタム エディターとデザイナーの作成](../extensibility/creating-custom-editors-and-designers.md)|カスタム エディターとデザイナーを作成する方法について説明します。|  
|[従来の言語サービスの開発](../extensibility/internals/developing-a-legacy-language-service.md)|カスタマイズ機能を提供する機能に関するドキュメントへのリンクを提供します、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]コア エディターの言語サービスのサポートを追加します。|  
|[フォントと色の使用](../extensibility/using-fonts-and-colors.md)|従来のインターフェイスで、フォントおよび色を使用する方法について説明します。|
