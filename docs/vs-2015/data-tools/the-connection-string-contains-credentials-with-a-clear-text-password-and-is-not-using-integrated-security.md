---
title: 接続文字列がクリア テキスト パスワードを使用して資格情報を含むし、統合セキュリティを使用していない |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0538620cde170ea9ae033a510c7fa01ff20c64d3
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60093151"
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>接続文字列にはクリア テキスト パスワード付きの資格情報が含まれていて、統合セキュリティは使用されていません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

重要情報を含む接続文字列を現在の DBML ファイルとアプリケーション構成ファイルに保存しますか?   重要情報を含めずに接続文字列を保存する場合は、[いいえ] をクリックします。  
  
 機密情報 (接続文字列に含まれているパスワード) を含むデータ接続を扱う場合は、接続文字列をプロジェクトの DBML ファイルおよびアプリケーション構成ファイルに保存するときに、機密情報を含めるかどうかを選択するオプションが提供されます。  
  
> [!WARNING]
>  **[接続]** プロパティの **[アプリケーション設定]** プロパティが明示的に **[False]** に設定されている場合、パスワードは DBML ファイルに追加されます。  
  
### <a name="to-save-the-connection-string-with-the-sensitive-information-in-the-projects-application-settings"></a>接続文字列を機密情報と共にプロジェクトのアプリケーション設定に保存するには  
  
- **[はい]** をクリックします。  
  
     接続文字列がアプリケーション設定として格納されます。 接続文字列には、プレーンテキストの機密情報が含まれます。 DBML ファイルには機密情報は含まれません。  
  
### <a name="to-save-the-connection-string-without-the-sensitive-information-in-the-projects-application-settings"></a>機密情報を含めずに接続文字列をプロジェクトのアプリケーション設定に保存するには  
  
- **[いいえ]** をクリックします。  
  
     接続文字列がアプリケーション設定として格納されますが、パスワードは含まれません。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio の LINQ to SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
