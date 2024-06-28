---
title: 行を結合する
linktitle: 行を結合する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の表の行を結合する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/combine-rows/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表の行を結合する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、Word 文書内の表の行をプログラムで操作したり、結合したりできるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントのロードとテーブルへのアクセス
表を使用して Word Processing を開始するには、表を含む文書をロードしてアクセスする必要があります。次の手順を実行します：

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードする
Document doc = new Document(dataDir + "Tables.docx");

//テーブルへのアクセス
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 3: テーブルの行を結合する
次に、2 番目のテーブルの行を最初のテーブルの最後まで結合します。次のコードを使用します。

```csharp
//テーブルの行の組み合わせ
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

ここでは、`while`ループを使用して 2 番目の配列のすべての行を反復処理し、それらを最初の配列の末尾に追加します。`Add`方法。次に、次のコマンドを使用してドキュメントから 2 番目のテーブルを削除します。`Remove`方法。

## ステップ 4: 変更したドキュメントを保存する
最後に、テーブル行を結合して変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
//変更したドキュメントを保存する
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用した行の結合のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// 番目のテーブルの行は、最初のテーブルの末尾に追加されます。
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	//現在のテーブルのすべての行を次のテーブルに追加します
	//セル数と幅が異なる複数のテーブルを 1 つのテーブルに結合できます。
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表の行を結合する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、Word 文書内の表の行をプログラムで操作できます。この機能を使用すると、データを効率的に結合してテーブルに整理できます。