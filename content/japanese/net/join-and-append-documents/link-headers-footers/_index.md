---
title: リンク ヘッダー フッター
linktitle: リンク ヘッダー フッター
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を結合および追加するときにヘッダーとフッターをリンクする方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/link-headers-footers/
---

このチュートリアルでは、Aspose.Words for .NET のヘッダーとフッターのリンク機能を使用する手順を説明します。この機能を使用すると、ソース ドキュメントのヘッダーとフッターをターゲット ドキュメントの前のセクションにリンクしながら、複数の Word ドキュメントを結合および追加できます。

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

## ステップ3: 追加されたドキュメントを新しいページに表示するように設定する

ソース文書のコンテンツが宛先文書の新しいページに表示されるようにするには、`SectionStart`ソース文書の最初のセクションのプロパティを`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## ステップ4: ヘッダーとフッターを前のセクションにリンクする

ソース文書のヘッダーとフッターを宛先文書の前のセクションにリンクするには、`LinkToPrevious`方法の`HeadersFooters`コレクション。通過することで`true`パラメータとして指定すると、ソース ドキュメント内の既存のヘッダーまたはフッターが上書きされます。

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## ステップ5: ソースドキュメントを宛先ドキュメントに追加する

これで、ソース文書を宛先文書に追加することができます。`AppendDocument`方法の`Document`クラス。`ImportFormatMode.KeepSourceFormatting`パラメータにより、追加操作中にソースの書式が保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ6: 最終文書を保存する

最後に、リンクされたヘッダーとフッターを含む結合された文書を、`Save`方法の`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Aspose.Words for .NET を使用したリンク ヘッダー フッターのサンプル ソース コード 

以下は、Aspose.Words for .NET を使用した C# の「リンク ヘッダー フッター」機能の完全なソース コードです。


```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//追加されたドキュメントを新しいページに表示するように設定します。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	//ソース ドキュメントのヘッダーとフッターを前のセクションにリンクします。
	//これにより、ソース ドキュメントに既に存在するヘッダーまたはフッターが上書きされます。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

これで完了です。Aspose.Words for .NET を使用して、ヘッダーとフッターのリンク機能を正常に実装できました。最終的なドキュメントには、ソース ドキュメントのヘッダーとフッターがターゲット ドキュメントの前のセクションにリンクされた結合されたコンテンツが含まれます。