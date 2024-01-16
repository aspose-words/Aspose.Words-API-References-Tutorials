---
title: ドキュメントをRTFに変換
linktitle: ドキュメントをRTFに変換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントを Docx から RTF 形式に変換する方法を学びます。サンプルソースコードを含むステップバイステップのチュートリアル。
type: docs
weight: 10
url: /ja/net/basic-conversions/docx-to-rtf/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して、Docx 形式の Word ドキュメントを RTF に変換する方法を説明します。提供されている C# ソース コードについて説明し、それを独自のプロジェクトに実装する方法を示します。

開始するには、Aspose.Words for .NET が開発環境にインストールされ、セットアップされていることを確認してください。まだ行っていない場合は、からライブラリをダウンロードしてインストールします。[Aspose.Releases]https://releases.aspose.com/words/net/。

## ステップ 1: ストリームからドキュメントを読み取る

まず、ストリームを開いて Docx ドキュメントを読み取ります。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## ステップ 2: ドキュメントをロードする

次に、ストリームからドキュメントを読み込みます。

```csharp
Document doc = new Document(stream);
```

## ステップ 3: ストリームを閉じる

ドキュメントがメモリにロードされるので、ストリームを閉じることができます。

```csharp
stream.Close();
```

## ステップ 4: ドキュメントに対する操作の実行

この時点で、ドキュメントに対して任意の操作を実行できます。

## ステップ 5: ドキュメントを RTF 形式で保存する

ドキュメントを RTF 形式で保存するには、ドキュメントをメモリ ストリームに保存します。

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## ステップ 6: ストリームを巻き戻す

メモリ ストリームをファイルに書き込む前に、その位置をゼロに巻き戻します。

```csharp
dstStream.Position = 0;
```

## ステップ 7: ストリームをファイルに書き込む

最後に、メモリ ストリームを RTF ファイルに書き込みます。

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

それでおしまい！ Aspose.Words for .NET を使用して、Docx 形式の Word 文書を RTF に正常に変換しました。

### Aspose.Words for .NET を使用した Docx To Rtf のソース コード例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//Aspose.Words がドキュメントを読み込むには、読み取り専用アクセスがあれば十分です。
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	//ここでストリームを閉じても構いません。ドキュメントはメモリ内にあるため、ストリームは必要なくなりました。
	stream.Close();

	// ...ドキュメントを使って何かをします。

	//ドキュメントを別の形式に変換し、ストリームに保存します。
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	//ストリーム位置をゼロに巻き戻して、次のリーダーの準備が整います。
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

このコードを独自のプロジェクトで自由に使用し、特定の要件に応じて変更してください。

### よくある質問

#### DOCX ファイルを RTF 形式に変換するにはどうすればよいですか?

DOCX ファイルを RTF 形式に変換するには、この機能を提供するさまざまなソフトウェア ツールまたはライブラリを使用できます。そのような信頼できるツールの 1 つが Aspose.Words for .NET です。これは、DOCX ファイルをプログラムで RTF 形式に変換する簡単かつ効率的な方法を提供します。ライブラリの API を使用して DOCX ファイルをロードし、希望の RTF 形式で保存できます。

#### 変換プロセスに制限はありますか?

変換プロセスの制限は、使用している特定のツールまたはライブラリによって異なります。一部のツールでは、入力ドキュメントのサイズや複雑さに制限がある場合があります。変換タスクの要件を処理できるツールを選択することが重要です。

#### 元の文書の書式設定とレイアウトを保持できますか?

はい、Aspose.Words を使用すると、変換プロセス中に元の文書の書式設定とレイアウトを保持できます。たとえば、Aspose.Words for .NET は、変換された RTF ドキュメント内の DOCX ファイルの書式設定、スタイル、その他の要素を維持するための包括的なサポートを提供します。

#### Aspose は DOCX から RTF への変換の信頼できるツールですか?

はい、Aspose.Words for .NET は、DOCX から RTF への変換のための信頼性の高いツールです。その堅牢な機能と優れたパフォーマンスにより、世界中の開発者や企業によって広く使用されています。このライブラリは、広範なドキュメント、定期的な更新、専用の技術サポートを提供しており、ドキュメント変換タスクにとって信頼できる選択肢となっています。