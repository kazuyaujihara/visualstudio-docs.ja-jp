---
title: 移植性に関する警告
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.PortabilityRules
helpviewer_keywords:
- portability warnings
- managed code analysis warnings, portability warnings
- warnings, portability
ms.assetid: 902e859a-2153-4970-baaa-8a5b4a11806f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 072858a9faafe312fd7c8314e7f25cf581c40844
ms.sourcegitcommit: e95dd8cedcd180e0bce6a75c86cf861757918290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72163068"
---
# <a name="portability-warnings"></a>移植性に関する警告
移植性の警告は、異なるオペレーティングシステム間での移植性をサポートします。

## <a name="in-this-section"></a>このセクションの内容

|Rule|説明|
|----------|-----------------|
|[CA1900:値型フィールドはポータブル @ no__t-0 にする必要があります|この規則では、明示的なレイアウト属性を使用して宣言された構造体が、64ビットオペレーティングシステム上のアンマネージコードにマーシャリングされるときに正しく配置されることを確認します。|
|[CA1901:P/Invoke 宣言はポータブル @ no__t-0 にする必要があります|このルールは、P/Invoke の各パラメーターと戻り値のサイズを評価し、32ビットおよび64ビットのオペレーティングシステムでアンマネージコードにマーシャリングされたときに、そのサイズが正しいことを確認します。|
|[CA1903:対象のフレームワークから API のみを使用する @ no__t-0|メンバーまたは型が、プロジェクトの対象のフレームワークに含まれていない Service Pack で導入されたメンバーまたは型を使用しています。|
