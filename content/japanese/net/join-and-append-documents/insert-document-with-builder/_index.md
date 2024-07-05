---
title: ビルダーでドキュメントを挿入
linktitle: ビルダーでドキュメントを挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、別のドキュメントの最後にドキュメントを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/insert-document-with-builder/
---

このチュートリアルでは、Aspose.Words for .NETを使用して、ドキュメントを別のドキュメントに挿入する方法について説明します。`DocumentBuilder`クラス。提供されているソース コードは、ソースの書式設定を保持しながら、別のドキュメントの最後にドキュメントを挿入する方法を示しています。

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

## ステップ3: DocumentBuilderを初期化する

新しいインスタンスを作成する`DocumentBuilder`クラスを作成し、宛先ドキュメントをパラメータとして渡します。

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## ステップ4: DocumentBuilderを配置する

移動`DocumentBuilder`文書の末尾に`MoveToDocumentEnd`方法。既存のコンテンツを挿入されたドキュメントから分離するためにページ区切りを挿入します。

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## ステップ5: ソース文書を挿入する

使用`InsertDocument`方法の`DocumentBuilder`クラスを使用して、ソース文書を宛先文書に挿入します。インポート形式モードを`ImportFormatMode.KeepSourceFormatting`ソースの書式設定を保持するため。

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ6: 変更したドキュメントを保存する

最後に、変更した宛先ドキュメントを`Save`方法の`Document`物体。

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

これで、Aspose.Words for .NET を使用してドキュメントを別のドキュメントに挿入する実装が完了します。

### Aspose.Words for .NET を使用してビルダーでドキュメントを挿入するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```