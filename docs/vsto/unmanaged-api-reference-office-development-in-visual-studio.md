---
title: アンマネージ API リファレンス (Visual Studio での Office 開発)
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, reference
- Office development in Visual Studio, unmanaged API reference
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 00db78359154dbda600fb4b58103bc04e89d16b2
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551329"
---
# <a name="unmanaged-api-reference-office-development-in-visual-studio"></a>アンマネージ API リファレンス (Visual Studio での Office 開発)

2007 Microsoft Office システム以降では、Office アプリケーションは[IManagedAddin インターフェイス](../vsto/imanagedaddin-interface.md)インターフェイスを使用して、 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]に含まれる VSTO アドインローダーコンポーネントを呼び出します。 このコンポーネントは、読み込みマネージ VSTO アドインを支援するために使用されます。このインターフェイスを実装することで、独自の VSTO アドイン ローダー コンポーネントを作成できます。

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="in-this-section"></a>このセクションの内容

[IManagedAddin インターフェイス](../vsto/imanagedaddin-interface.md)

Office アプリケーションでマネージド VSTO アドインの読み込みやアンロードを行うために実装できる COM インターフェイスです。
