---
title: 相対的な水平または垂直位置を設定する
linktitle: 相対的な水平または垂直位置を設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の表の相対的な水平位置または垂直位置を設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の表の相対的な水平位置または垂直位置を設定する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書内の表の相対的な水平位置または垂直位置を設定できるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントの読み込み
ドキュメントで Words Processing を開始するには、次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを読み込む
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

必ず「YOUR DOCUMENTS DIRECTORY」を実際のドキュメント ディレクトリへのパスに置き換え、正しいファイル名を指定してください。

## ステップ3: テーブルの相対位置を設定する
次に、テーブルの相対的な水平位置または垂直位置を設定します。次のコードを使用します。

```csharp
//テーブルを取得する
Table table = doc.FirstSection.Body.Tables[0];

//テーブルの相対的な水平位置の定義
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

//テーブルの相対的な垂直位置を定義する
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

ここでは、ドキュメントを使用して最初のセクションの本文から最初の表を取得します。次に、表の相対的な水平位置を`HorizontalAnchor`プロパティを使用して`RelativeHorizontalPosition.Column`値。同様に、テーブルの相対的な垂直位置を`VerticalAnchor`プロパティを使用して`RelativeVerticalPosition.Page`価値。

## ステップ4: 変更したドキュメントを保存する
最後に、テーブルの相対位置を定義して変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用して相対的な水平位置または垂直位置を設定するサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の表の相対的な水平位置または垂直位置を設定する方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、この相対位置を Word 文書内の表に適用できます。