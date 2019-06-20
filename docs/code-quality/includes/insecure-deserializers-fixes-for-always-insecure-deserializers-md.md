---
author: dotpaul
ms.author: paulming
ms.date: 05/01/2019
ms.topic: include
ms.openlocfilehash: bc423f10cfbae0b7a0cdaedb72f6891a0e12d228
ms.sourcegitcommit: b468d71052a1b8a697f477ab23a3644de139f1e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2019
ms.locfileid: "67254374"
---
- 可能であれば、代わりに、セキュリティで保護されたシリアライザーを使用し、**攻撃者を任意の型を逆シリアル化の指定を許可しない**します。 安全なシリアライザーによっては、次のとおりです。
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -使用しないでください<xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>します。 型競合回避モジュールを使用する必要があります、予想されるリストを逆シリアル化された型を制限します。
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft Json.NET - TypeNameHandling.None を使用します。 TypeNameHandling を別の値を使用する必要がありますがある場合は、カスタム ISerializationBinder での予期される一覧に逆シリアル化された型を制限します。
  - Protocol Buffers
- シリアル化されたデータの耐タンパー性を確認します。 シリアル化後に、シリアル化されたデータを暗号で署名します。 逆シリアル化する前に、暗号化署名を検証します。 公開暗号化キーとキーのローテーションの設計を保護します。