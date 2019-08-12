---
title: CA2106:アサートをセキュリティで保護します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: df19d31abe88c6d12bafc933ba740badb832eb16
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921069"
---
# <a name="ca2106-secure-asserts"></a>CA2106:アサートをセキュリティで保護します

|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|Category|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
メソッドは、アクセス許可をアサートし、呼び出し元に対してセキュリティチェックを実行しません。

## <a name="rule-description"></a>規則の説明
セキュリティ チェックを実行せずにセキュリティ アクセス許可をアサートすると、悪用される可能性があるセキュリティの弱点がコード内に残る場合があります。 セキュリティのアクセス許可がアサートされると、セキュリティスタックウォークが停止します。 呼び出し元に対してチェックを実行せずにアクセス許可をアサートすると、呼び出し元はアクセス許可を使用して間接的にコードを実行できます。 アサートを有害な方法で使用できない場合は、セキュリティチェックなしのアサートが許容されます。 呼び出したコードが無害である場合、またはユーザーが呼び出したコードに任意の情報を渡すことができない場合、アサートは無害です。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、メソッドまたはその宣言する型にセキュリティ要求を追加します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
セキュリティに関する注意事項を慎重に確認した後にのみ、この規則からの警告を非表示にします。

## <a name="see-also"></a>関連項目

- <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>
- [安全なコーディングのガイドライン](/dotnet/standard/security/secure-coding-guidelines)