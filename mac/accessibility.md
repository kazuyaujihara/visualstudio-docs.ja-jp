---
title: ユーザー補助
description: この記事では、Visual Studio for Mac でのユーザー補助機能と、それを有効にする方法について説明します。
author: conceptdev
ms.author: crdun
ms.date: 04/17/2019
ms.assetid: 2C4AAC2E-3B4A-4496-8BE0-1F5A7F81D1CA
ms.openlocfilehash: 0ee6ffc7bd1567a86bc361f55e00c52ccecddd61
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67824444"
---
# <a name="accessibility"></a>ユーザー補助

Visual Studio for Mac には以下のユーザー補助機能があるため、障碍のある方でも、これまで以上に使いやすくなっています。

- Solution Pad とエディター パッドでのテキストの拡大
- エディター内のテキスト サイズ オプション
- エディター内の色のカスタマイズ
- キーボード ナビゲーション
- ショートカットのカスタマイズ
- メソッドおよびパラメーターのコード補完機能

Apple は、これらの機能に加え、VoiceOver や Dictation など、特別なニーズがあるユーザーを支援するツールをいくつか提供しています。

macOS のユーザー補助機能の詳細については、[Apple 社の Web サイト](https://www.apple.com/accessibility/mac/)をご覧ください。

## <a name="enabling-macos-assistive-technologies-in-visual-studio-for-mac"></a>Visual Studio for Mac で macOS 支援技術を有効にする

Visual Studio for Mac の macOS 支援技術のサポートは、既定ではオフです。 有効にするには、次の手順を実行します。

1. **[Visual Studio] (メニュー) > [ユーザー設定] > [その他] > [アクセシビリティ]** の順に移動します

2. **[アクセシビリティの有効化]** チェックボックスをオンにします。

   ![ユーザー設定のアクセシビリティ チェックボックス](media/accessibility-preferences.png)

3. **[Visual Studio を再起動]** ボタンを選択して Visual Studio を再起動し、アップルの支援技術のサポートを有効にします。

## <a name="how-to-use-keyboard-navigation"></a>方法: キーボード ナビゲーションを使用する

キーボード ナビゲーションのサポートは macOS に組み込まれていますが、最も包括的なエクスペリエンスを実現するには、macOS を設定して **[すべてのコントロール]** を設定する必要があります。

![システム設定のキーボードのすべてのコントロール](media/accessibility-preferences-keyboard.png)

**[Full Keyboard Access]\(フル キーボード アクセス\)** を **[All controls]\(すべてのコントロール\)** に設定すると、ウィンドウまたはダイアログ内のすべてのコントロール間を移動できます。 以下のようにして、コントロールを選択できます。

- Tab キーで次のコントロールに進む
- Shift キーを押しながら Tab キーを押して前のコントロールに戻る
- 方向キーでコントロールの間を矢印の方向に移動する
- Ctrl キーを押しながら Tab キーを押して、テキスト領域ボックスから外に移動する
- スペース バーを押すと、現在フォーカスがあるコントロールがアクティブになります。

## <a name="how-to-enable-and-use-voiceover"></a>方法: VoiceOver を有効にして使用する

VoiceOver を有効または無効にするには、 **&#8984; + F5** キーを押します。

VoiceOver コマンドは、このガイドでは **VO+ *キー*** と表示されています。**VO** は **VoiceOver Utility** アプリケーションで設定されている修飾子を表します。 既定の修飾子は **Ctrl + Alt** です。たとえば、VoiceOver 修飾子によっては、**VO + M** は **Ctrl + Alt + M** を意味します。簡潔にするために、カーソルキーは**左**や**右**などと示されます。

Visual Studio for Mac のユーザー インターフェイスを操作するには、次のキーの組み合わせを使用します。

- **VO + 右/左**:ユーザー インターフェイス要素間を移動する
  - VoiceOver ではラベルとコントロールの種類が読み上げられ、その操作方法が説明されます。
- **VO + Shift + 下/上**:要素にステップ イン/アウトする
  - 要素内に入ると、**VO +左/右** キーを使用してその要素内を移動できます。
- **VO + Space**:コントロールを選択/操作する
- **VO + M**:Visual Studio for Mac メニュー バーを操作する

VoiceOver の使用の詳細とコマンドの包括的なリストについては、以下のガイドを参照してください。

- [Apple VoiceOver 入門ガイド](https://support.apple.com/en-us/guide/voiceover-guide/welcome/web)
- [macOS の VoiceOver コマンド](http://lab.dotjay.com/notes/voiceover-commands/)

## <a name="see-also"></a>関連項目

- [Visual Studio のユーザー補助機能 (Windows)](/visualstudio/ide/reference/accessibility-features-of-visual-studio)
