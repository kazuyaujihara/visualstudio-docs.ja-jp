---
title: コンテキスト メニュー |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - context menus
ms.assetid: 44fd9e6a-6d42-4aba-80ba-f37fa0070f1d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 19838bbc1dfeeb0a0df9e1e1ce409557b6a28f1e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56722370"
---
# <a name="context-menus"></a>コンテキスト メニュー
コンテキスト メニューでは、クライアント領域のアクティブなリージョンでユーザーを右クリックしたときに表示され、マウスの右ボタンが離されたときをオフにします。

## <a name="editor-context-menus"></a>エディター コンテキスト メニュー
 インターセプトすることで`ECMD_SHOWCONTEXTMENU`、言語サービスは、エディターに表示されるコンテキスト メニューを制御できます。 独自のコンテキスト メニューを表示するには、次のコマンド処理に渡されると、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>呼び出して<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A>します。 このコマンドを処理しない場合は、エディターの提供される標準のコンテキスト メニューが表示されます。 マーカーあたりごとに、コンテキスト メニューの内容を制御することもできます。 詳細については、[テキスト マーカーを使用して、従来の API を使用した](../extensibility/using-text-markers-with-the-legacy-api.md)と[従来の言語サービスのコマンドをインターセプト](../extensibility/internals/intercepting-legacy-language-service-commands.md)を参照してください。

## <a name="see-also"></a>関連項目
- [従来の言語サービスを開発します。](../extensibility/internals/developing-a-legacy-language-service.md)
- [メニューとコマンドを拡張します。](../extensibility/extending-menus-and-commands.md)