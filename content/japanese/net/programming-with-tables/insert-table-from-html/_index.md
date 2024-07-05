---
title: HTML からテーブルを挿入
linktitle: HTML からテーブルを挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して HTML から Word 文書に表を挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/insert-table-from-html/
---

このチュートリアルでは、Aspose.Words for .NET を使用して HTML から Word 文書に表を挿入する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、プログラムを使用して HTML から Word 文書に表を挿入できるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントの作成とドキュメントジェネレータの初期化
ドキュメントとドキュメント ジェネレーターを使用して Words Processing を開始するには、次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメント作成
Document doc = new Document();

//ドキュメントジェネレータを初期化する
DocumentBuilder builder = new DocumentBuilder(doc);
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ3: HTMLからテーブルを挿入する
次に、HTML コードを使用してドキュメントにテーブルを挿入します。次のコードを使用します。

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

ここでは`InsertHtml`ドキュメント ビルダーのメソッドを使用して、表を含む HTML を挿入します。指定された HTML は、2 つの行と各行に 2 つのセルを持つ表を作成します。必要に応じて HTML コードを変更することで、表の内容をカスタマイズできます。

## ステップ4: 変更したドキュメントを保存する
最後に、HTML から挿入されたテーブルを含む変更されたドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用して HTML からテーブルを挿入するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//AutoFitSettings は HTML から挿入されたテーブルには適用されないことに注意してください。
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して HTML から Word 文書に表を挿入する方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、プログラムによって HTML から Word 文書に表を挿入できます。この機能を使用すると、HTML ソースから Word 文書に表形式データを変換してインポートできます。
