---
title: コア エディター内で |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - core editor
ms.assetid: 8265f31c-c45b-4858-882c-6d9f1e3b9083
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a188116b09b846e81023c239d64d6386c7f2c6ae
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62861972"
---
# <a name="inside-the-core-editor"></a>コア エディター
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]のコア エディターは変更し、テキスト情報のクエリを実行できるいくつかのコンポーネントのセットです。 従来の API を使用して、コア エディターをカスタマイズしている場合は、エディター アダプター経由でルーティングされますが、これらのカスタマイズを使用する続行することがあります。 お勧め、ただし、API の新しいエディターに、カスタマイズを調整することです。

 コア エディターのいくつかの重要な側面を次の領域には。

- テキスト バッファー

- テキスト ビュー

- コード ウィンドウ

- テキスト マーカー

- テキスト マネージャー

- 言語サービスとの統合

## <a name="in-this-section"></a>このセクションの内容
- [従来の API を使用して、コア エディターをインスタンス化](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)手順を使用する方法について説明します<xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>エディター、コアのインスタンスを作成します。

- [従来の API を使用してテキスト バッファーへのアクセス](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)コア エディターでテキスト バッファーの役割について説明します、説明、バッファーにアクセスするために使用し、テキスト バッファー オブジェクトによって実装されるインターフェイスの一覧を提供する、関連付けられているシステム<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.

- [従来の API でのテキスト バッファー イベント](../extensibility/text-buffer-events-in-the-legacy-api.md)テキスト バッファー イベントの通知に使用されるインターフェイスの一覧を示します。

- [方法: 従来の API を使用したイベントのテキスト バッファーにご登録ください](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)テキスト バッファーのイベントを通知する方法について説明します。

- [グローバル設定を監視するテキスト マネージャーを使用して](../extensibility/using-the-text-manager-to-monitor-global-settings.md)コア エディター コンポーネントとグローバル設定情報を共有するテキスト マネージャーを使用する方法とテキスト マネージャー イベントの通知を受信する方法について説明します。

- [従来の API を使用してテキスト ビューにアクセス](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)コア エディターで、テキスト ビューの役割について説明し、によって実装されるインターフェイスを一覧表示、<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>オブジェクト。

- [従来の API を使用してコード ウィンドウをカスタマイズする](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)方法コード ウィンドウ テキスト ビューを囲むに使用、コード ウィンドウ マネージャーを使用するコード ウィンドウで、文字装飾を提供する方法について説明し、新しいビューの通知について説明します.

- [従来の API を使用して、表示設定を変更](../extensibility/changing-view-settings-by-using-the-legacy-api.md)強制設定を削除する方法と設定の表示を強制する方法についての詳細な手順について説明します。

- [言語サービスとコア エディター](../extensibility/language-services-and-the-core-editor.md)制御コード文字装飾を言語サービスのインスタンス化について説明します。

## <a name="related-sections"></a>関連項目
- [チュートリアル: エディターを作成するには、コアとエディター ファイルの種類を登録する](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)マネージ コードからのコア エディターを起動する方法についての詳細な手順について説明します。

- [ドロップダウン バー](../extensibility/drop-down-bar.md)コード ウィンドウで、ドロップダウン バーを使用する方法について説明し、ドロップダウン バーを実装するときに使用するインターフェイスについて説明します。

- [テキスト マーカーを使用して、従来の API を使用した](../extensibility/using-text-markers-with-the-legacy-api.md)テキスト マーカーとそのコア エディターでの使用方法の概念について説明し、アクセスし、テキスト マーカーの管理に使用されるインターフェイスを一覧表示します。

- [方法: 標準のテキスト マーカーを追加](../extensibility/how-to-add-standard-text-markers.md)テキスト マーカーを作成する方法と、ショートカット メニューにカスタム コマンドを追加する方法に関する手順について説明します。

- [方法: カスタム テキスト マーカーを作成](../extensibility/how-to-create-custom-text-markers.md)サービスとしてのマーカーの種類を指定する方法とカスタム テキスト マーカーを作成する方法の詳細手順について説明します。