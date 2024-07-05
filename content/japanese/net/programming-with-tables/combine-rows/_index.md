---
title: 行を結合する
linktitle: 行を結合する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の表の行を結合する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/combine-rows/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表の行を結合する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書内の表の行をプログラムで操作および結合できるようになります。

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

//テーブルへのアクセス
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ3: 表の行を結合する
次に、2 番目のテーブルの行を最初のテーブルの末尾に結合します。次のコードを使用します。

```csharp
//テーブル行の組み合わせ
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

ここでは`while`ループして2番目の配列のすべての行を反復し、最初の配列の末尾にそれらを追加します。`Add`次に、2番目のテーブルをドキュメントから削除します。`Remove`方法。

## ステップ4: 変更したドキュメントを保存する
最後に、結合されたテーブル行を含む変更されたドキュメントを保存する必要があります。次のコードを使用します。

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
	//セル数や幅が異なるテーブルを 1 つのテーブルに結合できます。
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表の行を結合する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、Word 文書内の表の行をプログラムで操作できます。この機能を使用すると、データを効率的に結合して表に整理できます。