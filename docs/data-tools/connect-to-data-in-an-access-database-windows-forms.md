---
title: Access データベース内のデータへの接続 (Windows フォーム)
ms.date: 02/12/2019
ms.topic: conceptual
helpviewer_keywords:
- databases, connecting to
- databases, Access
- data [Visual Studio], connecting
- connecting to data, from Access databases
- Access databases, connecting
ms.assetid: 4159e815-d430-4ad0-a234-e4125fcbef18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 9d4fcce4664483cd1d981f6a0b1233a6302c553b
ms.sourcegitcommit: b14b7a938a2aba9fcce4d5e813aadf2040b0dcda
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58647350"
---
# <a name="connect-to-data-in-an-access-database-windows-forms"></a>Access データベース内のデータへの接続 (Windows フォーム)

Access データベースに接続することができます (いずれか、 *.mdf*ファイルまたは *.accdb*ファイル) Visual Studio を使用します。 接続を定義すると、**[データ ソース ウィンドウ]** にデータが表示されます。 ここから、テーブルまたはビューをフォームにドラッグできます。

## <a name="prerequisites"></a>必須コンポーネント

これらの手順を行うには、Windows フォーム アプリケーション プロジェクト、および Microsoft Access データベース ファイル (*.accdb* ファイル) または Access 2000-2003 データベース (*.mdb* ファイル) が必要です。 ファイルの種類に対応する手順に従ってください。

## <a name="create-a-dataset-for-an-accdb-file"></a>データセット .accdb ファイルを作成します。

次の手順を使用して、Access 2013、Office 365、Access 2010、または Access 2007 によって作成されたデータベースに接続することができます。

1. データの接続先となる Windows フォーム アプリケーションを開きます。

2. 開くには、**データ ソース**ウィンドウで、**ビュー**メニューの **その他の Windows** > **データ ソース**します。

   ![[表示]、[その他のウィンドウ]、[データ ソース]](../data-tools/media/viewdatasources.png)

3. **[データ ソース]** ウィンドウで、 **[新しいデータ ソースの追加]** をクリックします。

   **データ ソース構成ウィザード**が開きます。

4. 選択**データベース**上、**データ ソースの種類を選択**ページ、し、 **次へ**。

5. 選択**データセット**上、**データベース モデルの選択**ページ、し、 **次へ**。

6. **[データ接続の選択]** ページで、**[新しい接続]** を選択して新しいデータ接続を構成します。

   **[接続の追加]** ダイアログ ボックスが表示されます。

7. 場合**データ ソース**に設定されていない**Microsoft Access データベース ファイル (OLE DB)** を選択、**変更**ボタンをクリックします。

   **データ ソースの変更** ダイアログ ボックスが表示されます。 データ ソースの一覧で選択**Microsoft Access データベース ファイル**します。 **データ プロバイダー**ドロップダウン リストで選択 **.NET Framework Data Provider for OLE DB**、選び、 **OK**。

8. 選択**参照**横に**データベース ファイル名**、順に移動します、 *.accdb*ファイル**オープン**します。

9. ユーザー名とパスワード (必要に応じて) を入力し、 **OK**します。

10. 選択**次**で、**データ接続の選択**ページ。

     データ ファイルは、現在のプロジェクトにないことを示すダイアログ ボックスが表示されます。 **[はい]** または **[いいえ]** をクリックします。

11. 選択**次**で、**接続文字列をアプリケーション構成ファイルに保存**ページ。

12. **[データベース オブジェクトの選択]** ページの **[テーブル]** ノードを展開します。

13. テーブルまたはビューをクリックして、データセットに含める選択**完了**します。

     プロジェクトにデータセットが追加され、テーブルとビューが **[データ ソース]** ウィンドウに表示されます。

## <a name="create-a-dataset-for-an-mdb-file"></a>データセット .mdb ファイルを作成します。

**データ ソース構成ウィザード**を実行して、データセットを作成します。

1. データの接続先となる Windows フォーム アプリケーションを開きます。

2. **ビュー**メニューの **その他の Windows** > **データソース**します。

   ![[表示]、[その他のウィンドウ]、[データ ソース]](../data-tools/media/viewdatasources.png)

3. **[データ ソース]** ウィンドウで、 **[新しいデータ ソースの追加]** をクリックします。

    **データ ソース構成ウィザード**が開きます。

4. 選択**データベース**上、**データ ソースの種類を選択**ページ、し、 **次へ**。

5. 選択**データセット**上、**データベース モデルの選択**ページ、し、 **次へ**。

6. **[データ接続の選択]** ページで、**[新しい接続]** を選択して新しいデータ接続を構成します。

7. データ ソースがない場合**Microsoft Access データベース ファイル (OLE DB)**、**変更**を開く、**データ ソースの変更**] ダイアログ ボックスを選択します**Microsoftデータベース ファイルにアクセス**、し、[ **OK**します。

8. **データベース ファイル名**の名前とパスを指定、 *.mdb*ファイルへの接続を選択する**OK**します。

   ![Access データベース ファイルへの接続を追加](../data-tools/media/add-connection-access-db.png)

9. 選択**次**で、**データ接続の選択**ページ。

10. 選択**次**で、**接続文字列をアプリケーション構成ファイルに保存**ページ。

11. **[データベース オブジェクトの選択]** ページの **[テーブル]** ノードを展開します。

12. 任意のテーブルまたはビュー、データセット内に指定し、選択**完了**します。

    プロジェクトにデータセットが追加され、テーブルとビューが **[データ ソース]** ウィンドウに表示されます。

## <a name="security"></a>セキュリティ

機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。 データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。 詳細については、「[接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。

## <a name="next-steps"></a>次の手順

先ほど作成したデータセットで提供されて、**データソース**ウィンドウ。 これで、以下のタスクをどれでも実行できます。

- 内の項目を選択して、**データ ソース**ウィンドウ、フォームにドラッグし、(を参照してください[Visual Studio でのデータにコントロールを Windows フォームのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md))。

- **データセット デザイナー**でデータ ソースを開き、データセットを構成しているオブジェクトを追加または編集します。

- 検証ロジックを追加、<xref:System.Data.DataTable.ColumnChanging>または<xref:System.Data.DataTable.RowChanging>データセット内のデータ テーブルのイベント (を参照してください[データセットのデータの検証](../data-tools/validate-data-in-datasets.md))。

## <a name="see-also"></a>関連項目

- [接続を追加する](../data-tools/add-new-connections.md)