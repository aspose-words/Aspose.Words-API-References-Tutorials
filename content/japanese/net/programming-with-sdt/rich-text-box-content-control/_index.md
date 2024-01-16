---
title: リッチテキストボックスコンテンツコントロール
linktitle: リッチテキストボックスコンテンツコントロール
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内にリッチ テキスト ボックス コンテンツ コントロールを作成し、テキストの書式設定とスタイル設定を可能にする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/rich-text-box-content-control/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内にリッチ テキスト ボックス コンテンツ コントロールを作成する方法を示します。リッチ テキスト ボックスのコンテンツ コントロールを使用すると、ユーザーはさまざまなスタイルと書式設定オプションを使用してテキストを入力し、書式設定することができます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントと StructuredDocumentTag を作成する
の新しいインスタンスを作成します。`Document`クラスと`StructuredDocumentTag`リッチ テキスト ボックス コンテンツ コントロールを表します。特定`SdtType.RichText`タイプとして、そして`MarkupLevel.Block`マークアップ レベルとして使用して、ブロック レベルのリッチ テキスト ボックスを作成します。

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## ステップ 3: リッチ テキスト コンテンツの作成と書式設定
段落を作成し、リッチ テキスト コンテンツを表すために実行します。テキストと色、フォントなどの書式設定オプションを設定します。

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## ステップ 4: リッチ テキスト コンテンツをコンテンツ コントロールに追加する
リッチ テキスト コンテンツを含む段落を`ChildNodes`リッチ テキスト ボックス コンテンツ コントロールのコレクション。

```csharp
sdtRichText.ChildNodes.Add(para);
```

## ステップ 5: コンテンツ コントロールをドキュメントに追加する
リッチ テキスト ボックス コンテンツ コントロールをドキュメントの本文に追加するには、`AppendChild`ドキュメントの最初のセクションの本文のメソッド。

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## ステップ 6: ドキュメントを保存する
を使用してドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.RichTextBoxContentControl.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Aspose.Words for .NET を使用したリッチ テキスト ボックス コンテンツ コントロールのソース コードの例 

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

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内にリッチ テキスト ボックス コンテンツ コントロールが正常に作成されました。