---
title: ページ番号付けを再開
linktitle: ページ番号付けを再開
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を結合および追加するときにページ番号付けを再開する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/restart-page-numbering/
---

このチュートリアルでは、Aspose.Words for .NET のページ番号付けの再開機能を使用する手順を説明します。この機能を使用すると、ソース ドキュメントのページ番号付けを再開しながら、Word ドキュメントを結合および追加できます。

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

## ステップ3: ソース文書のページ番号付けを再開するように設定する

ソース文書のページ番号付けを再開するには、`SectionStart`ソース文書の最初のセクションのプロパティを`SectionStart.NewPage`そして、`RestartPageNumbering`財産に`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## ステップ4: ソースドキュメントを宛先ドキュメントに追加する

これで、ソース文書を宛先文書に追加することができます。`AppendDocument`方法の`Document`クラス。`ImportFormatMode.KeepSourceFormatting`パラメータにより、追加操作中にソースの書式が保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ5: 最終文書を保存する

最後に、ページ番号の再開機能を有効にして結合した文書を保存します。`Save`方法の`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Aspose.Words for .NET を使用してページ番号を再開するためのサンプル ソース コード

以下は、Aspose.Words for .NET を使用した C# の「ページ番号の再開」機能の完全なソース コードです。
 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

これで完了です。Aspose.Words for .NET を使用してページ番号の再開機能を正常に実装しました。最終的なドキュメントには、ソース ドキュメントでページ番号が再開された結合されたコンテンツが含まれます。