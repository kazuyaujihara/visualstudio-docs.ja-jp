---
title: XAML 概要
ms.date: 07/31/2019
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a9b04012e2f0b046b3fd31058c9838740e833281
ms.sourcegitcommit: 90c3187d804ad7544367829d07ed4b47d3f8a72d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "68823918"
---
# <a name="overview-of-xaml"></a>XAML の概要

Extensible Application Markup Language (XAML) は XML を基盤とする宣言型言語です。 XAML は、ユーザー インターフェイスを構築するために、次の種類のアプリケーションで広く使用されています。

- [Windows Presentation Foundation (WPF) アプリ](/dotnet/framework/wpf/advanced/xaml-in-wpf)
- [ユニバーサル Windows プラットフォーム (UWP) アプリ](/windows/uwp/xaml-platform/xaml-overview)
- [Xamarin.Forms アプリ](/xamarin/xamarin-forms/xaml/)

次の XAML コードでは、単純なボタン コントロールが定義されます。

```xaml
<Button Click="ButtonClick">Show updates</Button>
```

XAML は、[Windows WorkFlow Foundation (WF) アプリ](/dotnet/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml)のワークフローを定義するためにも使用されます。

## <a name="xaml-designer"></a>XAML デザイナー

Visual Studio と Blend for Visual Studio には、WPF、UWP、Xamarin. Forms アプリのユーザー インターフェイス (UI) を構築するのに役立つ XAML デザイナーが付属しています。 [ツールボックス] または [アセット] ウィンドウからコントロールをドラッグし、プロパティ ウィンドウのプロパティを設定できます。 これらのアクションを実行するとき、Visual Studio と Blend for Visual Studio では、それに対応する XAML コードが作成されます。 XAML コードを直接編集する場合、それを行うこともできます。

このドキュメント セットの記事では、Visual Studio と Blend for Visual Studio の XAML デザイナーについて説明します。

## <a name="see-also"></a>関連項目

- [WPF アプリの XAML](/dotnet/framework/wpf/advanced/xaml-in-wpf)
- [UWP アプリの XAML](/windows/uwp/xaml-platform/xaml-overview)
- [Xamarin.Forms アプリの XAML](/xamarin/xamarin-forms/xaml/)