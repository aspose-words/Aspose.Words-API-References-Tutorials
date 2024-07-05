---
title: 表のセルの書式を設定する
linktitle: 表のセルの書式を設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してテーブル セルの書式を設定する手順ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/set-table-cell-formatting/
---

このチュートリアルでは、Aspose.Words for .NET を使用して表のセルの書式を定義する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word ドキュメントの表のセルの幅と余白 (パディング) を調整する方法がわかります。

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
builder. StartTable();
builder. InsertCell();
```

## ステップ4: セルの書式を設定する
これで、セルの書式設定を`CellFormat`の目的`DocumentBuilder`オブジェクト。対応するプロパティを使用して、セルの幅と余白 (パディング) を設定できます。

```csharp
CellFormat cellFormat = builder. CellFormat;
cellFormat. Width = 250;
cellFormat. LeftPadding = 30;
cellFormat. RightPadding = 30;
cellFormat. TopPadding = 30;
cellFormat.BottomPadding = 30;
```

## ステップ5: セルにコンテンツを追加する
次に、ドキュメントビルダーの`Writeln()`方法。

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## ステップ6: 表を完成させてドキュメントを保存する
最後に、`EndRow()`方法と`EndTable()`次に、変更したドキュメントをファイルに保存します。

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

### Aspose.Words for .NET を使用して表のセルの書式を設定するサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	CellFormat cellFormat = builder.CellFormat;
	cellFormat.Width = 250;
	cellFormat.LeftPadding = 30;
	cellFormat.RightPadding = 30;
	cellFormat.TopPadding = 30;
	cellFormat.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して表のセルの書式を設定する方法を学習しました。このステップ バイ ステップ ガイドに従うことで、Word ドキュメント内の表のセルの幅と余白を簡単に調整できます。Aspose.Words は、ドキュメント内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせて表の視覚的なレイアウトをカスタマイズできます。