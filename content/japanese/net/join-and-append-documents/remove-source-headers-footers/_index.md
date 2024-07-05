---
title: ソースヘッダーフッターを削除
linktitle: ソースヘッダーフッターを削除
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を結合および追加するときにヘッダーとフッターを削除する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/remove-source-headers-footers/
---

このチュートリアルでは、Aspose.Words for .NET のソース ヘッダー フッターの削除機能を使用する手順を説明します。この機能を使用すると、ソース ドキュメントからヘッダーとフッターを削除しながら、Word ドキュメントを結合および追加できます。

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

## ステップ3: ソースドキュメントセクションからヘッダーとフッターを削除する

ソース文書の各セクションからヘッダーとフッターを削除するには、`foreach`ループして呼び出し`ClearHeadersFooters`方法。

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## ステップ4: ヘッダー/フッターの「LinkToPrevious」設定を無効にする

ソース文書からヘッダーとフッターを消去した後でも、`HeadersFooters`設定することは可能です。この動作を回避するには、明示的に設定する必要があります。`false`最初のセクションの`HeadersFooters`財産。

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## ステップ5: ソースドキュメントを宛先ドキュメントに追加する

これで、ソース文書を宛先文書に追加することができます。`AppendDocument`方法の`Document`クラス。`ImportFormatMode.KeepSourceFormatting`パラメータにより、追加操作中にソースの書式が保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ6: 最終文書を保存する

最後に、ソースヘッダーフッターの削除機能を有効にして結合した文書を保存します。`Save`方法の`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Aspose.Words for .NET を使用してソース ヘッダー フッターを削除するサンプル ソース コード 

以下は、Aspose.Words for .NET を使用した C# の「ソース ヘッダー フッターの削除」機能の完全なソース コードです。


```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//ソース ドキュメントの各セクションからヘッダーとフッターを削除します。
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	//ソース文書からヘッダーとフッターが消去された後でも、「LinkToPrevious」設定は
	//ヘッダーフッターは設定可能です。これにより、ヘッダーとフッターは宛先から継続されます。
	//ドキュメント。この動作を回避するには、これを false に設定する必要があります。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
これで完了です。Aspose.Words for .NET を使用してソース ヘッダー フッターの削除機能を正常に実装しました。最終的なドキュメントには、ソース ドキュメントからヘッダーとフッターが削除された結合されたコンテンツが含まれます。