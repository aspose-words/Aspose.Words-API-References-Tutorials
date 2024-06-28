---
title: 行フォーマットでページ間の区切りを無効にする
linktitle: 行フォーマットでページ間の区切りを無効にする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の複数のページにわたる表の改行を無効にする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/row-format-disable-break-across-pages/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の複数ページの表の改行を無効にする方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終了するまでに、Word 文書の表内のすべての行の改行を無効にできるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントをロードする
文書で Word Processing を開始するには、次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードする
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換え、正しいファイル名を指定してください。

## ステップ 3: テーブルの行区切りを無効にする
次に、テーブル内のすべての行の行分割を無効にします。次のコードを使用します。

```csharp
//テーブルを取得する
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

//テーブル内のすべての行の改行を無効にする
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

ここでは、ドキュメントを使用して最初のテーブルをフェッチし、foreach ループを使用してテーブル内のすべての行を反復処理します。ループ内で、行ごとに行分割を無効にするには、`RowFormat.AllowBreakAcrossPages`財産を`false`.

## ステップ 4: 変更したドキュメントを保存する
最後に、表の改行を無効にして、変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用した Row Format Disable Break Across Pages のサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
//テーブル内のすべての行のページ間分割を無効にします。
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の複数ページの表の改行を無効にする方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、この無効化を Word 文書内の表に適用できます。