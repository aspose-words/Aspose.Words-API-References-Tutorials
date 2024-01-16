---
title: ページ幅に自動調整
linktitle: ページ幅に自動調整
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書のページ幅に表を自動的に合わせる方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/auto-fit-to-page-width/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、表を Word 文書のページ幅に自動的に合わせる方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、Word 文書内の表をプログラムで操作できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントの作成と構成
表を使用して Word Processing を開始するには、ドキュメントを作成し、ドキュメント ジェネレーターを構成する必要があります。次の手順を実行します：

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントとドキュメントジェネレーターを作成する
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 3: テーブルの挿入と構成
次に、ページの幅の半分を占める幅の表をドキュメントに挿入します。次のコードを使用します。

```csharp
//テーブルを挿入し、その幅を設定します
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

ここでは、ドキュメント ビルダーを使用して表の作成を開始し、セルを挿入し、表の推奨幅をページ幅の 50% に設定します。次に、各セルにテキストを追加します。

## ステップ 4: 変更したドキュメントを保存する
最後に、ページの幅に合わせて表を調整して、変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
//変更したドキュメントを保存する
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。
  
### Aspose.Words for .NET を使用したページ幅に自動調整するサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//ページ幅の半分を占める幅の表を挿入します。
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のページ幅に表を自動的に合わせる方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、Word 文書内の表をプログラムで操作できます。この機能を使用すると、ページに応じて表の幅を動的に調整できるため、プロフェッショナルで視覚的に魅力的なドキュメントが提供されます。