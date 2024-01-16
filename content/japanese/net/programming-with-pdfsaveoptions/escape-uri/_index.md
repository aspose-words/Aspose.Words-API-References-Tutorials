---
title: PDF ドキュメント内のエスケープ URI
linktitle: PDF ドキュメント内のエスケープ URI
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF ドキュメント内の URI をエスケープする方法のステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/escape-uri/
---

この記事では、Aspose.Words for .NET を使用して PDF ドキュメント内の URI をエスケープする方法に関するステップバイステップのガイドを提供します。コードの各部分について詳しく説明します。このチュートリアルを終えると、エスケープされた URI を含むハイパーリンクをドキュメントに挿入する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで見つけることができます。

## ステップ 1: ドキュメント ディレクトリを定義する

まず、ドキュメントが配置されているディレクトリへのパスを定義する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントと DocumentBuilder を作成する

次に、新しいものを作成する必要があります。`Document`オブジェクトと`DocumentBuilder`ドキュメントを構築するためのオブジェクト。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: エスケープされた URI を含むハイパーリンクを挿入する

使用`InsertHyperlink`の方法`DocumentBuilder`オブジェクトを使用してドキュメントにハイパーリンクを挿入します。 Uri は、次のコマンドを使用してエスケープする必要があります。`Uri.EscapeUriString`フォーマットエラーを回避する機能。

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test")、false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test")、
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test")、false);
```

## ステップ 4: ドキュメントを PDF として保存する

最後に、次のコマンドを使用してドキュメントを PDF として保存できます。`Save`の方法`Document`物体。出力ファイル名を指定します。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

それだけです ！ Aspose.Words for .NET を使用して、エスケープされた URI を含むハイパーリンクをドキュメントに正常に挿入できました。

### Aspose.Words for .NET でエスケープする Uri のサンプル ソース コード


```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test"、false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test"、false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメント内の URI をエスケープする方法について説明しました。 URI をエスケープすることで、書式設定エラーを回避し、ハイパーリンクが正しく解釈され、PDF ドキュメントに表示されるようにすることができます。説明されている手順に従って、エスケープされた URI を含むハイパーリンクを PDF ドキュメントに挿入します。必ず逃げてください。

### よくある質問

#### Q: PDF ドキュメント内のエスケープ URI とは何ですか? それが重要な理由は何ですか?
A: PDF ドキュメントのエスケープ URI とは、形式エラーを回避するために、URL 内の特殊文字をエスケープ シーケンスに変換する方法を指します。 URL 内の特殊文字は URL の構造を破壊し、誤解や不正確なレンダリングを引き起こす可能性があるため、これは重要です。特殊文字をエスケープすることで、URL が正しく解釈され、PDF ドキュメントに表示されることが保証されます。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメント内の URI をエスケープするにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメント内の URI をエスケープするには、次の手順に従います。

を置き換えて、ドキュメントが配置されているディレクトリ パスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリの実際のパスに置き換えます。

の新しいインスタンスを作成します。`Document`クラスと`DocumentBuilder`ドキュメントを構築するためのオブジェクト。

使用`InsertHyperlink`の方法`DocumentBuilder`オブジェクトを使用してドキュメントにハイパーリンクを挿入します。必ず次のコマンドを使用して URI をエスケープしてください。`Uri.EscapeUriString`フォーマットエラーを回避する機能。

使用`Save`の方法`Document`オブジェクトを使用して、出力ファイルの名前を指定してドキュメントを PDF 形式で保存します。

#### Q: PDF ドキュメント内で URI をエスケープする利点は何ですか?
A: PDF ドキュメントで URI エスケープを行う利点は次のとおりです。

形式エラーの防止: URI エスケープは、URL 内の特殊文字によって引き起こされる形式エラーを防止し、URL が正しく解釈されて PDF ドキュメントに表示されるようにします。

PDF リーダーとの互換性: エスケープ URI は通常、PDF リーダーで十分にサポートされており、より優れた互換性と一貫したユーザー エクスペリエンスが保証されます。

#### Q: URI ではどのような特殊文字をエスケープする必要がありますか?
 A: URI でエスケープする必要がある特殊文字は、スペース、<、>、"、#、%、{、}、|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.