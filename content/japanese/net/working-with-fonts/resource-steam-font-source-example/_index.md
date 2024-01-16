---
title: リソース Steam フォント ソースの例
linktitle: リソース Steam フォント ソースの例
second_title: Aspose.Words ドキュメント処理 API
description: リソース ストリーム フォント ソースを使用してカスタム フォントを Aspose.Words for .NET にロードする方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fonts/resource-steam-font-source-example/
---

このチュートリアルでは、Aspose.Words for .NET でリソース フロー フォント ソースを使用する方法を説明します。このフォント ソースを使用すると、リソース ストリームからフォントを読み込むことができます。これは、アプリケーションにカスタム フォントを組み込む場合に役立ちます。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C# プログラミング言語に関する実践的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ

## ステップ 1: ドキュメント ディレクトリを定義する
まず、Word 文書の場所へのディレクトリ パスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で適切なパスを指定します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントをアップロードし、リソース ストリーム フォント ソースを設定する
次に、次のコマンドを使用してドキュメントをロードします。`Document`クラスを作成し、を使用してリソース ストリーム フォント ソースを設定します。`FontSettings.DefaultInstance.SetFontsSources()`クラス。これにより、Aspose.Words がリソース ストリーム内のフォントを検索できるようになります。

```csharp
//ドキュメントをロードし、リソース ストリーム フォント ソースを設定します
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## ステップ 3: ドキュメントを保存する
最後にドキュメントを保存します。フォントは指定されたリソース ストリームからロードされ、ドキュメントに埋め込まれます。

```csharp
//文書を保存する
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Aspose.Words for .NET を使用したリソース Steam フォント ソースのサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET でリソース フロー フォント ソースを使用する方法を学習しました。この機能を使用すると、リソース フィードからフォントを読み込むことができます。これは、ドキュメントにカスタム フォントを埋め込む場合に便利です。さまざまなフォントを試し、Aspose.Words が提供するフォント管理の可能性を探ってください。

### よくある質問

#### Q: フォントをリソース ストリームから Aspose.Words にロードするにはどうすればよいですか?

 A: Aspose.Words のリソース ストリームからフォントを読み込むには、`FontSettings`クラスと`SetFontsSources`リソース ストリームを使用してフォント ソースを指定するメソッド。これにより、フォントを物理ファイルからではなくリソース ストリームから直接ロードできるようになります。

#### Q: Aspose.Words でリソース ストリームを使用してフォント ソースを指定する利点は何ですか?

A: リソース ストリームを使用してフォント ソースを指定すると、次のような利点があります。
- アプリケーションに組み込まれたリソースからフォントをロードできるため、ドキュメントの展開と配布が簡単になります。
- ニーズに応じてさまざまなリソース ストリームからフォントをロードできるため、フォント管理の柔軟性が向上します。

#### Q: .NET アプリケーションのリソース ストリームにフォントを追加するにはどうすればよいですか?

 A: .NET アプリケーションのリソース ストリームにフォントを追加するには、プロジェクト リソースにフォント ファイルを埋め込む必要があります。その後、開発プラットフォームに固有の方法 (例:`GetManifestResourceStream`を使用して`System.Reflection`名前空間)。

#### Q: 異なるリソース ストリームから複数のフォントを 1 つの Aspose.Words ドキュメントにロードすることはできますか?

 A: はい、さまざまなリソース ストリームから複数のフォントを 1 つの Aspose.Words ドキュメントに読み込むことは完全に可能です。を使用して複数のフォント ソースを指定できます。`SetFontsSources`の方法`FontSettings`クラスを作成し、各フォントに適切なリソース ストリームを提供します。

#### Q: Aspose.Words にフォントを読み込むためにどのタイプのリソース ストリームを使用できますか?

A: .NET アプリケーションに組み込まれたリソース ストリーム、外部ファイルからのリソース ストリーム、データベースからのリソース ストリームなど、さまざまな種類のリソース ストリームを使用して Aspose.Words にフォントを読み込むことができます。必ず適切なリソース ストリームを提供してください。セットアップとニーズに基づいてリソースが流れます。