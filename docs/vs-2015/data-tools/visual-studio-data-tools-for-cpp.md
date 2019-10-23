---
title: Visual Studio data tools for C++ |Microsoft Docs
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.date: 11/15/2016
ms.topic: conceptual
ms.assetid: 3a3849d9-1bc7-47d1-805e-1755223ccba2
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: jillfra
robots: noindex,nofollow
ms.openlocfilehash: ec68d54ced85737d66c64ca2dbf7942ca81e5314
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72621204"
---
# <a name="visual-studio-data-tools-for-c"></a>C++ 用の Visual Studio データ ツール
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ネイティブC++では、多くの場合、データソースにアクセスするときに最速のパフォーマンスが得られます。 ただし、Visual Studio でC++のアプリケーションのデータツールは、.net アプリケーションの場合ほど豊富ではありません。 たとえば、データソースウィンドウを使用してデータソースをC++デザイン画面にドラッグアンドドロップすることはできません。 オブジェクトリレーショナルレイヤーが必要な場合は、独自のものを作成するか、サードパーティ製品を使用する必要があります。  これはデータバインディング機能にも当てはまりますが、Microsoft Foundation Class ライブラリを使用するアプリケーションでは、一部のデータベースクラスをドキュメントやビューと共に使用して、データをメモリに格納し、ユーザーに表示することができます。 詳細については、「[ビジュアルC++でのデータアクセス](https://msdn.microsoft.com/library/7wtdsdkh.aspx)」を参照してください。

 SQL データベースに接続するにはC++ 、ネイティブアプリケーションで ODBC および OLE DB ドライバーと、Windows に含まれている ADO プロバイダーを使用できます。     これらのインターフェイスをサポートする任意のデータベースに接続できます。 ODBC ドライバーは標準です。 OLE DB は、旧バージョンとの互換性のために用意されています。 これらのデータテクノロジの詳細については、「 [Windows データアクセスコンポーネント](https://msdn.microsoft.com/library/windows/desktop/aa968814\(v=vs.85\).aspx)」を参照してください。

 SQL Server 2005 以降のカスタム機能を利用するには、 [SQL Server Native Client](https://msdn.microsoft.com/sqlserver/aa937733)を使用します。 Native client には、1つのネイティブダイナミックリンクライブラリ (DLL) に SQL Server ODBC ドライバーと SQL Server OLE DB プロバイダーも含まれています。 これらは、ネイティブコード Api (ODBC、OLE DB、ADO) を使用して Microsoft SQL Server するアプリケーションをサポートします。  SQL Server Native Client SQL Server Data Tools と共にインストールされます。 プログラミングガイドについては、 [SQL Server Native Client プログラミング](https://msdn.microsoft.com/library/ms130892.aspx)」を参照してください。

## <a name="to-connect-to-localdb-through-odbc-and-sql-native-client-from-a-c-application"></a>ODBC を使用して localDB に接続し、 C++アプリケーションから SQL Native Client するには

1. SQL Server Data Tools をインストールします。

2. 接続するサンプルの SQL データベースが必要な場合は、Northwind データベースをダウンロードし、新しい場所に解凍します。

3. SQL Server Management Studio を使用して、解凍した Northwind .mdf ファイルを localDB にアタッチします。 SQL Server Management Studio が開始されたら、(localdb) \MSSQLLocalDB. に接続します。

    ![SSMS の接続ダイアログ](../data-tools/media/raddata-ssms-connect-dialog.png "レーダーデータ SSMS 接続ダイアログ")

    次に、左側のウィンドウで localdb ノードを右クリックし、 **[アタッチ]** を選択します。

    ![SSMS のデータベースのアタッチ](../data-tools/media/raddata-ssms-attach-database.png "レーダーデータ SSMS データベースのアタッチ")

4. ODBC Windows SDK サンプルをダウンロードし、新しい場所に解凍します。 このサンプルでは、データベースへの接続とクエリとコマンドの実行に使用される基本的な ODBC コマンドを示します。 これらの関数の詳細については、 [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/library/windows/desktop/ms710252\(v=vs.85\).aspx)を参照してください。 ソリューションを初めて読み込むと ( C++フォルダー内にある)、visual studio はソリューションを現在のバージョンの visual studio にアップグレードすることを提供します。 **[はい]** をクリックします。

5. Native client を使用するには、そのヘッダーファイルと lib ファイルが必要です。 これらのファイルには、SQL .h で定義されている ODBC 関数以外の SQL Server に固有の関数と定義が含まれています。 [**プロジェクト** >  の**プロパティ** > **VC + + ディレクトリ**] で、次のインクルードディレクトリを追加します。

   **\<system ドライブ >: Server\110\SDK\Include**    このライブラリディレクトリは次のようになります。

   **c:\Program Server\110\SDK\Lib SQL**

6. これらの行を odbcsql .cpp に追加します。 #Define によって、無関係の OLE DB 定義がコンパイルされるのを防ぐことができます。

   ```
   #define _SQLNCLI_ODBC_
   #include <sqlncli.h>
   ```

    このサンプルでは、実際には native client の機能を使用していないので、コンパイルして実行するために上記の手順は必要ありません。 しかし、この機能を使用できるようにプロジェクトが構成されました。 詳細については、「 [SQL Server Native Client プログラミング](https://msdn.microsoft.com/library/ms130892\(v=sql.130\).aspx)」を参照してください。

7. ODBC サブシステムで使用するドライバーを指定します。 このサンプルでは、のドライバー接続文字列属性をコマンドライン引数として渡します。 [**プロジェクト** >  の**プロパティ** > **デバッグ**] で、次のコマンド引数を追加します。

   ```
   DRIVER="SQL Server Native Client 11.0"
   ```

8. F5 キーを押してアプリケーションをビルドし、実行します。 ドライバーから、データベースを入力するように求めるダイアログボックスが表示されます。 @No__t_0 を入力し、 **[信頼できる接続を使用する]** チェックボックスをオンにします。 **[OK]** を押します。 接続が成功したことを示すメッセージが表示されたコンソールが表示されます。 SQL ステートメントを入力できるコマンドプロンプトも表示されます。 次の画面は、クエリの例と結果を示しています。

    ![ODBC サンプルクエリの出力](../data-tools/media/raddata-odbc-sample-query-output.png "レーダーデータ ODBC サンプルクエリの出力")

## <a name="see-also"></a>参照
 [Visual Studio でのデータへのアクセス](../data-tools/accessing-data-in-visual-studio.md)
