---
title: テキストボックスを無視
linktitle: テキストボックスを無視
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、テキスト ボックスの書式を無視しながらドキュメントを追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/ignore-text-boxes/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、テキスト ボックスの書式設定を保持しながらドキュメントを追加する方法について説明します。提供されているソース コードは、追加プロセス中にテキスト ボックスを含めるようにインポート形式オプションを設定する方法を示しています。

## ステップ1: プロジェクトを設定する

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NETライブラリがインストールされています。ダウンロードはこちらから[Aspose.Releases]https://releases.aspose.com/words/net/ にアクセスするか、NuGet パッケージ マネージャーを使用してインストールします。
- ソース ドキュメントと宛先ドキュメントが配置されているドキュメント ディレクトリ パス。

## ステップ2: ソースドキュメントと宛先ドキュメントを開く

ソース文書と宛先文書を`Document`クラスコンストラクタ。置換`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ステップ3: インポート形式オプションを設定する

インスタンスを作成する`ImportFormatOptions`クラスを設定し、`IgnoreTextBoxes`財産に`false`これにより、追加プロセス中にテキスト ボックスが書式設定を保持したまま含められるようになります。

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## ステップ4: テキストボックスの内容を追加する

作成する`NodeImporter`オブジェクトを作成し、それを使用してテキスト ボックス ノードをソース ドキュメントから宛先ドキュメントにインポートします。ソース ドキュメントの各段落を反復処理し、宛先ドキュメントにインポートします。

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## ステップ5: 宛先ドキュメントを保存する

最後に、変更した宛先ドキュメントを`Save`方法の`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

これで、Aspose.Words for .NET を使用してテキスト ボックスの書式設定を保持しながらドキュメントを追加する実装が完了します。

### Aspose.Words for .NET を使用してテキスト ボックスを無視するサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//インポート時にソース テキスト ボックスの書式を維持します。
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```