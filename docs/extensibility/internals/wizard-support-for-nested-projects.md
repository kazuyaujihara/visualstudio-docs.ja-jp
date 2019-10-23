---
title: 入れ子になったプロジェクトに対するウィザードのサポート |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Add Item wizard
- nested projects, wizard support
- New Project wizard
ms.assetid: 1b496acc-b326-4cdb-bb48-e3b5c6f12e05
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5e498f21499f4b07bf77bb79829fc6d92227f1f2
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721435"
---
# <a name="wizard-support-for-nested-projects"></a>入れ子になったプロジェクト向けのウィザード サポート
IDE では、入れ子になったプロジェクトの親プロジェクトが実装できる2つのウィザードが実行されます。これは、**新しいプロジェクト**ウィザードと**項目の追加**ウィザードです。

 ユーザーが **[プロジェクトの追加]** を選択し、ファイル メニューの **[新しい]** プロジェクト をクリックするか、 **[追加]** を選択しソリューションエクスプローラーで **[新しいプロジェクト]** を右クリックして、**新しいプロジェクト**ウィザードを起動した場合は、IDE によって addproject が実行されます。コマンドおよび親プロジェクトの**addproject**コマンドの実装では、テンプレートプロジェクトファイル、または一連のコンテキストパラメーターを持つウィザード (.vsz) ファイルが返されます。

 同様に、親プロジェクトの**AddItem**ウィザードの実装では、異なるコンテキストパラメーターのセットを持つ .vsz ファイルが返されます。

 ウィザードの詳細については、「ウィザード (」を参照してください[.Vsz) ファイル](../../extensibility/internals/wizard-dot-vsz-file.md)、[コンテキストパラメーター](../../extensibility/internals/context-parameters.md) 、および[プロジェクトと項目テンプレートの登録](../../extensibility/internals/registering-project-and-item-templates.md)を行います。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>
- [入れ子になったプロジェクト](../../extensibility/internals/nesting-projects.md)