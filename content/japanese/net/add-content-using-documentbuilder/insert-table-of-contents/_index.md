---
title: Word文書に目次を挿入する
linktitle: Word文書に目次を挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に目次を挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/add-content-using-documentbuilder/insert-table-of-contents/
---
この包括的なチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に目次を挿入する方法を学習します。プロセスを案内し、必要な C# コード スニペットを提供します。このガイドを最後まで読み終えると、適切な見出しとページ番号を付けた目次を生成できるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ 1: 新しいドキュメントと DocumentBuilder を作成する
まず、Document クラスを使用して新しいドキュメントを作成し、DocumentBuilder オブジェクトを初期化します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: 目次を挿入する
次に、DocumentBuilder クラスの InsertTableOfContents メソッドを使用して目次を挿入します。メソッド内で必要な書式設定オプションを指定します。

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## ステップ 3: ドキュメントのコンテンツを追加する
目次を挿入した後、実際のドキュメントの内容を追加します。 StyleIdentifier を使用して、適切な見出しスタイルを設定します。

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## ステップ 4: 目次を更新する
新しく挿入された目次は、最初は空です。これを設定するには、ドキュメント内のフィールドを更新します。

```csharp
doc.UpdateFields();
```

## ステップ 5: ドキュメントを保存する
目次を挿入し、フィールドを更新した後、Document クラスの Save メソッドを使用してドキュメントをファイルに保存します。

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Aspose.Words for .NET を使用した目次の挿入のソース コード例
Aspose.Words for .NET を使用して目次を挿入するための完全なソース コードを次に示します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document オブジェクトを使用して DocumentBuilder を初期化する
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//目次を挿入
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

//実際のドキュメントの内容は 2 ページ目から始めます。
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


//新しく挿入された目次は、最初は空です。
//ドキュメント内のフィールドを更新して値を設定する必要があります。
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## 結論

おめでとう！ Aspose.Words for .NET を使用して Word 文書に目次を挿入する方法を学習しました。このステップバイステップ ガイドに従い、提供されているソース コードを利用すると、ドキュメントに適切な見出しとページ番号を付けた目次を生成できます。

### Word 文書に目次を挿入する場合の FAQ

#### Q: 目次の外観をカスタマイズできますか?

 A: はい、目次で指定されている書式設定オプションを変更することで、目次の外観をカスタマイズできます。`InsertTableOfContents`方法。パラメータを使用すると、ページ番号、インデント、その他のスタイルを制御できます。

#### Q: 目次に特定の見出しレベルを含めたい場合はどうすればよいですか?

 A: 目次内の値を調整することで、目次に含める必要な見出しレベルを指定できます。`InsertTableOfContents`方法。たとえば、次のように使用します。`"\\o \"1-3\""`見出しレベル 1 ～ 3 が含まれます。

#### Q: ドキュメントの内容を変更した場合、目次を自動的に更新できますか?

 A: はい、呼び出して目次を自動的に更新できます。`UpdateFields`ドキュメント上のメソッド。これにより、見出しの追加や削除など、ドキュメントのコンテンツに加えられた変更が確実に目次に反映されます。

#### Q: 目次の見出しレベルを別のスタイルにするにはどうすればよいですか?

 A: 見出しレベルごとに異なる段落スタイルを使用することで、見出しレベルのスタイルを変えることができます。異なるものを割り当てることで、`StyleIdentifier`の値`ParagraphFormat`の`DocumentBuilder`では、見出しレベルごとに個別のスタイルを作成できます。

#### Q: 目次の見出しに追加の書式設定を追加することはできますか?

 A: はい、目次の見出しにフォント スタイル、色、その他のプロパティなどの追加の書式設定を追加できます。を調整することで、`Font`のプロパティ`DocumentBuilder`では、見出しにカスタム書式を適用できます。