---
title: テーブルをまとめる
linktitle: テーブルをまとめる
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内で表をまとめる方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/keep-table-together/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内で表をまとめる方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書内で表を複数のページに分割せずにそのまま保持できるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントを読み込み、テーブルを取得する
表を使用して Words Processing を開始するには、ドキュメントをロードし、一緒に保持する表を取得する必要があります。次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを読み込む
Document doc = new Document(dataDir + "Table spanning two pages.docx");

//テーブルを取得する
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ3: 「KeepWithNext」オプションを有効にする
表をまとめ、複数のページに分割されないようにするには、表の最後の行の最後の段落を除く表の各段落に対して「KeepWithNext」オプションを有効にする必要があります。次のコードを使用します。

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

## ステップ4: 変更したドキュメントを保存する
最後に、テーブルをまとめた変更済みのドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用してテーブルをまとめるサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//表内の各段落がページをまたいで改ページされないようにするには、KeepWithNextを有効にする必要があります。
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
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内で表をまとめる方法を学習しました。このステップ バイ ステップ ガイドに従い、提供されている C# コードを実装することで、表をそのまま維持し、文書内で表が複数のページに分割されるのを防ぐことができます。この機能により、文書内の表の外観とレイアウトをより細かく制御できます。