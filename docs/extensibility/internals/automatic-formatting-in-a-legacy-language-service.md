---
title: 従来の言語サービスの自動書式設定 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 64fbf5b64b57425b1bdee3ae3475c234384db062
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62910606"
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>自動の従来の言語サービスで書式設定
オート フォーマット、言語サービスでは、ユーザーが既知のコード コンストラクトの入力を開始するとのコード スニペットが自動的に挿入します。

## <a name="automatic-formatting-behavior"></a>自動書式設定の動作
 たとえば、「*場合*、言語サービス自動的に一致する中かっこを挿入またはに応じて、適切なインデント レベルをに、言語サービスが新しい行カーソルを強制的場合は、ENTER キーを押すと、かどうか、前の行は、新しいスコープが表示されます。

 言語サービスの残りの部分に使用されるコマンドのフィルターは、自動書式設定するためも使用できます。 呼び出すことによって、対応する中かっこを強調することも<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>します。

## <a name="see-also"></a>関連項目
- [従来の言語サービスを開発します。](../../extensibility/internals/developing-a-legacy-language-service.md)