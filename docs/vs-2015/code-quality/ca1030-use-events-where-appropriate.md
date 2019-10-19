---
title: 'CA1030: 適切な場所にイベントを使用します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseEventsWhereAppropriate
- CA1030
helpviewer_keywords:
- CA1030
- UseEventsWhereAppropriate
ms.assetid: ea051367-deeb-40f9-9b65-eb818f1e133a
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 7ab3a576b5014799e470260567a4942b5c3ef9de
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661920"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030: 適切な場所にイベントを使用します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 パブリック、プロテクト、またはプライベートメソッドの名前は、次のいずれかで始まります。

- アドオン

- RemoveOn

- 起動

- 発生

## <a name="rule-description"></a>規則の説明
 この規則では、通常はイベントに使用される名前を持つメソッドを検出します。 イベントは、オブザーバーまたはパブリッシュ/サブスクライブデザインパターンに従います。これらは、あるオブジェクトの状態の変更を他のオブジェクトに伝達する必要があるときに使用されます。 明確に定義された状態変更に応答してメソッドが呼び出された場合、メソッドはイベントハンドラーによって呼び出される必要があります。 メソッドを呼び出すオブジェクトは、メソッドを直接呼び出すのではなく、イベントを発生させる必要があります。

 イベントの一般的な例としては、ボタンのクリックなどのユーザー操作によってコードのセグメントが実行されるユーザーインターフェイスアプリケーションがあります。 @No__t_0 イベントモデルは、ユーザーインターフェイスに限定されません。状態の変更を1つ以上のオブジェクトに伝達する必要があるすべての場所で使用する必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 オブジェクトの状態が変化したときにメソッドが呼び出された場合は、[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] イベントモデルを使用するようにデザインを変更することを検討してください。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 メソッドが [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] イベントモデルで動作しない場合は、このルールからの警告を非表示にします。
