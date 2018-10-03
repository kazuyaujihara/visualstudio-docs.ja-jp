---
title: Visual Studio のメニューとコマンド |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a1ed675-2bd1-4603-ba3a-f40dfb5cfb69
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b14648f27ea743ad74f3497571a0f2d9fa88b08e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47534350"
---
# <a name="menus-and-commands-for-visual-studio"></a>Visual Studio のメニューとコマンド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[Visual Studio のメニューとコマンド](https://docs.microsoft.com/visualstudio/extensibility/ux-guidelines/menus-and-commands-for-visual-studio)します。  
  
## <a name="command-usage"></a>コマンドの使用方法  
  
### <a name="overview"></a>概要  
 多くの個別の製品で構成されたスイートである、Microsoft Office とは異なりは、Visual Studio には、グローバルの Visual Studio IDE には、そのコマンド セットに各投稿ことの多くの製品が含まれています。 IDE では、コンテキストに基づいて、ユーザーが使用できる機能をフィルター処理によって何千ものコマンドの複雑さを管理します。  
  
 デザイン ウィンドウからコードの編集ウィンドウへの切り替えなど – ユーザーのコンテキストが変更された機能に関係のない場合、新しいコンテキストが表示されなくなります。 同時に、プロパティとツールボックスのオプションなど、関連の動的な情報と共に新しい機能の画面。 ユーザーでは、使用可能なコマンド セットのスワップすることはわかりません。 ユーザーは、気が散ってまたはコマンドが表示されるか消失して混乱を防ぐには、UI デザインによって、調整が必要な。 ユーザーの現在のコンテキストは常に示されます、1 つまたは複数の方法でなど、IDE のタイトル バー、プロパティ ウィンドウまたはプロパティ ページ ダイアログ ボックス。  
  
 コマンド バーの UI の柔軟性を確保します。 唯一のコマンドは、環境は、メイン メニューと、メイン コマンド バー両方カスタマイズおよびできるでも非表示にする Visual Studio に本質的な構造体します。 他のコマンド バーが表示され、アプリケーションの状態に基づいて表示されなくなります。 ツール ウィンドウおよびエディターのドキュメントでは、そのウィンドウの端の埋め込みツールバーも格納できます。  
  
#### <a name="basic-guidelines"></a>基本的なガイドライン  
  
##### <a name="use-existing-shared-commands-command-groups-and-menus-whenever-possible"></a>既存の共有コマンド、コマンド グループ、および可能な限りメニューを使用します。  
 コマンドは、コンテキストに基づいて通常表示、ため既存の共有メニューとコマンドのグループの使用により、コマンドの構造がコンテキストでの変更の間で比較的安定したこと。 共有のコマンドを再利用し、関連する共有コマンドの近くに新しいコマンドを配置することも IDE の複雑さを軽減しよりユーザー フレンドリなエクスペリエンスを作成します。 新しいコマンドを定義する場合は、既存の共有のコマンド グループに配置してみてください。 新しいグループを定義する場合は、配置関連のコマンド グループの近くに既存の共有 メニューで新しい最上位メニューを作成する前にします。  
  
##### <a name="do-not-create-icons-for-every-command"></a>すべてのコマンドのアイコンを作成しないでください。  
 コマンド アイコンを作成する前に慎重に検討します。 アイコンは、コマンドに対してのみ作成する必要があります。  
  
-   既定のツールバーに表示されます。  
  
-   ユーザーが経由のツールバーに追加する可能性が高い、**カスタマイズしています.** ダイアログ ボックス。  
  
-   別の Microsoft 製品で同じアクションに関連付けられたアイコンがあります。  
  
##### <a name="limit-the-addition-of-keyboard-shortcuts"></a>キーボード ショートカットの追加を制限します。  
 ユーザーの大半は、使用可能なすべてのショートカットのごく一部を使用します。 確かでない場合は、機能をキーボード ショートカットを連結しません。 ユーザーの作業では、新しいショートカットを追加する前にチームが発生します。  
  
