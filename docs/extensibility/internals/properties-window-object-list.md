---
title: プロパティウィンドウオブジェクトリスト |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Properties window, object list
ms.assetid: 6c159c9d-345d-4b23-8ddd-9839d338b62f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e50b3fe46edb8d14cad9a03a45bc8650cb9713ab
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72725183"
---
# <a name="properties-window-object-list"></a>プロパティ ウィンドウのオブジェクト一覧
**プロパティ** ウィンドウの オブジェクト ボックスの一覧では、選択範囲を、選択した1つまたは複数のウィンドウ内で使用可能な他のオブジェクトに変更できます。 この一覧で別のオブジェクトを選択すると、<xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A> の呼び出しがトリガーされ、新しいオブジェクトが選択されたことが環境に通知されます。 次に、 **[プロパティ]** ウィンドウに表示される情報が変更され、新しく選択されたオブジェクトに関連付けられたプロパティが表示されます。

## <a name="the-object-list"></a>オブジェクトの一覧
 オブジェクトの一覧は、オブジェクト名 (太字で表示) とオブジェクトの種類の2つのフィールドで構成されています。

 オブジェクトの型の左側に太字で表示されているオブジェクト名は、<xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> インターフェイスによって提供された `Name` プロパティを使用してオブジェクト自体から取得されます。 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo.GetClassInfo%2A>、<xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> の唯一のメソッドは、そのインターフェイスのコクラスの <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo> を返します。 **[プロパティ]** ウィンドウでは、<xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> を使用してコクラスの名前を取得します。これは、ドロップダウンリストにオブジェクト名として表示されます。

 オブジェクトに `Name` プロパティがない場合、オブジェクトリストの名前領域には名前が表示されません。 オブジェクトの一覧に名前が表示されるようにするには、オブジェクトに Name プロパティを追加します。

 COM オブジェクトが <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> を実装していない場合は、一覧の左側にあるオブジェクト名の代わりにインターフェイス名が **[プロパティ]** ウィンドウに表示されます。

## <a name="see-also"></a>関連項目
- [プロパティの拡張](../../extensibility/internals/extending-properties.md)