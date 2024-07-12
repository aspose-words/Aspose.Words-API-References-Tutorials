---
title: 表をコンテンツに自動調整
linktitle: 表をコンテンツに自動調整
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の表をその内容に合わせて自動的に調整する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/auto-fit-table-to-contents/
---

このチュートリアルでは、C# を使用して、Aspose.Words for .NET で Word 文書内の表をその内容に合わせて自動調整する方法を学習します。この機能を実現するためのコードを記述する手順を順を追って説明します。このチュートリアルの最後には、Word 文書内の表をプログラムで操作する方法を明確に理解できるようになります。

## ステップ1: プロジェクトを設定する
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: Word文書を読み込む
表を使用して Words Processing を開始するには、表を含む Word 文書を読み込む必要があります。次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Word文書を読み込む
Document doc = new Document(dataDir + "Tables.docx");
```

「YOUR DOCUMENT DIRECTORY」をドキュメントへの実際のパスに置き換えてください。

## ステップ3: テーブルにアクセスし、内容に合わせて自動調整する
次に、ドキュメント内のテーブルにアクセスし、自動調整動作を適用する必要があります。次のコードを使用します。

```csharp
//テーブルにアクセスする
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

//表をその内容に合わせて自動調整する
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

ここでは、型の最初の子ノードをキャストしています。`Table`文書から取り出して、`AutoFit`方法`AutoFitToContents`テーブルの幅をその内容に合わせて調整する動作。

## ステップ4: 変更したドキュメントを保存する
最後に、自動調整されたテーブルを含む変更されたドキュメントを保存する必要があります。次のコードを使用します。

```csharp
//変更したドキュメントを保存する
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

出力ドキュメントの正しいパスとファイル名を指定していることを確認してください。

### Aspose.Words for .NET を使用したテーブルをコンテンツに自動調整するサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の表をその内容に合わせて自動的に調整する方法を学びました。ステップバイステップのガイドに従い、提供されている C# コードを実装することで、Word 文書内の表をプログラムで操作できます。これにより、表の内容に基づいて表の幅を動的に調整できるため、よりプロフェッショナルで視覚的に魅力的な文書を作成できます。