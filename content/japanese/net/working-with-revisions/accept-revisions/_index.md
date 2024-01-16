---
title: 改訂を受け入れる
linktitle: 改訂を受け入れる
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の改訂を受け入れる方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/accept-revisions/
---

このチュートリアルでは、Aspose.Words for .NET の改訂受け入れ機能を使用して Word 文書の改訂を受け入れる手順を説明します。ソース コードを理解し、ドキュメントへの変更を受け入れるには、次の手順に従ってください。

## ステップ 1: ドキュメントコンテンツの追加と編集

この例では、ドキュメントを作成し、コンテンツを追加しています。変更と改訂を説明するためにいくつかの段落を使用します。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//最初の段落にテキストを追加し、さらに 2 つの段落を追加します。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## ステップ 2: レビューを追跡し、レビューを追加する

リビジョン追跡を有効にし、ドキュメントにリビジョンを追加します。その方法は次のとおりです。

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

//この段落はリビジョンであり、対応する「IsInsertRevision」フラグが設定されます。
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## ステップ 3: 段落を削除し、リビジョンを管理する

段落を削除し、保存されたリビジョンを確認します。その方法は次のとおりです。

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

//リビジョンを追跡しているため、段落は文書内にまだ存在しており、「IsDeleteRevision」フラグが設定されています。
//すべてのレビューを承認または拒否するまで、Microsoft Word でレビューとして表示されます。
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## ステップ 4: 変更を受け入れる

文書に対するすべての変更を受け入れます。その方法は次のとおりです。

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## ステップ 5: レビューの追跡を停止する

リビジョンの追跡を停止し、ドキュメントへの変更がリビジョンとして表示されないようにする予定です。その方法は次のとおりです。

```csharp
doc.StopTrackRevisions();
```
## ステップ 6: ドキュメントを保存する

テキスト入力フォームフィールドを挿入した後、`Save`方法。必ず適切なファイル パスを指定してください。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Aspose.Words for .NET を使用した改訂受け入れのソース コード例

Aspose.Words for .NET を使用してドキュメントの変更を受け入れるための完全なソース コードを次に示します。


```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//最初の段落にテキストを追加し、さらに 2 つの段落を追加します。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// つの段落がありますが、いずれのタイプの改訂としても登録されていません
//リビジョンの追跡中にドキュメント内のコンテンツを追加または削除すると、
//それらは文書内にそのように表示され、承認または拒否できます。
doc.StartTrackRevisions("John Doe", DateTime.Now);

//この段落はリビジョンであり、それに応じて「IsInsertRevision」フラグが設定されます。
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

//ドキュメントの段落コレクションを取得し、段落を削除します。
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

//リビジョンを追跡しているため、段落は文書内にまだ存在しており、「IsDeleteRevision」が設定されています。
//すべてのリビジョンが承認または拒否されるまで、Microsoft Word ではリビジョンとして表示されます。
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

//リビジョン削除の段落は、変更を受け入れると削除されます。
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

//リビジョンの追跡を停止すると、このテキストは通常のテキストとして表示されます。
//ドキュメントが変更された場合、リビジョンはカウントされません。
doc.StopTrackRevisions();

//文書を保存します。
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## 結論

このチュートリアルでは、Aspose.Words for .NET の改訂受け入れ機能を使用して Word 文書の改訂を受け入れる方法を学びました。文書コンテンツの追加と編集、改訂の追跡、改訂された段落の削除、すべての変更の承認、改訂の追跡の停止の手順に従いました。この知識を応用して、Aspose.Words for .NET を使用して独自の Word 文書のリビジョンを効果的に管理できるようになりました。

### よくある質問

#### Q: Aspose.Words for .NET でリビジョン追跡を有効にするにはどうすればよいですか?

#### 解決策 1:

 A: Aspose.Words for .NET でリビジョン追跡を有効にするには、`StartTrackRevisions`の方法`Document`オブジェクトを作成し、リビジョン追跡の作成者名と開始日を指定します。

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### 解決策 2:

 A: を使用してリビジョン追跡を有効にすることもできます。`Document`を受け入れるコンストラクタ`trackRevisions`そして`author`パラメーター。

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### Q: Aspose.Words for .NET でドキュメント内のすべての変更を受け入れるにはどうすればよいですか?

 A: を使用してください。`AcceptAllRevisions`の方法`Document`オブジェクトを使用して、ドキュメントに加えられたすべての変更を受け入れます。

```csharp
doc.AcceptAllRevisions();
```

#### Q: 変更されたドキュメントを承認されたリビジョンで保存するにはどうすればよいですか?

使用`Save`の方法`Document`オブジェクトを使用して、変更されたドキュメントを受け入れられたリビジョンで保存します。必ず正しいファイル パスを指定してください。

```csharp
doc.Save("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET でのリビジョンの追跡を停止するにはどうすればよいですか?

 A: を使用してください。`StopTrackRevisions`の方法`Document`オブジェクトを使用してリビジョンの追跡を停止します。

```csharp
doc.StopTrackRevisions();
```

#### Q: Aspose.Words for .NET を使用して文書内の改訂された段落を削除するにはどうすればよいですか?

 A: 文書内の改訂された段落を削除するには、`Remove`段落コレクションのメソッド。

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```