##### <a name="give-commands-a-default-menu-placement"></a>既定のメニューの配置コマンドを提供します。  
 お客様のコマンドは他のユーザーがカスタマイズし、それらを適切に設計を認識します。 非表示のコマンドとしては、このようなものはありません。 Visual Studio のすべてのコマンドが表示されます、**ツール > カスタマイズ**ダイアログ ボックスで、コマンド ウィンドウ、オート コンプリート、**ツール > オプション > キーボード**ダイアログ、および開発ツール環境 (DTE)。 コマンドを与えるため、名前と、.ctc ファイル内のツールヒントをできるように、ユーザーが簡単に見つけることを確認します。  
  
##### <a name="do-not-duplicate-shared-commands-on-an-embedded-toolbar"></a>埋め込みツールバーの共有のコマンドと重複しません。  
 ユーザーのフォーカスの領域の近くにコマンドを配置すると便利です。 これを行う 1 つの方法では、エディター、ツール ウィンドウまたはドキュメントの上部にあるの埋め込みのツールバーを作成します。 ツールバーに配置するコマンドは、ウィンドウ内のコンテンツ領域に固有になります。 これらのツールバー上の共有のコマンドと重複しません。 たとえば、埋め込みのツールバーで [保存] アイコンを配置ことはありません。  
  
### <a name="content-and-command-visibility"></a>コンテンツとコマンドの可視性  
 コマンドは、次のスコープに存在します。**環境**、**階層**、および**ドキュメント**します。 コマンド配置の信頼性を確保するために各スコープを理解します。  
  
 コマンド、**環境**スコープは、プライマリ コンテキストを確立および複数のコンテキストの間で共有されます。 可視性またはドキュメントおよびツール ウィンドウの配置を変更します。 コマンド環境では、スコープは**新しいプロジェクト**、**サーバーへの接続**、**プロセスにアタッチ**、**切り取り**、 **コピー**、**貼り付け**、**検索**、**オプション**、**カスタマイズ**、**新しいウィンドウ**、および**ヘルプ表示**します。  
  
 コマンド、**階層**スコープなどの Visual Studio の階層を管理する**プロジェクト**、**チーム**、および**データ**します。 たとえば、プロジェクトのサブコンテキスト – に関連する**デバッグ**、**ビルド**、**テスト**、**アーキテクチャ**、または**分析**. スコープには、階層内のコマンド**新しい項目の追加**、**新しいクエリ**、**プロジェクト設定**、**新しいデータ ソースの追加**、 **パフォーマンス ウィザードを起動して**、および**新しいダイアグラム**します。  
  
 コマンド、**ドキュメント**コード、デザイン、または作業項目クエリ (wiq」を参照) などのドキュメントの内容に act をスコープします。 これらもツール ウィンドウの表示で機能や、そのツール ウィンドウに固有で、それ以外の場合。 ドキュメントのスコープのコマンドは、自体などの階層に固有であるファイル オブジェクトに対しても機能**プロジェクトから削除**します。 スコープには、ドキュメントでのコマンド**リファクタリング > の名前を変更**、**作業項目のコピーを作成する**、**すべて展開**、**すべて折りたたむ**と**ユーザー タスクの作成**です。  
  
### <a name="command-placement-decisions"></a>コマンド配置を決定  
 コマンドを作成することが決まっている、適切な位置とキーボード ショートカットを作成するかどうかを決定する必要があります。 コマンドを配置する場所を確立するためにこの意思決定パスに従います。  
  
 ![コマンド配置の意思決定グラフ](../../extensibility/ux-guidelines/media/0501-a-commandplacement.png "0501 a_CommandPlacement")  
  
 **Visual Studio でのコマンドを配置するための意思決定パス**  
  
### <a name="command-placement-in-menus"></a>メニュー コマンドの配置  
  
