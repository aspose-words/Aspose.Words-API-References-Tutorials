---
title: 埋め込まれた Arial および Times Roman フォントをスキップして PDF サイズを最適化
linktitle: 埋め込まれた Arial および Times Roman フォントをスキップして PDF サイズを最適化
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Arial および Times Roman フォントを埋め込まずに最適化された PDF を生成するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

この記事では、Aspose.Words for .NET を使用して、埋め込まれた Arial および Times Roman フォントをメタファイル サイズにスキップすることで PDF サイズを最適化する機能の使用方法について、ステップ バイ ステップ ガイドを提供します。コードの各部分を詳しく説明します。このチュートリアルの最後には、ドキュメントでフォント埋め込みモード オプションを構成し、Arial および Times Roman フォントを埋め込まずに PDF を生成する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで参照できます。

## ステップ1: ドキュメントディレクトリを定義する

まず、ドキュメントが保存されているディレクトリへのパスを定義する必要があります。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントをアップロードする

次に、処理するドキュメントを読み込む必要があります。この例では、ドキュメントの名前は「Rendering.docx」で、指定されたドキュメント ディレクトリにあると想定しています。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ3: フォント埋め込みによるPDF保存オプションを設定する

生成されたPDFにArialとTimes Romanフォントを埋め込まないようにするには、`PdfSaveOptions`オブジェクトを設定し、`FontEmbeddingMode`財産に`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## ステップ4: 埋め込みフォントなしで文書をPDFとして保存する

最後に、以前に設定した保存オプションを使用して、ドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

以上です。Aspose.Words for .NET を使用して、Arial および Times Roman フォントを埋め込まずに PDF を正常に生成できました。

### Aspose.Words for .NET を使用して、メタファイル サイズで埋め込まれた Arial および Times Roman フォントをスキップするサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して、PDF ドキュメントで Arial および Times Roman フォントの埋め込みを無効にする方法を説明しました。説明されている手順に従うと、これらの特定のフォントを埋め込まずに PDF ファイルを生成できます。これにより、ファイル サイズが削減され、さまざまなプラットフォーム間でのドキュメントの互換性が向上します。この機能を使用する場合は、フォントの埋め込みを無効にした場合の影響を考慮してください。Aspose.Words for .NET のその他の機能を自由に調べて、PDF ファイルの生成を最適化してください。

### よくある質問

#### Q: PDF ドキュメントで Arial および Times Roman フォントの埋め込みを無効にするとは何ですか? また、それが重要なのはなぜですか?
A: PDF ドキュメントへの Arial および Times Roman フォントの埋め込みを無効にすると、生成された PDF ファイルにこれらのフォントが含まれなくなります。これは、PDF リーダー システムで既に一般的に使用されているフォントが含まれないようにすることで、PDF ファイルのサイズを縮小する上で重要です。また、さまざまなデバイスやプラットフォーム間で PDF ドキュメントの互換性が向上し、外観が一貫していることも保証できます。

#### Q: Aspose.Words for .NET を設定して、Arial および Times Roman フォントを PDF ドキュメントに埋め込まないようにするにはどうすればよいですか?
A: Aspose.Words for .NET を構成して、Arial および Times Roman フォントを PDF ドキュメントに埋め込まないようにするには、次の手順に従います。

ドキュメントが保存されているディレクトリパスを次のように設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリの実際のパスを入力します。

処理したい文書をロードします。`Document`クラスと指定されたドキュメント パス。

インスタンスを作成する`PdfSaveOptions`クラスを設定し、`FontEmbeddingMode`財産に`PdfFontEmbeddingMode.EmbedAll`これにより、生成された PDF ファイルに Arial と Times Roman を除くすべてのフォントが埋め込まれます。

使用`Save`方法の`Document`以前に設定した保存オプションを指定して、ドキュメントを PDF 形式で保存するオブジェクト。

#### Q: PDF ドキュメントで Arial および Times Roman フォントの埋め込みを無効にするとどのような利点がありますか?
A: PDF ドキュメントで Arial および Times Roman フォントの埋め込みを無効にすると、次のような利点があります。

PDF ファイル サイズの縮小: Arial や Times Roman などの一般的なフォントの埋め込みを避けることで、PDF ファイル サイズを縮小でき、ファイルの保存、共有、転送が容易になります。

互換性の向上: PDF リーダー システムで一般的に使用できるフォントを使用することで、さまざまなデバイスやプラットフォームでのドキュメントの互換性と外観が向上します。

#### Q: PDF ドキュメントで Arial フォントと Times Roman フォントの埋め込みを無効にすると、どのような影響がありますか?
A: PDF ドキュメントで Arial および Times Roman フォントの埋め込みを無効にすると、次のような結果になります。

異なる外観: PDF を開いたシステムで Arial および Times Roman フォントが使用できない場合は、代替フォントが使用されるため、意図した外観と異なる可能性があります。

読みやすさの問題: 使用される代替フォントは元のフォントほど読みやすくない場合があり、ドキュメントの読みやすさに影響する可能性があります。