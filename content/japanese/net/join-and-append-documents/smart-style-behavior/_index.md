---
title: スマートスタイルの動作
linktitle: スマートスタイルの動作
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を結合および追加するときにスマート スタイルの動作を維持する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/smart-style-behavior/
---

このチュートリアルでは、Aspose.Words for .NET のスマート スタイル動作機能を使用する手順を説明します。この機能を使用すると、スマート スタイル動作を維持しながら Word 文書を結合および追加できます。

## 前提条件

始める前に、次のものがあることを確認してください。

1. Aspose.Words for .NET がインストールされています。Aspose Web サイトからダウンロードするか、NuGet 経由でインストールできます。
2. Visual Studio またはその他の C# 開発環境。

## ステップ1: ドキュメントディレクトリを初期化する

まず、ドキュメントディレクトリへのパスを設定する必要があります。`dataDir`ドキュメントが保存されているパスへの変数。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ソースドキュメントと宛先ドキュメントを読み込む

次に、Aspose.Wordsを使用してソースドキュメントと宛先ドキュメントをロードする必要があります。`Document`クラス。`Document`ドキュメント名に応じてコンストラクターを作成します。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ステップ3: 宛先ドキュメントに改ページを挿入する

追加されたコンテンツが宛先文書の新しいページに表示されるようにするには、`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## ステップ4: スマートスタイルの動作オプションを設定する

追加操作中にスマートスタイルの動作を有効にするには、`ImportFormatOptions`そして、`SmartStyleBehavior`財産に`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## ステップ5: ソースドキュメントを宛先ドキュメントに追加する

これで、ソース文書を宛先文書に追加することができます。`InsertDocument`方法の`DocumentBuilder`クラス。`ImportFormatMode.UseDestinationStyles`パラメータを渡して`ImportFormatOptions`スマートなスタイルの動作を維持するためのオブジェクト。

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## ステップ6: 最終文書を保存する

最後に、スマートスタイル動作機能を有効にして結合した文書を保存します。`Save`方法の`Document`クラス。

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Aspose.Words for .NET を使用したスマート スタイル動作のサンプル ソース コード

以下は、Aspose.Words for .NET を使用した C# の「スマート スタイル動作」機能の完全なソース コードです。
 
```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

これで完了です。Aspose.Words for .NET を使用して、スマート スタイル動作機能を正常に実装しました。最終的なドキュメントには、スマート スタイル動作が維持された結合されたコンテンツが含まれます。