#### <a name="main-menu-bar"></a>メイン メニュー バー  
 メイン メニュー バーの UI に影響を与える特定のコンテキスト] メニューの [パッケージのコマンドの標準的な場所があります。 メイン メニュー バーは、環境はコマンドが表示されます。 コントロールを使用、その他のコマンドの構造とは異なります。 その他のすべてのコマンド バーだけのコンテキスト外にあるコマンドを無効にするかどうか、メニューまたはツールバーに配置されます。  
  
 環境では、IDE 全体とタスクの複数のドメイン間で共通しているメインのメニュー バーに組み込まれているコマンドのセットを定義します。 これらのコマンドは常に表示されるかに関係なくするは、Vspackage が環境に読み込まれます。 Vspackage では、このコマンドのセットを拡張できます、コマンド、コマンドの配置および各製品のセットは各チームの責任です。  
  
 Visual Studio のメイン メニューの構造は、次のメニュー カテゴリに分けることができます。  
  
##### <a name="core-menus"></a>Core メニュー  
  
-   ファイル  
  
-   編集  
  
-   表示  
  
-   ツール  
  
-   ウィンドウ  
  
-   ヘルプ  
  
##### <a name="project-specific-menus"></a>プロジェクト固有のメニュー  
  
-   プロジェクト  
  
-   ビルド  
  
-   デバッグ  
  
##### <a name="context-specific-menus"></a>特定のコンテキスト メニュー  
  
-   チーム  
  
-   データ  
  
-   テスト  
  
-   アーキテクチャ  
  
-   解析  
  
##### <a name="document-specific-menus"></a>ドキュメントに固有のメニュー  
  
-   形式  
  
-   テーブル  
  
##### <a name="when-designing-main-menus-adhere-to-these-rules"></a>メイン メニューを設計するときは、これらの規則に従います。  
  
-   特定のコンテキストで 25 の最上位の項目を超えない  
  
-   メニューは、600 ピクセルの高さを超えることはありません必要があります。  
  
-   Ultimate の SKU と一般的なプロファイルでなどの複数のコンテキストでのメイン メニューを評価します。  
  
-   フライアウト メニューを利用できます。  
  
-   フライアウト メニューには、少なくとも 3 つの項目とその 7 個を含める必要があります。  
  
-   フライアウト メニューが深いレベルの 1 つだけを移動する必要があります – 一部の Visual Studio メニュー項目がカスケード型のサブメニューがあるが、このパターンはお勧めできません。  
  
-   6 個の区切り記号を使用します。 グループは、次の図に従う必要があります。  
  
     ![メイン メニューのグループ化するためのガイドライン](../../extensibility/ux-guidelines/media/0501-b-mainmenus.png "0501 b_MainMenus")  
  
-   図に各グループ化する必要はありません、追加グループによって機能を追加することは制限されています。  
  
-   各グループは、2 ~ 7 つのメニュー項目が必要です。  
  
#### <a name="main-menu-ordering"></a>メイン メニューの順序付け  
 新しい最上位の項目を追加する前に、既存の最上位メニューで、コマンドを配置することを検討してください。 新しい最上位メニューを追加するときに必ず適切な場所に配置してください。 メニューは、プロジェクト、コンテキスト、またはドキュメントに特定するかどうかを決定します。 簡潔な最上位のメニューの名前を保持し、1 単語のみを使用します。  
  
 Core メニューには、ブックエンド コマンドの残りの部分が必要があります。 ファイル、編集、およびビューに常に左、およびツール ウィンドウには、ヘルプ、右に必ず.  
  
#### <a name="context-menus"></a>コンテキスト メニュー  
 習得が難しいインターフェイス内でのコンテキスト メニューが多すぎるの機能を配置することになります。 メイン メニュー バーから利用可能なすべての主要な機能があります。 コマンドの配置は、重複するコマンドを回避するために既存のコマンドと整合しない必要があります。 コンテキスト メニューは、シェルは、コンテキスト メニューで、ソリューション、プロジェクト ノード、またはプロジェクト項目はかどうかに応じて組み込む必要がある標準のメニュー グループを定義します。  
  
 コンテキスト メニューを設計する場合については、メイン メニューで、し、さらに、同じ規則に従います。  
  
-   25 のトップレベルのメニュー項目を超えないようにします。  
  
-   ポップアップ メニューが許容されますが、必要があります 1 階層を超えないように – カスケード フライアウトを使用しないでください。  
  
-   6 個の区切り記号を使用します。  
  
### <a name="command-placement-in-toolbars"></a>ツールバーのコマンドの配置  
  
#### <a name="general-toolbars"></a>[全般] ツールバー  
 ツールバーの配置の設計と、ときに、これらの標準に従います。  
  
-   ボタンの 1 つ以上の動詞を使用しないでください。 ボタンを 1 つ 1 つのアクションを = です。  
  
-   ラベルを強調する必要がある場合にのみ、アイコンの横のテキストを使用します。  
  
-   コンボ ボックスは 1 つのセッション内で複数回をプロパティにのみ使用します。 それ以外の場合、別の場所のプロパティを公開します。  
  
-   コンボ ボックスの幅は、ボックス + 30% 長い項目の幅を等しく必要があります。 たとえば、最長の項目が 200 ピクセルの場合は、コンボ ボックス 260 ピクセルがします。  
  
-   区切り記号の使用を制限します。 自体は、ドロップダウンの図形は、表示する区切り記号として機能するためアンチ パターンでは、ドロップダウン リストの横にある区切り記号の使用法が。  
  
-   6 つのアイコンに 3 つのアイコン グループを含める必要があります。  
  
-   修飾子は、複数の便利なコマンドの結果する場合、は、最後の設定を格納するための分割ボタンを使用します。  
  
     ![Visual Studio での分割ボタン](../../extensibility/ux-guidelines/media/0501-c-splitbuttons.png "0501 c_SplitButtons")  
  
     **分割ボタンの例です。左側の 6 つのコマンドは、1 つのボタンに代わりに適合できます。**  
  
#### <a name="product-specific-toolbars"></a>製品固有のツールバー  
 各製品には、初めて、製品をインストールした後、Visual Studio を起動を表示する必要がありますが含まれる頻繁に使用される既定ツールバーと重要なコマンドは、各製品の既定のツールバーを提供できます。  
  
 また、製品は、共有のコマンド グループと、IDE によって提供されるメニューを活用していることもする必要があります。 各共有コマンド グループは、ユーザーのわかりやすい方法で関連するコマンドを整理するためのものを共有 メニューに配置されます。 複雑さを軽減するためにこの共有のコマンドの構造を利用する重要です。  
  
#### <a name="global-toolbars"></a>グローバル ツールバー  
 グローバル ツールバーでは、ボックスから 1 つの行の右側に収めるに必要です。 新しいグローバル ツールバーを作成するときに、ツールバーの種類のガイドラインに従います。  
  
 **ツールバーの一般的なガイドライン:**  
  
-   各ツールバーには、コモン コントロール (グリッパー、オーバーフロー) で 24 ピクセルがあります。  
  
-   各ツール バー ボタンは、22 ピクセルの余白を含むワイドです。 分割ボタン、アイコンを行うには、11 もう 1 つのピクセルの幅が追加されます。  
  
-   ツールバーの間でのコマンドの重複は許可します。  
  
 **ドキュメントに固有のツールバー**特定のファイルの種類がアクティブなときに表示され、別のファイルの種類がアクティブになったときに表示されなくなります。  
  
-   ドキュメントに固有のツールバーには、複数の 12 個のボタンがありません。  
  
-   ツールバーの幅の合計は 300 ピクセルを超えないことがあります。  
  
-   ファイルの種類ごとには、1 つの埋め込みツールバーまたはドキュメント固有の 1 つのグローバル ツールバーの両方ではなくいずれかを持つことができます。  
  
 **コンテキスト固有のツールバー**表示時に特定のコンテキストに設定して、常にアクティブな期間を延長する傾向があります。  
  
-   コンテキストに固有のすべてのツールバーのボタンの制限には 18 です。  
  
-   コンテキストがアクティブな場合、ほとんどのユーザーはこのツール バー コマンドを採用一貫した方法はない場合、は、コンテキストを持つこのツールバー関連付けるはありませんから。  
  
-   コンテキストを終了するときに、ツールバーが消えることを確認します。 起動時にこれらのツールバーの [なし] が表示されます。  
  
 **ツールバーとコンテキストなしで**自動的に表示されることはありません。 これらは、のみと、ユーザーがアクティブにそれらを表示します。 最大の幅 200 ピクセル未満を保持します。  
  
### <a name="general-organization-and-shell-defined-groups"></a>一般的な組織とシェル定義のグループ  
 既存の共有コマンド、コマンド グループ、およびメニューを使用します。 新しいコマンドを定義する場合は、既存の共有のコマンド グループに配置してみてください。 新しいグループを定義する場合は、新しい最上位メニューを作成する前に、関連するコマンド グループの近くに既存の共有 メニューに配置してみてください。 これにより、IDE で一貫性のあるコマンドの配置を確保しながらコマンドの複雑さが軽減されます。  
  
 共有**形式**通常、デザイナー スタイルのドキュメント ウィンドウのコンテキストで表示] メニューの [が次の図に示します。  
  
 ![コールアウト付きの visual Studio の書式 メニュー](../../extensibility/ux-guidelines/media/0501-d-formatmenu.png "0501 d_FormatMenu")  
  
 **Visual Studio のメニュー グループ**  
  
### <a name="reducing-and-reusing-commands"></a>削減し、コマンドを再利用  
 コマンドは通常に基づいて表示コンテキストで任意の時点でユーザーに表示されるコマンドの数を減らすためにします。 ただし、既存の共有メニューが再利用する必要がありますも、コンテキストでの変更の間で安定したコマンドの構造が比較的が変更されることを確認するコマンド グループ。  
  
 共有のコマンドを再利用し、関連する共有コマンドの近くに新しいコマンドを配置することは、IDE の複雑さを軽減しよりユーザー フレンドリなエクスペリエンスを作成します。  
  
## <a name="naming-commands"></a>コマンドの名前を付ける  
  
### <a name="naming-conventions"></a>名前付け規則  
 ユーザーが検索して、コマンドラインを使用してまたはキーボード ショートカットへのバインドのいずれかのコマンドを実行できるように、一貫性のあるコマンドの名前を付けることが重要です。 コマンド名では、ユーザーがコマンド機能が表示されるカスケードまたはコンテキスト メニューまたはツールバーにある場合、どのような目的を理解するのにも役立ちます。  
  
#### <a name="when-naming-commands"></a>ときに名前を付けるコマンド。  
  
-   簡単にローカライズされるようにテキストを構築します。 詳細テキストのローカライズについては、次を参照してください。 [for Visual Studio の国際対応](http://msdn.microsoft.com/en-us/1cc35051-8126-441f-bea9-059245a47b1d)します。  
  
-   簡潔にします。 コマンドは、以下の 3 つの単語を使用する必要があります。  
  
-   タイトル文字の大文字と小文字を使用します。 各単語の最初の文字が大文字で入力する必要があります。 Visual Studio でのテキスト書式の詳細については、次を参照してください。[テキストのスタイル](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle)します。  
  
-   コマンドを配置する場所を考慮に入れる。 最上位のメニューまたはフライアウトのですか。 などとポップアップで、最上位レベルのコマンドの配置コマンドをグループ化する必要があります「配置」とフライアウトのコマンドする必要があります"Justify""Left""Right"、"Center、"なり具合です。 フライアウト コマンド「左揃え」または"Align Right です"という名前に重複します。  
  
     ![Visual Studio の書式 メニュー](../../extensibility/ux-guidelines/media/0502-a-formatmenu.png "0502 a_FormatMenu")  
  
### <a name="using-icons-with-commands"></a>コマンドとアイコンを使用します。  
 適度に使用するコマンドを使用してペアリングのアイコンを使用します。 そのコマンドを識別するために、ユーザーの能力を hastens コマンドを使用して、一意のイメージを関連付けること、イメージの使いすぎを簡潔化し、非効率性が発生します。 次の規則は、コマンドのアイコンを作成するかどうかを決定する際に役立ちます。  
  
#### <a name="use-an-icon-with-a-command-only-if"></a>コマンドの場合にのみでは、アイコンを使用します。  
  
-   同じコマンドでは、Microsoft Office アプリケーションのいずれかなど、著名な別の Microsoft 製品に関連付けられた、アイコンがあります。  
  
-   コマンドは、既定のツールバーに配置されます。  
  
-   コマンドはユーザーがツールバーを使用して、追加される可能性がある特別なコマンド、 **[カスタマイズ]** ダイアログ ボックス。  
  
## <a name="access-and-shortcut-keys"></a>アクセスし、ショートカット キー  
  
### <a name="overview"></a>概要  
 キーボードのキーの割り当ての 2 つの種類があります。  
  
-   **アクセス キー** (アクセラレータとも呼ばれます) キーボードによるアクセス許可する、メニューのコマンドを実行し、各ラベルに ダイアログ ボックスの UI。 アクセス キーは、アクセシビリティのためにほとんどの場合は、すべてのメニューとダイアログ ボックスのほとんどのコントロールに割り当てられている、記録する、現在のウィンドウのみに影響することはできません、およびローカライズをします。  
  
-   **ショートカット キー**コントロール (Ctrl) とファンクション (Fn) のキー シーケンスを使用して、ほとんどの場合。 生産性での高度なユーザーとヘルパーはよりデザインされます。 最もよく使用されるコマンドにのみ割り当てられているされ、メイン メニューをバイパスする間にクイック アクセスを許可します。 ショートカット キーは、記録して、プロファイル方式で一貫性のある割り当てなければなりません理由をします。 ショートカット キー スキームでは、プロファイルからを異なる場合があります。 ユーザーはを通じてキーのショートカットをカスタマイズ**ツール > オプション > キーボード**します。  
  
### <a name="assigning-access-keys"></a>アクセス キーの割り当てください。  
 アクセス キーは、Alt plus 英数字キーで構成されます。 例外なしには、各メニュー項目にアクセス キーを指定します。 Windows とアクセス キーを割り当てるための一般的な規則に従ってください。 たとえば、アクセス キーを**ファイル > 新規**は常に**alt キー、F、N**します。  
  
 小文字 ''l、'i' (大文字または小文字) でなどシングル ピクセル幅の文字を使用しないようにしを区別する困難なのでディセンダー (g、j、p、q、および y) を持つ文字は使用しないでください。  
  
 可能な場合、重複するキーを使用しないでください。 重複が避けられない場合は、メニュー システムは、キーを使用するすべてのコマンド間で循環して競合を処理します。 仮定の"Number"、"N"のアクセス キーに重複するファイル] メニューの [コマンドの例として**alt キー、F、N** 、新しいファイルを作成しますおよび**alt キーを押し、F、N、N**は"Number"コマンドを実行します。  
  
### <a name="assigning-shortcut-keys"></a>ショートカット キーの割り当てください。  
 すべてのコマンドの不必要な税システム (およびのユーザー メモリ) の場合、過剰ため、新しいショートカット キーの割り当てを回避します。 カスタマー エクスペリエンス向上プログラム (CEIP) からのデータは、Visual Studio のユーザーが統合されたショートカットのごく一部のみを使用することを示します。  
  
 ショートカットを定義するときに、これらの規則に従います。  
  
-   **制御 (Ctrl) とファンクション (Fn) のキー シーケンスを使用します。**  
  
-   **頻繁に使用されるショートカットが保持されます。** 最も一般的なショートカットを維持します。  
  
-   **エディターのショートカットを簡単に入力します。** 型へのショートカットを開発者がコードの書き込み中にほとんどを必要コマンドにバインドします。 たとえば、 **Edit.InvokeSmartTag** Ctrl などのクイック ショートカット キーが必要/cli に対する Alt + Shift + F10 のないとします。  
  
-   **一貫してテーマが適用されたショートカットに努めてください。**  
  
-   **どの修飾子キーを使用するかを判断する Windows のガイドラインに従います。** Ctrl キーの組み合わせを使用して、ドキュメント全体に適用されるコマンドなどの大規模な影響を与えるコマンド。 拡張または標準のショートカット キーの操作を補完するコマンドには、Shift キーの組み合わせを使用します。 Ctrl + alt キーの組み合わせを使用しないでください。  
  
-   **余分なショートカットを削除します。** レガシ機能がある場合は、アクセス キーが同じコマンドにすばやくアクセスを提供する場合は、極端な infrequency (よりも 10 倍 CEIP データからが少ない) または中程度 infrequency を (CEIP データから 100 回よりも少なくなります) で使用されるショートカットを削除することを検討してください。 例: alt キーを押し、H、C のヘルプ/コンテンツが開きます。  
  
 ショートカットの可用性をチェックする簡単な方法はありません。 ショートカットを追加する場合は、次の手順に従います。  
  
1.  一覧を確認[Visual Studio 2013 ショートカット](http://visualstudioshortcuts.com/2013/)を自分でグループ化のようなコマンドがあるかを確認します。  
  
2.  移動して**ツール > オプション > 環境 > キーボード**し、ショートカットをテストします。 「次の追加キーボード マップ スキームを適用します」で各キーボード マップ スキームが表示されるを確認します。 一意のショートカットを共有、全般、c#、VB、および C++ のプロファイルを確認してください。 ショートカットは、その場所のいずれかにマップされていない場合に使用できます。
