---
title: エディターと言語サービス拡張機能 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK]
ms.assetid: 5653bac9-724f-4948-a820-68ce6aa96365
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7fa3e4be6ee44011eb1286e3ebf22ee69f8e3397
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65683114"
---
# <a name="editor-and-language-service-extensions"></a>エディターと言語サービスの拡張機能
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio コード エディターのほとんどの機能を拡張することができます。 エディターでは、Windows Presentation Foundation (WPF) に基づいており、マネージ コードで記述されました。 この設計は、以前のバージョンの Visual Studio でデザインから異なる場合は、ほとんどの同じ機能を提供します。 エディターを拡張するには、Managed Extensibility Framework (MEF) を使用します。  
  
 Visual Studio SDK は、アダプターと呼ばれる*shim*以前のバージョン用に作成された Vspackage をサポートするためにします。 ただし、既存の VSPackage があればより優れたパフォーマンスと信頼性を取得する新しいテクノロジに更新することお勧めします。  
  
## <a name="related-topics"></a>関連トピック  
  
|タイトル|説明|  
|-----------|-----------------|  
|[エディターの項目テンプレートを使用した拡張機能の作成](../extensibility/creating-an-extension-with-an-editor-item-template.md)|エディター項目テンプレートの使用方法を紹介します。|  
|[エディターと言語サービスの拡張](../extensibility/extending-the-editor-and-language-services.md)|設計とコア エディターの機能を紹介し、それを拡張する方法について説明するドキュメントにリンクします。|  
|[エディターのレガシ インターフェイス](../extensibility/legacy-interfaces-in-the-editor.md)|既存のコードからコア エディターにアクセスする方法を説明するドキュメントにリンクします。|  
|[カスタム エディターとデザイナーの作成](../extensibility/creating-custom-editors-and-designers.md)|カスタム エディターを作成する方法を説明するドキュメントへのリンク。|  
|[従来の言語サービスの機能拡張](../extensibility/internals/legacy-language-service-extensibility.md)|プログラミング言語を Visual Studio に統合する方法を説明するドキュメントにリンクします。|  
|[MEF (Managed Extensibility Framework)](https://msdn.microsoft.com/library/6c61b4ec-c6df-4651-80f1-4854f8b14dde)|Managed Extensibility Framework (MEF) が導入されています。|  
|[Windows Presentation Foundation](https://msdn.microsoft.com/library/f667bd15-2134-41e9-b4af-5ced6fafab5d)|Windows Presentation Foundation (WPF) をについて説明します。|
