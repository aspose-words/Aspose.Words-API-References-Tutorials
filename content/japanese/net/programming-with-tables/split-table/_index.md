---
title: 分割テーブル
linktitle: 分割テーブル
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の表を分割する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/split-table/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表を分割する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルの最後には、Word 文書の特定の行から表を分割できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントをロードする
文書で Word Processing を開始するには、次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードする
Document doc = new Document(dataDir + "Tables.docx");
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換え、正しいファイル名を指定してください。

## ステップ 3: テーブルを分割する
次に、テーブルを特定の行から分割します。次のコードを使用します。

```csharp
//最初のテーブルを取得します
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

//テーブルを分割する線の決定
Row row = firstTable.Rows[2];

//分割テーブル用の新しいコンテナを作成する
Table table = (Table)firstTable.Clone(false);

//元のテーブルの後にコンテナを挿入します
firstTable.ParentNode.InsertAfter(table, firstTable);

//バッファ段落を追加してテーブル間の距離を維持する
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

//元のテーブルから分割テーブルに行を移動します。
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

ここでは、ドキュメントを使用してドキュメント ノードから最初のテーブルを取得します。次に、テーブルを分割する行を決定します。この例では、3 行目 (インデックス 2) です。次に、元のテーブルのクローンを作成して新しいコンテナを作成し、それを元のテーブルの後に挿入します。また、2 つのテーブル間の距離を維持するためにバッファー段落も追加します。次に、指定された行に到達するまで、do-while ループを使用して元のテーブルから分割テーブルに行を移動します。

## ステップ 4: 変更したドキュメントを保存する
最後に、保存する必要があります

  分割テーブルを使用してドキュメントが変更されました。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用した分割テーブルのサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
//テーブルを 3 行目 (両端を含む) で分割します。
Row row = firstTable.Rows[2];
//分割テーブル用の新しいコンテナを作成します。
Table table = (Table) firstTable.Clone(false);
//元のコンテナの後にコンテナを挿入します。
firstTable.ParentNode.InsertAfter(table, firstTable);
//バッファー段落を追加して、表が離れないようにしてください。
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表を分割する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、Word 文書内の特定の行から表を簡単に分割できます。