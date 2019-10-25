---
title: Visual Studio Shell |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- shell, Visual Studio
- Visual Studio, shell
ms.assetid: cb124ef4-1a6b-4bfe-bfbf-295ef9c07f36
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 60aa48da701857508f9b6fd7fc3d9d0c0603046e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722055"
---
# <a name="visual-studio-shell"></a>Visual Studio Shell
@No__t_0 シェルは [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] での統合の主要なエージェントです。 シェルには、Vspackage が共通のサービスを共有できるようにするために必要な機能が用意されています。 @No__t_0 のアーキテクチャ目標は Vspackage の主な機能を備えているため、シェルは基本機能を提供し、そのコンポーネント Vspackage 間の相互通信をサポートするフレームワークです。

## <a name="shell-responsibilities"></a>シェルの役割
 シェルには、次の主要な役割があります。

- (COM インターフェイスを通じて) ユーザーインターフェイス (UI) の基本要素をサポートします。 これには、既定のメニューとツールバー、ドキュメントウィンドウフレームまたはマルチドキュメントインターフェイス (MDI) 子ウィンドウ、ツールウィンドウフレーム、およびドッキングサポートが含まれます。

- ドキュメントの永続性を調整し、1つのドキュメントを複数の方法で、または互換性のない方法で開くことを保証するために、現在開いているすべてのドキュメントの実行中のリストを実行中のドキュメントテーブル (RDT) で保持する。

- コマンドルーティングとコマンド処理インターフェイスのサポート、`IOleCommandTarget`。

- 適切なタイミングで Vspackage を読み込んでいます。 シェルのパフォーマンスを向上させるには、VSPackage の遅延読み込みが必要です。

- 基本的なシェル機能を提供する、<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell> などの特定の共有サービスの管理、および基本的なウィンドウ機能を提供する <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>。

- ソリューション (.sln) ファイルの管理。 ソリューションには、Visual C++ 6.0 のワークスペース (dsw) ファイルに似た、関連するプロジェクトのグループが含まれています。

- シェル全体の選択、コンテキスト、および通貨を追跡します。 シェルは、次の種類の項目を追跡します。

  - 現在のプロジェクト

  - 現在のプロジェクト項目、または現在の <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> を ItemID する

  - **[プロパティ]** ウィンドウまたは `SelectionContainer` の現在の選択

  - コマンド、メニュー、およびツールバーの表示を制御する UI コンテキスト Id または CmdUIGuids

  - アクティブウィンドウ、ドキュメント、および元に戻すマネージャーなど、現在アクティブな要素

  - ダイナミックヘルプを駆動するユーザーコンテキスト属性

  シェルは、インストールされている Vspackage と現在のサービス間の通信も仲介します。 シェルのコア機能がサポートされ、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] に統合されたすべての Vspackage で使用できるようになります。 これらのコア機能には、次の項目が含まれます。

- **[バージョン情報]** ダイアログボックスとスプラッシュスクリーン

- **[新しい項目の追加] ダイアログボックスと [既存項目の追加**] ダイアログボックス

- **クラスビュー**ウィンドウと**オブジェクトブラウザー**

- **[参照]** ダイアログボックス

- **ドキュメントアウトライン**ウィンドウ

- **ダイナミックヘルプ**ウィンドウ

- **検索**と**置換**

- **[新規]** メニューの **[プロジェクトを開く]** および **[ファイルを開く]** ダイアログボックス

- **[ツール]** メニューの **[オプション]** ダイアログボックス

- **[プロパティ]** ウィンドウ

- **ソリューション エクスプローラー**

- **タスク一覧**ウィンドウ

- **ツールボックス**

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>
- <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>
- <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>
- [VSPackage](../../extensibility/internals/vspackages.md)