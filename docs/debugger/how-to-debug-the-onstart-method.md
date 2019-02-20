---
title: '方法: OnStart メソッドをデバッグ |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- OnStart method
- debugging [Visual Studio], Windows services
- debugging managed code, OnStart method
- debugging Windows Services applications, OnStart method
- Windows Service applications, debugging
ms.assetid: b06b5d65-424b-490f-bf58-97583cd7006a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2cfd6153389bbfe9cbbd36f33f6a2e4384509297
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227062"
---
# <a name="how-to-debug-the-onstart-method"></a>方法 : OnStart メソッドをデバッグする
Windows サービスをデバッグするには、サービスを起動し、デバッガーをサービス プロセスにアタッチします。 詳細については、「 [How to: Debug Windows Service Applications](/dotnet/framework/windows-services/how-to-debug-windows-service-applications)」を参照してください。 ただし、Windows サービスの <xref:System.ServiceProcess.ServiceBase.OnStart%2A?displayProperty=fullName> メソッドをデバッグするには、メソッド内部からデバッガーを起動する必要があります。

1. <xref:System.Diagnostics.Debugger.Launch%2A> メソッドの始めに、呼び出しを `OnStart()`に追加します。

    ```csharp
    protected override void OnStart(string[] args)
    {
        System.Diagnostics.Debugger.Launch();
    }
    ```

2. サービスを開始します ( `net start`を使うか、 **[サービス]** ウィンドウで開始することができます)。

    次のようなダイアログ ボックスが表示されます。

    ![OnStartDebug](../debugger/media/onstartdebug.png "OnStartDebug")

3.  **[はい、** service name> をデバッグします]\< を選びます。

4. [Just-In-Time デバッガー] ウィンドウで、デバッグに使う Visual Studio のバージョンを選びます。

    ![JustInTimeDebugger](../debugger/media/justintimedebugger.png "JustInTimeDebugger")

5. Visual Studio の新しいインスタンスが開始し、 `Debugger.Launch()` メソッドで実行が停止します。

## <a name="see-also"></a>参照
[デバッガーのセキュリティ](../debugger/debugger-security.md)  
[マネージド コードをデバッグする](../debugger/debugging-managed-code.md)
