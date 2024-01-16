---
title: Word 文書内のセクションに移動
linktitle: Word 文書内のセクションに移動
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の Word 文書機能でセクションに移動を使用して、Word 文書内のセクションと段落を操作するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/add-content-using-documentbuilder/move-to-section/
---
この例では、提供されている C# ソース コードを使用して、Aspose.Words for .NET の Word ドキュメントのセクションに移動機能を使用する方法を段階的に説明します。この機能を使用すると、Word 文書内のさまざまなセクションに移動して操作できます。この機能をアプリケーションに統合するには、次の手順に従ってください。

## ステップ 1: 新しいドキュメントを作成し、セクションを追加する

まず、新しいドキュメントを作成し、そこにセクションを追加する必要があります。この手順を実行するには、次のコードを使用します。

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

このコードは、新しい空のドキュメントを作成し、このドキュメントにセクションを追加します。

## ステップ 2: DocumentBuilder を 2 番目のセクションに移動し、テキストを追加します

次に、DocumentBuilder をドキュメントの 2 番目のセクションに移動し、そこにテキストを追加する必要があります。このステップを実行するには、次のコードを使用します。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

このコードは、既存のドキュメントから DocumentBuilder を作成し、カーソルを DocumentBuilder からドキュメントの 2 番目のセクションに移動します。最後に、指定されたテキストをこのセクションに追加します。

## ステップ 3: 既存の段落を含むドキュメントをロードする

段落を含む既存のドキュメントを操作する場合は、次のコードを使用してこのドキュメントをロードできます。

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

このコードは、指定されたドキュメントを読み込みます (「MyDir +」Paragraphs.docx を置き換えます)「」ドキュメントへの実際のパスを使用して)、ドキュメントの最初のセクションの段落のコレクションにアクセスします。この線`Assert.AreEqual(22, paragraphs.Count);`文書に 22 段落が含まれていることを確認します。

## ステップ 4: ドキュメントの DocumentBuilder を作成する

位置インデックスを使用して、特定の段落に DocumentBuilder カーソルを作成できます。

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## ステップ 5: カーソルを特定の段落に移動する


位置インデックスを使用して、DocumentBuilder カーソルを特定の段落に移動できます。その方法は次のとおりです。

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

このコードは、DocumentBuilder のカーソルを 2 番目のセクションの 3 番目の段落 (インデックス 2 の段落) の位置 10 に移動します。次に、テキストを含む新しい段落を追加し、カーソルがこの新しい段落に適切に配置されていることを確認します。

### Aspose.Words for .NET を使用した Move To Move To Section のソース コード例

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

//DocumentBuilder を 2 番目のセクションに移動し、テキストを追加します。
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

//段落のある文書を作成します。
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

//ドキュメントの DocumentBuilder を作成すると、デフォルトではそのカーソルはドキュメントの先頭にあります。
// DocumentBuilder によって追加されたコンテンツは、ドキュメントの先頭に追加されるだけです。
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//カーソルを段落内の任意の位置に移動できます。
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

それだけです ！提供されたソース コードを使用して、Aspose.Words for .NET のセクションへの移動機能を使用する方法を理解しました。この機能を独自のアプリケーションに統合し、Word 文書のセクションや段落を動的に操作できるようになりました。

## 結論

この例では、Aspose.Words for .NET のセクションへ移動機能を調べました。新しい文書を作成し、それにセクションを追加し、DocumentBuilder クラスを使用して Word 文書内の特定のセクションや段落に移動する方法を学習しました。この機能は、Aspose.Words for .NET を使用して Word ドキュメントのコンテンツと構造をプログラムで操作するための強力なツールを開発者に提供します。

### Word 文書内のセクションへの移動に関する FAQ

#### Q: Aspose.Words for .NET のセクションへ移動機能の目的は何ですか?

A: Aspose.Words for .NET のセクションへ移動機能を使用すると、開発者は Word 文書内のさまざまなセクションにプログラム的に移動して操作できます。ドキュメントの特定のセクションのコンテンツを挿入、変更、または削除する機能を提供します。

#### Q: DocumentBuilder を Word 文書内の特定のセクションに移動するにはどうすればよいですか?

A: DocumentBuilder を Word 文書内の特定のセクションに移動するには、DocumentBuilder クラスの MoveToSection メソッドを使用できます。このメソッドはターゲット セクションのインデックスをパラメータとして受け取り、そのセクションの先頭にカーソルを置きます。

#### Q: セクションへ移動機能を使用して特定のセクションに移動した後、コンテンツを追加または変更できますか?

A: はい、MoveToSection を使用して DocumentBuilder を目的のセクションに配置したら、Writeln、Write、InsertHtml などの DocumentBuilder クラスのさまざまなメソッドを使用して、そのセクションのコンテンツを追加または変更できます。

#### Q: セクションに移動機能を使用してドキュメント内の既存の段落を操作するにはどうすればよいですか?

A: Document コンストラクターを使用して段落を含む既存のドキュメントをロードし、FirstSection.Body.Paragraphs プロパティを使用して目的のセクションから段落のコレクションにアクセスできます。

#### Q: セクションへ移動機能を使用して、DocumentBuilder カーソルをセクション内の特定の段落に移動できますか?

A: はい、MoveToParagraph メソッドを使用して、DocumentBuilder カーソルをセクション内の特定の段落に移動できます。このメソッドは、ターゲット段落のインデックスと段落内の文字位置 (オフセット) をパラメータとして受け取ります。