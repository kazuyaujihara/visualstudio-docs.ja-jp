---
title: '方法: 元に戻すスタックをクリア |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eb1b1c1d79bab15baa8e8afcab719b3081e7265b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56712100"
---
# <a name="how-to-clear-the-undo-stack"></a>方法: 元に戻すスタックをクリアします。
次の手順では、元に戻すスタックをクリアする方法について説明します。

## <a name="to-clear-the-undo-stack"></a>元に戻すスタックをクリアするには

1.  元に戻すスタックの使用をオフにする、 [IOleUndoManager::DiscardFrom](/windows/desktop/api/ocidl/nf-ocidl-ioleundomanager-discardfrom)メソッド。 この例を次に示します。

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