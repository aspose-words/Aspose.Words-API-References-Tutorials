---
title: 埋め込みフォントを無効にしてPDFのサイズを縮小する
linktitle: 埋め込みフォントを無効にしてPDFのサイズを縮小する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを PDF に変換するときに、Windows フォントの埋め込みを無効にして PDF のサイズを縮小する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメント内の Windows フォント埋め込みを無効にして PDF サイズを縮小する手順を説明します。フォント埋め込みを無効にすると、生成される PDF ファイルのサイズを縮小できます。以下の手順に従ってください。

## ステップ1: ドキュメントの読み込み

まず、PDF に変換したいドキュメントをアップロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

ドキュメントへの正しいパスを必ず指定してください。

## ステップ2: PDF保存オプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、フォントを埋め込む方法を指定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

このオプションを使用すると、生成された PDF ファイルでの Windows フォントの統合を無効にすることができます。

## ステップ3: ドキュメントをPDFに変換する

使用`Save`変換オプションを指定してドキュメントを PDF に変換する方法:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

変換した PDF を保存するには、正しいパスを指定してください。

### Aspose.Words for .NET を使用して埋め込み Windows フォントを無効にするサンプル ソース コード

Aspose.Words for .NET を使用して PDF ドキュメントに Windows フォントを埋め込むことを無効にする完全なソース コードは次のとおりです。

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//出力 PDF は標準の Windows フォントを埋め込まずに保存されます。
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
以下の手順に従うと、Aspose.Words for .NET を使用して PDF ドキュメントへの Windows フォントの埋め込みを簡単に無効にできます。


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Windows フォントの埋め込みを無効にして PDF ファイルのサイズを縮小する方法を学習しました。フォントの埋め込みを無効にすると、生成される PDF ファイルのサイズが縮小され、ファイルの保存、共有、転送が容易になります。ただし、Windows フォントの埋め込みを無効にすると、最終的な PDF ドキュメントの外観や書式が変わる可能性があることに注意してください。この機能を使用するときは、これらの影響を必ず考慮してください。Aspose.Words for .NET のその他の機能も自由に調べて、PDF ファイルの生成を最適化してください。

### よくある質問

#### Q: PDF ドキュメントで Windows フォントの埋め込みを無効にするとは何ですか? また、なぜそれが重要なのですか?
A: PDF ドキュメントへの Windows フォントの埋め込みを無効にすると、生成された PDF ファイルに Windows フォントが含まれなくなります。これにより、埋め込まれた Windows フォント データが削除され、PDF ファイルのサイズが小さくなります。これは PDF ファイルのサイズを小さくするのに重要であり、PDF ファイルの保存、共有、転送が簡単になります。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメント内の Windows フォント埋め込みを無効にする方法を教えてください。
A: Aspose.Words for .NET を使用して PDF ドキュメントへの Windows フォントの埋め込みを無効にするには、次の手順に従います。

 PDFに変換したい文書を読み込み、`Document`クラスとドキュメントのパス。

インスタンスを作成する`PdfSaveOptions`クラスを設定し、`FontEmbeddingMode`財産に`PdfFontEmbeddingMode.EmbedNone`これにより、生成された PDF ファイルへの Windows フォントの埋め込みが無効になります。

使用`Save`方法の`Document`以前に設定した変換オプションを指定してドキュメントを PDF に変換するオブジェクト。

#### Q: PDF ドキュメントで Windows フォントの埋め込みを無効にするとどのような利点がありますか?
A: PDF ドキュメントで Windows フォントの埋め込みを無効にする利点は次のとおりです。

PDF ファイル サイズの縮小: Windows フォントの埋め込みを無効にすると、埋め込まれた Windows フォント データが削除され、生成される PDF ファイルのサイズが縮小されます。

より簡単な保存: PDF ファイルが小さいほど、保存、転送、保管が簡単になります。

より高速な共有と転送: 小さい PDF ファイルはより高速に共有および転送できるため、時間とリソースを節約できます。

#### Q: PDF ドキュメントで Windows フォントの埋め込みを無効にすると、どのような影響がありますか?
A: PDF ドキュメントへの Windows フォントの埋め込みを無効にすると、次のような結果が生じる可能性があります。

外観と書式の損失: ドキュメントで指定された Windows フォントが PDF を開いたシステムで使用できない場合は、代替フォントが使用されるため、外観と書式が正しくなくなる可能性があります。予想とは形状が異なります。

読みやすさの問題: 使用された代替フォントが元のフォントほど読みやすくない場合、PDF ドキュメント内のテキストの読みやすさに影響する可能性があります。