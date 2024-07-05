---
title: ソースをまとめる
linktitle: ソースをまとめる
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ソース コンテンツを宛先ドキュメントと一緒に保ちながら Word ドキュメントを結合および追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/keep-source-together/
---

このチュートリアルでは、Aspose.Words for .NET の Keep Source Together 機能を使用する手順を説明します。この機能を使用すると、ソース ドキュメントのコンテンツと宛先ドキュメントのコンテンツを一緒に保持しながら、複数の Word ドキュメントを結合および追加できます。 

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

## ステップ3: ソース文書を宛先文書のコンテンツの後に表示されるように設定する

ソース文書が宛先文書のコンテンツの直後に表示されるようにするには、`SectionStart`ソース文書の最初のセクションのプロパティを`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ステップ 4: ソース文書の「次の段落と連動」段落書式を設定する

ソース文書内の段落をまとめておくには、文書内の各段落を反復処理して、`KeepWithNext`財産に`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## ステップ5: ソースドキュメントを宛先ドキュメントに追加する

これで、ソース文書を宛先文書に追加することができます。`AppendDocument`方法の`Document`クラス。`ImportFormatMode.KeepSourceFormatting`パラメータにより、追加操作中にソースの書式が保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ6: 最終文書を保存する

最後に、「ソースをまとめる」機能を有効にして結合した文書を保存します。`Save`方法の`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Aspose.Words for .NET を使用してソースをまとめるサンプル ソース コード 

以下は、Aspose.Words for .NET を使用した C# の「ソースをまとめて保持」機能の完全なソース コードです。


```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//ソース ドキュメントを、宛先ドキュメントのコンテンツの直後に表示されるように設定します。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

これで完了です。Aspose.Words for .NET を使用して、Keep Source Together 機能を正常に実装できました。最終的なドキュメントには、ソース ドキュメント内の段落がまとめられた状態で結合されたコンテンツが含まれます。