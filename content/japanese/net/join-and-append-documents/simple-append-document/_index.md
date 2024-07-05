---
title: シンプルなドキュメントの追加
linktitle: シンプルなドキュメントの追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、書式を保持したまま Word 文書を結合および追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/simple-append-document/
---

このチュートリアルでは、Aspose.Words for .NET のシンプルなドキュメント追加機能を使用する手順を説明します。この機能を使用すると、追加オプションなしで Word ドキュメントを結合および追加できます。

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

## ステップ3: ソースドキュメントを宛先ドキュメントに追加する

これで、ソース文書を宛先文書に追加することができます。`AppendDocument`方法の`Document`クラス。`ImportFormatMode.KeepSourceFormatting`パラメータにより、追加操作中にソースの書式が保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ4: 最終文書を保存する

最後に、シンプル追加ドキュメント機能を使用して結合したドキュメントを保存します。`Save`方法の`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Aspose.Words for .NET を使用したシンプルなドキュメント追加の例のソース コード

以下は、Aspose.Words for .NET を使用した C# の「シンプルなドキュメント追加」機能の完全なソース コードです。

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//追加オプションを使用せずに、ソース ドキュメントを宛先ドキュメントに追加します。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

これで完了です。Aspose.Words for .NET を使用して、シンプルなドキュメント追加機能を正常に実装しました。最終的なドキュメントには、ソースの書式が保持された状態で結合されたコンテンツが含まれます。