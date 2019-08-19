---
title: Windows フォーム アプリを設計する
ms.date: 08/09/2019
ms.topic: conceptual
helpviewer_keywords:
- Windows Forms Designer
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8280a60f1d265336d427079bdef6612b42ed4330
ms.sourcegitcommit: 6b0503ed8d25454d6e39a8e606910b3fa58cf1d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68981638"
---
# <a name="windows-forms-designer-overview"></a>Windows フォーム デザイナーの概要

Visual Studio の Windows フォーム デザイナーでは、Windows フォーム ベースのアプリケーションを作成するための迅速な開発ソリューションが提供されます。 Windows フォーム デザイナーを使うと、フォームへのコントロールの追加、コントロールの位置調整、コントロールのイベントのコード作成を簡単に行うことができます。 Windows フォームについて詳しくは、「[Windows フォームの概要](/dotnet/framework/winforms/windows-forms-overview)」をご覧ください。

## <a name="functionality"></a>機能

デザイナーを使用すると、次のことができます。

- コンポーネント、データ コントロール、または Windows ベースのコントロールをフォームに追加します。

- デザイナーでフォームをダブルクリックしてそのフォームの `Load` イベントに対するコードを記述するか、フォーム上のコントロールをダブルクリックしてコントロールの既定のイベントに対するコードを記述します。

- コントロールを選択して名前を入力し、コントロールの Text プロパティを編集します。

- マウスまたは方向キーでコントロールを移動して、選択したコントロールの配置を調整します。 同様に、Ctrl キーと方向キーを使用して、配置をより正確に調整します。 最後に、Shift キーと方向キーを使用して、コントロールのサイズを調整します。

- **Shift** キーまたは **Ctrl** キーを押しながらクリックして、複数のコントロールを選択します。 **Shift** キーを押しながらクリックすると、最初に選択したコントロールが、サイズを調整または操作するときに最も優先されるコントロールになります。 **Ctrl** キーを押しながらクリックすると、最後に選択したコントロールが優先されるので、新しいコントロールを追加するたびに優先されるコントロールが変わります。 または、選択するコントロールを囲むように選択領域をドラッグして、複数のコントロールを選択することもできます。

> [!NOTE]
> フォームのリソース ( *.resx*) ファイルを変更するには、リソース エディターではなく Windows フォーム デザイナーを使用します。 フォーム ベースの .resx ファイルを編集すると、リソース エディターで行った変更が失われる可能性があることを示す警告が表示されます。 これは、Windows フォーム デザイナーによって .resx ファイルが生成されるためです。

## <a name="see-also"></a>関連項目

- [Windows フォームの概要](/dotnet/framework/winforms/windows-forms-overview)
- [Windows フォームのコントロール](/dotnet/framework/winforms/controls/)
- [Windows フォームのコントロールのアクセシビリティ](/dotnet/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form)
- [Windows フォームでのユーザー入力](/dotnet/framework/winforms/user-input-in-windows-forms)
- [Windows フォームでのデータ バインディング](/dotnet/framework/winforms/windows-forms-data-binding)
- [Windows フォーム アプリを拡張する](/dotnet/framework/winforms/advanced/)