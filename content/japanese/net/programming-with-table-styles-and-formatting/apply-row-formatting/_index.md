---
title: 行の書式設定を適用する
linktitle: 行の書式設定を適用する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してテーブルに行の書式設定を適用するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

このチュートリアルでは、Aspose.Words for .NET を使用してテーブルに行の書式設定を適用する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルを完了すると、Aspose.Words for .NET を使用して Word ドキュメントのテーブル行を書式設定する方法を明確に理解できるようになります。

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

## ステップ3: 新しいボードを開始する
行の書式設定を適用するには、まず、`StartTable()`ドキュメントコンストラクタのメソッド。

```csharp
Table table = builder. StartTable();
```

## ステップ4: セルを挿入して行形式に移動する
これで、テーブルにセルを挿入し、ドキュメントビルダーの`InsertCell()`そして`RowFormat`方法。

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## ステップ5: 行の高さを設定する
行の高さを設定するには、`Height`そして`HeightRule`行書式のプロパティ。この例では、行の高さを100ポイントに設定し、`Exactly`ルール。

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## ステップ6: 表の書式を定義する
いくつかの書式設定プロパティはテーブル自体に設定でき、すべてのテーブル行に適用されます。この例では、`LeftPadding`, `RightPadding`, `TopPadding`そして`BottomPadding`プロパティ。

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## ステップ7: 行にコンテンツを追加する
今ならできる

ドキュメントコンストラクタのメソッドを使用して行にコンテンツを追加します。この例では、`Writeln()`行にテキストを追加する方法。

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## ステップ8: 線とテーブルを完成させる
行にコンテンツを追加したら、`EndRow()`メソッドを使用してテーブルを終了します`EndTable()`方法。

```csharp
builder. EndRow();
builder. EndTable();
```

## ステップ9: 変更したドキュメントを保存する
最後に、変更したドキュメントをファイルに保存します。出力ドキュメントに適切な名前と場所を選択できます。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

おめでとうございます！Aspose.Words for .NET を使用して、テーブルに行の書式設定を適用しました。

### Aspose.Words for .NET を使用して行の書式を適用するためのサンプル ソース コード 

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
このチュートリアルでは、Aspose.Words for .NET を使用してテーブルに行の書式設定を適用する方法を学習しました。このステップ バイ ステップ ガイドに従うことで、この機能を C# プロジェクトに簡単に統合できます。テーブル行の書式設定の操作はドキュメント処理の重要な側面であり、Aspose.Words はこれを実現するための強力で柔軟な API を提供します。この知識があれば、Word ドキュメントの視覚的なプレゼンテーションを改善し、特定の要件を満たすことができます。