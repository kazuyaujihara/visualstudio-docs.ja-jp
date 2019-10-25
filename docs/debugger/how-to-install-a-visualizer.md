---
title: '方法: ビジュアライザーをインストールする |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3c9c2fa8a8fb300c3b7eb702ae3efd216e17141a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72733107"
---
# <a name="how-to-install-a-visualizer"></a>方法 : ビジュアライザーをインストールする
作成したビジュアライザーは、インストールして初めて [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] で使用できるようになります。 ビジュアライザーのインストールは簡単です。

> [!NOTE]
> UWP アプリでは、標準のテキスト、HTML、XML、および JSON ビジュアライザーのみがサポートされています。 カスタム (ユーザーが作成した) ビジュアライザーはサポートされていません。

### <a name="to-install-a-visualizer"></a>ビジュアライザーをインストールするには

1. 作成したビジュアライザーを含むダイナミック リンク ライブラリ (DLL: Dynamic Link Library) を探します。

2. DLL を次のいずれかの場所にコピーします。

    - *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`

    - `My Documents\` *VisualStudioVersion* `\Visualizers`

3. マネージド ビジュアライザーをリモート デバッグで使用するには、DLL をリモート コンピューター上の同じパスにコピーします。

4. デバッグ セッションを再開します。

## <a name="see-also"></a>関連項目
- [カスタム ビジュアライザーを作成する](../debugger/create-custom-visualizers-of-data.md)
- [方法 : ビジュアライザーを記述する](/visualstudio/debugger/create-custom-visualizers-of-data)