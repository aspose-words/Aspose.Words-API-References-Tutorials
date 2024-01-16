---
title: ヘッダー・フッターの作成
linktitle: ヘッダー・フッターの作成
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にヘッダーとフッターを作成する方法を学びます。各ページのヘッダーとフッターをカスタマイズします。
type: docs
weight: 10
url: /ja/net/working-with-headers-and-footers/create-header-footer/
---

ここでは、Aspose.Words for .NET 機能を使用してヘッダーとフッターを作成するための次の C# ソース コードを説明するステップバイステップ ガイドを示します。このコードを使用する前に、プロジェクトに Aspose.Words ライブラリが含まれていることを確認してください。

## ステップ 1: ドキュメント ディレクトリ パスを設定する

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

編集したドキュメントが保存されるドキュメント ディレクトリへの正しいパスを必ず指定してください。

## ステップ 2: ドキュメントとドキュメント ジェネレーターを作成する

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

ここで、のインスタンスを作成します。`Document`クラスとインスタンス`DocumentBuilder`このクラスを使用すると、ドキュメントを操作して要素を追加できるようになります。

## ステップ 3: ページパラメータと最初のヘッダーを設定する

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

//最初のページのヘッダー/フッターを他のページとは異なるものにするかどうかを指定します。
// PageSetup.OddAndEvenPagesHeaderFooter プロパティを使用して指定することもできます。
//奇数ページと偶数ページで異なるヘッダー/フッター。
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

ヘッダーの距離などのページ パラメーターを設定し、メイン ヘッダー (`HeaderPrimary`）。ドキュメント ジェネレーターを使用してテキストを追加し、ヘッダーの書式を設定します。

## ステップ 4: メインヘッダーに画像とテキストを挿入する

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

ドキュメント ジェネレーターを使用してメイン ヘッダーの左上隅に画像を挿入し、右揃えのテキストを追加します。

## ステップ 5: メインフッターに表を挿入する

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## ステップ 6: 新しいページを追加し、ヘッダー/フッターを設定する

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
//このセクションでは、最初のページに別のヘッダー/フッターは必要ありません。ドキュメントにはタイトル ページが 1 つだけ必要です。
//このページのヘッダー/フッターは前のセクションですでに定義されています。
pageSetup.DifferentFirstPageHeaderFooter = false;

//このセクションには、デフォルトで前のセクションのヘッダー/フッターが表示されます。このリンクを解除するには、 currentSection.HeadersFooters.LinkToPrevious(false) を呼び出します。
//新しいセクションではページ幅が異なるため、フッター テーブルには異なるセル幅を設定する必要があります。
currentSection.HeadersFooters.LinkToPrevious(false);

//このセクションに既存のヘッダー/フッターを使用したい場合は、
//ただし、いくつかの小さな変更を加えると、ヘッダー/フッターをコピーすることが合理的になる場合があります。
//前のセクションの内容を参照し、必要な箇所に必要な変更を適用します。
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

//文書を保存する
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

改ページとセクション区切りを追加して、主要なヘッダー/フッターが表示される新しいページを作成します。新しいセクションのパラメータを設定してから、`CopyHeadersFootersFromPreviousSection`前のセクションからヘッダー/フッターをコピーするメソッド。最後に、メインのフッター テーブルに適切なセル幅を設定し、ドキュメントを保存します。

### Aspose.Words for .NET を使用してヘッダーとフッターを作成するソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
//最初のページのヘッダー/フッターを他のページとは異なるものにするかどうかを指定します。
// PageSetup.OddAndEvenPagesHeaderFooter プロパティを使用して指定することもできます。
//奇数ページと偶数ページで異なるヘッダー/フッター。
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

//位置決めされた画像をヘッダーの上部/左隅に挿入します。
//ページの上端/左端からの距離を 10 ポイントに設定します。
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// 2 つのセルを持つ表を使用して、行上のテキストの一部を作成します (ページ番号付き)。
//左揃えに、テキストの他の部分 (著作権付き) は右揃えにします。
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// PAGE フィールドと NUMPAGES フィールドを使用して、現在のページ番号とページ数を自動計算します。
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();

//改ページして、主要なヘッダー/フッターが表示される 2 番目のページを作成します。
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
//このセクションには、最初のページに別のヘッダー/フッターは必要ありません。ドキュメントにはタイトル ページが 1 つだけ必要です。
//このページのヘッダー/フッターは前のセクションですでに定義されています。
pageSetup.DifferentFirstPageHeaderFooter = false;

//このセクションには、前のセクションのヘッダー/フッターが表示されます
//デフォルトでは、currentSection.HeadersFooters.LinkToPrevious(false) を呼び出して、このページ幅をキャンセルします。
//新しいセクションでは異なるため、フッター テーブルに異なるセル幅を設定する必要があります。
currentSection.HeadersFooters.LinkToPrevious(false);

//このセクションに既存のヘッダー/フッター セットを使用したい場合。
//ただし、若干の変更を加えると、ヘッダー/フッターをコピーした方が便利な場合があります。
//前のセクションの内容を参照し、必要な箇所に必要な変更を適用します。
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### よくある質問

#### Q: Aspose.Words でドキュメントにヘッダーを追加するにはどうすればよいですか?

 A: Aspose.Words でドキュメントにヘッダーを追加するには、`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)`方法。このメソッドは、文書の最初のセクションに主要な見出しを追加します。

#### Q: Aspose.Words でドキュメントにフッターを追加するにはどうすればよいですか?

 A: Aspose.Words でドキュメントにフッターを追加するには、`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`方法。このメソッドは、ドキュメントの最初のセクションにプライマリ フッターを追加します。

#### Q: Aspose.Words のヘッダーまたはフッターにテキストを追加するにはどうすればよいですか?

 A: Aspose.Words のヘッダーまたはフッターにテキストを追加するには、`HeaderFooter.Paragraphs`プロパティを使用してヘッダーまたはフッターの段落コレクションを取得し、テキストを含む段落をこのコレクションに追加します。`ParagraphCollection.Add`方法。

#### Q: Aspose.Words で、画像やページ番号を使用してヘッダーまたはフッターのコンテンツをカスタマイズできますか?

 A: はい、Aspose.Words では、画像やページ番号を使用してヘッダーまたはフッターのコンテンツをカスタマイズできます。次のようなオブジェクトを使用できます`Shape`のような画像やオブジェクトを追加するには`Field`ヘッダーまたはフッターにページ番号を追加します。

#### Q: Aspose.Words のヘッダーまたはフッターのテキストのフォント、サイズ、色を変更できますか?

 A: はい、Aspose.Words のヘッダーまたはフッターのテキストのフォント、サイズ、色を変更できます。次のようなテキスト書式設定プロパティにアクセスできます。`Font`フォントを変更するには、`Size`サイズを調整したり、`Color`文字の色を設定します。