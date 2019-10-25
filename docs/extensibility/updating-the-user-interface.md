---
title: ユーザーインターフェイスを更新しています |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- user interfaces, updating
- commands, updating UI
ms.assetid: 376e2f56-e7bf-4e62-89f5-3dada84a404b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bf41a41e68aa73e07bdcafe8bcdcd335fff6e6eb
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72718792"
---
# <a name="updating-the-user-interface"></a>ユーザー インターフェイスの更新
コマンドを実装したら、新しいコマンドの状態を使用してユーザーインターフェイスを更新するコードを追加できます。

 一般的な Win32 アプリケーションでは、コマンドセットを継続的にポーリングできます。また、個々のコマンドの状態は、ユーザーが表示するときに調整できます。 ただし、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] シェルでホストできる Vspackage の数は無制限であるため、詳細なポーリングによって応答性が低下する可能性があります。特に、マネージコードと COM の間の相互運用機能アセンブリ間でポーリングを行う場合です。

### <a name="to-update-the-ui"></a>UI を更新するには

1. 次のいずれかの操作を実行します。

    - <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> メソッドを呼び出します。

         @No__t_0 インターフェイスは、次のように <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> サービスから取得できます。

        ```csharp
        void UpdateUI(Microsoft.VisualStudio.Shell.ServiceProvider sp)
        {
            IVsUIShell vsShell = (IVsUIShell)sp.GetService(typeof(IVsUIShell));
            if (vsShell != null)
            {
                int hr = vsShell.UpdateCommandUI(0);
                Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(hr);
            }
        }

        ```

         @No__t_0 のパラメーターが0以外 (`TRUE`) の場合、更新は同期的に直ちに実行されます。 適切なパフォーマンスを維持するために、このパラメーターにゼロ (`FALSE`) を渡すことをお勧めします。 キャッシュを回避する場合は、vsct ファイルでコマンドを作成するときに `DontCache` フラグを適用します。 それでも、フラグは慎重に使用するか、パフォーマンスが低下する可能性があります。 コマンドフラグの詳細については、[コマンドフラグ要素](../extensibility/command-flag-element.md)のドキュメントを参照してください。

    - ウィンドウで埋め込み先アクティベーションモデルを使用して ActiveX コントロールをホストする Vspackage では、<xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> メソッドを使用する方が便利な場合があります。 @No__t_1 インターフェイスの <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> メソッドと <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> インターフェイスの <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> メソッドは機能的に同等です。 どちらの場合も、環境はすべてのコマンドの状態を再クエリします。 通常、更新プログラムはすぐには実行されません。 代わりに、アイドル時間まで更新が遅延されます。 シェルは、良好なパフォーマンスを維持するために、コマンドの状態をキャッシュします。 キャッシュを回避する場合は、vsct ファイルでコマンドを作成するときに `DontCache` フラグを適用します。 ただし、パフォーマンスが低下する可能性があるため、フラグは慎重に使用してください。

         @No__t_2 オブジェクトで `QueryInterface` メソッドを呼び出すか、または <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> サービスからインターフェイスを取得することによって、<xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> インターフェイスを取得できることに注意してください。

## <a name="see-also"></a>関連項目
- [VSPackage でユーザー インターフェイス要素を追加する方法](../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [実装](../extensibility/internals/command-implementation.md)