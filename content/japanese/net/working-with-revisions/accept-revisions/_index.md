---
title: 修正を承認
linktitle: 修正を承認
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の修正を受け入れる方法を学びます
type: docs
weight: 10
url: /ja/net/working-with-revisions/accept-revisions/
---

このチュートリアルでは、Aspose.Words for .NET の Accept Revisions 機能を使用して Word 文書の改訂を承認する手順を説明します。ソース コードを理解し、文書の変更を承認するには、以下の手順に従ってください。

## ステップ1: ドキュメントコンテンツの追加と編集

この例では、ドキュメントを作成し、コンテンツを追加します。変更と改訂を示すために、いくつかの段落を使用します。方法は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//最初の段落にテキストを追加し、さらに 2 つの段落を追加します。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## ステップ2: レビューを追跡してレビューを追加する

リビジョン追跡を有効にして、ドキュメントにリビジョンを追加します。手順は次のとおりです。

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

//この段落はリビジョンであり、対応する「IsInsertRevision」フラグが設定されます。
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## ステップ3: 段落を削除して変更を管理する

段落を削除し、保存されたリビジョンを確認します。方法は次のとおりです。

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

//リビジョンを追跡しているため、段落はまだ文書内に存在し、「IsDeleteRevision」フラグが設定されます。
//すべてのレビューが承認または拒否されるまで、Microsoft Word にレビューとして表示されます。
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## ステップ4: 変更を承認する

ドキュメントへのすべての変更を受け入れます。方法は次のとおりです。

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## ステップ5: レビューの追跡を停止する

ドキュメントへの変更がリビジョンとして表示されないように、リビジョンの追跡を停止します。手順は次のとおりです。

```csharp
doc.StopTrackRevisions();
```
## ステップ6: ドキュメントを保存する

テキスト入力フォームフィールドを挿入した後、`Save`メソッド。適切なファイル パスを指定してください。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Aspose.Words for .NET を使用した Accept Revisions のサンプル ソース コード

以下は、Aspose.Words for .NET を使用してドキュメントの変更を受け入れるための完全なソース コードです。


```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//最初の段落にテキストを追加し、さらに 2 つの段落を追加します。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//3つの段落がありますが、いずれも修正として登録されていません
//改訂を追跡しながら文書内のコンテンツを追加/削除すると、
//これらはドキュメント内にそのように表示され、承認/拒否することができます。
doc.StartTrackRevisions("John Doe", DateTime.Now);

//この段落はリビジョンであり、それに応じて「IsInsertRevision」フラグが設定されます。
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

//ドキュメントの段落コレクションを取得し、段落を削除します。
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

//リビジョンを追跡しているので、段落はまだ文書内に存在し、「IsDeleteRevision」が設定されます。
//すべての修正が承認または拒否されるまで、Microsoft Word に修正として表示されます。
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

//変更を承認すると、削除リビジョンの段落は削除されます。
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

//リビジョンの追跡を停止すると、このテキストは通常のテキストとして表示されます。
//ドキュメントが変更された場合、リビジョンはカウントされません。
doc.StopTrackRevisions();

//ドキュメントを保存します。
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## 結論

このチュートリアルでは、Aspose.Words for .NET の Accept Revisions 機能を使用して Word 文書の改訂を承認する方法を学習しました。ドキュメント コンテンツの追加と編集、改訂の追跡、改訂された段落の削除、すべての変更の承認、改訂の追跡の停止の手順を実行しました。これで、この知識を適用して、Aspose.Words for .NET を使用して独自の Word 文書の改訂を効果的に管理できます。

### よくある質問

#### Q: Aspose.Words for .NET でリビジョン追跡を有効にするにはどうすればいいですか?

#### 解決策1:

 A: Aspose.Words for .NETでリビジョントラッキングを有効にするには、`StartTrackRevisions`方法の`Document`オブジェクトを作成し、リビジョン追跡の作成者名と開始日を指定します。

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### 解決策2:

 A: リビジョントラッキングを有効にするには、`Document`コンストラクタは受け入れる`trackRevisions`そして`author`パラメーター。

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### Q: Aspose.Words for .NET を使用してドキュメント内のすべての変更を受け入れるにはどうすればよいですか?

 A:`AcceptAllRevisions`方法の`Document`ドキュメントに加えられたすべての変更を受け入れるオブジェクト。

```csharp
doc.AcceptAllRevisions();
```

#### Q: 承認された修正を加えた変更済みドキュメントを保存するにはどうすればよいですか?

使用`Save`方法の`Document`オブジェクトを使用して、変更されたドキュメントを承認されたリビジョンとともに保存します。正しいファイル パスを必ず指定してください。

```csharp
doc.Save("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET でリビジョンの追跡を停止するにはどうすればよいですか?

 A:`StopTrackRevisions`方法の`Document`追跡リビジョンを停止するにはオブジェクトを使用します。

```csharp
doc.StopTrackRevisions();
```

#### Q: Aspose.Words for .NET を使用してドキュメント内の修正された段落を削除するにはどうすればよいですか?

 A: 文書内の修正された段落を削除するには、`Remove`段落収集の方法。

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```