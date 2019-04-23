---
title: '方法: 名前でフォルダーをプログラムで取得します。'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook folders [Office development in Visual Studio], retrieving by name
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a494f954f3f670fb796b33a0dbd01e2512ad1d26
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60088627"
---
# <a name="how-to-programmatically-retrieve-a-folder-by-name"></a>方法: 名前でフォルダーをプログラムで取得します。
  この例では、名前付きカスタム フォルダーへの参照を取得し、フォルダーの内容を表示します。

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>例
 [!code-csharp[Trin_OL_GetFolderName#1](../vsto/codesnippet/CSharp/Trin_OL_GetFolderName/thisaddin.cs#1)]

## <a name="compile-the-code"></a>コードのコンパイル
 この例で必要な要素は次のとおりです。

- TestFolder という名前のフォルダー。

## <a name="see-also"></a>関連項目
- [フォルダーを操作します。](../vsto/working-with-folders.md)
- [方法: プログラムによって特定のフォルダー内を検索します。](../vsto/how-to-programmatically-search-within-a-specific-folder.md)
- [方法: プログラムによって特定の連絡先を検索します。](../vsto/how-to-programmatically-search-for-a-specific-contact.md)
- [方法: プログラムによってカスタム フォルダーのアイテムを作成します。](../vsto/how-to-programmatically-create-custom-folder-items.md)
