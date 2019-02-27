---
title: コード化された UI テスト用の Excel アドインのサンプル | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- coded UI tests, Excel Add-in sample
ms.assetid: 2cd52d1a-4c35-43ca-8a84-9c79dabd907f
caps.latest.revision: 18
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ded54760efe611b337c736e0474042b70ff8bf2e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54791951"
---
# <a name="sample-excel-add-in-for-coded-ui-testing"></a>コード化された UI テスト用の Excel アドインのサンプル
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

この [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 用アドイン サンプルは、Excel ワークシートのコード化された UI テストを明確にサポートし、Visual Studio Enterprise で動作するように設計されています。 このアドインは、Visual Studio Tools for Office を使用して作成されています。  
  
 Excel アドインを作成する方法の詳細については、次を参照してください。[チュートリアル。Excel 用の最初の VSTO アドインを作成する](http://msdn.microsoft.com/library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)またはの「Excel アドイン」MSDN を検索します。  
  
 Excel アドインは Excel 用のコード化された UI テスト拡張機能に関するこのドキュメントの主題ではありませんが、いくつかのコメントが役立ちます。  
  
 このアドインの重要な部分:  
  
-   `ThisAddIn` クラス - `ExcelUICommunicator` と [Excel 用にコード化された UI テストの拡張子のサンプル](../test/sample-coded-ui-test-extension-for-excel.md)の間の .NET リモート処理チャネルを管理します。  
  
-   `ExcelCodedUIAddinHelper_TemporaryKey.pfx` - アドインのテスト用のセキュリティ証明書。  
  
-   `ExcelUICommunicator` クラス - このクラスは、`IExcelUICommunication` インターフェイスを実装します。  
  
## <a name="thisaddin-class"></a>ThisAddIn クラス  
 このクラスのほとんどは、実際に Excel アドイン プロジェクトを作成するときに Visual Studio Tools for Office によって `ThisAddIn.Designer.cs` ファイルに生成されます。  
  
 実装する必要があるメンバーは、`ThisAddIn_Startup()` と `ThisAddIn_Shutdown()` のイベント ハンドラーです。 これらのイベント ハンドラーは、`ExcelUICommunicator` によって使用される .NET リモート処理チャネルを初期化または閉じることを目的としています。  
  
## <a name="excelcodeduiaddinhelpertemporarykeypfx"></a>ExcelCodedUIAddinHelper_TemporaryKey.pfx  
 このファイルには、Visual Studio Tools for Office によって生成され、アドインと拡張機能のテストのために Excel プロセスで動作するのに必要なアドイン アセンブリのアクセス許可を与える一時的なセキュリティ証明書が含まれます。 この証明書を削除した後、プロジェクトの**プロパティ** ウィンドウの **[署名]** タブで新しい証明書を作成するか、または独自のテスト用証明書をアタッチする必要があります。  
  
## <a name="exceluicommunicator-class"></a>ExcelUICommunicator クラス  
 このクラスは、`IExcelUITestCommunication` インターフェイスを実装し、Excel オブジェクト モデルから要求された UI 情報を取得します。 詳細については、「[Excel Communicator インターフェイスのサンプル](../test/sample-excel-communicator-interface.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コード化された UI テストと操作の記録を拡張して Microsoft Excel をサポート](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)   
 [チュートリアル : 初めての Excel 用 VSTO アドインの作成](http://msdn.microsoft.com/library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)   
 [Office および SharePoint 開発](http://msdn.microsoft.com/library/2ddec047-263a-4901-a54c-a15fc8472329)
