---
title: 表の行の書式を設定する
linktitle: 表の行の書式を設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してテーブル行の書式を設定する手順ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

このチュートリアルでは、Aspose.Words for .NET を使用して表の行の書式を設定する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word ドキュメントの表の行の高さとパディングを調整する方法がわかります。

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

## ステップ3: 新しいテーブルを開始してセルを追加する
テーブルの作成を開始するには、`StartTable()`ドキュメントコンストラクタのメソッドを使用してテーブルにセルを追加し、`InsertCell()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## ステップ4: 線の書式を定義する
これで、行の書式設定を`RowFormat`の目的`DocumentBuilder`オブジェクト。対応するプロパティを使用して、行の高さと余白 (パディング) を設定できます。

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## ステップ5: 表の余白を設定する
次に、対応するプロパティにアクセスしてテーブルのパディングを設定します。`Table`オブジェクト。これらの余白はテーブルのすべての行に適用されます。

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## ステップ6: 行にコンテンツを追加する
最後に、ドキュメントビルダーの`Writeln()`方法。

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## ステップ7: 表を完成させてドキュメントを保存する
で

最後に、テーブルの作成を終了します。`EndRow()`そして`EndTable()`メソッドを実行して、変更されたドキュメントをファイルに保存します。

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Aspose.Words for .NET を使用してテーブル行の書式を設定するサンプル ソース コード 

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
このチュートリアルでは、Aspose.Words for .NET を使用して表の行の書式を設定する方法を学習しました。このステップバイステップ ガイドに従うことで、Word ドキュメント内の表の行の高さと余白を簡単に調整できます。Aspose.Words は、ドキュメント内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせて表の視覚的なレイアウトをカスタマイズできます。