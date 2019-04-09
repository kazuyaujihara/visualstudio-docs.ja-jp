---
title: チーム プロジェクト チェックイン ポリシーによるコード品質の向上 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code quality, using check-in policies
- team-based development, enhancing code quality
ms.assetid: 0ab72c33-148a-4a8a-a7bf-046995514c84
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 02c6b2912d828f566236aa8f24868ae9314d743e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962524"
---
# <a name="enhancing-code-quality-with-team-project-check-in-policies"></a>チーム プロジェクト チェックイン ポリシーによるコード品質の向上
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Team Foundation バージョン コントロール (TFVC) を使用する場合は、チーム プロジェクトのチェックイン ポリシーを作成して、 コードの品質向上とグループ開発の効率化を実現するための対策を適用できます。 チェックイン ポリシーとは、チーム プロジェクト レベルで設定され、コードをチェックインする前に開発者のコンピューターに適用される規則です。  
  
 これらのチーム プロジェクト チェックイン ポリシーを指定できます。  
  
-   **ビルド**:ビルド中に作成されたビルド ブレークを新しいチェックインの前に修正しなければならないことが必要です。  
  
-   **変更セット コメント**:変更をチェックインするときに、ユーザーがコメントを指定する必要があります。  
  
-   **コード分析**:チェックインの前に、コード分析を実行することが必要です。  
  
-   **作業項目**:1 つまたは複数の作業項目チェックインに関連付けられている必要があります。  
  
> [!IMPORTANT]
>  チェックイン ポリシーを使用するには、 [!INCLUDE[vststfsLong](../includes/vststfslong-md.md)]に接続する必要があります。  
  
## <a name="common-tasks"></a>よく使う機能  
  
|タスク|関連する参照先|  
|----------|------------------------|  
|**作成し、チェックイン ポリシーを使用します。** チーム プロジェクトの設定を使用してチェックイン ポリシーを作成する[!INCLUDE[esprscc](../includes/esprscc-md.md)]します。|[品質ゲートの設定と適用](http://msdn.microsoft.com/library/bdc5666e-6cf0-45b2-a0a1-133c3f61e852)|  
|**作成し、コード分析チェックイン ポリシーを使用します。** コード分析規則の標準セットから選択することができます、またはカスタムのセットを作成することができます。|[コード分析を用いたチェックイン ポリシーの作成と使用](../code-quality/creating-and-using-code-analysis-check-in-policies.md)|  
  
## <a name="related-tasks"></a>関連タスク  
  
|タスク|関連する参照先|  
|----------|------------------------|  
|**開発環境を設定します。** 作成したり、コードを変更することが、前に、開発を設定し、適切なソース コードを使用して環境をテストする必要があります。 データベースを使用している場合は、そのデータベースのオフライン形式へのアクセス権も必要です。|[開発環境の設定](http://msdn.microsoft.com/7b686610-d379-4ca0-9608-73ef0e576e3a)|  
|**開発プロセスにおけるコード分析を使用します。** チームのメンバーは、それぞれの開発コンピューターでコード分析を実行します。 Visual Studio では、開発者が個々のコード プロジェクトについてコード分析を構成および実行し、実行したコード分析で発見された問題を表示および分析して、警告用の作業項目を作成します。|[アプリケーション品質の分析](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)|  
|**作成し、単体テストを実行します。** 単体テストは、開発者およびテスト担当者にも C#、Visual Basic .NET、および C++ のプロジェクトでクラスのメソッドにロジック エラーを確認する簡単な方法を提供します。 単体テストは、1 回作成するだけでよく、バグが追加されていないことを確認するために、ソース コードが変更されるたびに実行できます。|[コードの単体テスト](../test/unit-test-your-code.md)|  
|**作業項目と欠陥を追跡します。** 作業項目を使用して、追跡およびチーム プロジェクトに関する作業と情報の両方を管理することができます。 作業項目は [!INCLUDE[esprfound](../includes/esprfound-md.md)] が作業の割り当てと進行状況を追跡するために使用するデータベース レコードです。 さまざまな種類の作業項目を使用して、顧客要件、製品バグ、開発タスクなどの作業を追跡できます。|[作業の追跡し、ワークフローの管理&#91;リダイレクト&#93;](http://msdn.microsoft.com/d2d8637d-0ef8-4ca3-874e-a04713344032)|  
  
## <a name="external-resources"></a>外部リソース  
  
### <a name="guidance"></a>ガイダンス  
 [Visual Studio 2012 – Chapter 2 による継続的デリバリーのテスト。単体テスト:内部のテスト](http://go.microsoft.com/fwlink/?LinkID=255188)
