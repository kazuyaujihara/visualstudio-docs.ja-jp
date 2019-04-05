---
title: '方法: アクティビティ ログの使用 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, debugging
- VSPackages, troubleshooting
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
caps.latest.revision: 30
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 50ef738826a9eb85a081a7063c1ca55280bed3a8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976006"
---
# <a name="how-to-use-the-activity-log"></a>方法: アクティビティ ログを使用する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vspackage は、メッセージをアクティビティ ログに書き込むことができます。 この機能は、小売環境で Vspackage をデバッグするために特に便利です。  
  
> [!TIP]
>  アクティビティ ログは常にオンにします。 Visual Studio では、一般的な構成情報がある、最初の 10 個のエントリと同様に、100 を最後のエントリのローリング バッファーを保持します。  
  
### <a name="to-write-an-entry-to-the-activity-log"></a>アクティビティ ログにエントリを書き込む  
  
1.  このコードを挿入、<xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A>メソッドまたはコンス トラクターは、VSPackage を除くその他の方法で。  
  
    ```csharp  
    IVsActivityLog log = GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log == null) return;  
  
    int hr = log.LogEntry((UInt32)__ACTIVITYLOG_ENTRYTYPE.ALE_INFORMATION,  
        this.ToString(),  
        string.Format(CultureInfo.CurrentCulture,  
        "Called for: {0}", this.ToString()));  
    ```  
  
     このコードを取得、<xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog>サービスおよびにキャスト、<xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>インターフェイス。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A> 現在のカルチャのコンテキストを使用してアクティビティ ログに情報のエントリを書き込みます。  
  
2.  (通常は、コマンドが呼び出されたまたはウィンドウを開いた) ときに VSPackage が読み込まれるときに、テキストは、アクティビティ ログに書き込まれます。  
  
### <a name="to-examine-the-activity-log"></a>アクティビティ ログを確認するには  
  
1.  Visual Studio のデータのサブフォルダーでアクティビティ ログを検索: *%appdata%* \Microsoft\VisualStudio\14.0\ActivityLog.XML.  
  
2.  任意のテキスト エディターでは、アクティビティ ログを開きます。 一般的なエントリを次に示します。  
  
    ```  
    Called for: Company.MyApp.MyAppPackage ...  
    ```  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 アクティビティ ログは、サービスであるためには、アクティビティ ログは、VSPackage のコンス トラクターで使用できません。  
  
 記述する前に、アクティビティ ログを取得する必要があります。 キャッシュしたり、将来使用するためのアクティビティ ログを保存しないでください。  
  
## <a name="see-also"></a>関連項目  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [Vspackage のトラブルシューティング](../extensibility/troubleshooting-vspackages.md)   
 [VSPackage](../extensibility/internals/vspackages.md)
