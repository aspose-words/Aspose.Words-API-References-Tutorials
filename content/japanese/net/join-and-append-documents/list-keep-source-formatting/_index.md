---
title: リスト保持ソースの書式設定
linktitle: リスト保持ソースの書式設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントを結合および追加するときにリストの書式を保持する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/list-keep-source-formatting/
---

このチュートリアルでは、Aspose.Words for .NET の List Keep Source Formatting 機能を使用するプロセスを説明します。この機能を使用すると、リストのソース形式を維持しながら Word 文書を結合および追加できます。

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## ステップ 3: ソースドキュメントを連続的にフローするように設定する

ソースドキュメントのコンテンツが宛先ドキュメントに追加されたときに継続的に流れるようにするには、`SectionStart`ソースドキュメントの最初のセクションのプロパティを`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ステップ 4: ソースドキュメントを宛先ドキュメントに追加する

これで、`AppendDocument`の方法`Document`クラス。の`ImportFormatMode.KeepSourceFormatting`パラメーターを使用すると、リストの書式設定を含むソースの書式設定が追加操作中に確実に保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 5: 最終ドキュメントを保存する

最後に、リスト保持ソース書式設定機能を有効にして、結合されたドキュメントを保存します。`Save`の方法`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Aspose.Words for .NET を使用した List Keep Source Formatting のソース コード例 

Aspose.Words for .NET を使用した C# の List Keep Source Formatting 機能の完全なソース コードは次のとおりです。

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//文書の内容が継続的に流れるように追加します。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、List Keep Source Formatting 機能を正常に実装しました。最終的なドキュメントには、ソースドキュメントのリスト形式が保持されたマージされたコンテンツが含まれます。