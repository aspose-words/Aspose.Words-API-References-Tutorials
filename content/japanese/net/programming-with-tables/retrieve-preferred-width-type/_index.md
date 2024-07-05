---
title: 優先幅タイプを取得
linktitle: 優先幅タイプを取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word テーブル内のセルの種類と推奨幅の値を取得する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/retrieve-preferred-width-type/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書の表のセルから優先幅の種類とその値を取得する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書の表の特定のセルの優先幅の種類 (絶対、相対、または自動) とその値を取得できるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントの読み込み
ドキュメントで Words Processing を開始するには、次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを読み込む
Document doc = new Document(dataDir + "Tables.docx");
```

必ず「YOUR DOCUMENTS DIRECTORY」を実際のドキュメント ディレクトリへのパスに置き換え、正しいファイル名を指定してください。

## ステップ3: 優先幅のタイプと値を取得する
次に、特定のテーブル セルの推奨される幅のタイプとその値を取得します。次のコードを使用します。

```csharp
//テーブルを取得する
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

//自動テーブル調整を有効にする
table. AllowAutoFit = true;

//最初の行の最初のセルを取得します
Cell firstCell = table.FirstRow.FirstCell;

//優先幅タイプとその値を取得する
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

ここでは、ドキュメントを使用して最初のテーブルを取得し、次に自動テーブルフィットを有効にします。`AllowAutoFit`プロパティ。次に、表の最初の行の最初のセルを取得します。このセルから、`PreferredWidth.Type`財産とその価値`PreferredWidth.Value`財産。

### Aspose.Words for .NET を使用して推奨幅タイプを取得するためのサンプル ソース コード 

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
このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の表のセルから推奨される幅の種類とその値を取得する方法を学習しました。このステップ バイ ステップ ガイドに従い、提供されている C# コードを実装することで、Word 文書の表内の特定のセルのこの情報を取得できます。