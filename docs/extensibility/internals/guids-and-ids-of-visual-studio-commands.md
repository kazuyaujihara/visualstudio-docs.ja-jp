---
title: Visual Studio コマンドの Guid と Id |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands
- id
- command placement
- visual studio command
- guid
ms.assetid: 2ea4bee2-0259-4675-8e65-2023b312b516
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f7670eacc875bf7c5437d9bb92cc1932753093bd
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73186643"
---
# <a name="guids-and-ids-of-visual-studio-commands"></a>Visual Studio コマンドの Guid と Id
Visual Studio 統合開発環境 (IDE) に含まれるコマンドの GUID と ID の値は、Visual Studio SDK の一部としてインストールされる、vsct ファイルで定義されています。 詳細については、「 [IDE で定義されたコマンド、メニュー、およびグループ](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)」を参照してください。

 *Vsct*ファイルで定義されている IDE オブジェクトを操作する方法の詳細については、「[メニューとコマンドの拡張](../../extensibility/extending-menus-and-commands.md)」を参照してください。

## <a name="find-a-command-definition"></a>コマンド定義の検索
 Visual Studio では、1000を超えるコマンドが定義されているため、ここですべてを一覧表示するのは現実的ではありません。 代わりに、次の手順に従ってコマンドの定義を検索します。

### <a name="to-locate-a-command-definition"></a>コマンド定義を検索するには

1. Visual Studio で、 *< Visual STUDIO SDK のインストールパス\>\VisualStudioIntegration\Common\Inc\\* フォルダーにある次のファイルを開きます。 *vsct*、 *shellcmddef. vsct*、 *vsdbgcmdused。 vsct*、 *[ベンダー]。 vsct*。

    ほとんどの Visual Studio コマンドは、 *Sharedcmddef. vsct*および*shellcmddef. vsct*で定義されています。 *Vsdbgcmdused。 vsct*は、デバッガーに関連するコマンドと、[] を定義し*ます。 Vsct*は、Web 開発に固有のコマンドを定義します。

2. コマンドがメニュー項目の場合は、メニュー項目のテキストを正確に確認します。 コマンドがツールバーのボタンである場合は、一時停止したときに表示されるツールヒントのテキストを確認します。

3. **Ctrl**+**F**キーを押して、 **[検索]** ダイアログボックスを開きます。

4. [**検索**する文字列] ボックスに、手順2でメモしたテキストを入力します。

5. すべての**開い**ているドキュメントが **[検索対象]** ボックスに表示されていることを確認します。

6. [ボタン要素](../../extensibility/button-element.md)の `<Strings>` セクションでテキストが選択されるまで、 **[次を検索]** ボタンをクリックします。

    コマンドが表示される `<Button>` 要素は、コマンド定義です。

   コマンドの定義が見つかったら、コマンドと同じ `guid` と `id` の値を持つ[Commandplacement 要素](../../extensibility/commandplacement-element.md)を作成することによって、コマンドのコピーを別のメニューまたはツールバーに配置できます。 詳細については、「[再利用可能なボタンのグループの作成](../../extensibility/creating-reusable-groups-of-buttons.md)」を参照してください。

### <a name="special-cases"></a>特殊なケース
 次の場合、メニューテキストまたはツールヒントのテキストが、コマンド定義の内容と正確に一致しない可能性があります。

- **[ファイル]** メニューの **[印刷]** コマンドなど、下線付きの文字を含むメニュー項目。 *P*は下線付きで表示されます。

     メニュー項目名のアンパサンド (&) 文字の前にある文字は、下線付きで表示されます。 ただし、vsct ファイルは XML で記述されて*います。* XML では、アンパサンド (&) 文字を使用して特殊文字を指定し、表示されるアンパサンドを *&amp;amp;* としてスペル入力する必要があります。 したがって、 *vsct*ファイルでは、 **Print**コマンドは *&amp;amp; として表示されます。印刷*。

- [\<の現在のファイル名\>の**保存**] などの動的なテキストを含むコマンドと、動的に生成されたメニュー項目 ( **[最近使ったファイル]** の一覧の項目など)。

     動的テキストを検索するための信頼性の高い方法はありません。 代わりに、visual [studio のメニューの guid と id](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) 、または[visual studio のツールバーの guid と](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)id を参照して、目的のコマンドをホストするグループを検索し、そのグループの ID を検索します。 コマンド定義にグループが[親要素](../../extensibility/parent-element.md)として含まれていない場合は、の親を設定する `<CommandPlacement>` 要素に対して、 *sharedcmdplace Vsct*と*Shellcmdplace* (または*vsdbgcmdplace* ) vsct を検索します。メニュー. *Sharedcmdplace。 vsct*、 *Shellcmdplace*、および*vsdbgcmdplace*は、 *\<Visual Studio SDK のインストールパス\>\VisualStudioIntegration\Common\Inc\\* フォルダーにあります。

## <a name="see-also"></a>関連項目

- [Visual Studio コマンドテーブル (vsct) ファイル](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [VSCT XML スキーマリファレンス](../../extensibility/vsct-xml-schema-reference.md)
