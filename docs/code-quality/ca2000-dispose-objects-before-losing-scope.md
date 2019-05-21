---
title: CA2000:スコープを失う前にオブジェクトを破棄
ms.date: 05/14/2019
ms.topic: reference
f1_keywords:
- CA2000
- Dispose objects before losing scope
- DisposeObjectsBeforeLosingScope
helpviewer_keywords:
- CA2000
- DisposeObjectsBeforeLosingScope
ms.assetid: 0c3d7d8d-b94d-46e8-aa4c-38df632c1463
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 732b3d683802c50042ee40fee1549a9d247e2470
ms.sourcegitcommit: 283f2dbce044a18e9f6ac6398f6fc78e074ec1ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2019
ms.locfileid: "65804974"
---
# <a name="ca2000-dispose-objects-before-losing-scope"></a>CA2000:スコープを失う前にオブジェクトを破棄

|||
|-|-|
|TypeName|DisposeObjectsBeforeLosingScope|
|CheckId|CA2000|
|カテゴリ|Microsoft.Reliability|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

ローカル オブジェクト、<xref:System.IDisposable>型が作成されますが、オブジェクトに対するすべての参照がスコープ外の前に、オブジェクトが破棄されません。

## <a name="rule-description"></a>規則の説明

破棄できるオブジェクトに対するすべての参照がスコープ外になる前に、オブジェクトが明示的に破棄されない場合、ガベージ コレクターでオブジェクトのファイナライザーが実行されるときに破棄されますが、タイミングは一定ではありません。 例外的なイベントが発生するとオブジェクトのファイナライザーを実行できないため、オブジェクトは明示的に破棄する必要があります。

### <a name="special-cases"></a>特殊なケース

規則 CA2000 は、オブジェクトが破棄されていない場合でも、次の種類のローカル オブジェクトの発生します。

- <xref:System.IO.Stream?displayProperty=nameWithType>
- <xref:System.IO.TextReader?displayProperty=nameWithType>
- <xref:System.IO.TextWriter?displayProperty=nameWithType>
- <xref:System.Resources.IResourceReader?displayProperty=nameWithType>

これらの型のいずれかのオブジェクトをコンス トラクターに渡すと、フィールドに割り当てることを示します、*所有権の譲渡を dispose*新しく構築された型にします。 つまり、新しく構築された型では、オブジェクトの破棄を担当ようになりました。 場合は、コードは、これらの型の 1 つのオブジェクトをコンス トラクターに渡して、スコープ外にすべての参照の前に、オブジェクトが破棄しない場合でも、CA2000 が発生する規則違反はありません。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、オブジェクトに対するすべての参照がスコープ外になる前に、そのオブジェクトで <xref:System.IDisposable.Dispose%2A> を呼び出します。

使用することができます、 [ `using`ステートメント](/dotnet/csharp/language-reference/keywords/using-statement)([ `Using` ](/dotnet/visual-basic/language-reference/statements/using-statement) Visual basic) を実装するオブジェクトをラップする<xref:System.IDisposable>します。 この方法でラップされているオブジェクトがの末尾に自動的に破棄、`using`ブロックします。 ただし、次の状況がしないでまたはで処理することはできません、`using`ステートメント。

- 破棄可能なオブジェクトを取得するには、オブジェクトを構築する必要があります、`try/finally`の外側のブロックを`using`ブロックします。

- コンス トラクターで破棄可能なオブジェクトのメンバーを初期化できません、`using`ステートメント。

