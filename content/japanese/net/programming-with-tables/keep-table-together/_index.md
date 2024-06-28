---
title: テーブルを一緒に保つ
linktitle: テーブルを一緒に保つ
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内で表をまとめる方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/keep-table-together/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内で表をまとめる方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、Word 文書内で表が複数のページに分割されることなく、そのままの状態を維持できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントのロードとテーブルの取得
表を使用して Word Processing を開始するには、文書をロードし、まとめておきたい表をフェッチする必要があります。次の手順を実行します：

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードする
Document doc = new Document(dataDir + "Table spanning two pages.docx");

//テーブルを取得する
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 3: 「KeepWithNext」オプションを有効にする
表をまとめて保持し、複数のページに分割されないようにするには、表の最終行の最後の段落を除く、表内の各段落で「KeepWithNext」オプションを有効にする必要があります。次のコードを使用します。

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

ここでは、表内の各セルをループし、表の最後の行の最後の段落を除くセル内の各段落に対して「KeepWithNext」オプションを有効にします。

## ステップ 4: 変更したドキュメントを保存する
最後に、テーブルをまとめた状態で変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用した Keep Table Together のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//ページをまたいで改行しないように、表内のすべての段落で KeepWithNext を有効にする必要があります。
	//ただし、表の最後の行の最後の段落は除きます。
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内で表をまとめる方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、表をそのままの状態に保ち、ドキュメント内の複数のページに分割されるのを防ぐことができます。この機能を使用すると、ドキュメント内の表の外観とレイアウトをより詳細に制御できるようになります。