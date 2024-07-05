---
title: 行の書式設定 ページ間の区切りを無効にする
linktitle: 行の書式設定 ページ間の区切りを無効にする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の複数ページにまたがる表の改行を無効にする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/row-format-disable-break-across-pages/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の複数ページの表の改行を無効にする方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書内の表のすべての行の改行を無効にできるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントの読み込み
ドキュメントで Words Processing を開始するには、次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを読み込む
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

必ず「YOUR DOCUMENTS DIRECTORY」を実際のドキュメント ディレクトリへのパスに置き換え、正しいファイル名を指定してください。

## ステップ3: 表の行区切りを無効にする
次に、テーブル内のすべての行の行区切りを無効にします。次のコードを使用します。

```csharp
//テーブルを取得する
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

//テーブル内のすべての行の行区切りを無効にする
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

ここでは、ドキュメントを使用して最初のテーブルを取得し、foreachループを使用してテーブル内のすべての行を反復処理します。ループ内では、各行の行区切りを無効にするために、`RowFormat.AllowBreakAcrossPages`財産に`false`.

## ステップ4: 変更したドキュメントを保存する
最後に、表の改行を無効にして変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用して行書式でページ間の改ページを無効にするサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
//テーブル内のすべての行でページ間の分割を無効にします。
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の複数ページの表の改行を無効にする方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、Word 文書内の表にこの無効化を適用できます。