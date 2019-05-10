---
title: エディター拡張機能から DTE オブジェクトにアクセスします。
ms.date: 04/24/2019
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - getting the DTE object
ms.assetid: c1f40bab-c6ec-45b0-8333-ea5ceb02a39d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9c3e21ea3d05350a59d62fc9da9e0387f072ec16
ms.sourcegitcommit: 62f42113ae4dae1ddfff1c4e02445acc09913445
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "64878197"
---
# <a name="walkthrough-access-the-dte-object-from-an-editor-extension"></a>チュートリアル: エディター拡張機能から DTE オブジェクトにアクセスします。

Vspackage では、呼び出すことによって、DTE オブジェクトを取得できます、 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> DTE オブジェクトの型を持つメソッド。 Managed Extensibility Framework (MEF) 拡張機能でインポートできる<xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>を呼び出して、<xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A>メソッドの型を持つ<xref:EnvDTE.DTE>します。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルに従うには、Visual Studio SDK をインストールする必要があります。 詳細については、次を参照してください。 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)します。

## <a name="get-the-dte-object"></a>DTE オブジェクトを取得します。

1. 作成、 C# VSIX プロジェクトし、名前を付けます**DTETest**します。 追加、**エディター分類子**項目テンプレートと名前を付けます**DTETest**します。

   詳細については、次を参照してください。[エディターの項目テンプレートを使用した拡張機能を作成する](../extensibility/creating-an-extension-with-an-editor-item-template.md)します。

::: moniker range=">=vs-2019"

2. プロジェクトには、次のアセンブリ参照を追加します。

    - Microsoft.VisualStudio.Shell.Immutable.10.0

3. *DTETestProvider.cs*ファイルで、次の追加`using`ディレクティブ。

    ```csharp
    using EnvDTE;
    using Microsoft.VisualStudio.Shell;
    ```

4. `DTETestProvider`クラスは、インポート、<xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>します。

    ```csharp
    [Import]
    internal SVsServiceProvider ServiceProvider = null;
    ```

5. `GetClassifier()`メソッドの前に、次のコードを追加、`return`ステートメント。

    ```csharp
   ThreadHelper.ThrowIfNotOnUIThread();
   DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));
   ```

::: moniker-end

::: moniker range="vs-2017"

2. プロジェクトには、次のアセンブリ参照を追加します。

   - EnvDTE
   - Microsoft.VisualStudio.Shell.Framework

3. *DTETestProvider.cs*ファイルで、次の追加`using`ディレクティブ。

    ```csharp
    using EnvDTE;
    using Microsoft.VisualStudio.Shell;
    ```

4. `DTETestProvider`クラスは、インポート、<xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>します。

    ```csharp
    [Import]
    internal SVsServiceProvider ServiceProvider = null;
    ```

5. `GetClassifier()`メソッドの前に、次のコードを追加、`return`ステートメント。

    ```csharp
   DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));
   ```

::: moniker-end

## <a name="see-also"></a>関連項目

- [言語サービスとエディターの拡張ポイント](../extensibility/language-service-and-editor-extension-points.md)
- [DTE を使用して Visual Studio を起動します。](launch-visual-studio-dte.md)