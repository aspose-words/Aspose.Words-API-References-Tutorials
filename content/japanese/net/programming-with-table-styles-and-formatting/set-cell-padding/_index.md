---
title: セルの余白を設定する
linktitle: セルの余白を設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して表のセルの余白を設定する手順ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

このチュートリアルでは、Aspose.Words for .NET を使用して表のセルの余白を設定する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word 文書の表のセル コンテンツの左、上、右、下の余白 (スペース) を調整する方法がわかります。

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

## ステップ4: セルの余白を設定する
これでセルの余白を設定できます。`SetPaddings()`方法の`CellFormat`オブジェクト。余白はポイント単位で定義され、左、上、右、下の順序で指定されます。

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
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
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Aspose.Words for .NET を使用してセルの余白を設定するサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	//セルの内容の左/上/右/下に追加するスペースの量 (ポイント単位) を設定します。
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して表のセルの余白を設定する方法を学習しました。このステップ バイ ステップ ガイドに従うことで、セルの余白を簡単に調整して、Word ドキュメント内の表のコンテンツの左、上、右、下にスペースを作成できます。Aspose.Words は、ドキュメント内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせて表の書式をカスタマイズできます。