---
title: Word 文書のヘッダー フッターに移動
linktitle: Word 文書のヘッダー フッターに移動
second_title: Aspose.Words ドキュメント処理 API
description: このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word ドキュメント内のヘッダーとフッターを移動および変更する方法を学びます。
type: docs
weight: 10
url: /ja/net/add-content-using-documentbuilder/move-to-headers-footers/
---
この例では、Aspose.Words for .NET のヘッダー フッターに移動機能を調べます。 Aspose.Words は、開発者が Word ドキュメントをプログラムで作成、変更、変換できるようにする強力なドキュメント操作ライブラリです。ヘッダー/フッターに移動機能を使用すると、ドキュメント内のさまざまなヘッダーとフッターに移動して、それらにコンテンツを追加できます。

Aspose.Words for .NET を使用してヘッダー/フッターに移動機能を使用する方法を理解するために、ソース コードを段階的に見てみましょう。

## ステップ 1: ドキュメントとドキュメント ビルダーの初期化

まず、Document オブジェクトと DocumentBuilder オブジェクトを初期化します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: ヘッダーとフッターの構成

ドキュメントのヘッダー/フッター設定を指定します。この例では、ヘッダーとフッターが最初のページと奇数/偶数ページで異なるように設定します。

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## ステップ 3: さまざまなページのヘッダーを作成する

各ヘッダー タイプに移動し、コンテンツを追加します。この例では、最初のページ、偶数ページ、およびその他すべてのページのヘッダーを作成します。

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## ステップ 4: ドキュメント内にページを作成する
ドキュメントにコンテンツを追加して複数のページを作成します。例えば：

```csharp
//文書内に 2 ページを作成します。
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## ステップ 5: ドキュメントを保存する

変更したドキュメントを目的の場所に保存します。

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

必ず適切なファイル パスと形式 (DOCX など) を指定してください。

### Aspose.Words for .NET を使用したヘッダー/フッターへの移動のソース コード例

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//最初のページ、偶数ページ、奇数ページでヘッダーとフッターを異なるように指定します。
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

//ヘッダーを作成します。
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

//文書内に 2 ページを作成します。
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

## 結論

この例では、Aspose.Words for .NET のヘッダー/フッターに移動機能を調べました。 Word 文書内のさまざまなヘッダーとフッターに移動し、DocumentBuilder クラスを使用してそれらにコンテンツを追加する方法を学習しました。この機能により、開発者は特定のページまたはセクションのヘッダーとフッターをカスタマイズできるため、プロフェッショナルで構造化されたドキュメントを柔軟に作成できます。 Aspose.Words for .NET は、Word ドキュメントをプログラムで操作するための強力なツール セットを提供し、ドキュメント処理アプリケーションにとって不可欠なライブラリとなっています。

### Word 文書のヘッダー フッターへの移動に関する FAQ

#### Q: Aspose.Words for .NET のヘッダー/フッターに移動機能の目的は何ですか?

A: Aspose.Words for .NET のヘッダー/フッターへの移動機能を使用すると、開発者は Word 文書内のさまざまなヘッダーとフッターに移動し、プログラムでコンテンツを追加できます。これは、ドキュメント内のさまざまなページまたはセクションのヘッダーとフッターをカスタマイズする必要がある場合に便利です。

#### Q: ドキュメント内のページごとに異なるヘッダーとフッターを使用できますか?

A: はい、PageSetup.DifferentFirstPageHeaderFooter プロパティと PageSetup.OddAndEvenPagesHeaderFooter プロパティをそれぞれ使用して、最初のページ、偶数ページ、奇数ページに異なるヘッダーとフッターを指定できます。

#### Q: 特定のヘッダーとフッターにコンテンツを追加するにはどうすればよいですか?

A: 特定のヘッダーとフッターにコンテンツを追加するには、DocumentBuilder クラスの MoveToHeaderFooter メソッドを使用します。要件に基づいて、HeaderFirst、HeaderEven、および HeaderPrimary ヘッダー、または FooterFirst、FooterEven、および FooterPrimary フッターに移動できます。

#### Q: ドキュメント内の特定のセクションにヘッダーとフッターを作成できますか?

A: はい、DocumentBuilder クラスの MoveToSection メソッドを使用してドキュメント内の特定のセクションに移動し、そのセクション内にヘッダーとフッターを作成できます。

#### Q: Aspose.Words for .NET を使用して、変更したドキュメントをファイルに保存するにはどうすればよいですか?

A: Document クラスの Save メソッドを使用して、変更したドキュメントを目的の場所と形式で保存できます。必ず適切なファイル パスとファイル形式 (DOCX など) を指定してください。