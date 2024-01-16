---
title: ページレイアウトを更新する
linktitle: ページレイアウトを更新する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントを結合および追加するときにページ レイアウトを更新する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/update-page-layout/
---

このチュートリアルでは、Aspose.Words for .NET のページ レイアウトの更新機能を使用するプロセスについて説明します。この機能により、Word 文書を結合および追加するときにページ レイアウトが正しく更新されます。

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

## ステップ 3: 宛先ドキュメントのページ レイアウトを更新する

ソースドキュメントを追加する前にページレイアウトが正しく更新されていることを確認するには、`UpdatePageLayout`宛先ドキュメントのメソッド。

```csharp
dstDoc.UpdatePageLayout();
```

## ステップ 4: ソースドキュメントを宛先ドキュメントに追加する

これで、`AppendDocument`の方法`Document`クラス。の`ImportFormatMode.KeepSourceFormatting`パラメータを使用すると、追加操作中にソースの書式設定が確実に保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 5: ページ レイアウトを再度更新する

ソースドキュメントを追加した後、`UpdatePageLayout`宛先ドキュメントのメソッドを再度実行して、追加操作後に行われた変更がレンダリングされた出力に反映されていることを確認します。

```csharp
dstDoc.UpdatePageLayout();
```

## ステップ 6: 最終ドキュメントを保存する

最後に、ページ レイアウトの更新機能を有効にして、結合されたドキュメントを保存します。`Save`の方法`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Aspose.Words for .NET を使用したページ レイアウトの更新のソース コードの例

Aspose.Words for .NET を使用した C# の「ページ レイアウトの更新」機能の完全なソース コードは次のとおりです。

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//宛先ドキュメントが PDF、画像などにレンダリングされる場合。
	//または、UpdatePageLayout がソース ドキュメントの前に呼び出されます。追加されており、
	//その後に行われた変更は、レンダリングされた出力には反映されません。
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	//レンダリングされた出力に変更を更新するには、UpdatePageLayout を再度呼び出す必要があります。
	//再度呼び出されないと、追加されたドキュメントは次のレンダリングの出力に表示されません。
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

それでおしまい！ Aspose.Words for .NET を使用してページ レイアウトの更新機能を正常に実装しました。最終的なドキュメントには、ページ レイアウトが正しく更新されたマージされたコンテンツが含まれます。