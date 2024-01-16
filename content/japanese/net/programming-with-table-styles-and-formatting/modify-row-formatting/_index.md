---
title: 行の書式設定を変更する
linktitle: 行の書式設定を変更する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してテーブル行の書式設定を変更するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

このチュートリアルでは、Aspose.Words for .NET を使用してテーブル行の書式設定を変更する手順を段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word 文書内の表の行の境界線、高さ、改行を変更する方法がわかります。

## ステップ 1: ドキュメント ディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。ここに Word 文書が配置されます。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: 既存のドキュメントをロードする
次に、既存の Word 文書を`Document`クラス。

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## ステップ 3: 変更する行にアクセスします
テーブルの行の書式設定を変更するには、テーブル内の特定の行に移動する必要があります。私たちが使用するのは、`GetChild()`そして`FirstRow`テーブルの最初の行への参照を取得するメソッド。

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## ステップ 4: 行の書式設定を変更する
これで、のプロパティを使用して行の書式設定を変更できるようになりました。`RowFormat`クラス。たとえば、行の境界線を削除したり、自動高さを設定したり、改行を許可したりできます。

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Aspose.Words for .NET を使用した行の書式設定の変更のサンプル ソース コード 

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
このチュートリアルでは、Aspose.Words for .NET を使用してテーブル行の書式設定を変更する方法を学びました。このステップバイステップのガイドに従うことで、Word 文書の表の行の境界線、高さ、改行を簡単に調整できます。 Aspose.Words は、ドキュメント内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせてテーブルの視覚的なレイアウトをカスタマイズできます。