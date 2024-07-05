---
title: 行の書式を変更する
linktitle: 行の書式を変更する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してテーブル行の書式を変更するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

このチュートリアルでは、Aspose.Words for .NET を使用して表の行の書式を変更する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word ドキュメントの表の行の境界線、高さ、改行を変更する方法がわかります。

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは Word ドキュメントが保存されている場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: 既存のドキュメントを読み込む
次に、既存のWord文書を`Document`クラス。

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## ステップ3: 変更する行にアクセスする
表の行の書式を変更するには、表内の特定の行に移動する必要があります。`GetChild()`そして`FirstRow`テーブルの最初の行への参照を取得するメソッド。

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## ステップ4: 行の書式を変更する
これで、プロパティを使用して行の書式を変更できます。`RowFormat`クラス。たとえば、線の境界線を削除したり、自動高さを設定したり、改行を許可したりできます。

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Aspose.Words for .NET を使用して行の書式を変更するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//テーブルの最初の行を取得します。
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して表の行の書式を変更する方法を学習しました。このステップ バイ ステップ ガイドに従うことで、Word ドキュメント内の表の行の境界線、高さ、改行を簡単に調整できます。Aspose.Words は、ドキュメント内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせて表の視覚的なレイアウトをカスタマイズできます。