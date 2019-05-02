---
title: .NET コンパイラ プラットフォーム (&quot;Roslyn&quot;) 拡張機能 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 564201b3-1e18-4b88-b615-42c2f57f3fe8
caps.latest.revision: 5
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: fba277731444a294f276f43cc67b098039f4a64f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963369"
---
# <a name="net-compiler-platform-quotroslynquot-extensibility"></a>.NET コンパイラ プラットフォーム (&quot;Roslyn&quot;) の拡張機能
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

.NET コンパイラ プラットフォーム ("Roslyn") の主要な目的は、C# および Visual Basic コンパイラを開くと、ツールを許可して、プログラムについて豊富な情報コンパイラを共有する開発者があります。 コード分析ツールでは、コードの品質を向上させ、コード ジェネレーターの補助アプリケーションの構築にします。 スマートなツールとして、コンパイラのみが知っているコードの深い知識の詳細と詳細にアクセスが必要があります。 不透明なトランスレーター (内のソース コードおよびオブジェクト コード) ではなく、Roslyn コンパイラは、ツールやアプリケーション内のコード関連のタスクに使用できる Api を提供します。  
  
 最も重要な部分は Roslyn コンパイラ、その Api、サンプルとチュートリアル、およびこれらの Api の上に構築された実際のツールがすべて完全にオープン ソースがある[github.com/dotnet/roslyn](https://github.com/dotnet/Roslyn)します。 詳細については、Roslyn を使用するには、OSS サイトにアクセスしてください。 Roslyn Api を利用してツール ビルダーとして開始するリンクと同様に、最新の C# と VB の機能、エンド ユーザーとして使用できるを取得へのリンクが表示されます。  
  
## <a name="see-also"></a>関連項目  
 [Roslyn アナライザーの概要](../extensibility/getting-started-with-roslyn-analyzers.md)
