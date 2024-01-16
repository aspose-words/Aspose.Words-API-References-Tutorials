---
title: 完全なテーブルのクローンを作成する
linktitle: 完全なテーブルのクローンを作成する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、表全体を Word 文書に複製する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/clone-complete-table/
---

このチュートリアルでは、Aspose.Words for .NET を使用してテーブル全体のクローンを Word ドキュメントに作成する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、プログラムによって表のクローンを Word 文書に作成できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントのロードとテーブルへのアクセス
表を使用して Word Processing を開始するには、その表を含む文書をロードしてアクセスする必要があります。次の手順を実行します：

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードします
Document doc = new Document(dataDir + "Tables.docx");

//アレイへのアクセス
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 3: 完全なアレイのクローン
次に、テーブル全体のクローンを作成し、ドキュメント内の元のテーブルの後に挿入します。次のコードを使用します。

```csharp
//アレイのクローンを作成する
Table tableClone = (Table)table.Clone(true);

//クローン化したテーブルを元のテーブルの後にドキュメントに挿入します。
table.ParentNode.InsertAfter(tableClone, table);

// 2 つの表の間に空の段落を挿入します
//それ以外の場合は、保存時に 1 つに結合されます (これは文書の検証によるものです)。
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

ここで使用しているのは、`Clone`メソッドを使用して配列の完全なコピーを作成します。次に、使用します`InsertAfter`複製したテーブルをドキュメント内の元のテーブルの後に挿入します。また、保存時にテーブルがマージされないように、2 つのテーブルの間に空の段落を追加します。

## ステップ 4: 変更したドキュメントを保存する
最後に、変更したドキュメントを複製したテーブルとともに保存する必要があります。次のコードを使用します。

```csharp
//変更したドキュメントを保存する
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。
  
### Aspose.Words for .NET を使用した Clone Complete Table のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//テーブルのクローンを作成し、元のテーブルの後にドキュメントに挿入します。
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// 2 つの表の間に空の段落を挿入します。
	//そうしないと、保存時に 1 つに結合されます。これは文書の検証に関係します。
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してテーブル全体のクローンを Word ドキュメントに作成する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、プログラムを使用して Word 文書内のテーブルの複製を作成できます。この機能を使用すると、特定のニーズに合わせて配列に対して高度な操作を実行できます。