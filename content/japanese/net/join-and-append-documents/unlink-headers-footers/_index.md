---
title: ヘッダーとフッターのリンクを解除
linktitle: ヘッダーとフッターのリンクを解除
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ヘッダーとフッターのリンクを解除しながら Word 文書を結合および追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/unlink-headers-footers/
---

このチュートリアルでは、Aspose.Words for .NET のヘッダーとフッターのリンク解除機能を使用する手順を説明します。この機能を使用すると、ソース ドキュメントからヘッダーとフッターのリンクを解除しながら、Word ドキュメントを結合および追加できます。

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

## ステップ3: ソース文書のヘッダーとフッターのリンクを解除する

ソース文書のヘッダーとフッターをリンク解除して、宛先文書のヘッダーとフッターを継承しないようにするには、`LinkToPrevious`の財産`HeadersFooters`ソース文書の最初のセクションのコレクション`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## ステップ4: ソースドキュメントを宛先ドキュメントに追加する

これで、ソース文書を宛先文書に追加することができます。`AppendDocument`方法の`Document`クラス。`ImportFormatMode.KeepSourceFormatting`パラメータにより、追加操作中にソースの書式が保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ5: 最終文書を保存する

最後に、ヘッダーとフッターのリンク解除機能を有効にして結合した文書を保存します。`Save`方法の`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Aspose.Words for .NET を使用してヘッダーとフッターのリンクを解除するサンプル ソース コード

以下は、Aspose.Words for .NET を使用した C# の「ヘッダーとフッターのリンク解除」機能の完全なソース コードです。

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//これを止めるには、ソース文書のヘッダーとフッターのリンクを解除してください。
	//宛先ドキュメントのヘッダーとフッターを続行しないようにします。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

これで完了です。Aspose.Words for .NET を使用して、ヘッダーとフッターのリンク解除機能を正常に実装しました。最終的なドキュメントには、ソース ドキュメントのヘッダーとフッターがターゲット ドキュメントからリンク解除された、結合されたコンテンツが含まれます。