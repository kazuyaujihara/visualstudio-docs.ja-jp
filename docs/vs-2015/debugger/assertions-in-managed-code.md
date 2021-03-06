---
title: マネージ コードでアサーション |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], assertions in managed code
- Trace.Assert method
- debugging managed code, assertions
- Debug.Assert method
- Debug.Listeners property
- assertions, side effects
- Trace.Listeners property
- assertions, managed code
ms.assetid: 70ab2522-6486-4076-a1a9-e0f11cd0f3a1
caps.latest.revision: 32
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c47b2b05ab358826d594d0c6ef29c1b50e0a529f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51806543"
---
# <a name="assertions-in-managed-code"></a>マネージド コードのアサーション
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

アサーション、つまり `Assert` ステートメントは、条件をテストします。この条件は、`Assert` ステートメントへの引数として指定します。 条件が true と評価された場合、アクションは発生しません。 条件が false と評価された場合、アサーションは失敗です。 また、デバッグ ビルドを実行している場合、プログラムは中断モードになります。  
  
##  <a name="BKMK_In_this_topic"></a> このトピックの内容  
 [System.Diagnostics Namespace でアサートします。](#BKMK_Asserts_in_the_System_Diagnostics_Namespace)  
  
 [Debug.Assert メソッド](#BKMK_The_Debug_Assert_method)  
  
 [Debug.Assert の副作用](#BKMK_Side_effects_of_Debug_Assert)  
  
 [Trace および Debug の必要条件](#BKMK_Trace_and_Debug_Requirements)  
  
 [Assert の引数](#BKMK_Assert_arguments)  
  
 [Assert の動作をカスタマイズします。](#BKMK_Customizing_Assert_behavior)  
  
 [構成ファイルでのアサーションの設定](#BKMK_Setting_assertions_in_configuration_files)  
  
##  <a name="BKMK_Asserts_in_the_System_Diagnostics_Namespace"></a> System.Diagnostics Namespace でアサートします。  
 Visual Basic および Visual C# では、`Assert` 名前空間内の <xref:System.Diagnostics.Debug> または <xref:System.Diagnostics.Trace> から <xref:System.Diagnostics> メソッドを使用できます。 <xref:System.Diagnostics.Debug> クラスのメソッドはプログラムのリリース バージョンには含まれないので、リリース コードのサイズを増加させたり処理速度を低下させることはありません。  
  
 C++ は、<xref:System.Diagnostics.Debug> クラスのメソッドをサポートしません。 使用して同じ効果を得ることができます、<xref:System.Diagnostics.Trace>などの条件付きコンパイルは、クラス`#ifdef DEBUG`.`#endif`.  
  
 [このトピックの内容](#BKMK_In_this_topic)  
  
##  <a name="BKMK_The_Debug_Assert_method"></a> Debug.Assert メソッド  
 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> メソッドを自由に使用して、コードが正しい場合に true になる条件をテストできます。 たとえば、整数の除算関数を記述したとします。 数学の規則により、0 での除算は不可能です。 これはアサーションを使ってテストできます。  
  
```vb  
Function IntegerDivide(ByVal dividend As Integer, ByVal divisor As Integer) As Integer  
    Debug.Assert(divisor <> 0)  
    Return CInt(dividend / divisor)  
End Function  
```  
  
```csharp  
int IntegerDivide ( int dividend , int divisor )  
    { Debug.Assert ( divisor != 0 );  
        return ( dividend / divisor ); }  
```  
  
 デバッガーでこのコードを実行すると、アサーション ステートメントが評価されますが、リリース バージョンでは比較は行われません。このため、追加のオーバーヘッドは発生しません。  
  
 別の例を示します。 次のような、当座預金口座を実装するクラスがあります。  
  
```vb  
Dim amount, balance As Double  
balance = savingsAccount.balance  
Debug.Assert(amount <= balance)  
SavingsAccount.Withdraw(amount)  
```  
  
```csharp  
float balance = savingsAccount.Balance;  
Debug.Assert ( amount <= balance );  
savingsAccount.Withdraw ( amount );  
```  
  
 口座から現金を引き出す前に、これから引き出す額に対して残高が十分かどうかを確認します。 残高照会のためのアサーションは次のように記述できます。  
  
```vb  
Dim amount, balance As Double  
balance = savingsAccount.balance  
Trace.Assert(amount <= balance)  
SavingsAccount.Withdraw(amount)  
```  
  
```csharp  
float balance = savingsAccount.Balance;  
Trace.Assert ( amount <= balance );  
savingsAccount.Withdraw ( amount );  
```  
  
 コードのリリース バージョンを作成すると、<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> メソッドの呼び出しは無効になります。 つまり、残高照会は、リリース バージョンには反映されません。 この問題を解決するには、<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> を <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> で置き換えます。Trace.Assert は、リリース バージョンで無効になりません。  
  
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> の呼び出しを使用すると、<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> の呼び出しとは異なり、リリース バージョンに対してオーバーヘッドがかかります。  
  
 [このトピックの内容](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Side_effects_of_Debug_Assert"></a> Debug.Assert の副作用  
 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> を使用する場合は、`Assert` 内のコードを調べて、`Assert` を削除してもプログラムの結果が変わらないようにします。 そうしないと、プログラムのリリース バージョンにのみ現れるバグを誤って導入する可能性があります。 関数やプロシージャの呼び出しを含むアサートについては、特に注意が必要です。  
  
```vb  
' unsafe code  
Debug.Assert (meas(i) <> 0 )  
```  
  
```csharp  
// unsafe code  
Debug.Assert (meas(i) != 0 );  
```  
  
 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> をこのように使用するのは一見安全に思われますが、meas 関数は呼び出されるたびにカウンターを更新します。 リリース バージョンをビルドすると、この meas の呼び出しは除去されるので、カウンターは更新されません。 これが、副作用を伴う関数の例です。 副作用のある関数呼び出しを除去すると、リリース バージョンにだけ現れるバグが発生する可能性があります。 このような問題を防ぐため、<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> ステートメントには関数呼び出しを配置しないでください。 関数の代わりに、次のように一時変数を使用します。  
  
```vb  
temp = meas( i )  
Debug.Assert (temp <> 0)  
```  
  
```csharp  
temp = meas( i );  
Debug.Assert ( temp != 0 );  
```  
  
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> を使用する場合でも、`Assert` ステートメント内に関数呼び出しを配置しないようにします。 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> ステートメントはリリース ビルドで除去されないため、関数呼び出しは安全です。 しかし、そのような構造体を避ける習慣を付けておくことで、<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> を使用する際に間違いを犯す可能性が低くなります。  
  
 [このトピックの内容](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Trace_and_Debug_Requirements"></a> Trace および Debug の必要条件  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ウィザードを使用してプロジェクトを作成すると、既定では、リリース構成とデバッグ構成の両方に TRACE シンボルが定義されます。 DEBUG シンボルは、既定ではデバッグ ビルドにだけ定義されます。  
  
 それ以外の場合は、<xref:System.Diagnostics.Trace> メソッドが動作するように、プログラムのソース ファイルの先頭に次のいずれかを記述する必要があります。  
  
- `#Const TRACE = True` (Visual Basic の場合)  
  
- `#define TRACE` (Visual C# および C++ の場合)  
  
  または、次に示すように、TRACE オプションを使用してプログラムをビルドする必要があります。  
  
- `/d:TRACE=True` (Visual Basic の場合)  
  
- `/d:TRACE` (Visual C# および C++ の場合)  
  
  C# または Visual Basic のリリース ビルドで Debug メソッドを使用する必要がある場合は、リリース構成にデバッグ シンボルを定義する必要があります。  
  
  C++ は、<xref:System.Diagnostics.Debug> クラスのメソッドをサポートしません。 使用して同じ効果を得ることができます、<xref:System.Diagnostics.Trace>などの条件付きコンパイルは、クラス`#ifdef DEBUG`.`#endif`. これらのシンボルを定義することができます、 **\<プロジェクト > プロパティ ページ** ダイアログ ボックス。 詳細については、次を参照してください。 [Visual Basic デバッグ構成のプロジェクトの設定を変更する](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)または[C または C++ デバッグ構成のプロジェクトの設定を変更する](../debugger/project-settings-for-a-cpp-debug-configuration.md)します。  
  
##  <a name="BKMK_Assert_arguments"></a> Assert の引数  
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> と <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> は、最大で 3 つの引数を受け取ります。 最初の引数は調べる条件です。これは必ず指定します。 呼び出す場合<xref:System.Diagnostics.Trace.Assert%28System.Boolean%29?displayProperty=fullName>または<xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName>、引数の 1 つだけで、`Assert`メソッドは、条件をチェックし、結果が false の場合は、呼び出し履歴の内容を出力、**出力**ウィンドウ。 <xref:System.Diagnostics.Trace.Assert%28System.Boolean%29?displayProperty=fullName> および <xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName> の使用例は、次のようになります。  
  
```vb  
Debug.Assert(stacksize > 0)  
Trace.Assert(stacksize > 0)  
```  
  
```csharp  
Debug.Assert ( stacksize > 0 );  
Trace.Assert ( stacksize > 0 );   
```  
  
 2 番目と 3 番目の引数は文字列にする必要があります (存在する場合)。 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> または <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> を 2 つまたは 3 つの引数を使用して呼び出すと、1 番目の引数は条件として処理されます。 メソッドはこの条件をチェックし、結果が false の場合は 2 番目と 3 番目の文字列を出力します。 2 つの引数を使用した <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName> と <xref:System.Diagnostics.Trace.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName> の例を次に示します。  
  
```vb  
Debug.Assert(stacksize > 0, "Out of stack space")  
Trace.Assert(stacksize > 0, "Out of stack space")  
```  
  
```csharp  
Debug.Assert ( stacksize > 0, "Out of stack space" );  
Trace.Assert ( stacksize > 0, "Out of stack space" );  
```  
  
 <xref:System.Diagnostics.Debug.Assert%2A> および <xref:System.Diagnostics.Trace.Assert%2A> の使用例は、次のようになります。  
  
```vb  
Debug.Assert(stacksize > 0, "Out of stack space. Bytes left:" , Format(size, "G"))  
Trace.Assert(stacksize > 0, "Out of stack space. Bytes left:" , Format(size, "G"))  
Trace.Assert(stacksize > 0, "Out of stack space. Bytes left:", "inctemp failed on third call" )  
```  
  
```csharp  
Debug.Assert ( stacksize > 100, "Out of stack space" , "Failed in inctemp" );  
Trace.Assert ( stacksize > 0, "Out of stack space", "Failed in inctemp" );   
```  
  
 [このトピックの内容](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Customizing_Assert_behavior"></a> Assert の動作をカスタマイズします。  
 ユーザー インターフェイス モードでアプリケーションを実行する場合、`Assert`メソッドが表示されます、**アサーションが失敗した**ダイアログ ボックスの条件が失敗したとします。 アサーションが失敗したときに発生するアクションは、によって制御されます、<xref:System.Diagnostics.Debug.Listeners%2A>または<xref:System.Diagnostics.Trace.Listeners%2A>プロパティ。  
  
 出力動作をカスタマイズするには、<xref:System.Diagnostics.TraceListener> オブジェクトを `Listeners` コレクションに追加するか、<xref:System.Diagnostics.TraceListener> を `Listeners` コレクションから削除します。または、既存の <xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName> の `TraceListener` メソッドをオーバーライドして動作を変更します。  
  
 たとえば、オーバーライドする可能性があります、<xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName>メソッドを表示する代わりに、イベント ログに書き込む、**アサーションが失敗した** ダイアログ ボックス。  
  
 この方法で出力をカスタマイズするには、プログラムにリスナーが含まれている必要があります。また、<xref:System.Diagnostics.TraceListener> を継承し、その <xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName> メソッドをオーバーライドする必要があります。  
  
 詳細については、次を参照してください。[トレース リスナー](http://msdn.microsoft.com/library/444b0d33-67ea-4c36-9e94-79c50f839025)します。  
  
 [このトピックの内容](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Setting_assertions_in_configuration_files"></a> 構成ファイルでのアサーションの設定  
 アサーションは、コード内だけでなく、プログラム構成ファイル内でも設定できます。 詳細については、「<xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>」または「<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>   
 [デバッガーのセキュリティ](../debugger/debugger-security.md)   
 [アプリケーションのトレースとインストルメント](http://msdn.microsoft.com/library/773b6fc4-9013-4322-b728-5dec7a72e743)   
 [方法 : トレースとデバッグを指定して条件付きコンパイルを実行する](http://msdn.microsoft.com/library/56d051c3-012c-42c1-9a58-7270edc624aa)   
 [C#、F#、および Visual Basic のプロジェクトの種類](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [マネージド コードをデバッグする](../debugger/debugging-managed-code.md)



