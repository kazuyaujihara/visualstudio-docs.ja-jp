---
title: マネージド コードの "マネージ最小規則" 規則セット
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 44a50c54-8dd3-42b2-8387-532a150e5a6c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 183923a764cc3462e799c8f67677aa564c5fe59d
ms.sourcegitcommit: b83fefa8177c5554cbe2c59c4d102cbc534f7cc6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69585131"
---
# <a name="managed-minimum-rules-rule-set-for-managed-code"></a>マネージド コードの "マネージ最小規則" 規則セット

マネージ最小規則は、潜在的なセキュリティホール、アプリケーションのクラッシュ、その他の重要な論理エラーやデザインエラーなど、コードの最も重大な問題に焦点を当てています。 この規則セットは、プロジェクト用に作成するカスタム規則セットに含めます。

|ルール|説明|
|----------|-----------------|
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|破棄可能なフィールドを所有する型は、破棄可能でなければなりません|
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|空のファイナライザーを削除します|
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|破棄可能なフィールドは破棄されなければなりません|
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|オーバーライド時に演算子 equals をオーバーロードします`ValueType.Equals`|
