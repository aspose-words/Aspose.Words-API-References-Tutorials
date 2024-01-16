---
title: テーブル行の書式設定を設定する
linktitle: テーブル行の書式設定を設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してテーブル行の書式設定を設定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

このチュートリアルでは、Aspose.Words for .NET を使用してテーブル行の書式設定を設定するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word 文書内の表の行の高さとパディングを調整する方法がわかります。

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
テーブルの作成を開始するには、`StartTable()`ドキュメント コンストラクターのメソッドを使用して、テーブルにセルを追加します。`InsertCell()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## ステップ 4: 行の書式設定を定義する
これで、にアクセスして行の書式設定を設定できるようになりました。`RowFormat`のオブジェクト`DocumentBuilder`物体。対応するプロパティを使用して、行の高さとマージン (パディング) を設定できます。

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## ステップ 5: 表の余白を設定する
次に、対応するプロパティにアクセスしてテーブルのパディングを設定できます。`Table`物体。これらのマージンはテーブルのすべての行に適用されます。

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## ステップ 6: 行にコンテンツを追加する
最後に、ドキュメントビルダーを使用して行にコンテンツを追加できます。`Writeln()`方法。

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## ステップ 7: 表を完成させ、文書を保存する
で

最後に、を使用してテーブルの作成を終了します。`EndRow()`そして`EndTable()`メソッドを使用して、変更したドキュメントをファイルに保存します。

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Aspose.Words for .NET を使用したテーブル行の書式設定のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	//これらの書式設定プロパティはテーブルに設定され、テーブル内のすべての行に適用されます。
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してテーブルの行の書式設定を設定する方法を学びました。このステップバイステップのガイドに従うことで、Word 文書内の表の行の高さと余白を簡単に調整できます。 Aspose.Words は、ドキュメント内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせてテーブルの視覚的なレイアウトをカスタマイズできます。