---
title: FxCop 規則のポートの状態
ms.date: 05/21/2019
ms.topic: reference
helpviewer_keywords:
- fxcop rules
- fxcop analyzers, ported rules
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: d6d891001bbb46e01049c2c8d71bb25372bb8c29
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551061"
---
# <a name="fxcop-rule-port-status"></a>Fxcop 規則のポートの状態

以前に Visual Studio で静的コード分析を使用したことがある場合は、現在の実装で[FxCop アナライザー](install-fxcop-analyzers.md)として使用できる規則を考えているかもしれません。 このページには、移植されている規則と、移植されていない規則、およびそれらを移植する計画があるかどうかが一覧表示されます。

## <a name="ported-rules"></a>移植された規則

Roslyn-アナライザーリポジトリの自動生成された[ドキュメントページ](https://github.com/dotnet/roslyn-analyzers/blob/master/src/Microsoft.CodeAnalysis.FxCopAnalyzers/Microsoft.CodeAnalysis.FxCopAnalyzers.md)には、FxCop アナライザーに移植されたルールの最新の一覧が含まれています。 このページには、規則が既定で有効になっているかどうかや、関連付けられている*コード修正プログラム*があるかどうかなどの追加情報も含まれています。 ([コード修正](../ide/quick-actions.md)は、Visual Studio の電球アイコンメニューで使用できるワンクリック修正です)。

このページの日付のとき、 [fxcop アナライザー](install-fxcop-analyzers.md)に移植された fxcop 規則の一覧には次のものが含まれます。

ルール ID | Title
--------|---------
[CA1000](ca1000-do-not-declare-static-members-on-generic-types.md) | ジェネリック型の静的メンバーを宣言しません
[CA1001](ca1001-types-that-own-disposable-fields-should-be-disposable.md) | 破棄可能なフィールドを所有する型は、破棄可能でなければなりません
[CA1003](ca1003-use-generic-event-handler-instances.md) | 汎用イベント ハンドラーのインスタンスを使用します
[CA1008](ca1008-enums-should-have-zero-value.md) | Enums は 0 値を含んでいなければなりません
[CA1010](ca1010-collections-should-implement-generic-interface.md) | コレクションは、ジェネリック インターフェイスを実装しなければなりません
[CA1012](ca1012-abstract-types-should-not-have-constructors.md) | 抽象型にはコンストラクターを含めません
[CA1014](ca1014-mark-assemblies-with-clscompliantattribute.md) | アセンブリを CLSCompliant にマークします
[CA1016](ca1016-mark-assemblies-with-assemblyversionattribute.md) | アセンブリのバージョンをアセンブリにマークする
[CA1017](ca1017-mark-assemblies-with-comvisibleattribute.md) | アセンブリに ComVisible を設定します
[CA1018](ca1018-mark-attributes-with-attributeusageattribute.md) | 属性を AttributeUsageAttribute に設定します
[CA1019](ca1019-define-accessors-for-attribute-arguments.md) | 属性引数にアクセサーを定義します
[CA1024](ca1024-use-properties-where-appropriate.md) | 適切な場所にプロパティを使用します
[CA1027](ca1027-mark-enums-with-flagsattribute.md) | 列挙型を FlagsAttribute に設定します
[CA1028](ca1028-enum-storage-should-be-int32.md) | 列挙ストレージは Int32 でなければなりません
[CA1030](ca1030-use-events-where-appropriate.md) | 適切な場所にイベントを使用します
[CA1031](ca1031-do-not-catch-general-exception-types.md) | 一般的な例外の種類はキャッチしません
[CA1032](ca1032-implement-standard-exception-constructors.md) | 標準例外コンストラクターを実装します
[CA1033](ca1033-interface-methods-should-be-callable-by-child-types.md) | インターフェイス メソッドは、子型によって呼び出し可能でなければなりません
[CA1034](ca1034-nested-types-should-not-be-visible.md) | 入れ子にされた型を参照可能にすることはできません
[CA1036](ca1036-override-methods-on-comparable-types.md) | 比較可能な型でメソッドをオーバーライドします
[CA1040](ca1040-avoid-empty-interfaces.md) | 空のインターフェイスは使用しません
[CA1041](ca1041-provide-obsoleteattribute-message.md) | ObsoleteAttribute メッセージを指定します
[CA1043](ca1043-use-integral-or-string-argument-for-indexers.md) | インデクサーに整数または文字列引数を使用する
[CA1044](ca1044-properties-should-not-be-write-only.md) | プロパティを書き込み専用にすることはできません
[CA1050](ca1050-declare-types-in-namespaces.md) | 名前空間で型を宣言します
[CA1051](ca1051-do-not-declare-visible-instance-fields.md) | 参照可能なインスタンス フィールドを宣言しません
[CA1052](ca1052-static-holder-types-should-be-sealed.md) | 静的ホルダー型は static または NotInheritable である必要があります
[CA1053](ca1053-static-holder-types-should-not-have-constructors.md) | 静的ホルダー型にコンストラクターを含めることはできません (CA1053 は FxCop アナライザーの[CA1052](ca1052-static-holder-types-should-be-sealed.md)に含まれています)
[CA1054](ca1054-uri-parameters-should-not-be-strings.md) | Uri パラメーターを文字列にすることはできません
[CA1055](ca1055-uri-return-values-should-not-be-strings.md) | Uri 戻り値を文字列にすることはできません
[CA1056](ca1056-uri-properties-should-not-be-strings.md) | Uri プロパティを文字列にすることはできません
[CA1058](ca1058-types-should-not-extend-certain-base-types.md) | 型は、一定の基本型を拡張することはできません
[CA1060](ca1060-move-p-invokes-to-nativemethods-class.md) | Pinvokes をネイティブメソッドクラスに移動する
[CA1061](ca1061-do-not-hide-base-class-methods.md) | 基底クラス メソッドを非表示にしません
[CA1062](ca1062-validate-arguments-of-public-methods.md) | パブリック メソッドの引数の検証
[CA1063](ca1063-implement-idisposable-correctly.md) | IDisposable を正しく実装する
[CA1064](ca1064-exceptions-should-be-public.md) | 例外は public として設定する必要があります
[CA1065](ca1065-do-not-raise-exceptions-in-unexpected-locations.md) | 予期しない場所に例外を発生させません
CA1066 | 型{0}は Equals を\<オーバーライドするため、IEquatable T > を実装する必要があります
CA1067 | IEquatable\<T > を実装するときに、object.equals (object) をオーバーライドします
CA1068 | CancellationToken パラメーターは最後に指定する必要があります
CA1200 | プレフィックスで cref タグを使用しない
[CA1303](ca1303-do-not-pass-literals-as-localized-parameters.md) | ローカライズされるパラメーターとしてリテラルを渡さない
[CA1304](ca1304-specify-cultureinfo.md) | CultureInfo を指定します
[CA1305](ca1305-specify-iformatprovider.md) | IFormatProvider を指定します
[CA1307](ca1307-specify-stringcomparison.md) | StringComparison の指定
[CA1308](ca1308-normalize-strings-to-uppercase.md) | 文字列を大文字に標準化します
[CA1309](ca1309-use-ordinal-stringcomparison.md) | 序数の文字列比較を使用する
[CA1401](ca1401-p-invokes-should-not-be-visible.md) | P/Invoke は参照可能であることはできません
[CA1501](ca1501-avoid-excessive-inheritance.md) | 継承を使用しすぎないでください
[CA1502](ca1502-avoid-excessive-complexity.md) | メソッドの実装を複雑にしすぎないでください
[CA1505](ca1505-avoid-unmaintainable-code.md) | メンテナンスできないコードを使用しないでください
[CA1506](ca1506-avoid-excessive-class-coupling.md) | クラス結合度を大きくしすぎないでください
[CA1507](ca1507.md) | シンボル名を表すために名前を使用する
CA1508 | デッド条件コードを回避する
CA1509 | コードメトリックスルール指定ファイルのエントリが無効です
[CA1707](ca1707-identifiers-should-not-contain-underscores.md) | 識別子はアンダースコアを含むことはできません
[CA1708](ca1708-identifiers-should-differ-by-more-than-case.md) | 識別子は、大文字と小文字の区別以外にも相違していなければなりません
[CA1710](ca1710-identifiers-should-have-correct-suffix.md) | 識別子は、正しいサフィックスを含んでいなければなりません
[CA1711](ca1711-identifiers-should-not-have-incorrect-suffix.md) | 識別子は、不適切なサフィックスを含むことはできません
[CA1712](ca1712-do-not-prefix-enum-values-with-type-name.md) | 列挙型値を型名のプレフィックスにしません
[CA1714](ca1714-flags-enums-should-have-plural-names.md) | フラグ列挙型は、複数形の名前を含んでいなければなりません
[CA1715](ca1715-identifiers-should-have-correct-prefix.md) | 識別子は正しいプレフィックスを含んでいなければなりません
[CA1716](ca1716-identifiers-should-not-match-keywords.md) | 識別子はキーワードと同一にすることはできません
[CA1717](ca1717-only-flagsattribute-enums-should-have-plural-names.md) | FlagsAttribute 列挙型のみが複数形の名前を含んでいなければなりません
[CA1720](ca1720-identifiers-should-not-contain-type-names.md) | 識別子に型名が含まれています
[CA1721](ca1721-property-names-should-not-match-get-methods.md) | プロパティ名は get メソッドと同一にすることはできません
[CA1724](ca1724-type-names-should-not-match-namespaces.md) | 型名を名前空間と一致させることはできません
[CA1725](ca1725-parameter-names-should-match-base-declaration.md) | パラメーター名は基本宣言と同一でなければなりません
[CA1801](ca1801-review-unused-parameters.md) | 使用されていないパラメーターの確認
[CA1802](ca1802-use-literals-where-appropriate.md) | 適切な場所にリテラルを使用する
[CA1806](ca1806-do-not-ignore-method-results.md) | メソッドの結果を無視しない
[CA1810](ca1810-initialize-reference-type-static-fields-inline.md) | 参照型の静的フィールドをインラインで初期化します
[CA1812](ca1812-avoid-uninstantiated-internal-classes.md) | インスタンス化されていない内部クラスを使用しません
[CA1813](ca1813-avoid-unsealed-attributes.md) | アンシールド属性を使用しません
[CA1814](ca1814-prefer-jagged-arrays-over-multidimensional.md) | 複数次元の配列ではなくジャグ配列を使用します
[CA1815](ca1815-override-equals-and-operator-equals-on-value-types.md) | equals および operator equals を値型でオーバーライドします
[CA1816](ca1816-call-gc-suppressfinalize-correctly.md) | Dispose メソッドは Gc.suppressfinalize を呼び出す必要があります
[CA1819](ca1819-properties-should-not-return-arrays.md) | プロパティは、配列を返すことはできません
[CA1820](ca1820-test-for-empty-strings-using-string-length.md) | 文字列の長さを使用して空の文字列をテストします
[CA1821](ca1821-remove-empty-finalizers.md) | 空のファイナライザーの削除
[CA1822](ca1822-mark-members-as-static.md) | メンバーを static に設定します
[CA1823](ca1823-avoid-unused-private-fields.md) | 使用されていないプライベート フィールドを使用しません
[CA1824](ca1824-mark-assemblies-with-neutralresourceslanguageattribute.md) | アセンブリを NeutralResourcesLanguageAttribute に設定します
CA1825 | 長さ0の配列を割り当てないようにします。
CA1826 | インデックス可能なコレクションでは、列挙可能なメソッドを使用しないでください。 代わりに、コレクションを直接使用します。
[CA2000](ca2000-dispose-objects-before-losing-scope.md) | スコープを失う前にオブジェクトを破棄
[CA2002](ca2002-do-not-lock-on-objects-with-weak-identity.md) | 弱い ID を伴うオブジェクト上でロックしません
[CA2007](ca2007-do-not-directly-await-task.md) | 待機中のタスクで ConfigureAwait を呼び出すことを検討してください
CA2008 | TaskScheduler を渡さずにタスクを作成しない
CA2009 | ImmutableCollection 値に対して ToImmutableCollection を呼び出さないでください
CA2010 | PreserveSigAttribute でマークされたメソッドによって返される値を常に使用する
[CA2100](ca2100-review-sql-queries-for-security-vulnerabilities.md) | SQL クエリのセキュリティ脆弱性を確認
[CA2101](ca2101-specify-marshaling-for-p-invoke-string-arguments.md) | P/Invoke 文字列引数に対してマーシャリングを指定します
[CA2119](ca2119-seal-methods-that-satisfy-private-interfaces.md) | プライベート インターフェイスを満たすメソッドをシールします
[CA2153](ca2153-avoid-handling-corrupted-state-exceptions.md) | 破損状態の例外をキャッチしない
[CA2200](ca2200-rethrow-to-preserve-stack-details.md) | スタックの詳細を保持するために再スローします。
[CA2201](ca2201-do-not-raise-reserved-exception-types.md) | 予約された例外の種類を発生させません
[CA2207](ca2207-initialize-value-type-static-fields-inline.md) | 値型のスタティック フィールドのインラインを初期化します
[CA2208](ca2208-instantiate-argument-exceptions-correctly.md) | 引数の例外を正しくインスタンス化します
[CA2211](ca2211-non-constant-fields-should-not-be-visible.md) | 非定数フィールドは表示されません
[CA2213](ca2213-disposable-fields-should-be-disposed.md) | 破棄可能なフィールドは破棄されなければなりません
[CA2214](ca2214-do-not-call-overridable-methods-in-constructors.md) | コンストラクターのオーバーライド可能なメソッドを呼び出しません
[CA2216](ca2216-disposable-types-should-declare-finalizer.md) | 破棄可能な型はファイナライザーを宣言しなければなりません
[CA2217](ca2217-do-not-mark-enums-with-flagsattribute.md) | 列挙型を FlagsAttribute に設定しません
[CA2218](ca2218-override-gethashcode-on-overriding-equals.md) | オーバーライドする Equals で GetHashCode をオーバーライドします
[CA2219](ca2219-do-not-raise-exceptions-in-exception-clauses.md) | Finally 句で例外を発生させない
[CA2224](ca2224-override-equals-on-overloading-operator-equals.md) | オーバーロードする演算子 equals で Equals をオーバーライドします
[CA2225](ca2225-operator-overloads-have-named-alternates.md) | 演算子オーバーロードには名前付けされた代替が存在します
[CA2226](ca2226-operators-should-have-symmetrical-overloads.md) | 演算子は対称型オーバーロードを含まなければなりません
[CA2227](ca2227-collection-properties-should-be-read-only.md) | Collection プロパティは読み取り専用でなければなりません
[CA2229](ca2229-implement-serialization-constructors.md) | シリアル化コンストラクターを実装します
[CA2231](ca2231-overload-operator-equals-on-overriding-valuetype-equals.md) | 値型 Equals のオーバーライドで、演算子 equals をオーバーロードします
[CA2234](ca2234-pass-system-uri-objects-instead-of-strings.md) | 文字列ではなくシステム uri オブジェクトを渡す
[CA2235](ca2235-mark-all-non-serializable-fields.md) | すべてのシリアル化不可能なフィールドを設定します
[CA2237](ca2237-mark-iserializable-types-with-serializableattribute.md) | ISerializable 型を Serializable に設定します
[CA2241](ca2241-provide-correct-arguments-to-formatting-methods.md) | 書式設定メソッドに正しい引数を提供
[CA2242](ca2242-test-for-nan-correctly.md) | NaN に対して正しくテストします
[CA2243](ca2243-attribute-string-literals-should-parse-correctly.md) | 属性文字列リテラルは、正しく解析する必要があります
CA2244 | インデックス付き要素の初期化を複製しない
[CA2300](ca2300-do-not-use-insecure-deserializer-binaryformatter.md) | 安全ではないデシリアライザー BinaryFormatter を使用しないでください
[CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) | 最初に BinaryFormatter.Binder を設定しないで BinaryFormatter.Deserialize を呼び出さないでください
[CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md) | BinaryFormatter.Deserialize を呼び出す前に BinaryFormatter.Binder が設定されていることを確認します
[CA2305](ca2305-do-not-use-insecure-deserializer-losformatter.md) | 安全ではないデシリアライザー LosFormatter を使用しないでください
[CA2310](ca2310-do-not-use-insecure-deserializer-netdatacontractserializer.md) | 安全ではないデシリアライザー NetDataContractSerializer を使用しないでください
[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) | 最初に NetDataContractSerializer.Binder を設定しないで逆シリアル化しないでください
[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md) | NetDataContractSerializer.Binder を設定してから逆シリアル化してください
[CA2315](ca2315-do-not-use-insecure-deserializer-objectstateformatter.md) | 安全ではないデシリアライザー ObjectStateFormatter を使用しないでください
[CA2321](ca2321.md) | SimpleTypeResolver を使って JavaScriptSerializer で逆シリアル化しないでください
[CA2322](ca2322.md) | 逆シリアル化する前に JavaScriptSerializer が SimpleTypeResolver によって初期化されていないことを確認してください
[CA3001](ca3001-review-code-for-sql-injection-vulnerabilities.md) | SQL インジェクションの脆弱性のコード レビュー
[CA3002](ca3002-review-code-for-xss-vulnerabilities.md) | XSS の脆弱性のコード レビュー
[CA3003](ca3003-review-code-for-file-path-injection-vulnerabilities.md) | ファイル パス インジェクションの脆弱性のコード レビュー
[CA3004](ca3004-review-code-for-information-disclosure-vulnerabilities.md) | 情報漏えいの脆弱性のコード レビュー
[CA3005](ca3005-review-code-for-ldap-injection-vulnerabilities.md) | LDAP インジェクションの脆弱性のコード レビュー
[CA3006](ca3006-review-code-for-process-command-injection-vulnerabilities.md) | プロセス コマンド インジェクションの脆弱性のコード レビュー
[CA3007](ca3007-review-code-for-open-redirect-vulnerabilities.md) | オープン リダイレクトの脆弱性のコード レビュー
[CA3008](ca3008-review-code-for-xpath-injection-vulnerabilities.md) | XPath インジェクションの脆弱性のコード レビュー
[CA3009](ca3009-review-code-for-xml-injection-vulnerabilities.md) | XML インジェクションの脆弱性のコード レビュー
[CA3010](ca3010-review-code-for-xaml-injection-vulnerabilities.md) | XAML インジェクションの脆弱性のコード レビュー
[CA3011](ca3011-review-code-for-dll-injection-vulnerabilities.md) | DLL インジェクションの脆弱性のコード レビュー
[CA3012](ca3012-review-code-for-regex-injection-vulnerabilities.md) | RegEx インジェクションの脆弱性のコード レビュー
CA3061 | URL でスキーマを追加しない
[CA3075](ca3075-insecure-dtd-processing.md) | XML での DTD 処理が安全ではありません
[CA3076](ca3076-insecure-xslt-script-execution.md) | 安全ではない XSLT スクリプトの処理。
[CA3077](ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader.md) | API 設計、XmlDocument、XmlTextReader で安全ではない処理
[CA3147](ca3147-mark-verb-handlers-with-validateantiforgerytoken.md) | アンチ偽造トークンを検証する動詞ハンドラーをマークします
[CA5350](ca5350-do-not-use-weak-cryptographic-algorithms.md) | 脆弱な暗号アルゴリズムを使用しないでください
[CA5351](ca5351-do-not-use-broken-cryptographic-algorithms.md) | 破損した暗号アルゴリズムを使用しない
CA5358 | Unsafe 暗号モードを使用しない
CA5359 | 証明書の検証を無効にしない
CA5360 | 逆シリアル化で危険なメソッドを呼び出さないでください
CA5361 | 強力な暗号の SChannel 使用を無効にしない
CA5362 | Serializable クラスの Self を参照しない
CA5363 | 要求の検証を無効にしない
CA5364 | 非推奨のセキュリティプロトコルを使用しない
CA5365 | HTTP ヘッダーチェックを無効にしない
CA5366 | DataSet に XmlReader を使用する Xml の読み取り
CA5367 | ポインターフィールドを持つ型をシリアル化しない
CA5368 | ページから派生したクラスの ViewStateUserKey を設定する
CA5369 | 逆シリアル化に XmlReader を使用する
CA5370 | 読み取りの検証に XmlReader を使用する
CA5371 | スキーマ読み取りに XmlReader を使用する
CA5372 | Xpath ドキュメントに XmlReader を使用する
CA5373 | 廃止されたキー派生関数を使用しない
CA5374 | XslTransform を使用しない
CA5375 | アカウントを使用しない Shared Access Signature
CA5376 | SharedAccessProtocol HttpsOnly を使用する
CA5377 | コンテナーレベルのアクセスポリシーを使用する
CA5378 | ServicePointManagerSecurityProtocols を無効にしません
CA5379 | 弱いキー派生関数アルゴリズムを使用しない
CA9999 | アナライザーのバージョンが一致しません

## <a name="unported-rules"></a>アン移植規則

[FxCop アナライザー](install-fxcop-analyzers.md)に移植されていないルールのセットは、まだ[移植さ](#rules-that-may-be-ported)れていないものの、非推奨で、[移植](#deprecated-rules)されていないルールで構成されます。

### <a name="rules-that-may-be-ported"></a>移植される可能性がある規則

次の FxCop レガシ分析規則は、まだアナライザーとして実装されていませんが、の場合もあります。 これは、技術的な理由がブロックされているか、ルールの優先度が低いことが原因である可能性があります。 各ルールの移植状態の詳細については、 **[問題の追跡]** 列のリンクをクリックしてください。

ルール ID | 問題の追跡
--- | ---
[CA1002](ca1002-do-not-expose-generic-lists.md) | [https://github.com/dotnet/roslyn-analyzers/issues/369](https://github.com/dotnet/roslyn-analyzers/issues/369)
[CA1004](ca1004-generic-methods-should-provide-type-parameter.md) | [https://github.com/dotnet/roslyn-analyzers/issues/370](https://github.com/dotnet/roslyn-analyzers/issues/370)
[CA1005](ca1005-avoid-excessive-parameters-on-generic-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/371](https://github.com/dotnet/roslyn-analyzers/issues/371)
[CA1006](ca1006-do-not-nest-generic-types-in-member-signatures.md) | [https://github.com/dotnet/roslyn-analyzers/issues/372](https://github.com/dotnet/roslyn-analyzers/issues/372)
[CA1007](ca1007-use-generics-where-appropriate.md) | [https://github.com/dotnet/roslyn-analyzers/issues/373](https://github.com/dotnet/roslyn-analyzers/issues/373)
[CA1011](ca1011-consider-passing-base-types-as-parameters.md) | [https://github.com/dotnet/roslyn-analyzers/issues/375](https://github.com/dotnet/roslyn-analyzers/issues/375)
[CA1021](ca1021-avoid-out-parameters.md) | [https://github.com/dotnet/roslyn-analyzers/issues/377](https://github.com/dotnet/roslyn-analyzers/issues/377)
[CA1023](ca1023-indexers-should-not-be-multidimensional.md) | [https://github.com/dotnet/roslyn-analyzers/issues/378](https://github.com/dotnet/roslyn-analyzers/issues/378)
[CA1045](ca1045-do-not-pass-types-by-reference.md) | [https://github.com/dotnet/roslyn-analyzers/issues/391](https://github.com/dotnet/roslyn-analyzers/issues/391)
[CA1046](ca1046-do-not-overload-operator-equals-on-reference-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/392](https://github.com/dotnet/roslyn-analyzers/issues/392)
[CA1047: SEALED](ca1047-do-not-declare-protected-members-in-sealed-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/393](https://github.com/dotnet/roslyn-analyzers/issues/393)
[CA1048: SEALED](ca1048-do-not-declare-virtual-members-in-sealed-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/394](https://github.com/dotnet/roslyn-analyzers/issues/394)
[CA1049](ca1049-types-that-own-native-resources-should-be-disposable.md) | [https://github.com/dotnet/roslyn-analyzers/issues/395](https://github.com/dotnet/roslyn-analyzers/issues/395)
[CA1057](ca1057-string-uri-overloads-call-system-uri-overloads.md) | [https://github.com/dotnet/roslyn-analyzers/issues/401](https://github.com/dotnet/roslyn-analyzers/issues/401)
[CA1300](ca1300-specify-messageboxoptions.md) | [https://github.com/dotnet/roslyn-analyzers/issues/408](https://github.com/dotnet/roslyn-analyzers/issues/408)
[CA1301](ca1301-avoid-duplicate-accelerators.md) | [https://github.com/dotnet/roslyn-analyzers/issues/409](https://github.com/dotnet/roslyn-analyzers/issues/409)
[CA1306](ca1306-set-locale-for-data-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/414](https://github.com/dotnet/roslyn-analyzers/issues/414)
[CA1402](ca1402-avoid-overloads-in-com-visible-interfaces.md) | [https://github.com/dotnet/roslyn-analyzers/issues/418](https://github.com/dotnet/roslyn-analyzers/issues/418)
[CA1403](ca1403-auto-layout-types-should-not-be-com-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/419](https://github.com/dotnet/roslyn-analyzers/issues/419)
[CA1404](ca1404-call-getlasterror-immediately-after-p-invoke.md) | [https://github.com/dotnet/roslyn-analyzers/issues/420](https://github.com/dotnet/roslyn-analyzers/issues/420)
[CA1405](ca1405-com-visible-type-base-types-should-be-com-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/421](https://github.com/dotnet/roslyn-analyzers/issues/421)
[CA1407](ca1407-avoid-static-members-in-com-visible-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/423](https://github.com/dotnet/roslyn-analyzers/issues/423)
[CA1408](ca1408-do-not-use-autodual-classinterfacetype.md) | [https://github.com/dotnet/roslyn-analyzers/issues/424](https://github.com/dotnet/roslyn-analyzers/issues/424)
[CA1409](ca1409-com-visible-types-should-be-creatable.md) | [https://github.com/dotnet/roslyn-analyzers/issues/425](https://github.com/dotnet/roslyn-analyzers/issues/425)
[CA1410](ca1410-com-registration-methods-should-be-matched.md) | [https://github.com/dotnet/roslyn-analyzers/issues/426](https://github.com/dotnet/roslyn-analyzers/issues/426)
[CA1411](ca1411-com-registration-methods-should-not-be-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/427](https://github.com/dotnet/roslyn-analyzers/issues/427)
[CA1412](ca1412-mark-comsource-interfaces-as-idispatch.md) | [https://github.com/dotnet/roslyn-analyzers/issues/428](https://github.com/dotnet/roslyn-analyzers/issues/428)
[CA1413](ca1413-avoid-non-public-fields-in-com-visible-value-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/429](https://github.com/dotnet/roslyn-analyzers/issues/429)
[CA1414](ca1414-mark-boolean-p-invoke-arguments-with-marshalas.md) | [https://github.com/dotnet/roslyn-analyzers/issues/430](https://github.com/dotnet/roslyn-analyzers/issues/430)
[CA1415](ca1415-declare-p-invokes-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/431](https://github.com/dotnet/roslyn-analyzers/issues/431)
[CA1500](ca1500-variable-names-should-not-match-field-names.md) | [https://github.com/dotnet/roslyn-analyzers/issues/432](https://github.com/dotnet/roslyn-analyzers/issues/432)
[CA1600](ca1600-do-not-use-idle-process-priority.md) | [https://github.com/dotnet/roslyn-analyzers/issues/438](https://github.com/dotnet/roslyn-analyzers/issues/438)
[CA1601](ca1601-do-not-use-timers-that-prevent-power-state-changes.md) | [https://github.com/dotnet/roslyn-analyzers/issues/439](https://github.com/dotnet/roslyn-analyzers/issues/439)
[CA1700](ca1700-do-not-name-enum-values-reserved.md) | [https://github.com/dotnet/roslyn-analyzers/issues/440](https://github.com/dotnet/roslyn-analyzers/issues/440)
[CA1704](ca1704-identifiers-should-be-spelled-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/443](https://github.com/dotnet/roslyn-analyzers/issues/443)
[CA1709](ca1709-identifiers-should-be-cased-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/445](https://github.com/dotnet/roslyn-analyzers/issues/445)
[CA1713](ca1713-events-should-not-have-before-or-after-prefix.md) | [https://github.com/dotnet/roslyn-analyzers/issues/449](https://github.com/dotnet/roslyn-analyzers/issues/449)
[CA1719](ca1719-parameter-names-should-not-match-member-names.md) | [https://github.com/dotnet/roslyn-analyzers/issues/453](https://github.com/dotnet/roslyn-analyzers/issues/453)
[CA1722](ca1722-identifiers-should-not-have-incorrect-prefix.md) | [https://github.com/dotnet/roslyn-analyzers/issues/455](https://github.com/dotnet/roslyn-analyzers/issues/455)
[CA1726](ca1726-use-preferred-terms.md) | [https://github.com/dotnet/roslyn-analyzers/issues/458](https://github.com/dotnet/roslyn-analyzers/issues/458)
[CA1804](ca1804-remove-unused-locals.md) | [https://github.com/dotnet/roslyn-analyzers/issues/461](https://github.com/dotnet/roslyn-analyzers/issues/461)
[CA1811](ca1811-avoid-uncalled-private-code.md) | [https://github.com/dotnet/roslyn-analyzers/issues/464](https://github.com/dotnet/roslyn-analyzers/issues/464)
[CA1900](ca1900-value-type-fields-should-be-portable.md) | [https://github.com/dotnet/roslyn-analyzers/issues/474](https://github.com/dotnet/roslyn-analyzers/issues/474)
[CA2001](ca2001-avoid-calling-problematic-methods.md) | [https://github.com/dotnet/roslyn-analyzers/issues/477](https://github.com/dotnet/roslyn-analyzers/issues/477)
[CA2004](ca2004-remove-calls-to-gc-keepalive.md) | [https://github.com/dotnet/roslyn-analyzers/issues/479](https://github.com/dotnet/roslyn-analyzers/issues/479)
[CA2006](ca2006-use-safehandle-to-encapsulate-native-resources.md) | [https://github.com/dotnet/roslyn-analyzers/issues/480](https://github.com/dotnet/roslyn-analyzers/issues/480)
[CA2109](ca2109-review-visible-event-handlers.md) | [https://github.com/dotnet/roslyn-analyzers/issues/488](https://github.com/dotnet/roslyn-analyzers/issues/488)
[CA2204](ca2204-literals-should-be-spelled-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/529](https://github.com/dotnet/roslyn-analyzers/issues/529)
[CA2205](ca2205-use-managed-equivalents-of-win32-api.md) | [https://github.com/dotnet/roslyn-analyzers/issues/530](https://github.com/dotnet/roslyn-analyzers/issues/530)
[CA2212](ca2212-do-not-mark-serviced-components-with-webmethod.md) | [https://github.com/dotnet/roslyn-analyzers/issues/534](https://github.com/dotnet/roslyn-analyzers/issues/534)
[CA2215](ca2215-dispose-methods-should-call-base-class-dispose.md) | [https://github.com/dotnet/roslyn-analyzers/issues/535](https://github.com/dotnet/roslyn-analyzers/issues/535)
[CA2232](ca2232-mark-windows-forms-entry-points-with-stathread.md) | [https://github.com/dotnet/roslyn-analyzers/issues/545](https://github.com/dotnet/roslyn-analyzers/issues/545)
[CA2236](ca2236-call-base-class-methods-on-iserializable-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/548](https://github.com/dotnet/roslyn-analyzers/issues/548)
[CA2238](ca2238-implement-serialization-methods-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/549](https://github.com/dotnet/roslyn-analyzers/issues/549)
[CA2239](ca2239-provide-deserialization-methods-for-optional-fields.md) | [https://github.com/dotnet/roslyn-analyzers/issues/550](https://github.com/dotnet/roslyn-analyzers/issues/550)
[CA2240](ca2240-implement-iserializable-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/551](https://github.com/dotnet/roslyn-analyzers/issues/551)

### <a name="deprecated-rules"></a>非推奨の規則

次の FxCop レガシ分析ルールは非推奨とされており、アナライザーとして実装されません。 詳細については、 [roslyn-Analyzer GitHub の問題](https://github.com/dotnet/roslyn-analyzers/issues?utf8=%E2%9C%93&q=is:issue+label:FxCop-Port)に関するページで、ルール ID (たとえば、 **CA1009**) で検索することができます。

- [CA1009](ca1009-declare-event-handlers-correctly.md)
- [CA1020](ca1020-avoid-namespaces-with-few-types.md)
- [CA1025](ca1025-replace-repetitive-arguments-with-params-array.md)
- [CA1026](ca1026-default-parameters-should-not-be-used.md)
- [CA1035](ca1035-icollection-implementations-have-strongly-typed-members.md)
- [CA1038](ca1038-enumerators-should-be-strongly-typed.md)
- [CA1039](ca1039-lists-are-strongly-typed.md)
- [CA1059](ca1059-members-should-not-expose-certain-concrete-types.md)
- [CA1302](ca1302-do-not-hardcode-locale-specific-strings.md)
- [CA1400](ca1400-p-invoke-entry-points-should-exist.md)
- [CA1406](ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)
- [CA1504](ca1504-review-misleading-field-names.md)
- [CA1701](ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1702](ca1702-compound-words-should-be-cased-correctly.md)
- [CA1703](ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1800](ca1800-do-not-cast-unnecessarily.md)
- [CA1809](ca1809-avoid-excessive-locals.md)
- [CA1901](ca1901-p-invoke-declarations-should-be-portable.md)
- [CA1903](ca1903-use-only-api-from-targeted-framework.md)
- [CA2003](ca2003-do-not-treat-fibers-as-threads.md)
- [CA2102](ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)
- [CA2103](ca2103-review-imperative-security.md)
- [CA2104](ca2104-do-not-declare-read-only-mutable-reference-types.md)
- [CA2105](ca2105-array-fields-should-not-be-read-only.md)
- [CA2106](ca2106-secure-asserts.md)
- [CA2107](ca2107-review-deny-and-permit-only-usage.md)
- [CA2108](ca2108-review-declarative-security-on-value-types.md)
- [CA2111](ca2111-pointers-should-not-be-visible.md)
- [CA2112](ca2112-secured-types-should-not-expose-fields.md)
- [CA2114](ca2114-method-security-should-be-a-superset-of-type.md)
- [CA2115](ca2115-call-gc-keepalive-when-using-native-resources.md)
- [CA2116](ca2116-aptca-methods-should-only-call-aptca-methods.md)
- [CA2117](ca2117-aptca-types-should-only-extend-aptca-base-types.md)
- [CA2118](ca2118-review-suppressunmanagedcodesecurityattribute-usage.md)
- [CA2120](ca2120-secure-serialization-constructors.md)
- [CA2121](ca2121-static-constructors-should-be-private.md)
- [CA2122](ca2122-do-not-indirectly-expose-methods-with-link-demands.md)
- [CA2123](ca2123-override-link-demands-should-be-identical-to-base.md)
- [CA2124](ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)
- [CA2126](ca2126-type-link-demands-require-inheritance-demands.md)
- [CA2130](ca2130-security-critical-constants-should-be-transparent.md)
- [CA2131](ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)
- [CA2132](ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)
- [CA2133](ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)
- [CA2134](ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)
- [CA2135](ca2135-level-2-assemblies-should-not-contain-linkdemands.md)
- [CA2136](ca2136-members-should-not-have-conflicting-transparency-annotations.md)
- [CA2137](ca2137-transparent-methods-must-contain-only-verifiable-il.md)
- [CA2138](ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)
- [CA2139](ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute.md)
- [CA2140](ca2140-transparent-code-must-not-reference-security-critical-items.md)
- [CA2141](ca2141-transparent-methods-must-not-satisfy-linkdemands.md)
- [CA2142](ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)
- [CA2143](ca2143-transparent-methods-should-not-use-security-demands.md)
- [CA2144](ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays.md)
- [CA2145](ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute.md)
- [CA2146](ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)
- [CA2147](ca2147-transparent-methods-may-not-use-security-asserts.md)
- [CA2149](ca2149-transparent-methods-must-not-call-into-native-code.md)
- [CA2151](ca2151-fields-with-critical-types-should-be-security-critical.md)
- [CA2202](ca2202-do-not-dispose-objects-multiple-times.md)
- [CA2210](ca2210-assemblies-should-have-valid-strong-names.md)
- [CA2220](ca2220-finalizers-should-call-base-class-finalizer.md)
- [CA2221](ca2221-finalizers-should-be-protected.md)
- [CA2222](ca2222-do-not-decrease-inherited-member-visibility.md)([理由](https://github.com/dotnet/roslyn-analyzers/issues/1378))
- [CA2223](ca2223-members-should-differ-by-more-than-return-type.md)
- [CA2228: 未公開](ca2228-do-not-ship-unreleased-resource-formats.md)
- [CA2230](ca2230-use-params-for-variable-arguments.md)
- [CA2233](ca2233-operations-should-not-overflow.md)
- [CA5122](ca5122-p-invoke-declarations-should-not-be-safe-critical.md)

## <a name="see-also"></a>関連項目

- [FxCopAnalyzers の規則](https://github.com/dotnet/roslyn-analyzers/blob/master/src/Microsoft.CodeAnalysis.FxCopAnalyzers/Microsoft.CodeAnalysis.FxCopAnalyzers.md)