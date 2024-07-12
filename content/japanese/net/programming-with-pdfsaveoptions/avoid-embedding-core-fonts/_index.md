---
title: コアフォントを埋め込まないことでPDFファイルのサイズを縮小する
linktitle: コアフォントを埋め込まないことでPDFファイルのサイズを縮小する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を PDF に変換するときに、コア フォントを埋め込まないことで PDF ファイル サイズを縮小する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

このチュートリアルでは、Aspose.Words for .NET を使用してコア フォントを埋め込まずに PDF ファイルのサイズを縮小する手順を説明します。この機能を使用すると、Word 文書を変換するときに Arial、Times New Roman などの基本フォントを PDF に埋め込むかどうかを制御できます。次の手順に従います。

## ステップ1: ドキュメントの読み込み

まず、PDF に変換したい Word 文書をアップロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Word 文書への正しいパスを必ず指定してください。

## ステップ2: PDF変換オプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、基本的なフォント埋め込み回避を有効にします。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

このオプションは、基本フォントを PDF に埋め込むかどうかを制御します。

## ステップ3: ドキュメントをPDFに変換する

使用`Save`変換オプションを指定して Word 文書を PDF に変換する方法:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

変換した PDF を保存するには、正しいパスを指定してください。

### Aspose.Words for .NET を使用してコア フォントの埋め込みを回避するためのサンプル ソース コード

Aspose.Words for .NET でコア フォントの埋め込みを回避する機能を使用するための完全なソース コードは次のとおりです。

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//出力 PDF には、Arial、Times New Roman などのコア フォントは埋め込まれません。
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書を変換するときに、基本フォントを PDF に埋め込むかどうかを簡単に制御できます。


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して基本フォントを埋め込まないことで PDF ファイルのサイズを縮小する方法を説明しました。この機能を使用すると、Word 文書を変換するときに基本フォントを PDF に埋め込むかどうかを制御できます。説明されている手順に従うことで、基本フォントの埋め込みまたは非埋め込みを簡単に制御できます。これにより、PDF ファイルのサイズが縮小され、さまざまなデバイスやプラットフォームでの互換性が向上し、文書の外観が統一されます。基本フォントを埋め込まない場合の影響を考慮し、文書が期待どおりにレンダリングされるかどうか実験することを忘れないでください。

### よくある質問

#### Q: PDF ファイルにベースフォントを埋め込まないオプションとは何ですか? また、それが重要なのはなぜですか?
A: PDF ファイルに基本フォントを埋め込まないオプションは、Word 文書を変換するときに、Arial、Times New Roman などの基本フォントを PDF に埋め込む必要があるかどうかを制御します。これは、PDF リーダー システムで一般的に使用できるフォントを含めないようにすることで、PDF ファイルのサイズを縮小するために重要です。また、さまざまなデバイスやプラットフォーム間で PDF 文書の互換性を高め、外観の一貫性を保つことにも役立ちます。

#### Q: PDF ファイルに基本フォントを埋め込まないように Aspose.Words for .NET を構成するにはどうすればよいでしょうか?
A: Aspose.Words for .NET を構成して PDF ファイルにコア フォントを埋め込まないようにするには、次の手順に従います。

ドキュメントが保存されているディレクトリパスを次のように設定します。`"YOUR DOCUMENTS DIRECTORY"`ドキュメント ディレクトリの実際のパスを入力します。

 PDFに変換したいWord文書を読み込み、`Document`クラスと指定されたドキュメント パス。

インスタンスを作成する`PdfSaveOptions`クラスを設定し、`UseCoreFonts`財産に`true`これにより、生成された PDF ファイルに基本フォントが埋め込まれなくなります。

使用`Save`方法の`Document`以前に設定した変換オプションを指定してドキュメントを PDF 形式で保存するオブジェクト。

#### Q: PDF ファイルにベースフォントを埋め込まないことの利点は何ですか?
A: PDF ファイルにベースフォントを埋め込まないことの利点は次のとおりです。

PDF ファイル サイズの縮小: Arial、Times New Roman などの一般的なフォントの埋め込みを避けることで、PDF ファイルのサイズを縮小でき、ファイルの保存、共有、転送が容易になります。

互換性の向上: PDF リーダー システムで一般的に使用できる基本フォントを使用することで、さまざまなデバイスやプラットフォームでの互換性とドキュメントの外観が向上します。

#### Q: PDF ファイルに基本フォントを埋め込まないと、どのような影響がありますか?
A: PDF ファイルに基本フォントを埋め込まない場合の結果は次のようになります。

異なる外観: PDF を開いたシステムで基本フォントが使用できない場合は代替フォントが使用され、意図した外観と異なる可能性があります。

読みやすさの問題: 使用される代替フォントは元のフォントほど読みやすくない場合があり、ドキュメントの読みやすさに影響する可能性があります。