- 1 つだけ例外ハンドラーによって保護されているコンス トラクターが入れ子になったときに、[の一部を取得、`using`ステートメント](/dotnet/csharp/language-reference/language-specification/statements#the-using-statement)、外側のコンス トラクターで発生する可能性がない、入れ子になったコンス トラクターによって作成されたオブジェクト閉じています。 次の例では、エラー、<xref:System.IO.StreamReader>コンス トラクターで発生することができます、<xref:System.IO.FileStream>オブジェクト閉じられたことはありません。 CA2000 は、ここで、規則違反をフラグします。

   ```csharp
   using (StreamReader sr = new StreamReader(new FileStream("C:\myfile.txt", FileMode.Create)))
   { ... }
   ```

- 動的オブジェクトの dispose パターンを実装するシャドウ オブジェクトを使用する必要があります<xref:System.IDisposable>オブジェクト。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

しない限り、この規則による警告を抑制しないでください。

- 呼び出すオブジェクトでメソッドを呼び出して`Dispose`など <xref:System.IO.Stream.Close%2A>
- 警告を返しますを発生させたメソッド、<xref:System.IDisposable>オブジェクトをラップするオブジェクト。
- 割り当てのメソッドには、dispose の所有権はありません。別のオブジェクトまたはラッパーがメソッドで作成され、呼び出し元に返されるオブジェクトを破棄する必要がありますの転送は、

## <a name="related-rules"></a>関連するルール

- [CA2213: 破棄可能なフィールドは破棄されなければなりません](../code-quality/ca2213-disposable-fields-should-be-disposed.md)
- [CA 2202:オブジェクトを複数回破棄しません](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)

## <a name="example"></a>例

破棄可能なオブジェクトを返すメソッドを実装する場合は、catch ブロックのない try/finally ブロックを使用して、オブジェクトが破棄されたことを確認します。 try/finally ブロックを使用することによって、障害点での例外の発生が可能になり、そのオブジェクトが確実に破棄されます。

OpenPort1 メソッドでは、ISerializable オブジェクトの SerialPort を開くための呼び出し、または SomeMethod の呼び出しが失敗する可能性があります。 この実装では CA2000 警告は発生しません。

OpenPort2 メソッドでは、次の 2 つの SerialPort オブジェクトが宣言され、null に設定されます。

- `tempPort`。メソッド操作が成功しているかどうかをテストするのに使用されます。

- `port`。メソッドの戻り値に使用されます。

`tempPort` は、`try` ブロックで構築され、開かれます。その他必要な作業も同じ `try` ブロック内で実行されます。 `try` ブロックの最後に、開かれたポートが `port` オブジェクトに割り当てられ、このオブジェクトが返されます。`tempPort` オブジェクトは `null` に設定されます。

`finally` ブロックは `tempPort` 値をチェックします。 null でない場合、メソッド内の操作は失敗しています。`tempPort` は閉じられ、すべてのリソースが解放されます。 返されるオブジェクトには、メソッド操作が成功した場合、開かれた SerialPort オブジェクトが含まれます。メソッドの操作が失敗した場合は null になります。

```csharp
public SerialPort OpenPort1(string portName)
{
   SerialPort port = new SerialPort(portName);
   port.Open();  //CA2000 fires because this might throw
   SomeMethod(); //Other method operations can fail
   return port;
}

public SerialPort OpenPort2(string portName)
{
   SerialPort tempPort = null;
   SerialPort port = null;
   try
   {
      tempPort = new SerialPort(portName);
      tempPort.Open();
      SomeMethod();
      //Add any other methods above this line
      port = tempPort;
      tempPort = null;

   }
   finally
   {
      if (tempPort != null)
      {
         tempPort.Close();
      }
   }
   return port;
}
```

```vb
Public Function OpenPort1(ByVal PortName As String) As SerialPort

   Dim port As New SerialPort(PortName)
   port.Open()    'CA2000 fires because this might throw
   SomeMethod()   'Other method operations can fail
   Return port

End Function

Public Function OpenPort2(ByVal PortName As String) As SerialPort

   Dim tempPort As SerialPort = Nothing
   Dim port As SerialPort = Nothing

   Try
      tempPort = New SerialPort(PortName)
      tempPort.Open()
      SomeMethod()
      'Add any other methods above this line
      port = tempPort
      tempPort = Nothing

   Finally
      If Not tempPort Is Nothing Then
         tempPort.Close()
      End If

   End Try

   Return port

End Function
```

## <a name="example"></a>例

既定では、Visual Basic コンパイラは、すべての算術演算子のオーバーフローをチェックを持っています。 そのため、いずれかの Visual Basic 算術演算子で <xref:System.OverflowException> がスローされる可能性があります。 これにより、CA2000 のような予期しない規則違反が発生する場合があります。 たとえば、次の CreateReader1 関数では、Visual Basic コンパイラが加算に対するオーバーフロー チェックを実行し、それが例外をスローすると StreamReader が破棄されなくなるので、CA2000 違反が発生します。

これを修正するには、プロジェクトで Visual Basic コンパイラによるオーバーフロー チェックの実施を無効にするか、または次の CreateReader2 関数のようにコードを変更します。

オーバーフロー チェックの実施を無効にするには、ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**プロパティ**します。 をクリックして**コンパイル**、 をクリックして**詳細コンパイル オプション**、し確認**整数オーバーフローのチェックを解除**します。

[!code-vb[FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope#1](../code-quality/codesnippet/VisualBasic/ca2000-dispose-objects-before-losing-scope-vboverflow_1.vb)]

## <a name="see-also"></a>関連項目

- <xref:System.IDisposable>
- [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)