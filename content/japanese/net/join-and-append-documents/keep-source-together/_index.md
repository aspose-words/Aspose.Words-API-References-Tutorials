---
title: ソースをまとめて保管する
linktitle: ソースをまとめて保管する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ソース コンテンツを宛先ドキュメントと一緒に保持しながら Word ドキュメントを結合および追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/keep-source-together/
---

このチュートリアルでは、Aspose.Words for .NET の Keep Source Together 機能を使用するプロセスについて説明します。この機能を使用すると、ソース ドキュメントのコンテンツを宛先ドキュメントのコンテンツとともに保持しながら、複数の Word ドキュメントを結合して追加できます。 

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

## ステップ 3: ソースドキュメントが宛先ドキュメントのコンテンツの後に表示されるように設定する

ソースドキュメントが宛先ドキュメントのコンテンツの直後に表示されるようにするには、`SectionStart`ソースドキュメントの最初のセクションのプロパティを`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ステップ 4: ソース文書の段落書式を「次まで保持」に設定する

ソース文書内の段落をまとめて保持するには、文書内の各段落を反復処理して、`KeepWithNext`財産を`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## ステップ 5: ソースドキュメントを宛先ドキュメントに追加する

これで、`AppendDocument`の方法`Document`クラス。の`ImportFormatMode.KeepSourceFormatting`パラメータを使用すると、追加操作中にソースの書式設定が確実に保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 6: 最終ドキュメントを保存する

最後に、「ソースを一緒に保持」機能を有効にして、結合されたドキュメントを保存します。`Save`の方法`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Aspose.Words for .NET を使用した Keep Source Together のソース コード例 

Aspose.Words for .NET を使用した C# の「Keep Source Together」機能の完全なソース コードは次のとおりです。


```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//ソースドキュメントが宛先ドキュメントのコンテンツの直後に表示されるように設定します。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、Keep Source Together 機能を正常に実装しました。最終的なドキュメントには、ソースドキュメント内の段落がまとめられた、マージされたコンテンツが含まれます。