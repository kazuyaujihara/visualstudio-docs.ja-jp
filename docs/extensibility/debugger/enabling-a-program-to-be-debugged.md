---
title: デバッグするプログラムを有効にする |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], enabling for programs
ms.assetid: 61d24820-0cd9-48b6-8674-6813f7493237
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1f301de66421ef1327b86d900305cb4ecbfb5623
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56695129"
---
# <a name="enable-a-program-to-be-debugged"></a>デバッグするプログラムを有効にします。
(DE)、デバッグ エンジンでは、プログラムをデバッグする前にする必要があります最初を起動する、DE か、既存のプログラムにアタッチします。

## <a name="in-this-section"></a>このセクションの内容
 [ポートの取得](../../extensibility/debugger/getting-a-port.md)をデバッグするプログラムを有効にする最初の手順として、ポートを取得する方法について説明します。

 [プログラムを登録](../../extensibility/debugger/registering-the-program.md)デバッグするプログラムを有効にするのには、次の手順について説明します。 ポートに登録します。 プログラムをデバッグできる登録されると、アタッチまたは・ イン タイム (JIT) デバッグのプロセスによっていずれか。

 [プログラムにアタッチ](../../extensibility/debugger/attaching-to-the-program.md)次の手順について説明します。 プログラムにデバッガーをアタッチします。

 [起動ベースのアタッチ](../../extensibility/debugger/launch-based-attachment.md)プログラムは、起動すると、SDM によって自動的に起動ベースの添付ファイルについて説明します。

 [必要なイベントを送信](../../extensibility/debugger/sending-the-required-events.md)手順について説明するデバッグ エンジン (DE) を作成するときに必要なイベントと、プログラムにアタッチします。

## <a name="related-sections"></a>関連項目
 [カスタム デバッグ エンジンを作成する](../../extensibility/debugger/creating-a-custom-debug-engine.md)デバッグ エンジン (DE) を定義し、DE インターフェイスとさまざまな操作モード間の遷移にデバッガーが発生する方法を使用して実装するサービスについて説明します。