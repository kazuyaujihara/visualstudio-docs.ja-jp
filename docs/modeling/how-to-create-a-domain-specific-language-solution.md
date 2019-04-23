---
title: '方法: ドメイン固有言語ソリューションを作成する'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.designerwizard
helpviewer_keywords:
- Domain-Specific Language Tools, walkthroughs
- walkthroughs [Domain-Specific Language Tools], creating domain-specific language
- Domain-Specific Language Tools, creating solutions
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9b1799ac2e7124f79d10dcc8860a994e2f182ea7
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60051350"
---
# <a name="how-to-create-a-domain-specific-language-solution"></a>方法: ドメイン固有言語ソリューションを作成する
ドメイン固有言語 (DSL) を作成するには、特殊な Visual Studio ソリューションを使用します。

## <a name="prerequisites"></a>必須コンポーネント

この手順を開始する前に、これらのコンポーネントをインストールします。

- Visual Studio
- Visual Studio SDK (の一部としてインストールされている、 **Visual Studio 拡張機能の開発**ワークロード)
- Modeling SDK (Visual Studio のコンポーネントとしてインストールされます)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="creating-a-domain-specific-language-solution"></a>ドメイン固有言語ソリューションを作成します。

1. 新たに作成して DSL ウィザードを起動**ドメイン固有言語デザイナー**プロジェクト。

   > [!NOTE]
   > 可能であれば、プロジェクトの選択した名前が有効な Visual をする必要がありますC#識別子のため、コードを生成するために使用可能性があります。

   ::: moniker range="vs-2017"

   ![DSL ダイアログの作成](../modeling/media/create_dsldialog.png)

   ::: moniker-end

2. DSL テンプレートを選択します。

    **ドメイン固有言語のオプションの選択**などソリューション テンプレートのいずれかの選択 ページで、**最小言語**します。 DSL を作成する次のようなテンプレートを選択します。

    ソリューション テンプレートの詳細については、次を参照してください。[ドメイン固有言語ソリューション テンプレートの選択](../modeling/choosing-a-domain-specific-language-solution-template.md)します。

3. ファイル名拡張子を入力、**ファイル拡張子**ページ。 自分のコンピューターで一意である必要がありする任意のコンピューターでは、DSL をインストールします。 メッセージが表示する必要があります**アプリケーションまたは Visual Studio エディターにこの拡張機能使用しない**します。

   - 完全にインストールされていない以前の実験的な Dsl で、ファイル名拡張子を使用した場合ことができますをオフにすることを使用して、**実験用インスタンスをリセット**ツールで、Visual Studio SDK メニューで見つかります。

   - このファイルの拡張機能を使用する別の Visual Studio Extension がコンピューターに完全にインストールされている場合は、アンインストールを検討してください。 **ツール** メニューをクリックして **拡張機能マネージャー** をクリックします。

4. 検査、および必要に応じて調整、ウィザードの残りのページのフィールド。 設定に満足したら、クリックして**完了**します。 設定の詳細については、次を参照してください。 [DSL デザイナーのウィザード ページ](#settings)します。

    ウィザードの名前は 2 つのプロジェクトを含むソリューションを作成します**Dsl**と**DslPackage**します。

   > [!NOTE]
   >  信頼されていないソースからのテキスト テンプレートを実行するには、をクリックしないを通知するメッセージが表示された場合**OK**します。 このメッセージが再び表示されるように設定できます。

## <a name="settings"></a> DSL デザイナーのウィザード ページ
 既定値から変更されていないフィールドのいくつかのままにすることができます。 ただし、ファイル拡張子のフィールドを設定することを確認します。

### <a name="solution-settings-page"></a>ソリューションの設定 ページ
 **どのテンプレート、ドメイン固有言語を基になるか?**
DSL を作成する次のようなテンプレートを選択します。 別のテンプレートは、便利な開始ポイントを提供します。 ソリューション テンプレートを選択すると、ウィザードには、説明が表示されます。 ソリューション テンプレートの詳細については、次を参照してください。[ドメイン固有言語ソリューション テンプレートの選択](../modeling/choosing-a-domain-specific-language-solution-template.md)します。

 **ドメイン固有言語の名前にしますか。**
既定値は、ソリューション名です。 コードは、この値から生成されます。 C# クラス名として有効な場合があります。

### <a name="file-extension-page"></a>ファイル拡張子 ページ
 **どのような拡張機能がモデル ファイルが使用しますか。**
新しいファイル拡張子を入力します。

 このファイルの拡張機能が既に登録されていないこと、このコンピューターで使用する次のように確認します。

 下を見て**他のツールやアプリケーションは、この拡張機能を処理するために登録されている**します。 メッセージが表示された場合**アプリケーションまたは Visual Studio エディターにこの拡張機能使用しない**、このファイルの拡張機能を使用することができます。

 ツールまたはパッケージの一覧を表示する場合は、次のいずれかを実行する必要があります。

- 別のファイル拡張子を入力します。

     \- または -

- Visual Studio の実験用インスタンスをリセットします。 これは、すべてが以前にビルドされた Dsl の登録解除します。 **開始** メニューのをクリックして**すべてのプログラム**、 **Microsoft Visual Studio 2010 SDK**、**ツール**、し**リセット、Microsoft Visual Studio 2010 実験用インスタンス**します。 もう一度使用するその他の任意の Dsl を再構築することができます。

     \- または -

- このファイルの拡張機能を使用して、Visual Studio 拡張機能がコンピューターに完全にインストールされている場合をアンインストールします。 **ツール** メニューをクリックして **拡張機能マネージャー** をクリックします。

### <a name="product-settings-page"></a>製品の設定 ページ
 **新しいドメイン固有言語が含まれている製品の名前は何ですか。**
既定値は、DSL の名前です。

 この値は、このファイル拡張子を持つファイルを記述する、Windows エクスプ ローラー (またはファイル エクスプ ローラー) で使用されます。

 **製品が属している会社の名前は何ですか。**
会社名。

 この値は DSL パッケージの AssemblyInfo プロパティに組み込まれます。

 **このソリューションでプロジェクトのルート名前空間とは何ですか。**
これは、会社から構成される名前と製品名を既定値です。

### <a name="signing-page"></a>[署名] ページ
 **厳密な名前キー ファイルを作成**既定オプションは、DSL のアセンブリの署名に新しいキーを作成します。

 **既存の厳密な名前キーを使用して、** 別のアセンブリと DSL を統合する場合は、このオプションを使用します。

 厳密な名前付けの詳細については、次を参照してください。[の作成と using strong-named Assemblies](http://go.microsoft.com/fwlink/?LinkId=186073)します。

## <a name="see-also"></a>関連項目

- [方法: ドメイン固有言語を定義する](../modeling/how-to-define-a-domain-specific-language.md)
- [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
