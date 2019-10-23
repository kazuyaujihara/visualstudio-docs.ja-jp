---
title: 'CA2006: SafeHandle を使用してネイティブリソースをカプセル化する |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2006
- UseSafeHandleToEncapsulateNativeResources
helpviewer_keywords:
- UseSafeHandleToEncapsulateNativeResources
- CA2006
ms.assetid: a71950bd-bcc1-463d-b1f2-5233bc451456
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 394fafb0c9185a5e11ba759a5b873236956cf25b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652208"
---
# <a name="ca2006-use-safehandle-to-encapsulate-native-resources"></a>CA2006: SafeHandle を使用して、ネイティブ リソースを要約します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseSafeHandleToEncapsulateNativeResources|
|CheckId|CA2006|
|カテゴリ|Microsoft.Reliability|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 マネージコードでは、<xref:System.IntPtr> を使用してネイティブリソースにアクセスします。

## <a name="rule-description"></a>規則の説明
 マネージコードで `IntPtr` を使用すると、セキュリティと信頼性の問題が発生する可能性があります。 @No__t_0 のすべての使用を確認して、<xref:System.Runtime.InteropServices.SafeHandle> または同様のテクノロジを使用するかどうかを判断する必要があります。 @No__t_0 が、マネージコードが所有していると見なされるネイティブリソース (メモリ、ファイルハンドル、ソケットなど) を表していると、問題が発生します。 マネージコードがリソースを所有している場合は、それに関連付けられているネイティブリソースも解放する必要があります。これに失敗すると、リソースが漏えいする可能性があるためです。

 このようなシナリオでは、`IntPtr` に対してマルチスレッドアクセスが許可され、`IntPtr` によって表されるリソースを解放する方法が提供されている場合にも、セキュリティや信頼性の問題が発生します。 これらの問題には、リソースの解放時の `IntPtr` 値のリサイクル、およびリソースの同時使用が別のスレッドで行われていることが含まれます。 これにより、あるスレッドが間違ったリソースに関連付けられたデータの読み取りまたは書き込みを行うことができる競合状態が発生する可能性があります。 たとえば、型が OS ハンドルを `IntPtr` として格納し、ユーザーが**Close**とそのハンドルを使用するその他のメソッドの両方を同時に呼び出し、何らかの同期なしで呼び出すことができる場合、コードにハンドルリサイクルの問題があります。

 このハンドルリサイクル問題は、データの破損や、多くの場合、セキュリティの脆弱性を引き起こす可能性があります。 `SafeHandle` とその兄弟クラス <xref:System.Runtime.InteropServices.CriticalHandle> は、このようなスレッド処理の問題を回避できるように、リソースへのネイティブハンドルをカプセル化するメカニズムを提供します。 さらに、`SafeHandle` とその兄弟クラス `CriticalHandle` を使用して他のスレッド処理の問題を解決することもできます。たとえば、ネイティブメソッドの呼び出しに対するネイティブハンドルのコピーを含むマネージオブジェクトの有効期間を慎重に制御することができます。 このような状況では、多くの場合、`GC.KeepAlive` の呼び出しを削除できます。 @No__t_0 を使用する場合に発生するパフォーマンスのオーバーヘッドと、より低い `CriticalHandle` になるほど、多くの場合、慎重な設計によって減らすことができます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 @No__t_0 使用法を `SafeHandle` に変換して、ネイティブリソースへのアクセスを安全に管理します。 例については、<xref:System.Runtime.InteropServices.SafeHandle> リファレンスのトピックを参照してください。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この警告を抑制しないでください。

## <a name="see-also"></a>参照
 <xref:System.IDisposable>
