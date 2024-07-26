---
title: 完全なテーブルを複製
linktitle: 完全なテーブルを複製
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、表全体を Word 文書に複製する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/clone-complete-table/
---

このチュートリアルでは、Aspose.Words for .NET を使用してテーブル全体を Word 文書に複製する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、プログラムによってテーブルを Word 文書に複製できるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントを読み込み、テーブルにアクセスする
表を使用して Words Processing を開始するには、表を含むドキュメントを読み込んでアクセスする必要があります。次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを読み込む
Document doc = new Document(dataDir + "Tables.docx");

//アレイへのアクセス
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ3: フルアレイクローン
次に、テーブル全体を複製し、元のテーブルの後にドキュメントに挿入します。次のコードを使用します。

```csharp
//アレイのクローンを作成する
Table tableClone = (Table)table.Clone(true);

//複製した表を元の表の後に文書に挿入します。
table.ParentNode.InsertAfter(tableClone, table);

// 2つの表の間に空の段落を挿入する
//それ以外の場合は、保存時に 1 つに結合されます (これはドキュメントの検証によるものです)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

ここでは、`Clone`メソッドを使用して配列の完全なコピーを作成します。次に`InsertAfter`複製された表を元の表の後にドキュメントに挿入します。また、保存時に 2 つの表が結合されないように、2 つの表の間に空の段落を追加します。

## ステップ4: 変更したドキュメントを保存する
最後に、クローンされたテーブルとともに変更されたドキュメントを保存する必要があります。次のコードを使用します。

```csharp
//変更したドキュメントを保存する
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。
  
### Aspose.Words for .NET を使用して完全なテーブルを複製するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//表を複製し、元の表の後にドキュメントに挿入します。
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// 2つの表の間に空の段落を挿入します。
	//そうでなければ、保存時に 1 つに結合されます。これはドキュメントの検証に関係します。
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、テーブル全体を Word 文書に複製する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、プログラムによって Word 文書内のテーブルを複製できます。この機能を使用すると、特定のニーズに合わせて配列に対して高度な操作を実行できます。