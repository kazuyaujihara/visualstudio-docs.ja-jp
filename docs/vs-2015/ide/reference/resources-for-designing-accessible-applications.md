---
title: ユーザー補助アプリケーションのデザイン リソース | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- accessibility, Windows applications
- Windows applications, accessibility
- Web applications, accessibility
- accessibility, Web applications
ms.assetid: 426bf023-bb34-43c4-9edb-c307191c8170
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 35e84dc3ae817ab3c5346d83fc5f37934a34e0f9
ms.sourcegitcommit: b56dc6fadc6c924beed36bb4c2ccc16cf6bcfa1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2019
ms.locfileid: "68740166"
---
# <a name="resources-for-designing-accessible-applications"></a>ユーザー補助アプリケーションのデザイン リソース
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

ユーザー補助 Windows アプリケーションおよび Web サイトを開発するためのヒントと例、およびユーザー補助設計をサポートする技術については、以下のリンク先を参照してください。 ユーザー補助についての一般的な情報は、Web サイト [http://www.microsoft.com/enable/](http://www.microsoft.com/enable/) にあります。  
  
## <a name="technologies"></a>テクノロジ  
  
- **Microsoft Active Accessibility** Microsoft Windows 上で実行するアプリケーションを開発する際に、ユーザー補助機能のサポートを向上できる COM ベースの技術です。 この技術では、ユーザー インターフェイス要素についての情報を公開するための信頼できるメソッドを提供する COM インターフェイスとアプリケーション プログラミング要素に加え、オペレーティング システムに組み込まれているダイナミック リンク ライブラリも用意されます。 詳細については、「[https://msdn.microsoft.com/library/windows/desktop/dd373592(v=vs.85).aspx](https://msdn.microsoft.com/library/windows/desktop/dd373592\(v=vs.85\).aspx)」を参照してください。  
  
- **Microsoft .NET Speech 技術** Microsoft .NET Speech SDK は、Microsoft [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] コントロール、Microsoft Internet Explorer Speech アドイン、サンプル アプリケーション、およびドキュメントを 1 つにしたセットであり、Web 開発者はこの SDK を使って、音声対応の [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] アプリケーションを作成、デバッグ、および配置できます。 各ツールはシームレスに Microsoft Visual Studio と統合されるため、開発者は使い慣れた環境で開発を行うことができます。 詳細については、「[https://msdn.microsoft.com/library/ms950383.aspx](https://msdn.microsoft.com/library/ms950383.aspx)」を参照してください。  
  
- **SAMI 1.0 の理解** Microsoft SAMI (Synchronized Accessible Media Interchange) テクノロジを利用すると、開発者は PC マルチメディアの音声コンテンツにキャプションを付けることができます。 詳細については、「[https://msdn.microsoft.com/library/ms971327.aspx](https://msdn.microsoft.com/library/ms971327.aspx)」を参照してください。  
  
## <a name="windows-applications"></a>Windows アプリケーション  
  
- [チュートリアル: アクセス可能な windows ベースのアプリケーション](https://msdn.microsoft.com/library/654c7f2f-1586-480b-9f12-9d9b8f5cc32b)の作成このトピックでは、サンプル windows アプリケーションで、認定 windows ロゴの5つのアクセシビリティ要件を含めるための詳細な手順について説明します。  
  
- [キーボード ユーザー インターフェイス デザインのガイドライン](/previous-versions/windows/desktop/dnacc/guidelines-for-keyboard-user-interface-design) この技術情報では、ユーザーがキーボードから操作できる Windows アプリケーション ユーザー インターフェイスの設計方法について説明します。  
  
- [コンソール ユーザー補助](/previous-versions/windows/desktop/dnacc/console-accessibility) この技術情報では、ユーザー補助のサポートのために Windows XP でコンソールを表示するための API とイベントについて説明します。 
  
## <a name="web-sites"></a>Web サイト  
  
- [チュートリアル: イメージコントロール、メニューコントロール、および AutoPostBack](https://msdn.microsoft.com/library/ff7b5021-48b3-46bf-921f-9fe1e0e32202)を使用するためのアクセシビリティに関するガイドラインこのトピックでは、web 用のユーザー補助機能のデザインに関するヒントだけでなく、ユーザー補助コントロールをサンプル web ページに含めるための詳細な手順について説明します。  
  
- [Web ページのユーザー補助機能の強化](/previous-versions/windows/desktop/dnacc/making-web-pages-more-accessible) この技術情報では、ユーザー補助機能を持つ HTML 3.2 の要素が一覧にしてあります。また、Web サイトの開発で使用してユーザー補助機能を強化するための要素も示しています。 
  
- [ユーザー補助機能を持つ Web ページを DHTML を使って作成](/previous-versions//ms528445(v=vs.85)) この技術情報には、ユーザー補助機能を持つ HTML 4.0 要素およびユーザー補助機能を持つ Web 設計のヒントが一覧にしてあります。 
  
- [ユーザー補助機能を持たない Web ページの代替テキスト](/previous-versions/windows/desktop/dnacc/text-alternatives-to-inaccessible-web-pages) この技術情報では、XML および XSLT を使用して、テキストのみのバージョンなど、同じ Web ページを複数の形式で表示する方法について説明しています。 
  
### <a name="third-party-resources"></a>サードパーティのリソース  
  
- **W3C (World Wide Web Consortium) の WAI (Web Accessibility Initiative)** この Web サイトには、ユーザー補助機能を持つ Web サイトの開発に関するガイドラインと技術情報が示されています。 詳細については、「[http://www.w3.org/WAI/GL/](http://www.w3.org/WAI/GL/)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio のユーザー補助機能](../../ide/reference/accessibility-features-of-visual-studio.md)
