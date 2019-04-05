---
title: サービス参照 ダイアログ ボックスの構成 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: reference
f1_keywords:
- msvse_wcf.dlg.ConfigureServiceReference
helpviewer_keywords:
- WCF services, Configure Service Reference dialog box
- service references [Visual Studio], configuring behavior
- Configure Service Reference dialog box
ms.assetid: 25e4c36b-2db6-4e71-9010-b7068255d09d
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4cc4ae6704f59f33de091fe528c7e05898361115
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974019"
---
# <a name="configure-service-reference-dialog-box"></a>[サービス参照の構成] ダイアログ ボックス
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
**サービス参照の構成**ダイアログ ボックスでは、動作を構成できます。[!INCLUDE[vsindigo](../includes/vsindigo-md.md)]サービス。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、[ツール] メニューの [設定のインポートとエクスポート] をクリックします。 詳細については、「 [Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
 **[サービス参照の構成]** ダイアログ ボックスにアクセスするには、**ソリューション エクスプローラー**でサービス参照を右クリックし、**[サービス参照の構成]** を選択します。 **[サービス参照の追加] ダイアログ ボックス**で **[詳細]** ボタンをクリックしてダイアログ ボックスにアクセスすることもできます。  
  
## <a name="task-list"></a>タスク一覧  
  
-   WCF サービスがホストされるアドレスを変更するには、**[アドレス]** フィールドに新しいアドレスを入力します。  
  
-   WCF クライアント内のクラスのアクセス レベルを変更するには、**[生成されたクラスのアクセス レベル]** リストでアクセス レベル キーワードを選択します。  
  
-   WCF サービスのメソッドを非同期に呼び出すには、**[非同期操作を生成する]** チェック ボックスをオンにします。  
  
-   WCF クライアントでメッセージ コントラクト型を生成するには、**[メッセージ コントラクトを常に生成]** チェック ボックスをオンにします。  
  
-   WCF クライアントのリストまたはディクショナリ コレクションの型を指定するには、**[コレクション型]** リストおよび **[ディクショナリ コレクション型]** リストから型を選択します。  
  
-   型の共有を無効にするには、**[参照されたアセンブリで型を再利用]** チェック ボックスをオフにします。 参照されたアセンブリのサブセットで型の共有を有効にするには、**[参照されたアセンブリで型を再利用]** チェック ボックスをオンにし、**[参照されたアセンブリを指定して型を再利用]** チェック ボックスをオンにして、**[Referenced assemblies list]\(参照されたアセンブリの一覧\)** で必要な参照を選択します。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **Address**  
 サービス参照がサービスを検索する Web アドレスを更新するために使用されます。 たとえば、開発中のサービスは開発サーバーでホストされ、その後、運用サーバーに移されることがあり、アドレスの変更が必要になります。  
  
> [!NOTE]
>  Address 要素は、**[サービス参照の構成]** ダイアログ ボックスが **[サービス参照の追加] ダイアログ ボックス**から表示された場合は使用できません。  
  
 **[生成されたクラスのアクセス レベル]**  
 WCF クライアント クラスのコード アクセス レベルを特定します。  
  
> [!NOTE]
>  Web サイト プロジェクトの場合、このオプションは常に `Public` に設定され、変更できません。 詳細については、次を参照してください。[サービス参照のトラブルシューティング](../data-tools/troubleshooting-service-references.md)します。  
  
 **[非同期操作を生成する]**  
 WCF サービス メソッドの呼び出しが同期 (既定) または非同期のどちらであるかを指定します。  
  
 **[タスク ベースの操作を生成する]**  
 非同期コードを作成する場合、このオプションにより、.Net 4 で導入されたタスク並列ライブラリ (TPL) を利用できます。 参照してください[タスク並列ライブラリ (TPL)](http://msdn.microsoft.com/library/dd460717.aspx)します。  
  
 **[メッセージ コントラクトを常に生成]**  
 WCF クライアント向けにメッセージ コントラクト型が生成されるかどうかを指定します。 メッセージ コントラクトの詳細については、次を参照してください。 [Using Message Contracts](http://msdn.microsoft.com/library/1e19c64a-ae84-4c2f-9155-91c54a77c249)します。  
  
 **[コレクション型]**  
 WCF クライアントのリスト コレクション型を指定します。 既定の型は <xref:System.Array> です。  
  
 **[ディクショナリ コレクション型]**  
 WCF クライアントのディクショナリ コレクション型を指定します。 既定の型は <xref:System.Collections.Generic.Dictionary%602> です。  
  
 **[参照されたアセンブリで型を再利用]**  
 サービスが追加または更新された場合、WCF クライアントが、新しい型を生成する代わりに、参照されたアセンブリ内の既存の型を再利用するかどうかを指定します。 既定では、このチェック ボックスはオンになっています。  
  
 **[参照されたアセンブリすべてで型を再利用]**  
 選択した場合、すべての型、**参照されたアセンブリ一覧**可能であれば再利用されます。 既定では、このチェック ボックスはオンになっています。  
  
 **[参照されたアセンブリを指定して型を再利用]**  
 選択した場合、選択した型でのみ、**参照されたアセンブリ一覧**が再利用されます。  
  
 **[Referenced assemblies list]\(参照されたアセンブリの一覧\)**  
 プロジェクトまたは Web サイトで参照されたアセンブリの一覧を含みます。 ときに**参照されたアセンブリを指定した型を再利用**が選択されている個々 のアセンブリを選択またはクリアできます。  
  
 **[Web 参照の追加]**  
 表示、 [NIB:Web 参照 ダイアログ ボックスを追加](http://msdn.microsoft.com/bdf05776-c591-40af-bfd7-e1e2aa1e87b5)します。  
  
> [!NOTE]
>  このオプションは、[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] のバージョン 2.0 を対象にするプロジェクトでのみ使用する必要があります。  
  
> [!NOTE]
>  **Web 参照の追加**ボタンが使用可能な場合にのみ、**サービス参照の構成**からダイアログ ボックスが表示されます、**サービス参照の追加 ダイアログ ボックス**します。  
  
## <a name="see-also"></a>関連項目  
 [方法: 追加、更新、またはサービス参照の削除](http://msdn.microsoft.com/library/cacc14bd-4455-4a44-be78-d2ac16113dd9)   
 [方法: Web サービスへの参照を追加します。](http://msdn.microsoft.com/library/952e49a1-567e-4a74-8cd7-f2e7b62c3168)   
 [Windows Communication Foundation サービスと WCF Data Services](../data-tools/configure-service-reference-dialog-box.md)
