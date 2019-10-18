---
title: 暗号化警告
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d96723ea-a293-488d-b9db-adb437e50cdd
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c72dd1455405ecbabb86ca10744639d402881cef
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72449144"
---
# <a name="cryptography-warnings"></a>暗号化警告
暗号化警告では、暗号化を適切に使用することで、ライブラリとアプリケーションの安全性を高めています。 この警告によって、プログラムにセキュリティ上の欠陥が含まれるのを防ぐことができます。 この警告のいずれかを無効にする場合、明確にコードに理由を記載し、開発プロジェクトの指定されたセキュリティ管理者にも報告します。

|規則|説明|
|----------|-----------------|
|[CA5350: 脆弱な暗号アルゴリズムを使用しないでください。](../code-quality/ca5350.md)|現在、さまざまな理由で弱い暗号化アルゴリズムとハッシュ関数が使用されていますが、保護対象のデータの機密性や整合性を保証するためにこれらを使用しないでください。        このルールは、コードで TripleDES、SHA1、または RIPEMD160 アルゴリズムが検出されるとトリガーされます。|
|[CA5351 破られた暗号アルゴリズムを使用しないでください](../code-quality/ca5351.md)|破られた暗号アルゴリズムはセキュアであるとは見なされず、それらを使用しないことを強くお勧めします。 このルールは、コードに MD5 ハッシュ アルゴリズムや、DES か RC2 のいずれかの暗号化アルゴリズムが検出されるとトリガーされます。|
