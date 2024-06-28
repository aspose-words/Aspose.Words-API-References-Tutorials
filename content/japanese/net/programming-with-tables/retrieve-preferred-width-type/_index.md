---
title: 優先幅タイプの取得
linktitle: 優先幅タイプの取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word テーブル内のセルのタイプと推奨される幅の値を取得する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/retrieve-preferred-width-type/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書の表のセルから推奨される幅のタイプとその値を取得する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルの最後には、Word 文書表の特定のセルの推奨幅タイプ (絶対、相対、または自動) とその値を取得できるようになります。

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

## ステップ 3: 適切な幅のタイプと値を取得する
次に、テーブルの特定のセルに対して推奨される幅のタイプとその値を取得します。次のコードを使用します。

```csharp
//テーブルを取得する
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

//自動テーブル調整を有効にする
table. AllowAutoFit = true;

//最初の行の最初のセルを取得します
Cell firstCell = table.FirstRow.FirstCell;

//推奨される幅のタイプとその値を取得します
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

ここでは、ドキュメントを使用して最初のテーブルをフェッチし、次に、`AllowAutoFit`財産。次に、テーブルの最初の行の最初のセルを取得します。このセルから、次のコマンドを使用して、推奨される幅のタイプを取得できます。`PreferredWidth.Type`プロパティとその値を使用して、`PreferredWidth.Value`財産。

### Aspose.Words for .NET を使用した優先幅タイプの取得のサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書の表のセルから推奨される幅のタイプとその値を取得する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、Word 文書の表内の特定のセルについてこの情報を取得できます。