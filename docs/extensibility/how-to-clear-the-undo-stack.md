---
title: '方法: 元に戻すスタックをクリア |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 442c362a3d9c65cd75a4f3f5446228630f9cb5b1
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66344616"
---
# <a name="how-to-clear-the-undo-stack"></a>方法: 元に戻すスタックをクリアします。
次の手順では、元に戻すスタックをクリアする方法について説明します。

## <a name="to-clear-the-undo-stack"></a>元に戻すスタックをクリアするには

1. 元に戻すスタックの使用をオフにする、 [IOleUndoManager::DiscardFrom](/windows/desktop/api/ocidl/nf-ocidl-ioleundomanager-discardfrom)メソッド。 この例を次に示します。

    ```
    HRESULT CCmdWindow::ClearUndoStack()
    {
      HRESULT hr = S_OK;

      if (m_pUndoMgr == NULL)
        {
        IfFailGo(m_pTextLines->GetUndoManager(&m_pUndoMgr));
        ASSERT(m_pUndoMgr != NULL, "",;);
        }

      IfFailGo(m_pUndoMgr->DiscardFrom(NULL));

    Error:
      return hr;
    }
    ```

## <a name="see-also"></a>関連項目
- [方法: 元に戻す管理を実装](../extensibility/how-to-implement-undo-management.md)