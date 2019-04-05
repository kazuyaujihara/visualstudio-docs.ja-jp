---
title: プロジェクト モデルの要素 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], implementation considerations
- project models
- projects [Visual Studio SDK], elements
ms.assetid: a1dbe0dc-68da-45d7-8704-5b43ff7e4fc4
caps.latest.revision: 19
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d4e47712df1f76556ced8c69abb8bf5af085d01e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962886"
---
# <a name="elements-of-a-project-model"></a>プロジェクト モデルの要素
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

インターフェイスと実装のすべてのプロジェクトの[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]基本的な構造を共有: プロジェクトの種類のプロジェクト モデル。 VSPackage を開発するには、プロジェクト モデルを取得するでは、設計上の決定に従っているし、IDE によって提供されるグローバルの機能と連携するオブジェクトを作成します。 プロジェクト項目を保存する方法を制御する、たとえば、制御できない通知ファイルを維持する必要があります。 ユーザーが開いているプロジェクト項目にフォーカスが移るし、選択**保存**上、**ファイル**メニューで、[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]メニュー バーで、プロジェクトの種類コードする必要があります、IDE からコマンドをインターセプト、ファイルを保持してとファイルが不要になった変更されたことを IDE に戻るには、通知を送信します。  
  
 VSPackage は、IDE インターフェイスへのアクセスを提供するサービスを介して、IDE と対話します。 たとえば、特定のサービスにするモニターとルート コマンドやプロジェクトで行った選択のコンテキスト情報を提供します。 VSPackage のために必要なすべてのグローバル IDE 機能は、サービスによって提供されます。 サービスの詳細については、次を参照してください。[方法。サービスを取得](../../extensibility/how-to-get-a-service.md)します。  
  
 その他の実装の考慮事項:  
  
- 1 つのプロジェクト モデルは、1 つ以上のプロジェクトの種類を含めることができます。  
  
- プロジェクトの種類とアテンダント プロジェクト ファクトリに登録されていない個別に Guid。  
  
- 各プロジェクト テンプレート ファイルまたはユーザーが経由で、新しいプロジェクトを作成するときに、新しいプロジェクト ファイルを初期化するためにウィザードが適用される場合があります、 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] UI。 たとえば、[!INCLUDE[vcprvc](../../includes/vcprvc-md.md)]テンプレートは、最終的になるものの .vcproj ファイルを初期化します。  
  
  次の図は、プライマリ インターフェイス、サービス、および一般的なプロジェクトの実装を構成するオブジェクトを示します。 アプリケーションの支援、HierUtil7 を使用すると、基になるオブジェクトとその他のプログラミングの定型コードを作成します。 HierUtil7 アプリケーション ヘルパーの詳細については、次を参照してください。[ビルド内にありません。HierUtil7 プロジェクト クラスを使用して、プロジェクトの種類 (C++) を実装する](http://msdn.microsoft.com/a5c16a09-94a2-46ef-87b5-35b815e2f346)します。  
  
  ![Visual Studio プロジェクト モデル グラフィック](../../extensibility/internals/media/vsprojectmodel.gif "vsProjectModel")  
  Project モデル  
  
  インターフェイスと、前の図に表示されるサービスと、ダイアグラムに含まれていないその他の省略可能なインターフェイスの詳細については、次を参照してください。[プロジェクト モデルのコア コンポーネント](../../extensibility/internals/project-model-core-components.md)します。  
  
  プロジェクトのコマンドをサポートし、したがってを実装する必要があります、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>コマンド コンテキスト Guid によるコマンドのルーティングに参加するインターフェイス。  
  
## <a name="see-also"></a>関連項目  
 [チェックリスト:新しいプロジェクトの種類を作成します。](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [: ビルドに存在しませんHierUtil7 プロジェクト クラスを使用して、プロジェクトの種類 (C++) を実装するには](http://msdn.microsoft.com/a5c16a09-94a2-46ef-87b5-35b815e2f346)   
 [プロジェクト モデルのコア コンポーネント](../../extensibility/internals/project-model-core-components.md)   
 [プロジェクト ファクトリを使用してプロジェクト インスタンスを作成します。](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)   
 [方法: サービスを取得します。](../../extensibility/how-to-get-a-service.md)   
 [プロジェクト タイプの作成](../../extensibility/internals/creating-project-types.md)
