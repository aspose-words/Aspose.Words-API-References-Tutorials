---
title: スタイリッシュにテーブルを作る
linktitle: スタイリッシュにテーブルを作る
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してカスタム スタイルでテーブルを構築するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

このチュートリアルでは、Aspose.Words for .NET を使用してスタイル設定されたテーブルを作成する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word ドキュメントにカスタム スタイルのテーブルを作成する方法がわかります。

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集した Word 文書を保存する場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: 新しいドキュメントとドキュメントビルダーを作成する
次に、新しいインスタンスを作成する必要があります。`Document`クラスとそのドキュメントのドキュメント コンストラクター。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: 新しい表を作成してセルを挿入する
テーブルの構築を開始するには、`StartTable()`ドキュメントビルダーのメソッドを使用してテーブルにセルを挿入し、`InsertCell()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## ステップ4: テーブルのスタイルを定義する
これで、テーブルスタイルを設定することができます。`StyleIdentifier`プロパティ。この例では、「MediumShading1Accent1」スタイルを使用しています。

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## ステップ5: テーブルにスタイルオプションを適用する
スタイルによってどの特性をフォーマットするかを指定するには、`StyleOptions`配列のプロパティ。この例では、「FirstColumn」、「RowBands」、および「FirstRow」というオプションを適用します。

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## ステップ6: テーブルのサイズを自動的に調整する
配列の内容に応じて配列のサイズを自動的に調整するには、`AutoFit()`方法`AutoFitBehavior.AutoFitToContents`行動。

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## ステップ7: セルにコンテンツを追加する
これで、セルにコンテンツを追加できるようになりました。`Writeln()`そして`InsertCell()`ドキュメントビルダーのメソッド。この例では、「Item」と「Quantity（

kg)」とそれに対応するデータを表示します。

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

## ステップ8: 変更したドキュメントを保存する
最後に、変更したドキュメントをファイルに保存します。出力ドキュメントに適切な名前と場所を選択できます。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

おめでとうございます！Aspose.Words for .NET を使用して、カスタム スタイルのテーブルを構築できました。

### Aspose.Words for .NET を使用してスタイル付きテーブルを作成するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	//テーブルの書式を設定する前に、まず少なくとも 1 行を挿入する必要があります。
	builder.InsertCell();
	//一意のスタイル識別子に基づいて、使用するテーブル スタイルを設定します。
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	//スタイルによってフォーマットする機能を適用します。
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
このチュートリアルでは、Aspose.Words for .NET を使用してスタイル設定された表を作成する方法を学習しました。このステップ バイ ステップ ガイドに従うことで、Word 文書内の表のスタイルを簡単にカスタマイズできます。Aspose.Words は、文書内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、Word 文書の視覚的なプレゼンテーションを改善し、特定のニーズを満たすことができます。