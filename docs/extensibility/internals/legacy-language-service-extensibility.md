---
title: 従来の言語サービス拡張機能 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services
- Visual Studio, language services
ms.assetid: 2700cd4d-5f68-43fc-b62f-dc80c3f3aa85
caps.latest.revision: 43
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 339e23411f10e8cde32900feea4618c0806faacf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62860060"
---
# <a name="legacy-language-service-extensibility"></a>従来の言語サービスの機能拡張
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

言語サービスは、IDE でソース コードを編集するため、言語固有のサポートを提供します。  
  
 従来の言語サービスは、VSPackage の一部として実装されますが、言語サービスの機能を実装する新しい方法は MEF 拡張機能を使用します。 言語サービスを実装する新しい方法の詳細についてを参照してください。[エディターと言語サービス拡張](../../extensibility/editor-and-language-service-extensions.md)します。  
  
 このセクションでは、構造と従来の言語サービスの実装について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [従来の言語サービスの移行](../../extensibility/internals/migrating-a-legacy-language-service.md)  
 言語サービスを Visual Studio 2008 から最新バージョンに更新する方法について説明します。  
  
 [従来の言語サービスの基本情報](../../extensibility/internals/legacy-language-service-essentials.md)  
 Visual Studio のプログラミング言語に統合する言語サービスを開発する方法に関する重要な情報を提供します。  
  
 [従来の言語サービスの開発](../../extensibility/internals/developing-a-legacy-language-service.md)  
 言語サービスを作成するのに役立つトピックへのリンクを提供します。  
  
 [従来の言語サービスでの構文の色分け表示](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 言語サービスで構文の強調表示のサポートについてを説明します。  
  
 [従来の言語サービスの実装](../../extensibility/internals/implementing-a-legacy-language-service1.md)  
 Managed package framework (MPF) を使用して、マネージ コードでのフル機能の言語サービスを実装する方法について説明します。  
  
 [シンボル参照ツールのサポート](../../extensibility/internals/supporting-symbol-browsing-tools.md)  
 ライブラリと、IDE でシンボルのツリー ビューを参照するためのツールについて説明します。  
  
## <a name="related-sections"></a>関連項目  
 [エディターと言語サービスの拡張機能](../../extensibility/editor-and-language-service-extensions.md)  
 Visual Studio エディターの概要を示します。  
  
 [デバッグのための言語サービスのサポート](../../extensibility/internals/language-service-support-for-debugging.md)  
 Visual Studio Debugging SDK を作成し、プログラムをデバッグするために使用するデバッガー コンポーネントのカスタマイズに必要な情報を含むに関する情報とリンクを提供します。
