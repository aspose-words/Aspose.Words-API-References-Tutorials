---
title: Word文書に表を作成する
linktitle: Word文書に表を作成する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内に表を作成する方法を学びます。
type: docs
weight: 10
url: /ja/net/add-content-using-documentbuilder/build-table/
---
このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内に表を作成する方法を学習します。プロセスを案内し、必要な C# コード スニペットを提供します。このガイドを終えると、DocumentBuilder クラスを使用してカスタムの書式設定とコンテンツを含む表を作成できるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ 1: 新しいドキュメントを作成する
まず、Document クラスを使用して新しいドキュメントを作成します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: テーブルを開始する
次に、DocumentBuilder クラスの StartTable メソッドを使用して、テーブルの構築を開始します。

```csharp
Table table = builder.StartTable();
```

## ステップ 3: セルを挿入してコンテンツを追加する
これで、DocumentBuilder クラスの InsertCell メソッドと Write メソッドを使用して、テーブルにセルを挿入し、セルにコンテンツを追加できるようになりました。必要に応じてセルの書式設定をカスタマイズします。

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## ステップ 4: 列を終了する
最初の行のセルにコンテンツを追加した後、DocumentBuilder クラスの EndRow メソッドを使用して行を終了します。

```csharp
builder.EndRow();
```

## ステップ 5: 行の書式設定をカスタマイズする
RowFormat オブジェクトと CellFormat オブジェクトのプロパティを設定することで、行の書式設定をカスタマイズできます。

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## ステップ 6: テーブルを終了する
表を完成するには、DocumentBuilder クラスの EndTable メソッドを使用します。

```csharp
builder.EndTable();
```

### Aspose.Words for .NET を使用してテーブルを構築するためのソース コードの例
Aspose.Words for .NET を使用してテーブルを構築するための完全なソース コードを次に示します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## 結論
おめでとう！ Aspose.Words for .NET を使用して Word 文書内に表を作成する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、カスタム書式設定を使用したテーブルを作成できるようになります。

### Word 文書でのテーブルの作成に関する FAQ

#### Q: Aspose.Words for .NET とは何ですか?

A: Aspose.Words for .NET は、開発者が .NET アプリケーションでプログラム的に Microsoft Word ドキュメントを作成、読み取り、編集、変換できるようにする強力なドキュメント処理ライブラリです。テキスト操作、表の作成、文書保護、書式設定など、Word 文書を操作するための幅広い機能を提供します。

#### Q: Aspose.Words for .NET を使用して Word 文書内に表を作成するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書内に表を作成するには、次の手順に従います。
1. の新しいインスタンスを作成します。`Document`クラスと`DocumentBuilder`物体。
2. 使用`StartTable`の方法`DocumentBuilder`クラスを使用してテーブルの作成を開始します。
3. 表にセルを挿入し、`InsertCell`そして`Write`のメソッド`DocumentBuilder`クラス。
4. を使用して行を終了します`EndRow`の方法`DocumentBuilder`クラス。
5. のプロパティを設定して行の書式設定をカスタマイズします。`RowFormat`そして`CellFormat`オブジェクト。
6. を使用してテーブルを終了します`EndTable`の方法`DocumentBuilder`クラス。
7. 文書を保存します。

#### Q: テーブルとそのセルの書式設定をカスタマイズするにはどうすればよいですか?

 A: テーブルのさまざまなプロパティを設定することで、テーブルとそのセルの書式設定をカスタマイズできます。`RowFormat`そして`CellFormat`オブジェクト。たとえば、セルの配置、テキストの縦方向と横方向、セルの高さ、行の高さなどを調整できます。これらのプロパティを使用すると、テーブルとその内容を希望どおりの外観にすることができます。

#### Q: 結合されたセルやその他の高度な機能を使用して複雑なテーブルを作成できますか?

 A: はい。Aspose.Words for .NET は、結合セル、ネストされたテーブル、複雑なテーブル レイアウトのサポートなど、複雑なテーブルを構築するための高度な機能を提供します。使用できます`MergeCells`セルを結合するメソッド、`StartTable`ネストされたテーブルを作成する方法、および目的のテーブル構造を実現するその他の方法。

#### Q: Aspose.Words for .NET はさまざまな Word ドキュメント形式と互換性がありますか?

A: はい、Aspose.Words for .NET は、DOC、DOCX、RTF などを含むさまざまな Word ドキュメント形式と互換性があります。従来の形式 (DOC) と最新の XML ベースの形式 (DOCX) の両方をサポートしており、さまざまな形式のドキュメントを問題なく操作できます。

#### Q: Aspose.Words for .NET の詳細情報とドキュメントはどこで入手できますか?

 A: 包括的なドキュメントとコード例は、次の場所にあります。[APIリファレンス](https://reference.aspose.com/words/net/)。このドキュメントには、ライブラリの機能と、.NET アプリケーションでの使用方法に関する詳細情報が記載されています。