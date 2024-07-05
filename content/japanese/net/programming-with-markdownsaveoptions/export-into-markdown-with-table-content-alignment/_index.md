---
title: 表の内容を揃えて Markdown にエクスポートする
linktitle: 表の内容を揃えて Markdown にエクスポートする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、さまざまな配置のテーブル コンテンツを Markdown ファイルにエクスポートする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
ここでは、.NET 用の Aspose.Words ライブラリを使用して、テーブル コンテンツの位置合わせを行ったコンテンツを Markdown ファイルにエクスポートするのに役立つ次の C# ソース コードについて説明するステップ バイ ステップ ガイドを示します。このコードを使用する前に、プロジェクトに Aspose.Words ライブラリが含まれていることを確認してください。

## ステップ1: ドキュメントディレクトリのパスを設定する

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

編集したドキュメントが保存されるドキュメント ディレクトリへの正しいパスを必ず指定してください。

## ステップ2: ドキュメントとドキュメントジェネレーターを作成する

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

ここでは、`Document`クラスとインスタンス`DocumentBuilder`ドキュメントを操作し、要素を追加できるクラスです。

## ステップ3: 異なる段落配置のセルを表に挿入する

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

ドキュメント ビルダーを使用して、表にセルを挿入し、各セルに異なる段落の配置を設定します。

## ステップ4: Markdownエクスポートオプションを設定し、変更したドキュメントを保存する

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

さまざまなテーブル コンテンツの配置で Markdown エクスポート オプションを設定し、各配置オプションを使用して変更されたドキュメントを保存します。

### Aspose.Words for .NET を使用してテーブル コンテンツの位置合わせを行った Markdown にエクスポートするサンプル ソース コード

```csharp

            
	//ドキュメント ディレクトリへのパス。
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	//表内のすべての段落を揃えます。
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	//この場合の配置は、対応する表の列の最初の段落から取得されます。
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	//変更したドキュメントを保存する
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
