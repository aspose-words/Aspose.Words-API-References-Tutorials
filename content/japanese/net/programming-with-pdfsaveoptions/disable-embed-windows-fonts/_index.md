---
title: 埋め込みフォントを無効にして PDF サイズを縮小する
linktitle: 埋め込みフォントを無効にして PDF サイズを縮小する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを PDF に変換するときに、Windows フォントの埋め込みを無効にして PDF サイズを縮小する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメントへの Windows フォントの埋め込みを無効にして PDF サイズを削減する手順を説明します。フォントの埋め込みを無効にすると、生成される PDF ファイルのサイズを小さくできます。以下の手順に従います。

## ステップ 1: ドキュメントをロードする

まず、PDF に変換するドキュメントをアップロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

必ずドキュメントへの正しいパスを指定してください。

## ステップ 2: PDF 保存オプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、フォントを埋め込む方法を指定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

このオプションを使用すると、生成された PDF ファイルへの Windows フォントの統合を無効にすることができます。

## ステップ 3: ドキュメントを PDF に変換する

使用`Save`変換オプションを指定してドキュメントを PDF に変換するメソッド:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

変換された PDF を保存するための正しいパスを指定してください。

### Aspose.Words for .NET を使用して Windows フォントの埋め込みを無効にするソース コードの例

Aspose.Words for .NET を使用して PDF ドキュメントへの Windows フォントの埋め込みを無効にする完全なソース コードは次のとおりです。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//出力 PDF は、標準の Windows フォントを埋め込まずに保存されます。
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
これらの手順に従うことで、Aspose.Words for .NET を使用して PDF ドキュメントへの Windows フォントの埋め込みを簡単に無効にすることができます。


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Windows フォントの埋め込みを無効にして PDF ファイルのサイズを削減する方法を学びました。フォントの埋め込みを無効にすると、生成される PDF ファイルのサイズが小さくなり、ファイルの保存、共有、転送が容易になります。ただし、Windows フォントの埋め込みを無効にすると、最終的な PDF ドキュメントの外観や書式が変更される可能性があることに注意することが重要です。この機能を使用するときは、これらの影響を必ず考慮してください。 PDF ファイルの生成を最適化するために、Aspose.Words for .NET のさらに多くの機能を自由に探索してください。

### よくある質問

#### Q: PDF ドキュメントへの Windows フォント埋め込みを無効にするのは何ですか?また、それが重要な理由は何ですか?
A: PDF ドキュメントへの Windows フォントの埋め込みを無効にすることは、生成された PDF ファイルに Windows フォントが含まれないようにするプロセスです。これにより、埋め込まれた Windows フォント データが削除され、PDF ファイルのサイズが削減されます。これは PDF ファイルのサイズを小さくするために重要であり、保存、共有、転送がより速くなります。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメントへの Windows フォントの埋め込みを無効にするにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメントへの Windows フォントの埋め込みを無効にするには、次の手順に従います。

 PDF に変換したいドキュメントをロードします。`Document`クラスとドキュメントのパス。

のインスタンスを作成します。`PdfSaveOptions`クラスを設定して、`FontEmbeddingMode`財産を`PdfFontEmbeddingMode.EmbedNone`。これにより、生成された PDF ファイルへの Windows フォントの埋め込みが無効になります。

使用`Save`の方法`Document`オブジェクトを使用して、前に構成した変換オプションを指定してドキュメントを PDF に変換します。

#### Q: PDF ドキュメントへの Windows フォントの埋め込みを無効にする利点は何ですか?
A: PDF ドキュメントへの Windows フォントの埋め込みを無効にする利点は次のとおりです。

PDF ファイル サイズの縮小: Windows フォントの埋め込みを無効にすると、埋め込まれた Windows フォント データが削除され、生成される PDF ファイルのサイズが小さくなります。

保存が簡単: PDF ファイルが小さいほど、保存、保存、転送が簡単です。

共有と転送の高速化: 小さい PDF ファイルの共有と転送が高速になり、時間とリソースを節約できます。

#### Q: PDF ドキュメントへの Windows フォント埋め込みを無効にするとどのような影響がありますか?
A: PDF ドキュメントへの Windows フォントの埋め込みを無効にすると、次のような結果が生じる可能性があります。

外観と書式の損失: ドキュメントで指定された Windows フォントが PDF を開いたシステムで使用できない場合、代替フォントが使用され、外観と書式が正しくなくなる可能性があります。予想していたものと形が違う。

可読性の問題: 使用されている代替フォントが元のフォントほど可読性が低い場合、PDF ドキュメント内のテキストの可読性に影響を及ぼす可能性があります。