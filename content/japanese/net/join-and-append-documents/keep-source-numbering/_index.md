---
title: ソース番号を保持
linktitle: ソース番号を保持
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でソース番号の書式を保持しながらドキュメントを追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/keep-source-numbering/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、番号付き段落の元の番号付け書式を保持しながら、ソース ドキュメントを宛先ドキュメントに追加する方法について説明します。

## ステップ1: プロジェクトを設定する

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NETライブラリがインストールされています。ダウンロードはこちらから[Aspose.Releases]https://releases.aspose.com/words/net/ にアクセスするか、NuGet パッケージ マネージャーを使用してインストールします。
- ソース ドキュメントと宛先ドキュメントが保存されるドキュメント ディレクトリ パス。

## ステップ2: 宛先ドキュメントとソースドキュメントを作成する

インスタンスを作成する`Document`宛先ドキュメントとソースドキュメント用。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ステップ3: インポート時にソース番号を保持する

ソース文書の番号付き段落の番号書式を保持するには、`ImportFormatOptions`そして設定`KeepSourceNumbering`に`true`。 使う`NodeImporter`ソース文書から宛先文書にノードをインポートするには、`ImportFormatMode.KeepSourceFormatting`そしてその`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## ステップ4: 段落をインポートして追加する

ソース文書内の段落を反復処理し、各段落を目的の文書にインポートします。`importer`インポートしたノードを宛先ドキュメントの本文に追加します。

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## ステップ5: 変更したドキュメントを保存する

変更した文書を保存するには、`Save`方法の`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

これにより、Aspose.Words for .NET を使用して、元の番号付け書式を維持しながら、ソース ドキュメントを宛先ドキュメントに追加する実装が完了します。

### Aspose.Words for .NET を使用してソース番号を保持するサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//番号付き段落をインポートするときにソース リストの書式を維持します。
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```