---
title: 宛先スタイルを使用する
linktitle: 宛先スタイルを使用する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、宛先ドキュメント スタイルを適用しながら Word ドキュメントを結合および追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/use-destination-styles/
---

このチュートリアルでは、Aspose.Words for .NET の「宛先スタイルの使用」機能を使用する手順について説明します。この機能を使用すると、宛先ドキュメントのスタイルを適用しながら、Word ドキュメントを結合および追加できます。

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

## ステップ3: ソースドキュメントに宛先スタイルを追加する

宛先文書のスタイルを適用しながらソース文書を宛先文書に追加するには、`AppendDocument`方法の`Document`クラスで`ImportFormatMode.UseDestinationStyles`パラメータ。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## ステップ4: 最終文書を保存する

最後に、結合した文書を「宛先スタイルの使用」機能を有効にして保存します。`Save`方法の`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Aspose.Words for .NET を使用して宛先スタイルを使用するためのサンプル ソース コード

以下は、Aspose.Words for .NET を使用した C# の「Use Destination Styles」機能の完全なソース コードです。

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//宛先ドキュメントのスタイルを使用してソース ドキュメントを追加します。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

これで完了です。Aspose.Words for .NET を使用して、宛先スタイルの使用機能を正常に実装しました。最終ドキュメントには、宛先ドキュメントのスタイルが適用された結合されたコンテンツが含まれます。