---
title: Word ドキュメントから Vba モジュールのクローンを作成する
linktitle: Word ドキュメントから Vba モジュールのクローンを作成する
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書から VBA モジュールのクローンを作成する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-vba-macros/clone-vba-module/
---

このチュートリアルでは、.NET 用の Aspose.Words ライブラリを使用して、マクロを含む Word ドキュメントから VBA モジュールのクローンを作成する方法を説明します。 VBA モジュールを複製すると、あるソース ドキュメントから別のドキュメントに VBA コードを再利用またはコピーできます。 .NET プロジェクトのコードを理解して実装できるように、段階的に説明します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C# プログラミング言語に関する実践的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ
- クローンを作成するモジュールを含む VBA プロジェクトを含む Word 文書

## ステップ 1: ドキュメント ディレクトリを定義する
まず、Word 文書の場所へのディレクトリ パスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で適切なパスを指定します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ソースドキュメントをロードする
次に、VBA プロジェクトとクローンを作成するモジュールを含むソース Word ドキュメントを読み込みます。

```csharp
//ソースドキュメントをロードします
Document doc = new Document(dataDir + "VBA project.docm");
```

## ステップ 3: VBA プロジェクトで新しいドキュメントを作成し、モジュールのクローンを作成する
空の VBA プロジェクトで新しいドキュメントを作成し、ソース ドキュメントから指定されたモジュールのクローンを作成します。

```csharp
//空の VBA プロジェクトを使用して新しいドキュメントを作成する
Document destDoc = new Document { VbaProject = new VbaProject() };

//モジュールのクローンを作成する
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## ステップ 4: 宛先ドキュメントを保存する
最後に、複製された VBA モジュールを含む宛先ドキュメントをファイルに保存します。

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Aspose.Words for .NET を使用した Clone Vba モジュールのサンプル ソース コード 
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
このチュートリアルでは、Aspose.Words for .NET を使用して、マクロを含む Word 文書から VBA モジュールのクローンを作成する方法を説明しました。 VBA モジュールのクローンを作成すると、あるソース ドキュメントの VBA コードを別のドキュメントで簡単に再利用できます。この機能を自由に使用して、さまざまなドキュメント内のマクロを整理および管理してください。

### よくある質問

#### Q: VBA モジュールの複製とは何ですか?

A: VBA モジュールの複製は、VBA コードを含むモジュールをソース Word ドキュメントから別のドキュメントにコピーすることで構成されます。これにより、VBA コードをさまざまなコンテキストで再利用したり、他のドキュメントと共有したりできます。

#### Q: Word 文書から VBA モジュールを複製するための前提条件は何ですか?

A: Word 文書から VBA モジュールのクローンを作成するには、C# プログラミング言語に関する実践的な知識が必要です。 Aspose.Words for .NET ライブラリをプロジェクトにインストールする必要もあります。また、クローンを作成するモジュールを含む VBA プロジェクトを含む Word 文書も必要です。

#### Q: コード内でドキュメント ディレクトリを設定するにはどうすればよいですか?

 A: 提供されたコードでは、置き換える必要があります。`"YOUR DOCUMENTS DIRECTORY"` VBA プロジェクトを含む Word 文書が配置されているディレクトリへの適切なパスを置き換えます。

#### Q: クローンされた VBA モジュールを含む宛先ドキュメントを保存するにはどうすればよいですか?

 A: クローンされた VBA モジュールを含む宛先ドキュメントを保存するには、`Save`の方法`Document`目的の宛先パスとファイル名を指定してクラスを作成します。