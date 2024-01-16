---
title: リンク ヘッダー フッター
linktitle: リンク ヘッダー フッター
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントを結合および追加するときにヘッダーとフッターをリンクする方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/link-headers-footers/
---

このチュートリアルでは、Aspose.Words for .NET のリンク ヘッダー フッター機能を使用するプロセスを説明します。この機能を使用すると、ソース文書のヘッダーとフッターを宛先文書の前のセクションにリンクしながら、複数の Word 文書を結合および追加できます。

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

## ステップ 3: 追加されたドキュメントを新しいページに表示するように設定する

ソース文書のコンテンツが宛先文書の新しいページに確実に表示されるようにするには、`SectionStart`ソースドキュメントの最初のセクションのプロパティを`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## ステップ 4: ヘッダーとフッターを前のセクションにリンクする

ソース文書のヘッダーとフッターを宛先文書の前のセクションにリンクするには、`LinkToPrevious`の方法`HeadersFooters`コレクション。通りすがりに`true`パラメータとして、ソースドキュメント内の既存のヘッダーまたはフッターをオーバーライドします。

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## ステップ 5: ソースドキュメントを宛先ドキュメントに追加する

これで、`AppendDocument`の方法`Document`クラス。の`ImportFormatMode.KeepSourceFormatting`パラメータを使用すると、追加操作中にソースの書式設定が確実に保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 6: 最終ドキュメントを保存する

最後に、リンクされたヘッダーとフッターを含む結合されたドキュメントを保存します。`Save`の方法`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Aspose.Words for .NET を使用したリンク ヘッダー フッターのソース コードの例 

Aspose.Words for .NET を使用した C# の「ヘッダー フッターのリンク」機能の完全なソース コードは次のとおりです。


```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//追加されたドキュメントが新しいページに表示されるように設定します。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	//ソース文書のヘッダーとフッターを前のセクションにリンクします。
	//これにより、ソース文書内にすでに存在するヘッダーまたはフッターがオーバーライドされます。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

それでおしまい！ Aspose.Words for .NET を使用してリンク ヘッダー フッター機能を正常に実装しました。最終的なドキュメントには、宛先ドキュメントの前のセクションにリンクされたソースドキュメントのヘッダーとフッターを含むマージされたコンテンツが含まれます。