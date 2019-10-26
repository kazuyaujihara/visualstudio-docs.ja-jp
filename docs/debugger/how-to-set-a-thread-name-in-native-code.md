---
title: '方法: ネイティブコードのスレッド名を設定する |Microsoft Docs'
ms.date: 12/17/2018
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], threads
- SetThreadName function
- threading [Visual Studio], names
- thread names
- debugging [Visual Studio], threads
ms.assetid: c85d0968-9f22-4d69-87f4-acca2ae777b8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 1e719563c831c50cc325d70d0de431f4be1bf514
ms.sourcegitcommit: 257fc60eb01fefafa9185fca28727ded81b8bca9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2019
ms.locfileid: "72911425"
---
# <a name="how-to-set-a-thread-name-in-native-code"></a>方法 : ネイティブ コードのスレッド名を設定する
スレッド名の設定は、Visual Studio のどのエディションでも実行できます。 スレッドの名前付けは、実行中のプロセスをデバッグするときに、 **[スレッド]** ウィンドウで目的のスレッドを識別するのに役立ちます。 わかりにくい名前付きスレッドを使用することは、クラッシュダンプ検査で事後分析を実行する場合や、さまざまなツールを使用してパフォーマンスキャプチャを分析する場合にも役立ちます。

## <a name="ways-to-set-a-thread-name"></a>スレッド名を設定する方法

スレッド名を設定するには、2つの方法があります。 1つ目は、 [Setthreaddescription](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreaddescription)関数を使用する方法です。 2つ目は、Visual Studio デバッガーがプロセスにアタッチされている間に特定の例外をスローすることです。 各アプローチには、利点と注意点があります。 `SetThreadDescription` の使用は、Windows 10 バージョン1607または Windows Server 2016 以降でサポートされています。

どちらの方法も、必要に応じて、互いに独立したメカニズムが使用されるため、_両方_の方法を併用できます。

### <a name="set-a-thread-name-by-using-setthreaddescription"></a>`SetThreadDescription` を使用してスレッド名を設定する

利点:
* スレッド名は、SetThreadDescription が呼び出された時点でデバッガーがプロセスにアタッチされたかどうかに関係なく、Visual Studio でデバッグするときに表示されます。
* スレッド名は、Visual Studio でクラッシュダンプを読み込むことによって事後分析のデバッグを実行するときに表示されます。
* また、他のツール ( [WinDbg](/windows-hardware/drivers/debugger/debugger-download-tools)デバッガーや[Windows performance analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)パフォーマンスアナライザーなど) を使用しているときにも、スレッド名が表示されます。

注意事項:
* スレッド名は、Visual Studio 2017 バージョン15.6 以降のバージョンでのみ表示されます。
* クラッシュダンプファイルの事後分析では、クラッシュが Windows 10 バージョン1607、Windows Server 2016、またはそれ以降のバージョンの Windows で作成された場合にのみ、スレッド名が表示されます。

*例:*

```C++
#include <windows.h>
#include <processthreadsapi.h>

int main()
{
    HRESULT r;
    r = SetThreadDescription(
        GetCurrentThread(),
        L"ThisIsMyThreadName!"
    );

    return 0;
}
```

### <a name="set-a-thread-name-by-throwing-an-exception"></a>例外をスローしてスレッド名を設定する

プログラムでスレッド名を設定するもう1つの方法は、特別に構成された例外をスローすることによって、Visual Studio デバッガーに対して目的のスレッド名を通知することです。

利点:
* すべてのバージョンの Visual Studio で動作します。

注意事項:
* は、例外ベースのメソッドが使用された時点でデバッガーがアタッチされている場合にのみ機能します。
* このメソッドを使用して設定されたスレッド名は、ダンプまたはパフォーマンス分析ツールでは使用できません。

*例:*

次に示す `SetThreadName` 関数は、この例外ベースのアプローチを示しています。 スレッド名はスレッドに自動的にコピーされるので、`SetThreadName` の呼び出しが完了した後に `threadName` パラメーターのメモリを解放できるようにします。

```C++
//
// Usage: SetThreadName ((DWORD)-1, "MainThread");
//
#include <windows.h>
const DWORD MS_VC_EXCEPTION = 0x406D1388;
#pragma pack(push,8)
typedef struct tagTHREADNAME_INFO
{
    DWORD dwType; // Must be 0x1000.
    LPCSTR szName; // Pointer to name (in user addr space).
    DWORD dwThreadID; // Thread ID (-1=caller thread).
    DWORD dwFlags; // Reserved for future use, must be zero.
} THREADNAME_INFO;
#pragma pack(pop)
void SetThreadName(DWORD dwThreadID, const char* threadName) {
    THREADNAME_INFO info;
    info.dwType = 0x1000;
    info.szName = threadName;
    info.dwThreadID = dwThreadID;
    info.dwFlags = 0;
#pragma warning(push)
#pragma warning(disable: 6320 6322)
    __try{
        RaiseException(MS_VC_EXCEPTION, 0, sizeof(info) / sizeof(ULONG_PTR), (ULONG_PTR*)&info);
    }
    __except (EXCEPTION_EXECUTE_HANDLER){
    }
#pragma warning(pop)
}
```

## <a name="see-also"></a>関連項目
- [マルチスレッド アプリケーションのデバッグ](../debugger/debug-multithreaded-applications-in-visual-studio.md)
- [デバッガーでのデータ表示](../debugger/viewing-data-in-the-debugger.md)
- [方法 : マネージド コードのスレッド名を設定する](../debugger/how-to-set-a-thread-name-in-managed-code.md)
