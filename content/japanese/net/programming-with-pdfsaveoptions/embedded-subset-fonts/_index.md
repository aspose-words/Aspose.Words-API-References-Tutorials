---
title: PDF ドキュメントにサブセットフォントを埋め込む
linktitle: PDF ドキュメントにサブセットフォントを埋め込む
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF ドキュメントにフォント サブセットを埋め込む手順ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

この記事では、Aspose.Words for .NET でフォント サブセット埋め込み機能を使用する方法について、ステップ バイ ステップ ガイドを提供します。コードの各部分を詳しく説明します。このチュートリアルの最後には、ドキュメントにフォントのサブセットを埋め込み、ドキュメントで使用されているグリフのみを含む PDF を生成する方法を理解できるようになります。

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

## ステップ3: PDFとして保存オプションを設定する

文書で使用されているフォントのサブセットのみを含むPDFを作成するには、`PdfSaveOptions`オブジェクト`EmbedFullFonts`プロパティが設定されている`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## ステップ4: フォントサブセットを含むPDFとして文書を保存する

最後に、フォントサブセットを使用して文書をPDFとして保存します。出力ファイル名と`saveOptions`前の手順で構成したオブジェクト。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

これで完了です。Aspose.Words for .NET を使用して、ドキュメントにフォントのサブセットを埋め込み、ドキュメントで使用されているグリフのみを含む PDF を生成できました。

### Aspose.Words for .NET を使用してフォント サブセットを埋め込むためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//出力 PDF には、ドキュメント内のフォントのサブセットが含まれます。
	// PDF フォントには、ドキュメントで使用されているグリフのみが含まれます。
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメントにフォント サブセットを埋め込む方法を学習しました。フォントのサブセットを埋め込むと、実際に使用されている文字のみを使用してドキュメントの外観を維持しながら PDF ファイルのサイズを縮小できます。これにより、PDF を表示および印刷する際の互換性とパフォーマンスが向上します。Aspose.Words for .NET の機能をさらに詳しく調べて、フォント サブセットが埋め込まれた PDF ドキュメントの生成を最適化してください。

### よくある質問

#### Q: PDF ドキュメントにフォント サブセットを埋め込むとは何ですか?
A: PDF ドキュメントにフォント サブセットを埋め込むとは、すべてのフォント全体ではなく、ドキュメントで使用されているグリフだけを含めるプロセスです。これにより、ドキュメントで実際に使用されている文字を表示するために必要なフォント データだけが含まれるため、PDF ファイルのサイズが小さくなります。

#### Q: 完全なフォントを埋め込むことと、フォントのサブセットを埋め込むことの違いは何ですか?
A: 完全なフォントの埋め込みとは、ドキュメントで使用されているすべてのフォントを PDF ファイルに含めることを意味します。これにより、ドキュメントは設計どおりに表示されますが、PDF ファイルのサイズが大きくなる可能性があります。対照的に、フォント サブセットの埋め込みには、ドキュメントで使用されているグリフのみが含まれるため、PDF ファイルのサイズは小さくなりますが、後で文字を追加した場合にドキュメントの外観を正確に再現する機能が制限されます。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメントにフォント サブセットを埋め込むにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメントにフォント サブセットを埋め込むには、次の手順に従います。

ドキュメントディレクトリのパスを次のように設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリの実際のパスを入力します。

処理したい文書をロードします。`Document`クラスとドキュメント パス。

 PDF保存オプションを設定するには、`PdfSaveOptions`クラスと設定`EmbedFullFonts`財産に`false`これにより、ドキュメントで使用されているフォント サブセットのみが PDF ファイルに含まれるようになります。

フォントサブセットを埋め込んだPDF形式で文書を保存するには、`Save`方法の`Document`オブジェクトでは、出力ファイルの名前と、以前に設定した保存オプションを指定します。

#### Q: PDF ドキュメントにフォント サブセットを埋め込む利点は何ですか?
A: PDF ドキュメントにフォント サブセットを埋め込む利点は次のとおりです。

PDF ファイル サイズの縮小: ドキュメントで使用されるグリフのみを含めることで、完全なフォントを埋め込む場合に比べて PDF ファイル サイズが縮小されます。

ドキュメントの外観の保持: PDF ファイルに含まれるフォントのサブセットにより、実際に使用されている文字のみを使用してドキュメントの外観を再現できます。

ライセンスの制限との互換性: ライセンスの制限により完全なフォントを合法的に埋め込むことができない場合は、フォントのサブセットを埋め込むことが推奨される場合があります。