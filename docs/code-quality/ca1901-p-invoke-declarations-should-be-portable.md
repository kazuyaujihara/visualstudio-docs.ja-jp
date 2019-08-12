---
title: CA1901:P/Invoke 宣言はポータブルでなければなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
helpviewer_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
ms.assetid: 90361812-55ca-47f7-bce9-b8775d3b8803
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4a45b7061ae9d183ec7ee02a3b733ee9340b3689
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921303"
---
# <a name="ca1901-pinvoke-declarations-should-be-portable"></a>CA1901:P/Invoke 宣言はポータブルでなければなりません

|||
|-|-|
|TypeName|PInvokeDeclarationsShouldBePortable|
|CheckId|CA1901|
|Category|Microsoft. 移植性|
|互換性に影響する変更点|中断-P/Invoke がアセンブリの外部で参照可能である場合。 非中断-P/Invoke がアセンブリの外部で参照できない場合。|

## <a name="cause"></a>原因
このルールは、P/Invoke の各パラメーターと戻り値のサイズを評価し、32ビットおよび64ビットのプラットフォームでアンマネージコードにマーシャリングされたときのサイズが正しいことを確認します。 この規則の最も一般的な違反は、プラットフォームに依存するポインターサイズの変数が必要な固定サイズの整数を渡すことです。

## <a name="rule-description"></a>規則の説明
次のいずれかのシナリオがこの規則に違反しています。

- 戻り値またはパラメーターは、 `IntPtr`として型指定する必要がある場合、固定サイズの整数として型指定されます。

- 戻り値またはパラメーターは、固定サイズ`IntPtr`の整数として型指定する必要があるときに、として型指定されます。

## <a name="how-to-fix-violations"></a>違反の修正方法
また`IntPtr`はを使用し`UIntPtr`て、 `Int32`また`UInt32`はではなくハンドルを表すことで、この違反を修正できます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この警告を抑制しないでください。

## <a name="example"></a>例
次の例は、このルールの違反を示しています。

```csharp
internal class NativeMethods
{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, IntPtr nIconIndex);
}
```

この例`nIconIndex`では、パラメーターは`IntPtr`として宣言されています。これは32ビットプラットフォームでは幅が4バイト、64ビットプラットフォームでは幅が8バイトです。 次のアンマネージ宣言では、がすべての`nIconIndex`プラットフォームの4バイト符号なし整数であることがわかります。

```csharp
HICON ExtractIcon(HINSTANCE hInst, LPCTSTR lpszExeFileName,
    UINT nIconIndex);
```

## <a name="example"></a>例
違反を修正するには、次のように宣言を変更します。

```csharp
internal class NativeMethods{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, uint nIconIndex);
}
```

## <a name="see-also"></a>関連項目
[Portability Warnings](../code-quality/portability-warnings.md)