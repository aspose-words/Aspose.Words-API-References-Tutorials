---
title: ビルダーを使用してドキュメントを挿入
linktitle: ビルダーを使用してドキュメントを挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、別のドキュメントの末尾にドキュメントを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/insert-document-with-builder/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、ドキュメントを別のドキュメントに挿入する方法について説明します。`DocumentBuilder`クラス。提供されているソース コードは、ソースの書式を維持しながら別のドキュメントの末尾にドキュメントを挿入する方法を示しています。

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

## ステップ 3: DocumentBuilder を初期化する

の新しいインスタンスを作成します。`DocumentBuilder`クラスを作成し、宛先ドキュメントをパラメータとして渡します。

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## ステップ 4: DocumentBuilder を配置する

を移動します。`DocumentBuilder`を使用して文書の最後まで`MoveToDocumentEnd`方法。改ページを挿入して、挿入されたドキュメントから既存のコンテンツを分離します。

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## ステップ 5: ソース文書を挿入する

使用`InsertDocument`の方法`DocumentBuilder`ソースドキュメントを宛先ドキュメントに挿入するクラス。インポート形式モードを次のように設定します。`ImportFormatMode.KeepSourceFormatting`ソースの書式を保持します。

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 6: 変更したドキュメントを保存する

最後に、変更した宛先ドキュメントを次のコマンドを使用して保存します。`Save`の方法`Document`物体。

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

これで、Aspose.Words for .NET を使用してドキュメントを別のドキュメントに挿入する実装が完了しました。

### Aspose.Words for .NET を使用した「Insert Document With Builder」のソース コード例 

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