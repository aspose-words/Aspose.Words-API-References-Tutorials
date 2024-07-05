---
title: リストのソース書式を保持
linktitle: リストのソース書式を保持
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を結合および追加するときにリストの書式を保持する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/list-keep-source-formatting/
---

このチュートリアルでは、Aspose.Words for .NET のリストのソース書式保持機能を使用する手順を説明します。この機能を使用すると、リストのソース書式を保持しながら Word 文書を結合および追加できます。

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## ステップ3: ソースドキュメントを連続フローするように設定する

ソース文書のコンテンツが宛先文書に追加されるときに連続して流れるようにするには、`SectionStart`ソース文書の最初のセクションのプロパティを`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ステップ4: ソースドキュメントを宛先ドキュメントに追加する

これで、ソース文書を宛先文書に追加することができます。`AppendDocument`方法の`Document`クラス。`ImportFormatMode.KeepSourceFormatting`パラメータにより、リストの書式設定を含むソースの書式設定が追加操作中に保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ5: 最終文書を保存する

最後に、リストのソース書式維持機能を有効にして結合した文書を保存します。`Save`方法の`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Aspose.Words for .NET を使用したリストのソース フォーマットの保持のサンプル ソース コード 

以下は、Aspose.Words for .NET を使用した C# のリスト保持ソース書式設定機能の完全なソース コードです。

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//ドキュメントのコンテンツを追加して、連続的に流れるようにします。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

これで完了です。Aspose.Words for .NET を使用して、リストのソース書式を保持する機能を正常に実装しました。最終的なドキュメントには、ソース ドキュメントのリスト書式が保持された状態で結合されたコンテンツが含まれます。