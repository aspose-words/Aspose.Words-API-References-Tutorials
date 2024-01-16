---
title: コアフォントを埋め込まないことで PDF ファイルサイズを削減
linktitle: コアフォントを埋め込まないことで PDF ファイルサイズを削減
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を PDF に変換するときに、コア フォントを埋め込まずに PDF ファイル サイズを削減する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

このチュートリアルでは、Aspose.Words for .NET でコア フォントを埋め込まずに PDF ファイル サイズを削減する手順を説明します。この機能を使用すると、Word 文書を変換するときに、Arial、Times New Roman などの基本フォントを PDF に埋め込む必要があるかどうかを制御できます。以下の手順に従います。

## ステップ 1: ドキュメントをロードする

まず、PDF に変換する Word 文書をアップロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Word 文書への正しいパスを指定してください。

## ステップ 2: PDF 変換オプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、基本的なフォント埋め込みの回避を有効にします。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

このオプションは、基本フォントを PDF に埋め込むかどうかを制御します。

## ステップ 3: ドキュメントを PDF に変換する

使用`Save`変換オプションを指定して Word 文書を PDF に変換する方法:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

変換された PDF を保存するための正しいパスを指定してください。

### Aspose.Words for .NET を使用したコア フォントの埋め込みを回避するためのサンプル ソース コード

Aspose.Words for .NET でコア フォントの埋め込みを回避する機能を使用するための完全なソース コードを次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//出力 PDF には、Arial、Times New Roman などのコア フォントは埋め込まれません。
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

これらの手順に従うことで、Aspose.Words for .NET を使用して Word 文書を変換するときに、基本フォントを PDF に埋め込むかどうかを簡単に制御できます。


## 結論

このチュートリアルでは、Aspose.Words for .NET で基本フォントを埋め込まずに PDF ファイルのサイズを削減する方法を説明しました。この機能を使用すると、Word 文書の変換時にベース フォントを PDF に埋め込むかどうかを制御できます。概要を説明した手順に従うことで、基本フォントの埋め込みまたは非埋め込みを簡単に制御できます。これにより、PDF ファイルのサイズが削減され、互換性が向上し、さまざまなデバイスやプラットフォーム上でドキュメントの一貫した外観が保証されます。基本フォントを埋め込まない場合の結果を考慮し、ドキュメントが期待どおりにレンダリングされるかどうかを実験することを忘れないでください。

### よくある質問

#### Q: PDF ファイルにベース フォントを埋め込まないオプションとは何ですか?また、それが重要なのはなぜですか?
A: PDF ファイルにベース フォントを埋め込まないオプションは、Word 文書の変換時に Arial、Times New Roman などのベース フォントを PDF に埋め込む必要があるかどうかを制御します。これは、PDF リーダー システムで一般的に利用可能なフォントを含めることを避け、PDF ファイルのサイズを削減するために重要です。また、さまざまなデバイスやプラットフォーム間での PDF ドキュメントの互換性の向上と一貫した外観の確保にも役立ちます。

#### Q: PDF ファイルに基本フォントを埋め込まないように Aspose.Words for .NET を構成するにはどうすればよいですか?
A: PDF ファイルにコア フォントを埋め込まないように Aspose.Words for .NET を構成するには、次の手順に従います。

を置き換えて、ドキュメントが配置されているディレクトリ パスを設定します。`"YOUR DOCUMENTS DIRECTORY"`ドキュメントディレクトリの実際のパスに置き換えます。

 PDF に変換したい Word 文書をロードします。`Document`クラスと指定されたドキュメントのパス。

のインスタンスを作成します。`PdfSaveOptions`クラスを設定して、`UseCoreFonts`財産を`true`。これにより、生成された PDF ファイルに基本フォントが埋め込まれることがなくなります。

使用`Save`の方法`Document`オブジェクトを使用して、前に構成した変換オプションを指定してドキュメントを PDF 形式で保存します。

#### Q: PDF ファイルに基本フォントを埋め込まないことの利点は何ですか?
A: PDF ファイルにベース フォントを埋め込まないことの利点は次のとおりです。

PDF ファイル サイズの縮小: Arial、Times New Roman などの一般的に利用可能なフォントの埋め込みを回避することで、PDF ファイル サイズを縮小でき、ファイルの保存、共有、転送が容易になります。

互換性の向上: PDF リーダー システムで一般的に利用できる基本フォントを使用することで、さまざまなデバイスやプラットフォーム上での互換性とドキュメントの外観が向上します。

#### Q: PDF ファイルに基本フォントを埋め込まないと、どのような影響がありますか?
A: PDF ファイルに基本フォントを埋め込まないと、次のような結果が生じます。

異なる外観: PDF を開いたシステムで基本フォントが使用できない場合は、代替フォントが使用され、意図したものとは異なる外観になる可能性があります。

読みやすさの問題: 使用される代替フォントは元のフォントほど読みにくく、文書の読みやすさに影響を与える可能性があります。