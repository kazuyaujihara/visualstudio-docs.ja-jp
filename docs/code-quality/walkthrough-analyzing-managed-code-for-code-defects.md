---
title: コード障害のためのマネージコードの分析のチュートリアル |Microsoft Docs
ms.date: 01/29/2018
ms.topic: conceptual
helpviewer_keywords:
- code analysis [Visual Studio]
- managed code, analyzing
author: mikadumont
ms.author: midumont
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 4a00fdb2a41a03554113f2ecb626185aab2c74d5
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547998"
---
# <a name="walkthrough-use-static-code-analysis-to-find-code-defects"></a>チュートリアル: 静的コード分析を使用してコード障害を検出する

このチュートリアルでは、従来のコード分析を使用して、マネージプロジェクトのコード障害を分析します。

この記事では、.NET のデザインガイドラインに準拠するために、レガシ分析を使用して .NET マネージコードアセンブリを分析するプロセスについて説明します。

## <a name="create-a-class-library"></a>クラスライブラリを作成する

### <a name="to-create-a-class-library"></a>クラス ライブラリを作成するには

1. **[ファイル]** メニューで、 **[新規]**  >  **[プロジェクト]** の順に選択します。

1. **[新しいプロジェクト]** ダイアログボックスで、[**インストールされ** > た**ビジュアルC#** ] を展開し、 **[Windows デスクトップ]** を選択します。

1. **[クラスライブラリ (.NET Framework)]** テンプレートを選択します。

1. **[名前]** テキストボックスに「 **CodeAnalysisManagedDemo** 」と入力し、[ **OK]** をクリックします。

1. プロジェクトが作成されたら、 *Class1.cs*ファイルを開きます。

1. Class1.cs の既存のテキストを次のコードに置き換えます。

   ```csharp
   using System;

   namespace testCode
   {
       public class demo : Exception
       {
           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int item { get { return _item; } }
       }
   }
   ```

1. Class1.cs ファイルを保存します。

## <a name="analyze-the-project"></a>プロジェクトを分析する

### <a name="to-analyze-a-managed-project-for-code-defects"></a>マネージプロジェクトでコード障害を分析するには

1. **ソリューションエクスプローラー**で CodeAnalysisManagedDemo プロジェクトを選択します。

1. **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

     [CodeAnalysisManagedDemo のプロパティ] ページが表示されます。

1. **[コード分析]** タブをクリックします。

1. **[ビルドでコード分析を有効に**する] チェックボックスがオンになっていることを確認します。

1. **[この規則セットを実行]** ドロップダウンリストで、 **[Microsoft すべての規則]** を選択します。

1. **[ファイル]** メニューの **[選択した項目を保存]** をクリックし、プロパティページを閉じます。

1. **[ビルド]** メニューの **[CodeAnalysisManagedDemo のビルド]** をクリックします。

    CodeAnalysisManagedDemo プロジェクトビルドの警告は、 **[エラー一覧]** ウィンドウと **[出力]** ウィンドウに表示されます。

## <a name="correct-the-code-analysis-issues"></a>コード分析の問題を修正する

### <a name="to-correct-code-analysis-rule-violations"></a>コード分析規則の違反を修正するには

1. **[表示]** メニューの **[エラー一覧]** をクリックします。

    選択した開発者プロファイルによっては、 **[表示]** メニューの **[その他のウィンドウ]** をポイントし、 **[エラー一覧]** を選択しなければならない場合があります。

1. **ソリューション エクスプローラー**で、 **[すべてのファイルを表示]** をクリックします。

1. [プロパティ] ノードを展開し、 *AssemblyInfo.cs*ファイルを開きます。

1. 警告を修正するには、次のヒントを使用します。

   [CA1014アセンブリに CLSCompliantAttribute](../code-quality/ca1014-mark-assemblies-with-clscompliantattribute.md)を設定します。Microsoft Design: ' demo ' は CLSCompliantAttribute でマークする必要があり、その値は true である必要があります。

   1. AssemblyInfo.cs ファイルに`using System;`コードを追加します。

   1. 次に、コード`[assembly: CLSCompliant(true)]`を AssemblyInfo.cs ファイルの末尾に追加します。

   [CA1032標準の例外コンストラクター](../code-quality/ca1032-implement-standard-exception-constructors.md)を実装します。Microsoft の設計:このクラスに次のコンストラクターを追加します: public demo (String)

   1. コンストラクター `public demo (String s) : base(s) { }`をクラス`demo`に追加します。

   [CA1032標準の例外コンストラクター](../code-quality/ca1032-implement-standard-exception-constructors.md)を実装します。Microsoft の設計:このクラスに次のコンストラクターを追加します: public demo (String, Exception)

   1. コンストラクター `public demo (String s, Exception e) : base(s, e) { }`をクラス`demo`に追加します。

   [CA1032標準の例外コンストラクター](../code-quality/ca1032-implement-standard-exception-constructors.md)を実装します。Microsoft の設計:このクラスに次のコンストラクターを追加します: protected demo (SerializationInfo, StreamingContext)

   1. Class1.cs ファイルの`using System.Runtime.Serialization;`先頭にコードを追加します。

   1. 次に、コンストラクターを追加します。`protected demo (SerializationInfo info, StreamingContext context) : base(info, context) { } to the class demo.`

   [CA1032標準の例外コンストラクター](../code-quality/ca1032-implement-standard-exception-constructors.md)を実装します。Microsoft の設計:このクラスに次のコンストラクターを追加します: public demo ()

   1. コンストラクター `public demo () : base() { }`をクラス`demo`に追加**します。**

   [CA1709識別子は、大文字](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)と小文字が正しく区別されます。Microsoft. 名前付け:' Testcode ' に変更して、名前空間名 ' testCode ' の大文字と小文字を修正してください。

   1. 名前空間`testCode`の大文字と小`TestCode`文字の区別をに変更します。

   [CA1709識別子は、大文字](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)と小文字が正しく区別されます。Microsoft. 名前付け:' Demo ' に変更して、型名 ' demo ' の大文字と小文字の指定を訂正してください。

   1. メンバーの名前をに`Demo`変更します。

   [CA1709識別子は、大文字](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)と小文字が正しく区別されます。Microsoft. 名前付け:' Item ' に変更して、メンバー名 ' item ' の大文字と小文字の指定を訂正してください。

   1. メンバーの名前をに`Item`変更します。

   [CA1710識別子には正しいサフィックス](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)が必要です。Microsoft. 名前付け:' TestCode. demo ' の名前を ' Exception ' で終わるように変更します。

   1. クラスの名前とそのコンストラクターをに`DemoException`変更します。

   [CA2210アセンブリには有効な厳密](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md)な名前が必要です。厳密な名前のキーを使用して ' CodeAnalysisManagedDemo ' に署名します。

   1. **[プロジェクト]** メニューの **[CodeAnalysisManagedDemo のプロパティ]** をクリックします。

      プロジェクトのプロパティが表示されます。

   1. **[署名]** タブを選択します。

   1. **[アセンブリの署名]** チェックボックスをオンにします。

   1. [**文字列名キーファイルを選択**してください] ボックスの一覧で、[新規] を選択 **\<します。>** 。

      **[厳密な名前キーの作成]** ダイアログボックスが表示されます。

   1. **[キーファイル名]** に「testkey」と入力します。

   1. パスワードを入力し、[ **OK]** を選択します。

   1. **ファイル** メニューの **選択した項目の保存** をクリックし、プロパティページ を閉じます。

   [CA2237:ISerializable 型を SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)に設定します。Microsoft. 使用法:この型が ISerializable を実装しているため、型 ' demo ' に [Serializable] 属性を追加します。

   1. 属性をクラス`demo`に追加します。 `[Serializable ()]`

   変更が完了すると、Class1.cs ファイルは次のようになります。

   ```csharp
   using System;
   using System.Runtime.Serialization;

   namespace TestCode
   {
       [Serializable()]
       public class DemoException : Exception
       {
           public DemoException () : base() { }
           public DemoException(String s) : base(s) { }
           public DemoException(String s, Exception e) : base(s, e) { }
           protected DemoException(SerializationInfo info, StreamingContext context) : base(info, context) { }

           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int Item { get { return _item; } }
       }
   }
   ```

1. プロジェクトをリビルドします。

## <a name="exclude-code-analysis-warnings"></a>コード分析の警告を除外する

1. 残りの各警告について、次の操作を行います。

    1. **エラー一覧**で警告を選択します。

    1. 右クリックメニュー (コンテキストメニュー) で、[**抑制ファイルで** **非** > 表示にする] を選択します。

1. プロジェクトをリビルドします。

     プロジェクトがビルドされ、警告やエラーは発生しません。

## <a name="see-also"></a>関連項目

[マネージコードのコード分析](../code-quality/code-analysis-for-managed-code-overview.md)