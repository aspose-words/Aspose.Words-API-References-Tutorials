---
title: スタイルを使用してテーブルを作成する
linktitle: スタイルを使用してテーブルを作成する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してカスタム スタイルでテーブルを作成するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

このチュートリアルでは、Aspose.Words for .NET を使用してスタイル付きテーブルを作成するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word 文書内にカスタム スタイルの表を作成する方法がわかります。

## ステップ 1: ドキュメント ディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集した Word 文書を保存する場所です。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: 新しいドキュメントとドキュメント ビルダーを作成する
次に、の新しいインスタンスを作成する必要があります。`Document`クラスとそのドキュメントのドキュメント コンストラクター。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: 新しいテーブルを開始し、セルを挿入する
テーブルの構築を開始するには、`StartTable()`ドキュメントビルダーのメソッドを使用して、テーブルにセルを挿入します。`InsertCell()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## ステップ 4: テーブルのスタイルを定義する
これで、テーブルのスタイルを設定できるようになりました。`StyleIdentifier`財産。この例では、「MediumShading1Accent1」スタイルを使用しています。

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## ステップ 5: スタイル オプションをテーブルに適用する
を使用して、スタイルによってどの特性を書式設定するかを指定できます。`StyleOptions`配列のプロパティ。この例では、「FirstColumn」、「RowBands」、「FirstRow」のオプションを適用します。

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## ステップ 6: テーブル サイズを自動的に調整する
配列の内容に基づいて配列のサイズを自動的に調整するには、`AutoFit()`を使用したメソッド`AutoFitBehavior.AutoFitToContents`行動。

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## ステップ 7: セルにコンテンツを追加する
これで、次を使用してセルにコンテンツを追加できるようになりました。`Writeln()`そして`InsertCell()`ドキュメントビルダーのメソッド。この例では、「Item」と「Quantity (

kg)」および対応するデータ。

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## ステップ 8: 変更したドキュメントを保存する
最後に、変更したドキュメントをファイルに保存します。出力ドキュメントの適切な名前と場所を選択できます。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

おめでとうございます！これで、Aspose.Words for .NET を使用してカスタム スタイルのテーブルが構築されました。

### Aspose.Words for .NET を使用したスタイル付きテーブルの構築のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	//表の書式設定を設定する前に、まず少なくとも 1 行を挿入する必要があります。
	builder.InsertCell();
	//一意のスタイル識別子に基づいて、使用するテーブル スタイルを設定します。
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	//どのフィーチャをスタイルによって書式設定する必要があるかを適用します。
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してスタイル付きテーブルを作成する方法を学びました。このステップバイステップのガイドに従うことで、Word 文書内の表のスタイルを簡単にカスタマイズできます。 Aspose.Words は、ドキュメント内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、Word 文書の視覚的なプレゼンテーションを改善し、特定のニーズを満たすことができます。