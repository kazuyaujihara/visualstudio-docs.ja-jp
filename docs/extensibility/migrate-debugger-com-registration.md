---
title: 64 ビット デバッガー COM クラスの登録の移行 |Microsoft Docs
ms.date: 11/10/2016
ms.topic: conceptual
ms.assetid: 45cfcee6-7a68-4d4f-b3f6-e2d8a0fa066a
author: gregg-miskelly
ms.author: greggm
manager: jillfra
ms.workload:
- greggm
ms.openlocfilehash: 74fbb959f8272be001aad8a576724d5eb1ad6157
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56712204"
---
# <a name="migrate-64-bit-debugger-com-class-registration"></a>64 ビット デバッガー COM クラスの登録を移行します。

COM に登録するデバッガー拡張機能を regsvr32、regasm を使用するか、レジストリおよび読み込むを直接記述 HKEY_CLASSES_ROOT でクラス*msvsmon.exe* (リモート デバッガー)、これでこれを提供するにはHKEY_CLASSES_ROOT への書き込みをしなくても msvsmon を登録します。 これは従来の .NET デバッガーの式エバリュエーターまたはデバッグ エンジンの読み込みに構成されている、影響、 *msvsmon.exe*プロセス。

## <a name="msvsmon-comclass-def"></a>msvsmon-def comclass

この方法を使用するには追加、  **.msvsmon-comclass-def.json* msvsmon の横にあるファイル (InstallDir:* \Common7\IDE\Remote Debugger\x64*)。

管理されている、1 つを登録する msvsmon-def comclass ファイルの例と 1 つのネイティブ クラスを次に示します。

ファイル名:*MyCompany.MyExample.msvsmon-comclass-def.json*

```json
{
  "managedCOMClasses": [
    {
      "clsid": "{C9F48B25-36ED-4B22-8210-98BC5BE4D1E7}",
      "assemblyName": "MyCompany.MyAssembly",
      "className": "MyCompany.MyNamespace.MyClass"
    }
  ],
  "nativeCOMClasses": [
    {
      "clsid": "{42A476E9-8FA7-44D5-ADFE-216AD371EEC9}",
      "dllPath": "MyExample.dll"
    }
  ]
}
```
