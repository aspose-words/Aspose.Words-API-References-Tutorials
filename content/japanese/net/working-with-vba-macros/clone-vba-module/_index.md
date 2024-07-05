---
title: Word 文書から VBA モジュールを複製する
linktitle: Word 文書から VBA モジュールを複製する
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書から VBA モジュールを複製する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-vba-macros/clone-vba-module/
---

このチュートリアルでは、.NET 用の Aspose.Words ライブラリを使用して、マクロを含む Word 文書から VBA モジュールを複製する方法を説明します。VBA モジュールを複製すると、あるソース ドキュメントから別のドキュメントに VBA コードを再利用またはコピーできます。.NET プロジェクトでコードを理解して実装できるように、手順を追って説明します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C#プログラミング言語の実用的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ
- 複製したいモジュールを含む VBA プロジェクトを含む Word 文書

## ステップ1: ドキュメントディレクトリを定義する
まず、Word文書の場所にディレクトリパスを設定する必要があります。`"YOUR DOCUMENT DIRECTORY"`コード内に適切なパスを追加します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ソースドキュメントを読み込む
次に、VBA プロジェクトと複製するモジュールを含むソース Word 文書を読み込みます。

```csharp
//ソースドキュメントを読み込む
Document doc = new Document(dataDir + "VBA project.docm");
```

## ステップ3: VBAプロジェクトで新しいドキュメントを作成し、モジュールを複製する
空の VBA プロジェクトを使用して新しいドキュメントを作成し、ソース ドキュメントから指定されたモジュールを複製します。

```csharp
//空のVBAプロジェクトで新しいドキュメントを作成する
Document destDoc = new Document { VbaProject = new VbaProject() };

//モジュールを複製する
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## ステップ4: 宛先ドキュメントを保存する
最後に、複製された VBA モジュールを含む宛先ドキュメントをファイルに保存します。

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Aspose.Words for .NET を使用して Vba モジュールを複製するためのサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、マクロを含む Word 文書から VBA モジュールを複製する方法を説明しました。VBA モジュールを複製すると、あるソース ドキュメントの VBA コードを別のドキュメントで簡単に再利用できます。この機能を使用して、さまざまなドキュメントのマクロを整理および管理してください。

### よくある質問

#### Q: VBA モジュールを複製するとはどういうことですか?

A: VBA モジュールの複製とは、VBA コードを含むモジュールをソース Word 文書から別の文書にコピーすることです。これにより、VBA コードをさまざまなコンテキストで再利用したり、他の文書と共有したりできるようになります。

#### Q: Word 文書から VBA モジュールを複製するための前提条件は何ですか?

A: Word 文書から VBA モジュールを複製するには、C# プログラミング言語の実用的な知識が必要です。また、プロジェクトに Aspose.Words for .NET ライブラリをインストールする必要があります。さらに、複製するモジュールを含む VBA プロジェクトを含む Word 文書も必要です。

#### Q: コード内でドキュメントディレクトリを設定するにはどうすればいいですか?

 A: 提供されたコードでは、`"YOUR DOCUMENTS DIRECTORY"` VBA プロジェクトを含む Word 文書が保存されているディレクトリへの適切なパスを指定します。

#### Q: 複製された VBA モジュールを使用して宛先ドキュメントを保存するにはどうすればよいですか?

 A: クローンされたVBAモジュールを含む宛先ドキュメントを保存するには、`Save`方法の`Document`目的の宛先パスとファイル名を指定してクラスを作成します。