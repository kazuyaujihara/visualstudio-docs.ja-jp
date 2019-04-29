---
title: Ca 2153 コード分析ルールは、破損状態例外を
ms.date: 02/19/2019
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4b75e45b8a199265eaefe3a2b3c37ed62039e0eb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62542158"
---
# <a name="ca2153-avoid-handling-corrupted-state-exceptions"></a>CA2153:破損状態例外の処理を回避します。

|||
|-|-|
|TypeName|AvoidHandlingCorruptedStateExceptions|
|CheckId|CA2153|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

[破損状態例外 (Cse)](https://msdn.microsoft.com/magazine/dd419661.aspx)そのメモリ破損がプロセス内に存在します。 プロセスをクラッシュさせるのではなくこれらの例外をキャッチすることは、攻撃者が破損したメモリ領域にセキュリティ上の弱点を見出すことができた場合に、セキュリティ上の脆弱性となる可能性があります。

## <a name="rule-description"></a>規則の説明

CSE は、プロセスが破損状態にあり、システムによってキャッチされていないことを示します。 破損した状態では、汎用ハンドラーのみが例外をキャッチでメソッドをマークする場合、<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>属性。 既定で、[共通言語ランタイム (CLR)](/dotnet/standard/clr) Cse の catch ハンドラーは呼び出されません。

最も安全なオプションでは、これらの種類の例外をキャッチせず、プロセスがクラッシュするを許可します。 コードのログ記録もメモリ破損のバグを悪用する攻撃者を許可できます。

たとえば、すべての例外をキャッチする汎用ハンドラーで Cse をキャッチするときに、この警告がトリガー`catch (System.Exception e)`または`catch`ありません例外パラメーターを使用します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この警告を解決するには、次のいずれかの操作を行います。

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 属性を削除します。 これにより、CSE を catch ハンドラーに渡さない既定の実行時の動作に戻ります。

- 特定の例外の種類をキャッチするハンドラーではなく汎用 catch ハンドラーを削除します。 Cse は、ハンドラーのコードに処理できる安全な場合 (まれな) 場合があります。

- Catch ハンドラーに、呼び出し元に例外を渡し、実行中のプロセスを終了すると、する必要があります CSE を再スローします。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告は抑制しないでください。

## <a name="pseudo-code-example"></a>擬似コードの例

### <a name="violation"></a>違反

次の擬似コードでは、このルールにより検出されたパターンを示しています。

```csharp
[HandleProcessCorruptedStateExceptions]
// Method that handles CSE exceptions.
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (Exception e)
    {
        // Handle exception.
    }
}
```

### <a name="solution-1---remove-the-attribute"></a>解決策 1 - 属性を削除します。

削除、<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>属性により、破損状態例外は、メソッドによって処理されません。

```csharp
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (Exception e)
    {
        // Handle exception.
    }
}
```

### <a name="solution-2---catch-specific-exceptions"></a>解決策 2 - 特定の例外をキャッチします。

汎用 catch ハンドラーを削除し、特定の例外の種類のみをキャッチします。

```csharp
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (IOException e)
    {
        // Handle IOException.
    }
    catch (UnauthorizedAccessException e)
    {
        // Handle UnauthorizedAccessException.
    }
}
```

### <a name="solution-3---rethrow"></a>解決策 3 - を再スローします。

例外を再スローします。

```csharp
[HandleProcessCorruptedStateExceptions]
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (Exception e)
    {
        // Rethrow the exception.
        throw;
    }
}
```