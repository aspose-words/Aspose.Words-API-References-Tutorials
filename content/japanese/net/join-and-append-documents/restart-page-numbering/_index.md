---
title: ページ番号付けを再開する
linktitle: ページ番号付けを再開する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を結合および追加するときにページ番号付けを再開する方法を説明します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/restart-page-numbering/
---

このチュートリアルでは、Aspose.Words for .NET のページ番号付けの再開機能を使用するプロセスについて説明します。この機能を使用すると、ソース文書のページ番号付けを再開しながら、Word 文書を結合および追加できます。

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

## ステップ 3: ページ番号付けを再開するようにソース文書を設定する

ソース文書でページ番号付けを再開するには、`SectionStart`ソースドキュメントの最初のセクションのプロパティを`SectionStart.NewPage`そして、`RestartPageNumbering`財産を`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## ステップ 4: ソースドキュメントを宛先ドキュメントに追加する

これで、`AppendDocument`の方法`Document`クラス。の`ImportFormatMode.KeepSourceFormatting`パラメータを使用すると、追加操作中にソースの書式設定が確実に保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 5: 最終ドキュメントを保存する

最後に、結合されたドキュメントを、ページ番号付けの再開機能を有効にして保存します。`Save`の方法`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Aspose.Words for .NET を使用したリスタート ページ番号付けのソース コード例

Aspose.Words for .NET を使用した C# の「ページ番号付けの再開」機能の完全なソース コードは次のとおりです。
 

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

それでおしまい！ Aspose.Words for .NET を使用して、ページ番号付けの再開機能を正常に実装しました。最終的なドキュメントには、ソースドキュメントでページ番号が再開されたマージされたコンテンツが含まれます。