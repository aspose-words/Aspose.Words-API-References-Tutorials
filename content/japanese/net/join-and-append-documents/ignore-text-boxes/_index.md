---
title: テキストボックスを無視する
linktitle: テキストボックスを無視する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、テキスト ボックスの書式設定を無視してドキュメントを追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/ignore-text-boxes/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、テキスト ボックスの書式を維持しながらドキュメントを追加する方法について説明します。提供されたソース コードは、追加プロセス中にテキスト ボックスを含めるようにインポート形式オプションを設定する方法を示しています。

## ステップ 1: プロジェクトをセットアップする

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NET ライブラリがインストールされています。からダウンロードできます[Aspose.Releases]https://releases.aspose.com/words/net/ または NuGet パッケージ マネージャーを使用してインストールします。
- ソースおよび宛先ドキュメントが配置されるドキュメント ディレクトリ パス。

## ステップ 2: ソース文書と宛先文書を開く

を使用して、ソースドキュメントと宛先ドキュメントを開きます。`Document`クラスコンストラクター。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ステップ 3: インポート形式オプションを設定する

のインスタンスを作成します。`ImportFormatOptions`クラスを設定して、`IgnoreTextBoxes`財産を`false`。これにより、書式設定を維持しながら、追加プロセス中にテキスト ボックスが確実に組み込まれます。

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## ステップ 4: テキスト ボックスの内容を追加する

を作成します`NodeImporter`オブジェクトを作成し、それを使用して、ソース ドキュメントから宛先ドキュメントにテキスト ボックス ノードをインポートします。ソース文書の各段落を繰り返し処理し、それを宛先文書にインポートします。

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## ステップ 5: 宛先ドキュメントを保存する

最後に、変更した宛先ドキュメントを次のコマンドを使用して保存します。`Save`の方法`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

これで、Aspose.Words for .NET を使用してテキスト ボックスの書式を維持しながらドキュメントを追加する実装が完了しました。

### Aspose.Words for .NET を使用したテキスト ボックスを無視するソース コードの例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//インポート時にソース テキスト ボックスの書式設定を維持します。
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