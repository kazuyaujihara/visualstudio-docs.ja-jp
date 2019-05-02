---
title: '方法: プログラムによってブックとしてテキスト ファイルを開く'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 61e51f6274bc22ed0d34d33f5ff85bfbfbd927bd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62812459"
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>方法: プログラムによってブックとしてテキスト ファイルを開く
  テキスト ファイルをブックとして開くことができます。 開きたいテキスト ファイルの名前を渡す必要があります。 ファイル内のデータの列の形式、解析を開始する行番号など、いくつかの省略可能なパラメーターを指定できます。

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="example"></a>例
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]

## <a name="compile-the-code"></a>コードのコンパイル
 この例では、次のコンポーネントが必要です。

- という名前のコンマ区切りのテキスト ファイル`Test.txt`少なくとも 3 つの行のテキストを格納しています。

- テキスト ファイル`Test.txt`C ドライブに保存します。

## <a name="see-also"></a>関連項目
- [ブックを操作します。](../vsto/working-with-workbooks.md)
- [方法: プログラムによってブックを開く](../vsto/how-to-programmatically-open-workbooks.md)
- [方法: プログラムによって新しいブックを作成します。](../vsto/how-to-programmatically-create-new-workbooks.md)
- [方法: プログラムによってブックを保存します。](../vsto/how-to-programmatically-save-workbooks.md)
- [方法: プログラムによってブックを閉じる](../vsto/how-to-programmatically-close-workbooks.md)
- [Office ソリューションの省略可能なパラメーター](../vsto/optional-parameters-in-office-solutions.md)
