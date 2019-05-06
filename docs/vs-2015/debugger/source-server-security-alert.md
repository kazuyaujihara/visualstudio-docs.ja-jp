---
title: ソース サーバーのセキュリティ警告 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.enablewarning
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cc7c68fe767d2add0842e30f66c51a3dcc84905f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63447291"
---
# <a name="source-server-security-alert"></a>ソース サーバー のセキュリティ警告
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ソース サーバーの使用時は、認識できて信頼できる場所からのシンボル ファイルのみを使用してください。  
  
 ソース サーバーのサポートを有効にすると、この警告が表示されます。 ソース サーバーのコマンドは、デバッグ シンボル ファイル (PDB ファイル) に埋め込まれています。 PDB ファイルの作成元を確認してください。  
  
> [!IMPORTANT]
> 次の潜在的なセキュリティの脅威は、移行元サーバーを使用する場合を考慮する必要があります。任意のコマンドは、アプリケーションの PDB ファイルに埋め込むことができます、srcsrv.ini ファイルに実行するもののみを配置するようにします。 srcsvr.ini ファイルにないコマンドを実行しようとすると、確認のダイアログ ボックスが表示されます。 詳細については、次を参照してください。[セキュリティ警告。デバッガーは信頼されていないコマンドを実行する必要があります](../debugger/security-warning-debugger-must-execute-untrusted-command.md)します。コマンドのパラメーターの検証は行われません、そのコマンドを信頼するように注意してください。 たとえば、cmd.exe を信頼した場合、悪意のあるユーザーが危険な動作を実行するようにコマンドにパラメーターを指定する可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [シンボル (.pdb) とソース ファイルの指定](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [デバッガーのセキュリティ](../debugger/debugger-security.md)   
 [ソース サーバー](http://msdn.microsoft.com/library/windows/desktop/ms680641.aspx)
