---
title: PDF ドキュメント内の URI をエスケープする
linktitle: PDF ドキュメント内の URI をエスケープする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF ドキュメント内の URI をエスケープする方法のステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/escape-uri/
---

この記事では、Aspose.Words for .NET を使用して PDF ドキュメントの URI をエスケープする方法について、ステップ バイ ステップで説明します。コードの各部分を詳しく説明します。このチュートリアルの最後には、エスケープされた URI を含むハイパーリンクをドキュメントに挿入する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで参照できます。

## ステップ1: ドキュメントディレクトリを定義する

まず、ドキュメントが保存されているディレクトリへのパスを定義する必要があります。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントとDocumentBuilderを作成する

次に、新しい`Document`オブジェクトと`DocumentBuilder`ドキュメントを構築するためのオブジェクト。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: エスケープされたURIでハイパーリンクを挿入する

使用`InsertHyperlink`方法の`DocumentBuilder`オブジェクトを使用して文書にハイパーリンクを挿入します。URIは`Uri.EscapeUriString`フォーマットエラーを回避する機能。

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test")、
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## ステップ4: ドキュメントをPDFとして保存する

最後に、ドキュメントをPDFとして保存するには、`Save`方法の`Document`オブジェクト。出力ファイル名を指定します。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

以上です。Aspose.Words for .NET を使用して、エスケープされた URI を含むハイパーリンクをドキュメントに正常に挿入できました。

### Aspose.Words for .NET を使用した URI エスケープのサンプル ソース コード


```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", 偽);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", 偽);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメント内の URI をエスケープする方法について説明しました。URI をエスケープすることで、書式設定エラーを回避し、ハイパーリンクが PDF ドキュメント内で正しく解釈され表示されるようになります。エスケープされた URI を含むハイパーリンクを PDF ドキュメントに挿入するには、説明されている手順に従ってください。必ずエスケープしてください。

### よくある質問

#### Q: PDF ドキュメントのエスケープ URI とは何ですか? また、なぜ重要ですか?
A: PDF ドキュメントの URI のエスケープとは、URL 内の特殊文字をエスケープ シーケンスに変換して、フォーマット エラーを回避する方法を指します。URL 内の特殊文字は URL の構造を破壊し、誤解や誤ったレンダリングにつながる可能性があるため、これは重要です。特殊文字をエスケープすることで、URL が正しく解釈され、PDF ドキュメントに表示されることが保証されます。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメント内の URI をエスケープするにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメント内の URI をエスケープするには、次の手順に従います。

ドキュメントが保存されているディレクトリパスを次のように設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリの実際のパスを入力します。

新しいインスタンスを作成する`Document`クラスと`DocumentBuilder`ドキュメントを構築するためのオブジェクト。

使用`InsertHyperlink`方法の`DocumentBuilder`オブジェクトを使用して文書にハイパーリンクを挿入します。URIをエスケープすることを忘れないでください。`Uri.EscapeUriString`フォーマットエラーを回避する機能。

使用`Save`方法の`Document`出力ファイルの名前を指定してドキュメントを PDF 形式で保存するオブジェクト。

#### Q: PDF ドキュメントで URI をエスケープする利点は何ですか?
A: PDF ドキュメントで URI エスケープを行う利点は次のとおりです。

フォーマット エラーの防止: URI エスケープは、URL 内の特殊文字によって発生するフォーマット エラーを防止し、URL が正しく解釈されて PDF ドキュメントに表示されるようにします。

PDF リーダーとの互換性: エスケープされた URI は一般に PDF リーダーで適切にサポートされているため、互換性が向上し、一貫したユーザー エクスペリエンスが保証されます。

#### Q: URI でエスケープする必要がある特殊文字は何ですか?
 A: URI でエスケープする必要がある特殊文字は、スペース、<、>、"、#、%、{、} です。|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.