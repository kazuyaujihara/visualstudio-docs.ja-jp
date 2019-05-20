---
title: 単体テストを作成するサンプル プロジェクト | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit test sample [Visual Studio]
- unit tests, samples
ms.assetid: db80aaf2-0652-4d3f-a8c5-2a98fd8502a2
caps.latest.revision: 32
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 67ebbde52facf50eff534322d85a926968acdf0d
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65705958"
---
# <a name="sample-project-for-creating-unit-tests"></a>単体テストを作成するサンプル プロジェクト
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このサンプル コードは、次のチュートリアルで使用するために用意されています。  
  
- [チュートリアル: マネージ コードを作成して、単体テストを実行して](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)します。 このチュートリアルでは、単体テストの作成とカスタマイズ、実行、およびテスト結果の検討の手順について説明します。  
  
- [チュートリアル: テストの実行し、コード カバレッジの表示](https://msdn.microsoft.com/d4aab8e2-2140-4975-b4e3-41ef3fa944c8)します。 このチュートリアルでは、テストされているプロジェクトのコードの割合を示すコード カバレッジ データを表示する方法を説明します。  
  
- [チュートリアル: コマンド ライン テスト ユーティリティの使用](https://msdn.microsoft.com/library/52c11992-9e94-4067-a4b7-59f19d69d867)。 このチュートリアルでは、MSTest.exe コマンドライン ユーティリティを使用してテストを実行し、結果を表示します。  
  
## <a name="sample-code"></a>サンプル コード  
 このサンプルにある唯一の意図的なエラーは、Debit メソッドで、"m_balance += amount" の等号の前はプラス (+) ではなくマイナス (-) にする必要があるということです。  
  
```  
using System;   
  
namespace BankAccountNS  
{  
    /// <summary>   
    /// Bank Account demo class.   
    /// </summary>   
    public class BankAccount  
    {  
        private string m_customerName;  
  
        private double m_balance;  
  
        private bool m_frozen = false;  
  
        private BankAccount()  
        {  
        }  
  
        public BankAccount(string customerName, double balance)  
        {  
            m_customerName = customerName;  
            m_balance = balance;  
        }  
  
        public string CustomerName  
        {  
            get { return m_customerName; }  
        }  
  
        public double Balance  
        {  
            get { return m_balance; }  
        }  
  
        public void Debit(double amount)  
        {  
            if (m_frozen)  
            {  
                throw new Exception("Account frozen");  
            }  
  
            if (amount > m_balance)  
            {  
                throw new ArgumentOutOfRangeException("amount");  
            }  
  
            if (amount < 0)  
            {  
                throw new ArgumentOutOfRangeException("amount");  
            }  
  
            m_balance += amount; // intentionally incorrect code  
        }  
  
        public void Credit(double amount)  
        {  
            if (m_frozen)  
            {  
                throw new Exception("Account frozen");  
            }  
  
            if (amount < 0)  
            {  
                throw new ArgumentOutOfRangeException("amount");  
            }  
  
            m_balance += amount;  
        }  
  
        private void FreezeAccount()  
        {  
            m_frozen = true;  
        }  
  
        private void UnfreezeAccount()  
        {  
            m_frozen = false;  
        }  
  
        public static void Main()  
        {  
            BankAccount ba = new BankAccount("Mr. Bryan Walton", 11.99);   
  
            ba.Credit(5.77);  
            ba.Debit(11.22);  
            Console.WriteLine("Current balance is ${0}", ba.Balance);  
        }  
  
    }  
}  
```  
  
 /* 例として登場する企業、組織、製品、ドメイン名、電子メール アドレス、ロゴ、人物、場所、およびイベントはすべて架空のものです。  実在する会社、組織、製品、ドメイン名、電子メールアドレス、ロゴ、人物、場所、イベントなどとは一切関係ありません。 \*/  
  
## <a name="working-with-the-code"></a>コードの操作  
 このコードを操作するには、必要なプロジェクトを [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] で作成する必要があります。 「チュートリアルを準備する」セクションの手順に従って[チュートリアル。マネージ コードを作成して、単体テストを実行して](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)します。  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル: 作成して、マネージ コードの単体テストの実行](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)   
 [チュートリアル: テストの実行し、コード カバレッジの表示](https://msdn.microsoft.com/d4aab8e2-2140-4975-b4e3-41ef3fa944c8)   
 [チュートリアル : コマンド ライン テスト ユーティリティの使用](https://msdn.microsoft.com/library/52c11992-9e94-4067-a4b7-59f19d69d867)
