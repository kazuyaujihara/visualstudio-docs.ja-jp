---
title: プロパティ ウィンドウのボタン |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Properties window, buttons
ms.assetid: bdd2e3a7-ae6e-4e88-be1a-e0e3b7ddbbcc
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8ecd7dd4efab203ca398822dee9bd7fbc9724f35
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63424649"
---
# <a name="properties-window-buttons"></a>プロパティ ウィンドウのボタン
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

開発言語と製品の種類に応じて、**プロパティ** ウィンドウのツールバーに特定のボタンがデフォルトで表示されます。 すべての場合において、 **Categorized**、 **Alphabetized**、**プロパティ**、および **プロパティ ページ** ボタンが表示されます。 Visual C＃ および Visual Basic では、**イベント** ボタンも表示されます。 特定のVisual C ++プロジェクトでは、 **VC + + メッセージ** と **VC オーバーライド** ボタンが表示されます。 その他のプロジェクトの種類に対して追加のボタンが表示される場合があります。 **プロパティ** ウィンドウのボタンの詳細については、[プロパティ ウィンドウ](../../ide/reference/properties-window.md) を参照してください。  
  
## <a name="implementation-of-properties-window-buttons"></a>プロパティ ウィンドウのボタンの実装  
 クリックすると、 **Categorized**ボタン、Visual Studio の呼び出し、<xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties>をカテゴリにそのプロパティを並べ替えるにはフォーカスのあるオブジェクトのインターフェイス。 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties> 実装されている、`IDispatch`に提示されるオブジェクト、**プロパティ**ウィンドウ。  
  
 これには、負の値を持つ 11 の定義済みプロパティ カテゴリがあります。 カスタムのカテゴリを定義できますを割り当てることに、定義済みのカテゴリと区別するための正の値をお勧めします。  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.MapPropertyToCategory%2A>メソッドは、指定したプロパティの適切なプロパティのカテゴリ値を返します。 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.GetCategoryName%2A>メソッド カテゴリ名を含む文字列を返します。 のみ、Visual Studio は、標準的なプロパティのカテゴリの値を知っているために、カスタム カテゴリ値のサポートを提供する必要があります。  
  
 クリックすると、 **Alphabetized**ボタン名でアルファベット順にプロパティが表示されます。 名前によって取得`IDispatch`ローカライズされた並べ替えアルゴリズムに従ってします。  
  
 ときに、**プロパティ**ウィンドウが開いて、**プロパティ**自動的に表示されているボタンとして選択されています。 環境の他の部分で同じボタンが表示され、表示をクリックすることができます、**プロパティ**ウィンドウ。  
  
 **プロパティ ページ**ボタンが使用できない場合`ISpecifyPropertyPages`選択したオブジェクトが実装されていません。 プロパティ ページのソリューションやプロジェクトに通常関連付けられている表示構成に依存するプロパティがすることもできます (たとえば、Visual C) でプロジェクト項目に関連付けられます。  
  
> [!NOTE]
> ツール バー ボタンを追加することはできません、**プロパティ**アンマネージ コードを使用してウィンドウ。 ツール バー ボタンを追加するから派生したマネージ オブジェクトを作成する必要があります<xref:System.Windows.Forms.Design.PropertyTab>します。  
  
## <a name="see-also"></a>関連項目  
 [プロパティの拡張](../../extensibility/internals/extending-properties.md)
