---
title: ソースヘッダーフッターを削除
linktitle: ソースヘッダーフッターを削除
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントを結合および追加するときにヘッダーとフッターを削除する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/remove-source-headers-footers/
---

このチュートリアルでは、Aspose.Words for .NET のソース ヘッダー フッターの削除機能を使用するプロセスを説明します。この機能を使用すると、ソース文書からヘッダーとフッターを削除しながら、Word 文書を結合および追加できます。

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

## ステップ 3: ソースドキュメントのセクションからヘッダーとフッターを削除する

ソース文書の各セクションからヘッダーとフッターを削除するには、`foreach`ループして呼び出します`ClearHeadersFooters`方法。

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## ステップ 4: HeadersFooters の「LinkToPrevious」設定を無効にする

ソース文書からヘッダーとフッターを削除した後でも、「LinkToPrevious」設定が無効になる可能性があります。`HeadersFooters`まだ設定できます。この動作を回避するには、明示的に次のように設定する必要があります。`false`最初のセクションについては`HeadersFooters`財産。

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## ステップ 5: ソースドキュメントを宛先ドキュメントに追加する

これで、`AppendDocument`の方法`Document`クラス。の`ImportFormatMode.KeepSourceFormatting`パラメータを使用すると、追加操作中にソースの書式設定が確実に保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 6: 最終ドキュメントを保存する

最後に、ソース ヘッダー フッターの削除機能を有効にして結合されたドキュメントを保存します。`Save`の方法`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Aspose.Words for .NET を使用してソース ヘッダー フッターを削除するソース コードの例 

Aspose.Words for .NET を使用した C# の「ソース ヘッダー フッターの削除」機能の完全なソース コードは次のとおりです。


```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//ソース文書の各セクションからヘッダーとフッターを削除します。
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	//ヘッダーとフッターがソース文書から削除された後でも、「LinkToPrevious」設定は
	//HeadersFooters については引き続き設定できます。これにより、ヘッダーとフッターが宛先から継続されます。
	//書類。この動作を回避するには、これを false に設定する必要があります。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
それでおしまい！ Aspose.Words for .NET を使用して、ソース ヘッダー フッターの削除機能を正常に実装しました。最終的なドキュメントには、ソースドキュメントからヘッダーとフッターが削除された、マージされたコンテンツが含まれます。