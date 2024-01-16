---
title: ヘッダーとフッターのリンクを解除する
linktitle: ヘッダーとフッターのリンクを解除する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してヘッダーとフッターのリンクを解除しながら、Word ドキュメントを結合および追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/unlink-headers-footers/
---

このチュートリアルでは、Aspose.Words for .NET のヘッダー フッターのリンク解除機能を使用するプロセスを説明します。この機能を使用すると、ソース文書からヘッダーとフッターのリンクを解除しながら、Word 文書を結合および追加できます。

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

## ステップ 3: ソースドキュメント内のヘッダーとフッターのリンクを解除する

ソースドキュメントのヘッダーとフッターのリンクを解除して、宛先ドキュメントのヘッダーとフッターを続行しないようにするには、`LinkToPrevious`の財産`HeadersFooters`ソースドキュメントの最初のセクションにあるコレクションを`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## ステップ 4: ソースドキュメントを宛先ドキュメントに追加する

これで、`AppendDocument`の方法`Document`クラス。の`ImportFormatMode.KeepSourceFormatting`パラメータを使用すると、追加操作中にソースの書式設定が確実に保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 5: 最終ドキュメントを保存する

最後に、ヘッダーとフッターのリンクを解除する機能を有効にして、結合されたドキュメントを保存します。`Save`の方法`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Aspose.Words for .NET を使用したヘッダー フッターのリンク解除のソース コード例

Aspose.Words for .NET を使用した C# の「ヘッダー フッターのリンク解除」機能の完全なソース コードは次のとおりです。

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//これを防ぐには、ソースドキュメント内のヘッダーとフッターのリンクを解除します。
	//宛先ドキュメントのヘッダーとフッターを継続しないようにします。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、ヘッダー フッターのリンク解除機能を正常に実装しました。最終的なドキュメントには、ソースドキュメントのヘッダーとフッターが宛先ドキュメントからリンク解除された、マージされたコンテンツが含まれます。