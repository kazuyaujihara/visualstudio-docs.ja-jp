---
title: Windows のドキュメント |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio SDK, document windows
ms.assetid: 50081d48-987f-43db-8bf9-51b7cf76e9c0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8d53cb3298ec3a8190f79ad87bd89e646ccbafbe
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56633214"
---
# <a name="document-windows"></a>ドキュメント ウィンドウ
Visual Studio で、*ドキュメント ウィンドウ*はマルチ ドキュメント インターフェイス (MDI) ウィンドウに関連付けられている子フレーム ウィンドウです。 ドキュメント ウィンドウは、通常、表示やソース コードまたはテキストの変更を使用しますが、その他の機能の種類をホストすることもできます。 ドキュメント ウィンドウ:

- 同時に複数のファイルを表示できるように、MDI 親内の別の水平または垂直タブ グループに整理できます。

- 任意の順序で MDI 親にドッキングできます。

- 自由にフロートすることができます。

- その他の MDI ウィンドウのタブ オーダー内でリンクされています。

  グループ化のためのコマンドをドッキングとフローティング見つかりますドキュメント ウィンドウ タブのショートカット メニュー上。

  Visual Studio でウィンドウの動作の詳細については、[ウィンドウ レイアウトをカスタマイズ](../../ide/customizing-window-layouts-in-visual-studio.md)を参照してください。

## <a name="document-window-implementation"></a>ドキュメント ウィンドウの実装
 ドキュメント ウィンドウは、エディターの実装によって作成されます。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>インターフェイス エディターをインスタンス化の一部としてドキュメント ウィンドウを作成します。 詳細については、[レガシー インターフェイス エディター](../../extensibility/legacy-interfaces-in-the-editor.md)を参照してください。

> [!NOTE]
>  後方の提供をウィンドウ内のナビゲーションのポイントに転送は、実装、<xref:Microsoft.VisualStudio.Shell.Interop.IVsBackForwardNavigation>インターフェイス。 テキスト エディターでは、ドキュメント内のナビゲーションのポイントを識別するためにテキスト マーカーが使用されます。

## <a name="the-running-document-table"></a>実行中の document テーブル
 IDE では、実行されているドキュメント テーブル (RDT) を使用して、すべてのドキュメント ウィンドウの状態を追跡します。 RDT は、どのドキュメントを windows にソリューションを閉じたときなど、または、ファイルが編集されているときに、イベントの通知メカニズムです。 詳細については、[document テーブルを実行している](../../extensibility/internals/running-document-table.md)を参照してください。

## <a name="see-also"></a>関連項目
- [ドキュメントの読み込みの遅延](../../extensibility/internals/delayed-document-loading.md)