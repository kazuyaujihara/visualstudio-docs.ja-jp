---
title: データを保存する前にデータ バインド コントロールの中の編集をコミット |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- committing edited records
- data-bound controls, in-process edits
- DataBinding class, committing edited records
- hierarchical update, committing edited records
- BindingSource class, committing edited records
- EndEdit method
ms.assetid: 61af4798-eef7-468c-b229-5e1497febb2f
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2def3f3512e7a6ebc2e084f0bca4d6b1707ecd04
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65699493"
---
# <a name="commit-in-process-edits-on-data-bound-controls-before-saving-data"></a>データの保存前にデータ バインド コントロールで実行中の編集をコミットする
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

データ バインド コントロール内の値を編集するには、ユーザーを更新された値に、コントロールがバインドされている基になるデータ ソースにコミットする現在のレコードを移動する必要があります。 項目をドラッグすると、[データ ソース ウィンドウ](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)を削除する最初の項目のフォームへにコードが生成されます、**保存**ボタン クリックしてイベントの<xref:System.Windows.Forms.BindingNavigator>します。 このコードは、<xref:System.Windows.Forms.BindingSource.EndEdit%2A>のメソッド、<xref:System.Windows.Forms.BindingSource>します。 呼び出しでは、そのため、<xref:System.Windows.Forms.BindingSource.EndEdit%2A>メソッドは、最初にのみ生成<xref:System.Windows.Forms.BindingSource>フォームに追加されています。  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 呼び出しは、現在編集中のデータ バインド コントロールで実行されている変更をコミットします。 したがって、あるデータ バインド コントロールにフォーカスがある状態で **[保存]** ボタンをクリックすると、実際の保存 (`TableAdapterManager.UpdateAll` メソッド) が実行される前に、そのコントロール内のすべての保留中の編集がコミットされます。  
  
 自動的に変更をコミットするアプリケーションを構成するには、ユーザーが、保存の一部として変更をコミットせずにデータを保存しようとしています。 場合でもプロセス。  
  
> [!NOTE]
> デザイナーに追加、`BindingSource.EndEdit`最初の項目に対してのみコードがフォームにドロップします。 呼び出すコード行を追加する必要があるため、<xref:System.Windows.Forms.BindingSource.EndEdit%2A>メソッドごとに<xref:System.Windows.Forms.BindingSource>形式にします。 呼び出すコード行を手動で追加することができます、<xref:System.Windows.Forms.BindingSource.EndEdit%2A>メソッドごとに<xref:System.Windows.Forms.BindingSource>します。 また、追加することができます、`EndEditOnAllBindingSources`をフォームにメソッドと保存を実行する前に付けます。  
  
 次のコードでは、 [LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)すべてを反復処理するクエリ<xref:System.Windows.Forms.BindingSource>コンポーネントと呼び出し、<xref:System.Windows.Forms.BindingSource.EndEdit%2A>メソッドごとに<xref:System.Windows.Forms.BindingSource>フォームで。  
  
## <a name="to-call-endedit-for-all-bindingsource-components-on-a-form"></a>フォーム上のすべての BindingSource コンポーネントの EndEdit を呼び出す  
  
1. 次のコードを含むフォームを追加、<xref:System.Windows.Forms.BindingSource>コンポーネント。  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#1](../snippets/csharp/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/CS/Form1.cs#1)]
     [!code-vb[VSProDataOrcasEndEditOnAll#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/VB/Form1.vb#1)]  
  
2. 次のフォームのデータを保存する呼び出しのすぐ前に、のコード行を追加 (、`TableAdapterManager.UpdateAll()`メソッド)。  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#2](../snippets/csharp/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/CS/Form1.cs#2)]
     [!code-vb[VSProDataOrcasEndEditOnAll#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio でのデータへの Windows フォーム コントロールのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [階層更新](../data-tools/hierarchical-update.md)
