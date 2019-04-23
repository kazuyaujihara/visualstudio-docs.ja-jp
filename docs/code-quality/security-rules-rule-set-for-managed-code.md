---
title: マネージド コードの "セキュリティ規則" 規則セット
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 564aeac6-03fa-41b0-b655-88179f0ab01b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 45c51a6c5496686ef84b17341c97f00680a80bdd
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59366043"
---
# <a name="security-rules-rule-set-for-managed-code"></a>マネージド コードの "セキュリティ規則" 規則セット
Microsoft のセキュリティ規則ルールが報告される潜在的なセキュリティの問題の数を最大化するセットを含める必要があります。

|ルール|説明|
|----------|-----------------|
|[CA2100](../code-quality/ca2100-review-sql-queries-for-security-vulnerabilities.md)|SQL クエリのセキュリティ脆弱性を確認|
|[CA 2102](../code-quality/ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)|汎用ハンドラーの CLSCompliant でない例外をキャッチします|
|[CA 2103](../code-quality/ca2103-review-imperative-security.md)|命令型のセキュリティを確認します|
|[CA 2104](../code-quality/ca2104-do-not-declare-read-only-mutable-reference-types.md)|読み取り専用の変更可能な参照型を宣言しません|
|[CA 2105](../code-quality/ca2105-array-fields-should-not-be-read-only.md)|配列フィールドを読み取り専用にすることはできません|
|[CA 2106](../code-quality/ca2106-secure-asserts.md)|アサートをセキュリティで保護します|
|[CA2107](../code-quality/ca2107-review-deny-and-permit-only-usage.md)|拒否および許可のみの使用を確認します|
|[CA2108](../code-quality/ca2108-review-declarative-security-on-value-types.md)|値型での宣言セキュリティを確認します|
|[CA 2109](../code-quality/ca2109-review-visible-event-handlers.md)|表示するイベント ハンドラーを確認します|
|[CA2111](../code-quality/ca2111-pointers-should-not-be-visible.md)|ポインターは参照可能にすることはできません|
|[CA2112](../code-quality/ca2112-secured-types-should-not-expose-fields.md)|セキュリティで保護された型はフィールドを公開してはなりません|
|[CA2114](../code-quality/ca2114-method-security-should-be-a-superset-of-type.md)|メソッド セキュリティは型のスーパーセットでなければなりません|
|[CA 2115](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)|ネイティブ リソースを使用しているときには GC.KeepAlive を呼び出します|
|[CA2116](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)|APTCA メソッドは APTCA メソッドのみを呼び出すことができます|
|[CA2117](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)|APTCA 型は APTCA 基本型のみを拡張することができます|
|[CA2118](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md)|SuppressUnmanagedCodeSecurityAttribute の使用法を確認してください|
|[CA 2119](../code-quality/ca2119-seal-methods-that-satisfy-private-interfaces.md)|プライベート インターフェイスを満たすメソッドをシールします|
|[CA2120](../code-quality/ca2120-secure-serialization-constructors.md)|シリアル化コンストラクターをセキュリティで保護します|
|[CA 2121](../code-quality/ca2121-static-constructors-should-be-private.md)|静的コンストラクターはプライベートでなければなりません|
|[CA2122](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)|リンク要求を含むメソッドを間接的に公開しません|
|[CA2123](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)|オーバーライドのリンク要求はベースと同一でなければなりません|
|[CA2124](../code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)|脆弱性のある finally 句を外側の try でラップします|
|[CA2126](../code-quality/ca2126-type-link-demands-require-inheritance-demands.md)|型のリンク要求には継承要求が必要です|
|[CA 2130](../code-quality/ca2130-security-critical-constants-should-be-transparent.md)|セキュリティ上重要な定数は透過的である必要がある|
|[CA2131](../code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)|セキュリティ上重要な型は型等価性に参加してはならない|
|[CA2132](../code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)|既定のコンストラクターは、基本型の既定コンストラクターと同程度以上、重要であることが必要|
|[CA2133](../code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)|デリゲートは透過性の整合がとれたメソッドにバインドする必要がある|
|[CA2134](../code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)|メソッドは、基本メソッドをオーバーライドしている場合、透過性の整合性を保つ必要がある|
|[CA2135](../code-quality/ca2135-level-2-assemblies-should-not-contain-linkdemands.md)|レベル 2 のアセンブリは LinkDemand を含んではならない|
|[CA2136](../code-quality/ca2136-members-should-not-have-conflicting-transparency-annotations.md)|メンバーには、透過性注釈の競合があってはならない|
|[CA2137](../code-quality/ca2137-transparent-methods-must-contain-only-verifiable-il.md)|透過的メソッドは、検証可能な IL のみを含まなければならない|
|[CA2138](../code-quality/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)|透過的メソッドは、SuppressUnmanagedCodeSecurity 属性を持つメソッドを呼び出してはならない|
|[CA2139](../code-quality/ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute.md)|透過的メソッドは、HandleProcessCorruptingExceptions 属性を使用してはならない|
|[CA2140](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|透過的コードは、セキュリティ上重要な項目を参照してはならない|
|[CA2141](../code-quality/ca2141-transparent-methods-must-not-satisfy-linkdemands.md)|透過的メソッドは、Linkdemand を満たしていませんする必要があります。|
|[CA 2142](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)|透過的コードは、LinkDemand を使用して保護されてはならない|
|[CA 2143](../code-quality/ca2143-transparent-methods-should-not-use-security-demands.md)|透過的メソッドは、セキュリティ確認要求を使用してはならない|
|[CA 2144](../code-quality/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays.md)|透過的コードは、バイト配列からアセンブリを読み込んではならない|
|[CA2145](../code-quality/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute.md)|透過的メソッドを SuppressUnmanagedCodeSecurityAttribute で修飾してはならない|
|[CA2146](../code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)|型は、基本型およびインターフェイスと同程度以上、重要でなければならない|
|[CA2147](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|透過コードは、セキュリティ アサートを使用してはならない|
|[CA2149](../code-quality/ca2149-transparent-methods-must-not-call-into-native-code.md)|透過的メソッドは、ネイティブ コード内に呼び出しを行ってはならない|
|[CA 2210](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md)|アセンブリには有効な厳密な名前が必要です|
|[CA2300](ca2300-do-not-use-insecure-deserializer-binaryformatter.md)|安全ではないデシリアライザー BinaryFormatter を使用しないでください|
|[CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)|最初に BinaryFormatter.Binder を設定しないで BinaryFormatter.Deserialize を呼び出さないでください|
|[CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)|BinaryFormatter.Deserialize を呼び出す前に BinaryFormatter.Binder が設定されていることを確認します|
|[CA3001](../code-quality/ca3001-review-code-for-sql-injection-vulnerabilities.md)|SQL インジェクションの脆弱性のコード レビュー|
|[CA3002](../code-quality/ca3002-review-code-for-xss-vulnerabilities.md)|XSS の脆弱性のコード レビュー|
|[CA3003](../code-quality/ca3003-review-code-for-file-path-injection-vulnerabilities.md)|ファイル パス インジェクションの脆弱性のコード レビュー|
|[CA3004](../code-quality/ca3004-review-code-for-information-disclosure-vulnerabilities.md)|情報漏えいの脆弱性のコード レビュー|
|[CA3005](../code-quality/ca3005-review-code-for-ldap-injection-vulnerabilities.md)|LDAP インジェクションの脆弱性のコード レビュー|
|[CA3006](../code-quality/ca3006-review-code-for-process-command-injection-vulnerabilities.md)|プロセス コマンド インジェクションの脆弱性のコード レビュー|
|[CA3007](../code-quality/ca3007-review-code-for-open-redirect-vulnerabilities.md)|オープン リダイレクトの脆弱性のコード レビュー|
|[CA3008](../code-quality/ca3008-review-code-for-xpath-injection-vulnerabilities.md)|XPath インジェクションの脆弱性のコード レビュー|
|[CA3009](../code-quality/ca3009-review-code-for-xml-injection-vulnerabilities.md)|XML インジェクションの脆弱性のコード レビュー|
|[CA3010](../code-quality/ca3010-review-code-for-xaml-injection-vulnerabilities.md)|XAML インジェクションの脆弱性のコード レビュー|
|[CA3011](../code-quality/ca3011-review-code-for-dll-injection-vulnerabilities.md)|DLL インジェクションの脆弱性のコード レビュー|
|[CA3012](../code-quality/ca3012-review-code-for-regex-injection-vulnerabilities.md)|RegEx インジェクションの脆弱性のコード レビュー|
