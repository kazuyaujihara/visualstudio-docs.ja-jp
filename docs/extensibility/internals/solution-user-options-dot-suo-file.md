---
title: ソリューションユーザーオプション (..Suo) File |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .suo files, VSPackages
- suo files, VSPackages
- solutions, .suo files
- solutions, user options
- solution user options (.suo) file
ms.assetid: 75258e0d-600d-4a3d-94f4-3d7ac12cb47c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6f21e4a4a6530692709247e64b0d84aa7b06eb3a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72723810"
---
# <a name="solution-user-options-suo-file"></a>ソリューション ユーザー オプション (.Suo) ファイル
ソリューションユーザーオプション (.suo) ファイルには、ユーザーごとのソリューションオプションが含まれています。 このファイルをソースコード管理にチェックインしないでください。

 ソリューションユーザーオプション (.suo) ファイルは、バイナリ形式で格納された構造化ストレージ (複合ファイル) です。 ユーザー情報をストリームに保存します。ストリームの名前は、.suo ファイル内の情報を識別するために使用されるキーです。 ソリューションユーザーオプションファイルは、ユーザー設定を保存するために使用され、Visual Studio がソリューションを保存するときに自動的に作成されます。

 環境で .suo ファイルが開かれると、現在読み込まれているすべての Vspackage が列挙されます。 VSPackage が <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> インターフェイスを実装している場合、環境は、.suo ファイルからすべてのデータを読み込むように求める VSPackage の <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.LoadUserOptions%2A> メソッドを呼び出します。

 VSPackage は、.suo ファイルに書き込まれたストリームを知る必要があります。 VSPackage は、記述されたストリームごとに、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.LoadPackageUserOpts%2A> を通じて環境にコールバックし、ストリームの名前であるキーによって識別される特定のストリームを読み込みます。 次に、環境は VSPackage にコールバックし、ストリームの名前と <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.LoadPackageUserOpts%2A> メソッドへの `IStream` ポインターを渡して、特定のストリームを読み取ります。

 その時点で、`LoadUserOptions` に別の呼び出しが行われ、.suo ファイルの別のセクションに読み取る必要があるかどうかが確認されます。 このプロセスは、.suo ファイル内のすべてのデータストリームが環境によって読み取られ、処理されるまで続きます。

 ソリューションが保存または閉じられると、環境は <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.SaveUserOptions%2A> メソッドへのポインターを使用して <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.SavePackageSolutionProps%2A> メソッドを呼び出します。 保存するバイナリ情報を含む `IStream` は、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.WriteUserOptions%2A> メソッドに渡されます。このメソッドは、.suo ファイルに情報を書き込み、もう一度 `SaveUserOptions` メソッドを呼び出して、.suo ファイルに書き込む情報の別のストリームがあるかどうかを確認します。

 これらの2つのメソッド (`SaveUserOptions` と `WriteUserOptions`) は、.suo ファイルに保存される情報のストリームごとに再帰的に呼び出され、`IVsSolutionPersistence` へのポインターで渡されます。 これらは再帰的に呼び出され、.suo ファイルへの複数のストリームの書き込みを可能にします。 このようにすると、ユーザー情報はソリューションと共に保持され、次にソリューションを開いたときに確実に表示されます。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>
- [ソリューション](../../extensibility/internals/solutions-overview.md)