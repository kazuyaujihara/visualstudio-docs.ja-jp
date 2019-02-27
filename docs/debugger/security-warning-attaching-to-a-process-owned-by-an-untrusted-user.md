---
title: 'セキュリティ警告: 信頼されていないユーザーが所有するプロセスにアタッチするには危険が伴います。 次の情報に関して疑わしい、または不明ながこのプロセスにアタッチされません |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.attachsecuritywarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 52246c1e-a371-40a0-b756-a435cc51876f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0f44c429dad42a0a46fe2c00f9b6a82dfcdb92b8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56687251"
---
# <a name="security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process"></a>セキュリティ警告: 信頼されていないユーザーが所有するプロセスにアタッチするには危険が伴います。 以下の情報に関して疑わしい点がある場合や、不明な場合は、このプロセスにアタッチしないでください。
この警告ダイアログ ボックスは、部分的に信頼されているコードを含むプロセスや、信頼関係のないユーザーが所有するプロセスにアタッチしようとすると表示されます。 悪意のあるコードを含む信頼関係のないプロセスによって、デバッグを実行しているコンピューターに障害が発生する可能性があります。 何らかの理由によりプロセスを信頼していない場合は、**[キャンセル]** をクリックしてデバッグを回避します。

 正当なシナリオをデバッグするときに、この警告を非表示に、Visual Studio を閉じるし、このレジストリ キーの値を 1 に設定: `HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\<version>\Debugger\DisableAttachSecurityWarning`、し、Visual Studio を再起動します。 シナリオのデバッグが終わったら、値を 0 にリセットし、Visual Studio を再起動します。

 "信頼できるユーザー" には、ユーザー自身と、.NET Framework がインストールされているコンピューターで一般に定義される標準ユーザーのグループ (`aspnet`、`localsystem`、`networkservice`、`localservice` など) が含まれます。

## <a name="uielement-list"></a>UIElement の一覧
 デバッグが要求されたアセンブリの名前

 ユーザーの現在のユーザー

 アタッチしてデバッグを続行するには、キーを押してをアタッチします。

 プロセスに接続しないでアタッチしません。

## <a name="see-also"></a>参照
- [実行中のプロセスへのアタッチ](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)
- [デバッガーのセキュリティ](../debugger/debugger-security.md)