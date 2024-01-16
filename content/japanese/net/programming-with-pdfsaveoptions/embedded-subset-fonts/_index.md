---
title: PDF ドキュメントにサブセット フォントを埋め込む
linktitle: PDF ドキュメントにサブセット フォントを埋め込む
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF ドキュメントにフォント サブセットを埋め込むためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

この記事では、Aspose.Words for .NET でフォント サブセット埋め込み機能を使用する方法について段階的なガイドを提供します。コードの各部分について詳しく説明します。このチュートリアルを終えると、フォントのサブセットをドキュメントに埋め込み、ドキュメントで使用されているグリフのみを含む PDF を生成する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで見つけることができます。

## ステップ 1: ドキュメント ディレクトリを定義する

まず、ドキュメントが配置されているディレクトリへのパスを定義する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをアップロードする

次に、処理するドキュメントをロードする必要があります。この例では、ドキュメントが「Rendering.docx」という名前で、指定されたドキュメント ディレクトリに配置されていると仮定します。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ 3: PDF として保存オプションを構成する

ドキュメントで使用されているフォントのサブセットのみを含む PDF を作成するには、`PdfSaveOptions`オブジェクトを使用して`EmbedFullFonts`に設定されたプロパティ`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## ステップ 4: フォント サブセットを含む PDF としてドキュメントを保存する

最後に、フォント サブセットを使用してドキュメントを PDF として保存できます。出力ファイル名と`saveOptions`前のステップで構成したオブジェクト。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

それだけです ！ Aspose.Words for .NET を使用して、ドキュメントにフォントのサブセットを埋め込み、ドキュメントで使用されているグリフのみを含む PDF を生成することができました。

### Aspose.Words for .NET を使用してフォント サブセットを埋め込むためのサンプル ソース コード

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//出力 PDF には、ドキュメント内のフォントのサブセットが含まれます。
	// PDF フォントには、文書内で使用されているグリフのみが含まれます。
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメントにフォント サブセットを埋め込む方法を学習しました。フォントのサブセットを埋め込むと、実際に使用される文字のみを使用してドキュメントの外観を維持しながら、PDF ファイルのサイズを削減できます。これにより、PDF の表示および印刷時の互換性とパフォーマンスが向上します。 Aspose.Words for .NET の機能をさらに詳しく調べて、フォント サブセットが埋め込まれた PDF ドキュメントの生成を最適化してください。

### よくある質問

#### Q: PDF ドキュメントへのフォント サブセットの埋め込みとは何ですか?
A: PDF ドキュメントへのフォント サブセットの埋め込みは、完全なフォントをすべて含めるのではなく、ドキュメント内で使用されているグリフのみを含めるプロセスです。実際に文書内で使用される文字を表示するために必要なフォントデータのみを含めることで、PDF ファイルのサイズを削減します。

#### Q: 完全なフォントの埋め込みとフォントのサブセットの埋め込みの違いは何ですか?
A: 完全なフォントの埋め込みとは、ドキュメントで使用されているすべてのフォントを PDF ファイルに含めることを意味します。これにより、ドキュメントはデザインどおりに正確に表示されますが、PDF ファイルのサイズが大きくなる可能性があります。対照的に、埋め込みフォント サブセットには文書内で使用されているグリフのみが含まれるため、PDF ファイルのサイズは小さくなりますが、後で文字を追加した場合に文書の外観を正確に複製する能力は制限されます。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメントにフォント サブセットを埋め込むにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメントにフォント サブセットを埋め込むには、次の手順に従います。

置き換えてドキュメント ディレクトリ パスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリの実際のパスに置き換えます。

を使用して、処理するドキュメントをロードします。`Document`クラスとドキュメントのパス。

のインスタンスを作成して PDF 保存オプションを構成します。`PdfSaveOptions`クラスと設定`EmbedFullFonts`財産を`false`。これにより、ドキュメントで使用されているフォントのサブセットのみが PDF ファイルに含まれるようになります。

を使用してフォント サブセットを埋め込んだ PDF 形式でドキュメントを保存します。`Save`の方法`Document`オブジェクトを作成し、出力ファイルの名前と前に構成した保存オプションを指定します。

#### Q: PDF ドキュメントにフォント サブセットを埋め込む利点は何ですか?
A: PDF ドキュメントにフォント サブセットを埋め込む利点は次のとおりです。

PDF ファイル サイズの縮小: ドキュメント内で使用されているグリフのみを含めることにより、フォント全体を埋め込む場合と比べて、PDF ファイル サイズが縮小されます。

文書の外観の保持: PDF ファイルに含まれるフォントのサブセットにより、実際に使用される文字のみを使用して文書の外観を再現できます。

ライセンスの制限との互換性: ライセンスの制限により完全なフォントを合法的に埋め込むことができない場合は、フォントのサブセットを埋め込むことが推奨される場合があります。