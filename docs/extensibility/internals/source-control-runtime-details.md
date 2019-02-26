---
title: ソース管理ランタイムの詳細 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], runtime details
ms.assetid: 1acd30e0-f98c-4bde-b9cd-4076845887df
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3f7501a25596fc0a818277d164337bb0d4e4e077
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56618797"
---
# <a name="source-control-runtime-details"></a>ソース管理ランタイムの詳細
プロジェクトは、ユーザーは、ウィザードなどのオートメーション コント ローラーまたはソース管理にプロジェクトのファイルを追加するとき、ソース管理に追加されます。 ソース管理されているある自体のプロジェクトが指定はしません。ソース管理をサポートしていますが、これを手動で追加する必要があります。

## <a name="registering-with-a-source-control-package"></a>ソース管理のパッケージへの登録
 ソース管理に、プロジェクト内のファイルが追加されると、環境を呼び出す<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>cookie としてソース管理システムで使用される 4 つの不透明な文字列を提供します。 プロジェクト ファイル内には、これらの文字列を格納します。 これらの文字列渡す必要があります (ソース管理パッケージを管理する Visual Studio コンポーネント) のソース コントロール スタブをプロジェクトの種類の起動時に呼び出すことによって<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>します。 これでさらに適切なソース管理パッケージを読み込みますありの実装への呼び出しを転送`IVsSccManager2::RegisterSccProject`します。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>
- [ソース管理のサポート](../../extensibility/internals/supporting-source-control.md)