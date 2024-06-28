---
title: ソースの番号付けを維持する
linktitle: ソースの番号付けを維持する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でソース番号の書式設定を維持しながらドキュメントを追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/keep-source-numbering/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、番号付き段落の元の番号付け書式を維持しながら、ソース ドキュメントを宛先ドキュメントに追加する方法について説明します。

## ステップ 1: プロジェクトをセットアップする

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NET ライブラリがインストールされています。からダウンロードできます[Aspose.Releases]https://releases.aspose.com/words/net/ または NuGet パッケージ マネージャーを使用してインストールします。
- ソースドキュメントと宛先ドキュメントが保存されるドキュメントディレクトリのパス。

## ステップ 2: 宛先ドキュメントとソースドキュメントを作成する

のインスタンスを作成します`Document`宛先ドキュメントとソースドキュメント用。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ステップ 3: インポート時にソースの番号付けを維持する

ソース文書の番号付き段落の番号付け書式を保持するには、次のインスタンスを作成します。`ImportFormatOptions`そしてセット`KeepSourceNumbering`に`true`。使う`NodeImporter`ソースドキュメントから宛先ドキュメントにノードをインポートするには、次のように指定します。`ImportFormatMode.KeepSourceFormatting`そしてその`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## ステップ 4: 段落をインポートして追加する

ソース文書内の段落を繰り返し処理し、各段落を宛先文書にインポートします。`importer`。インポートされたノードを宛先ドキュメントの本文に追加します。

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## ステップ 5: 変更したドキュメントを保存する

変更したドキュメントを保存するには、`Save`の方法`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

これで、Aspose.Words for .NET を使用して、元の番号付け書式を維持しながら、ソース ドキュメントを宛先ドキュメントに追加する実装が完了しました。

### Aspose.Words for .NET を使用した Keep Source Numbering のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//番号付き段落をインポートするときにソース リストの書式設定を維持します。
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