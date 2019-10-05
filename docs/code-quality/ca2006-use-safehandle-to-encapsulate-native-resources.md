---
title: CA2006:SafeHandle を使用して、ネイティブ リソースを要約します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2006
- UseSafeHandleToEncapsulateNativeResources
helpviewer_keywords:
- UseSafeHandleToEncapsulateNativeResources
- CA2006
ms.assetid: a71950bd-bcc1-463d-b1f2-5233bc451456
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 0e671deab060346bb998932495e5590f19945eaa
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233102"
---
# <a name="ca2006-use-safehandle-to-encapsulate-native-resources"></a>CA2006:SafeHandle を使用して、ネイティブ リソースを要約します

|||
|-|-|
|TypeName|UseSafeHandleToEncapsulateNativeResources|
|CheckId|CA2006|
|カテゴリ|Microsoft.Reliability|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

マネージコードは<xref:System.IntPtr> 、を使用してネイティブリソースにアクセスします。

## <a name="rule-description"></a>規則の説明

マネージコード`IntPtr`でを使用すると、セキュリティと信頼性の問題が発生する可能性があります。 または類似`IntPtr`のテクノロジを使用<xref:System.Runtime.InteropServices.SafeHandle>するかどうかを判断するには、の使用をすべて確認する必要があります。 が、マネージコードが`IntPtr`所有していると見なされるネイティブリソース (メモリ、ファイルハンドル、ソケットなど) を表している場合に、問題が発生します。 マネージコードがリソースを所有している場合は、それに関連付けられているネイティブリソースも解放する必要があります。これに失敗すると、リソースが漏えいする可能性があるためです。

このようなシナリオでは、に対し`IntPtr`てマルチスレッドアクセスが許可されていて、 `IntPtr`によって表されるリソースを解放する方法が提供されている場合にも、セキュリティや信頼性の問題が発生します。 これらの問題には、 `IntPtr`リソースの解放時に値がリサイクルされ、他のスレッドでもリソースが同時に使用されることがあります。 これにより、あるスレッドが間違ったリソースに関連付けられたデータの読み取りまたは書き込みを行うことができる競合状態が発生する可能性があります。 たとえば、型がとして`IntPtr` OS ハンドルを格納し、ユーザーが**Close**とそのハンドルを同時に使用するその他のメソッドを同時に呼び出し、何らかの同期を行わない場合、コードにハンドルリサイクルの問題があります。

このハンドルリサイクル問題は、データの破損や、多くの場合、セキュリティの脆弱性を引き起こす可能性があります。 `SafeHandle`とその兄弟クラス<xref:System.Runtime.InteropServices.CriticalHandle>は、リソースへのネイティブハンドルをカプセル化して、そのようなスレッド処理の問題を回避できるようにするメカニズムを提供します。 また、とその兄弟`SafeHandle`クラス`CriticalHandle`を使用して、他のスレッド処理の問題に対応することもできます。たとえば、ネイティブメソッドの呼び出しに対するネイティブハンドルのコピーを含むマネージオブジェクトの有効期間を、厳密に制御することができます。 このような状況では、多くの場合`GC.KeepAlive`、への呼び出しを削除できます。 およびを使用`SafeHandle`する場合に発生するパフォーマンスのオーバーヘッドは、より低い`CriticalHandle`レベルにすると、多くの場合、慎重な設計によって減らすことができます。

## <a name="how-to-fix-violations"></a>違反の修正方法

使用`IntPtr`法を`SafeHandle`に変換し、ネイティブリソースへのアクセスを安全に管理します。 例に<xref:System.Runtime.InteropServices.SafeHandle>ついては、リファレンス記事を参照してください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この警告を抑制しないでください。

## <a name="see-also"></a>関連項目

- <xref:System.IDisposable>