---
title: リッチテキストボックスコンテンツコントロール
linktitle: リッチテキストボックスコンテンツコントロール
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、テキストの書式設定とスタイル設定を可能にする、Word 文書にリッチ テキスト ボックス コンテンツ コントロールを作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/rich-text-box-content-control/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にリッチ テキスト ボックス コンテンツ コントロールを作成する方法を説明します。リッチ テキスト ボックス コンテンツ コントロールを使用すると、ユーザーはさまざまなスタイルと書式設定オプションを使用してテキストを入力し、書式設定できます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントとStructuredDocumentTagを作成する
新しいインスタンスを作成する`Document`クラスと`StructuredDocumentTag`リッチテキストボックスコンテンツコントロールを表すために指定します。`SdtType.RichText`タイプとして`MarkupLevel.Block`ブロックレベルのリッチテキストボックスを作成するには、マークアップレベルとして使用します。

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## ステップ3: リッチテキストコンテンツを作成してフォーマットする
段落を作成し、実行してリッチ テキスト コンテンツを表します。テキストと、色、フォントなどの書式設定オプションを設定します。

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## ステップ4: コンテンツコントロールにリッチテキストコンテンツを追加する
リッチテキストコンテンツを含む段落を`ChildNodes`リッチ テキスト ボックス コンテンツ コントロールのコレクション。

```csharp
sdtRichText.ChildNodes.Add(para);
```

## ステップ5: ドキュメントにコンテンツコントロールを追加する
リッチテキストボックスコンテンツコントロールをドキュメントの本文に追加するには、`AppendChild`ドキュメントの最初のセクションの本文の方法。

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## ステップ6: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.RichTextBoxContentControl.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Aspose.Words for .NET を使用したリッチ テキスト ボックス コンテンツ コントロールのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書にリッチ テキスト ボックス コンテンツ コントロールを正常に作成できました。