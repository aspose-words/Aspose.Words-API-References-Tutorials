---
title: 表の内容を調整してマークダウンにエクスポート
linktitle: 表の内容を調整してマークダウンにエクスポート
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、さまざまな配置でテーブル コンテンツを Markdown ファイルにエクスポートする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
ここでは、.NET 用の Aspose.Words ライブラリを使用して、テーブル コンテンツの配置を指定してコンテンツを Markdown ファイルにエクスポートするのに役立つ次の C# ソース コードを説明するステップバイステップ ガイドを示します。このコードを使用する前に、プロジェクトに Aspose.Words ライブラリが含まれていることを確認してください。

## ステップ 1: ドキュメント ディレクトリ パスを設定する

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

編集したドキュメントが保存されるドキュメント ディレクトリへの正しいパスを必ず指定してください。

## ステップ 2: ドキュメントとドキュメント ジェネレーターを作成する

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

ここで、のインスタンスを作成します。`Document`クラスとインスタンス`DocumentBuilder`このクラスを使用すると、ドキュメントを操作して要素を追加できるようになります。

## ステップ 3: 異なる段落配置で表にセルを挿入する

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

ドキュメント ビルダーを使用して表にセルを挿入し、セルごとに異なる段落の配置を設定します。

## ステップ 4: Markdown エクスポート オプションを設定し、変更したドキュメントを保存する

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

さまざまなテーブル コンテンツの配置で Markdown エクスポート オプションを設定し、各配置オプションを使用して変更したドキュメントを保存します。

### Aspose.Words for .NET を使用してテーブル コンテンツを配置して Markdown にエクスポートするソース コードの例

```csharp

            
	//ドキュメントディレクトリへのパス。
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

	//この場合の配置は、対応するテーブル列の最初の段落から取得されます。
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	//変更したドキュメントを保存する
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
