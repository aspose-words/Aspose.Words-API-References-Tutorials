---
title: テーブルスタイルの作成
linktitle: テーブルスタイルの作成
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してカスタム テーブル スタイルを作成するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/create-table-style/
---

このチュートリアルでは、Aspose.Words for .NET を使用して表スタイルを作成する手順を段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word 文書内の表のカスタム スタイルを作成する方法がわかります。

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

## ステップ 3: 新しいテーブルを開始し、セルを追加する
テーブルの作成を開始するには、`StartTable()`ドキュメントビルダーのメソッドを使用してテーブルにセルを追加します。`InsertCell()`メソッドを使用し、セルの内容を に書き込みます。`Write()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## ステップ 4: 表スタイルを作成する
これで、次を使用してテーブル スタイルを作成できます。`TableStyle`クラスと`Add()`ドキュメントからのメソッド`s `スタイルズコレクション。境界線、マージン、パディングなどのスタイルのプロパティを定義します。

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## ステップ 5: 表スタイルを表に適用する
最後に、作成した表スタイルを表に適用します。`Style`テーブルのプロパティ。

```csharp
table.Style = tableStyle;
```

## ステップ 6: 変更したドキュメントを保存する
最後に、変更したドキュメントをファイルに保存します。出力ドキュメントの適切な名前と場所を選択できます。

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

おめでとうございます！これで、Aspose.Words for .NET を使用してテーブルのカスタム スタイルが作成されました。

### Aspose.Words for .NET を使用したテーブル スタイルの作成のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してテーブル スタイルを作成する方法を学びました。このステップバイステップのガイドに従うことで、Word 文書内の表のスタイルを簡単にカスタマイズできます。 Aspose.Words は、ドキュメント内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、Word 文書の視覚的なプレゼンテーションを改善し、特定のニーズを満たすことができます。