---
title: 行の書式設定を適用する
linktitle: 行の書式設定を適用する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してテーブルに行の書式設定を適用するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

このチュートリアルでは、Aspose.Words for .NET を使用してテーブルに行の書式設定を適用するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルを終えると、Aspose.Words for .NET を使用して Word 文書内の表の行を書式設定する方法を明確に理解できるようになります。

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

## ステップ 3: 新しいボードを開始する
行の書式設定を適用するには、まず、`StartTable()`ドキュメントコンストラクターのメソッド。

```csharp
Table table = builder. StartTable();
```

## ステップ 4: セルを挿入し、行の書式設定に進みます。
これで、テーブルにセルを挿入し、ドキュメント ビルダーのツールを使用してそのセルの行形式にアクセスできるようになりました。`InsertCell()`そして`RowFormat`方法。

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## ステップ 5: 行の高さを設定する
行の高さを設定するには、`Height`そして`HeightRule`行フォーマットのプロパティ。この例では、行の高さを 100 ポイントに設定し、`Exactly`ルール。

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## ステップ 6: テーブルの書式設定を定義する
一部の書式設定プロパティはテーブル自体に設定でき、テーブルのすべての行に適用されます。この例では、次のコマンドを使用してテーブルマージンプロパティを設定します。`LeftPadding`, `RightPadding`, `TopPadding`そして`BottomPadding`プロパティ。

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## ステップ 7: 行にコンテンツを追加する
今ならできる

ドキュメント コンストラクターのメソッドを使用して、行にコンテンツを追加します。この例では、`Writeln()`行にテキストを追加するメソッド。

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## ステップ 8: ラインとテーブルを完成させる
行にコンテンツを追加したら、`EndRow()`メソッドを使用してテーブルを終了します。`EndTable()`方法。

```csharp
builder. EndRow();
builder. EndTable();
```

## ステップ 9: 変更したドキュメントを保存する
最後に、変更したドキュメントをファイルに保存します。出力ドキュメントの適切な名前と場所を選択できます。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

おめでとうございます！これで、Aspose.Words for .NET を使用してテーブルに行の書式設定が適用されました。

### Aspose.Words for .NET を使用した行の書式設定の適用のサンプル ソース コード 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してテーブルに行の書式設定を適用する方法を学びました。このステップバイステップ ガイドに従うことで、この機能を C# プロジェクトに簡単に統合できます。テーブル行の書式設定の操作はドキュメント処理の重要な側面であり、Aspose.Words はこれを実現するための強力で柔軟な API を提供します。この知識があれば、Word 文書の視覚的なプレゼンテーションを改善し、特定の要件を満たすことができます。