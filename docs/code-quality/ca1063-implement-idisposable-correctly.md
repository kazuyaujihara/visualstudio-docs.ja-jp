---
title: CA1063:IDisposable を正しく実装します
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- ImplementIDisposableCorrectly
- CA1063
helpviewer_keywords:
- CA1063
- ImplementIDisposableCorrectly
ms.assetid: 12afb1ea-3a17-4a3f-a1f0-fcdb853e2359
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 22ecfcdd6dc20f5837622ec2cc3469f11c7efa8c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62788556"
---
# <a name="ca1063-implement-idisposable-correctly"></a>CA1063:IDisposable を正しく実装します

|||
|-|-|
|TypeName|ImplementIDisposableCorrectly|
|CheckId|CA1063|
|Category|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

<xref:System.IDisposable?displayProperty=nameWithType>インターフェイスが正しく実装されていません。 これに考えられる理由:

- <xref:System.IDisposable> クラスで実装したです。

- 最終処理 reoverridden です。

- Dispose() がオーバーライドされます。

- Dispose() メソッドはパブリックではない[シール](/dotnet/csharp/language-reference/keywords/sealed)、または名前付き**Dispose**します。

- Dispose (bool) は、保護された、仮想、または封印されていないではありません。

- 封印されていない種類は、Dispose() が dispose (true) を呼び出す必要があります。

- 封印されていない型の場合、Finalize 実装は呼び出しませんいずれかまたは両方の dispose (bool) または基本クラスのファイナライザー。

これらのパターンのいずれかの違反が警告 CA1063 をトリガーします。

宣言および実装しているすべての封印されていない型、<xref:System.IDisposable>インターフェイスを提供する必要があります独自`protected virtual void Dispose(bool)`メソッド。 `Dispose()` 呼び出す必要があります`Dipose(true)`、ファイナライザーを呼び出す必要がありますと`Dispose(false)`します。 封印されていない型宣言および実装を作成するかどうか、<xref:System.IDisposable>インターフェイスが定義する必要があります`Dispose(bool)`呼び出すようにします。 詳細については、次を参照してください。 [(.NET ガイド) のアンマネージ リソースをクリーンアップする](/dotnet/standard/garbage-collection/unmanaged)と[Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)します。

既定では、このルールのみが検索に、外部から参照の種類が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

すべて<xref:System.IDisposable>型を実装する必要があります、 [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)正しくします。

## <a name="how-to-fix-violations"></a>違反の修正方法

コードを調べて、この違反を修正するは、次の解決策の確認します。

- 削除<xref:System.IDisposable>の種類によって実装され、代わりに、基底クラス Dispose の実装をオーバーライドするインターフェイスの一覧。

- 型から、ファイナライザーを削除、Dispose (bool disposing) をオーバーライドし、'disposing' が false のコード パスに finalization 論理を配置します。

- Dispose (bool disposing) をオーバーライドし、'disposing' が true に、コード パスに dispose 論理を入れます。

- Dispose() をパブリックとして宣言されていることを確認し、[シール](/dotnet/csharp/language-reference/keywords/sealed)します。

- Dispose メソッドの名前を変更**Dispose** public として宣言されかどうかを確認して、[シール](/dotnet/csharp/language-reference/keywords/sealed)。

- Dispose (bool) を protected として宣言されていることを確認して、仮想、および封印されていないことができます。

- Dispose (true) を呼び出すように Dispose() の変更を呼び出して<xref:System.GC.SuppressFinalize%2A>オブジェクトの現在のインスタンスで (`this`、または`Me`Visual Basic で)、しを返します。

- ように戻ります、dispose (false) を呼び出し、ファイナライザーを変更します。

- 封印されていない型宣言および実装を作成するかどうか、<xref:System.IDisposable>インターフェイス、ことを確認の実装<xref:System.IDisposable>このセクションで既に説明したパターンに従います。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告は抑制しないでください。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1063.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="pseudo-code-example"></a>擬似コードの例

次の擬似コードでは、管理を使用するクラスで dispose (bool) を実装する方法と、ネイティブ リソースの一般的な例を示します。

```csharp
public class Resource : IDisposable
{
    private IntPtr nativeResource = Marshal.AllocHGlobal(100);
    private AnotherResource managedResource = new AnotherResource();

    // Dispose() calls Dispose(true)
    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    // NOTE: Leave out the finalizer altogether if this class doesn't
    // own unmanaged resources, but leave the other methods
    // exactly as they are.
    ~Resource()
    {
        // Finalizer calls Dispose(false)
        Dispose(false);
    }

    // The bulk of the clean-up code is implemented in Dispose(bool)
    protected virtual void Dispose(bool disposing)
    {
        if (disposing)
        {
            // free managed resources
            if (managedResource != null)
            {
                managedResource.Dispose();
                managedResource = null;
            }
        }
        // free native resources if there are any.
        if (nativeResource != IntPtr.Zero)
        {
            Marshal.FreeHGlobal(nativeResource);
            nativeResource = IntPtr.Zero;
        }
    }
}
```

## <a name="see-also"></a>関連項目

- [Dispose パターン (framework デザイン ガイドライン)](/dotnet/standard/design-guidelines/dispose-pattern)
- [アンマネージ リソース (.NET ガイド) をクリーンアップします。](/dotnet/standard/garbage-collection/unmanaged)