---
title: スマートなスタイルの動作
linktitle: スマートなスタイルの動作
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントを結合および追加するときにスマート スタイルの動作を維持する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/smart-style-behavior/
---

このチュートリアルでは、Aspose.Words for .NET のスマート スタイル動作機能を使用するプロセスを説明します。この機能を使用すると、スマート スタイルの動作を維持しながら Word 文書を結合および追加できます。

## 前提条件

始める前に、以下のものがあることを確認してください。

1. Aspose.Words for .NET がインストールされています。 Aspose Web サイトからダウンロードするか、NuGet 経由でインストールできます。
2. Visual Studio またはその他の C# 開発環境。

## ステップ 1: ドキュメント ディレクトリを初期化する

まず、ドキュメント ディレクトリへのパスを設定する必要があります。の値を変更します。`dataDir`変数をドキュメントが配置されているパスに設定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ソースドキュメントと宛先ドキュメントをロードする

次に、Aspose.Words を使用してソース ドキュメントと宛先ドキュメントをロードする必要があります。`Document`クラス。ファイル名を更新します。`Document`ドキュメント名に従ってコンストラクターを作成します。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ステップ 3: 宛先ドキュメントに改ページを挿入する

追加されたコンテンツが宛先ドキュメントの新しいページに確実に表示されるようにするには、`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## ステップ 4: スマート スタイルの動作オプションを設定する

追加操作中にスマート スタイルの動作を有効にするには、次のインスタンスを作成する必要があります。`ImportFormatOptions`そして、`SmartStyleBehavior`財産を`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## ステップ 5: ソースドキュメントを宛先ドキュメントに追加する

これで、`InsertDocument`の方法`DocumentBuilder`クラス。使用`ImportFormatMode.UseDestinationStyles`パラメータを指定して渡します`ImportFormatOptions`スマート スタイルの動作を維持するためのオブジェクト。

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## ステップ 6: 最終ドキュメントを保存する

最後に、スマート スタイル動作機能を有効にして、結合されたドキュメントを保存します。`Save`の方法`Document`クラス。

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Aspose.Words for .NET を使用したスマート スタイル動作のソース コード例

Aspose.Words for .NET を使用した C# の「スマート スタイル動作」機能の完全なソース コードは次のとおりです。
 
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

それでおしまい！ Aspose.Words for .NET を使用してスマート スタイル動作機能を正常に実装しました。最終的なドキュメントには、スマート スタイルの動作が維持されたマージされたコンテンツが含まれます。