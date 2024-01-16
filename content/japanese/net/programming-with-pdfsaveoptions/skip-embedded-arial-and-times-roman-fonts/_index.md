---
title: 埋め込み Arial および Times Roman フォントをスキップして PDF サイズを最適化
linktitle: 埋め込み Arial および Times Roman フォントをスキップして PDF サイズを最適化
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Arial および Times Roman フォントを埋め込まずに最適化された PDF を生成するためのステップバイステップのガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

この記事では、Aspose.Words for .NET で埋め込まれた Arial および Times Roman フォントをメタファイル サイズにスキップして PDF サイズを最適化する機能を使用する方法について、ステップバイステップのガイドを提供します。コードの各部分について詳しく説明します。このチュートリアルを終えると、文書内でフォント埋め込みモード オプションを構成し、Arial フォントと Times Roman フォントを埋め込まずに PDF を生成する方法を理解できるようになります。

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

## ステップ 3: フォント埋め込みを使用して PDF として保存オプションを構成する

生成された PDF への Arial および Times Roman フォントの埋め込みをスキップするには、`PdfSaveOptions`オブジェクトを設定して、`FontEmbeddingMode`財産を`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## ステップ 4: フォントを埋め込まずにドキュメントを PDF として保存する

最後に、前に設定した保存オプションを使用してドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

それだけです ！ Aspose.Words for .NET を使用して、Arial フォントと Times Roman フォントを埋め込まずに PDF を生成することに成功しました。

### Aspose.Words for .NET を使用して、埋め込まれた Arial および Times Roman フォントをメタファイル サイズでスキップするソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメントへの Arial および Times Roman フォントの埋め込みを無効にする方法を説明しました。概要を説明した手順に従うと、これらの特定のフォントを埋め込まずに PDF ファイルを生成できます。これにより、ファイル サイズが削減され、さまざまなプラットフォーム間でドキュメントの互換性が向上します。この機能を使用するときは、フォントの埋め込みを無効にした場合の影響を必ず考慮してください。 PDF ファイルの生成を最適化するために、Aspose.Words for .NET のさらに多くの機能を自由に探索してください。

### よくある質問

#### Q: PDF ドキュメントへの Arial および Times Roman フォントの埋め込みを無効にすることは何ですか?また、それが重要な理由は何ですか?
A: PDF ドキュメントへの Arial および Times Roman フォントの埋め込みを無効にすることは、生成される PDF ファイルにこれらのフォントを含めないプロセスです。これは、PDF リーダー システムですでに一般的に利用可能なフォントを含めることを避け、PDF ファイルのサイズを削減するために重要です。また、さまざまなデバイスやプラットフォーム間での PDF ドキュメントの互換性の向上と一貫した外観の確保にも役立ちます。

#### Q: PDF ドキュメントに Arial フォントと Times Roman フォントが埋め込まれないように Aspose.Words for .NET を構成するにはどうすればよいですか?
A: PDF ドキュメントに Arial および Times Roman フォントを埋め込まないように Aspose.Words for .NET を構成するには、次の手順に従います。

を置き換えて、ドキュメントが配置されているディレクトリ パスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリの実際のパスに置き換えます。

を使用して、処理するドキュメントをロードします。`Document`クラスと指定されたドキュメントのパス。

のインスタンスを作成します。`PdfSaveOptions`クラスを設定して、`FontEmbeddingMode`財産を`PdfFontEmbeddingMode.EmbedAll`。これにより、生成された PDF ファイルに Arial と Times Roman を除くすべてのフォントが埋め込まれます。

使用`Save`の方法`Document`オブジェクトを使用して、前に構成した保存オプションを指定してドキュメントを PDF 形式で保存します。

#### Q: PDF ドキュメントへの Arial および Times Roman フォントの埋め込みを無効にする利点は何ですか?
A: PDF ドキュメントへの Arial および Times Roman フォントの埋め込みを無効にする利点は次のとおりです。

PDF ファイル サイズの縮小: Arial や Times Roman などの一般的に利用可能なフォントの埋め込みを避けることで、PDF ファイル サイズを縮小でき、ファイルの保存、共有、転送が容易になります。

互換性の向上: PDF リーダー システムで一般的に利用できるフォントを使用することにより、さまざまなデバイスやプラットフォームでのドキュメントの互換性と外観が向上します。

#### Q: PDF ドキュメントへの Arial および Times Roman フォントの埋め込みを無効にすると、どのような影響がありますか?
A: PDF ドキュメントへの Arial および Times Roman フォントの埋め込みを無効にすると、次のような結果が生じます。

外観の違い: PDF を開いたシステムで Arial フォントと Times Roman フォントが使用できない場合は、代替フォントが使用され、意図したものとは異なる外観になる可能性があります。

読みやすさの問題: 使用される代替フォントは元のフォントほど読みにくい可能性があり、文書の読みやすさに影響を与える可能性があります。