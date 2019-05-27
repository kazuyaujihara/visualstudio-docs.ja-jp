---
title: ユーザー設定ストアへの書き込み |Microsoft Docs
ms.date: 05/23/2019
ms.topic: conceptual
ms.assetid: efd27f00-7fe5-45f8-9b97-371af732be97
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe8187fe11f4818433aed847a7bc67d4a889ad3a
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66206881"
---
# <a name="writing-to-the-user-settings-store"></a>ユーザー設定ストアへの書き込み
ユーザーの設定は、書き込み可能の設定で使用されているように、**ツール/オプション**ダイアログ、[プロパティ] ウィンドウ、およびその他の特定のダイアログ ボックス。 Visual Studio 拡張機能は、これらを使用少量のデータを格納するのにことがあります。 このチュートリアルでは、ユーザー設定ストアへの書き込みから読み取りによって、外部ツールとして Visual Studio をメモ帳を追加する方法を示します。

## <a name="writing-to-the-user-settings-store"></a>ユーザー設定ストアへの書き込み

1. UserSettingsStoreExtension をという名前の VSIX プロジェクトを作成し、UserSettingsStoreCommand をという名前のカスタム コマンドを追加します。 カスタム コマンドを作成する方法の詳細については、次を参照してください[メニュー コマンドを使用して拡張機能の作成。](../extensibility/creating-an-extension-with-a-menu-command.md)

2. UserSettingsStoreCommand.cs で、次のコードを追加ステートメントを使用します。

    ```csharp
    using System.Collections.Generic;
    using Microsoft.VisualStudio.Settings;
    using Microsoft.VisualStudio.Shell.Settings;
    ```

3. MenuItemCallback では、メソッドの本体を削除し、設定の保存、次のようにユーザーを取得します。

    ```csharp
    private void MenuItemCallback(object sender, EventArgs e)
    {
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);
    }
    ```

4. メモ帳は、外部ツールとして既に設定されているかどうかを調べるようになりました。 ToolCmd 設定が"Notepad"を次のようがあるかどうかを判断するすべての外部ツールを反復処理する必要があります。

    ```csharp
    private void MenuItemCallback(object sender, EventArgs e)
    {
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);

        // Find out whether Notepad is already an External Tool.
        int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys");
        bool hasNotepad = false;
        CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo;
        for (int i = 0; i < toolCount; i++)
        {
            if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0)
            {
                hasNotepad = true;
                break;
            }
        }
    }

    ```

5. メモ帳が外部のツールとして設定されていない場合は、次のように設定します。

    ```vb
    private void MenuItemCallback(object sender, EventArgs e)
    {
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);

        // Find out whether Notepad is already installed.
        int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys");
        bool hasNotepad = false;
        CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo;
        for (int i = 0; i < toolCount; i++)
        {
            if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0)
            {
                hasNotepad = true;
                break;
            }
        }

        string message = (hasNotepad) ? "Notepad already installed" : "Installing Notepad";
         if (!hasNotepad)
        {
            userSettingsStore.SetString("External Tools", "ToolTitle" + toolCount, "&Notepad");
            userSettingsStore.SetString("External Tools", "ToolCmd" + toolCount, "C:\\Windows\\notepad.exe");
            userSettingsStore.SetString("External Tools", "ToolArg" + toolCount, "");
            userSettingsStore.SetString("External Tools", "ToolDir" + toolCount, "$(ProjectDir)");
            userSettingsStore.SetString("External Tools", "ToolSourceKey" + toolCount, "");
            userSettingsStore.SetUInt32("External Tools", "ToolOpt" + toolCount, 0x00000011);

            userSettingsStore.SetInt32("External Tools", "ToolNumKeys", toolCount + 1);
        }
    }
    ```

6. コードをテストします。 ロールバックしなければならない、レジストリをもう一度実行する前にように、外部のツールとしてメモ帳を追加、ことに注意してください。

7. コードをビルドし、デバッグを開始します。

8. **ツール** メニューのをクリックして**呼び出す UserSettingsStoreCommand**します。 これをメモ帳に追加されます、**ツール**メニュー。

9. ツールで、メモ帳を表示する必要があります]/[オプション] メニューの [クリックして**メモ帳**メモ帳のインスタンスを起動する必要があります。