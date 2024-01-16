---
title: 宛先スタイルを使用する
linktitle: 宛先スタイルを使用する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して宛先ドキュメント スタイルを適用しながら Word ドキュメントを結合および追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/use-destination-styles/
---

このチュートリアルでは、Aspose.Words for .NET の宛先スタイルの使用機能を使用するプロセスを説明します。この機能を使用すると、宛先ドキュメントのスタイルを適用しながら、Word ドキュメントを結合および追加できます。

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

## ステップ 3: ソースドキュメントに宛先スタイルを追加する

宛先ドキュメントのスタイルを適用しながらソースドキュメントを宛先ドキュメントに追加するには、`AppendDocument`の方法`Document`とのクラス`ImportFormatMode.UseDestinationStyles`パラメータ。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## ステップ 4: 最終ドキュメントを保存する

最後に、結合されたドキュメントを、「宛先スタイルの使用」機能を有効にして保存します。`Save`の方法`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Aspose.Words for .NET を使用した宛先スタイルの使用のソース コード例

Aspose.Words for .NET を使用した C# の "Use Destination Styles" 機能の完全なソース コードは次のとおりです。

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//宛先ドキュメントのスタイルを使用してソースドキュメントを追加します。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、宛先スタイルの使用機能が正常に実装されました。最終的なドキュメントには、宛先ドキュメントのスタイルが適用されたマージされたコンテンツが含まれます。