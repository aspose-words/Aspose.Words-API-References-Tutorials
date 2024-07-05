---
title: ページレイアウトの更新
linktitle: ページレイアウトの更新
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を結合および追加するときにページ レイアウトを更新する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/update-page-layout/
---

このチュートリアルでは、Aspose.Words for .NET のページ レイアウト更新機能を使用する手順について説明します。この機能により、Word 文書を結合および追加するときにページ レイアウトが正しく更新されます。

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

## ステップ3: 宛先ドキュメントのページレイアウトを更新する

ソース文書を追加する前にページレイアウトが正しく更新されていることを確認するには、`UpdatePageLayout`宛先ドキュメントのメソッド。

```csharp
dstDoc.UpdatePageLayout();
```

## ステップ4: ソースドキュメントを宛先ドキュメントに追加する

これで、ソース文書を宛先文書に追加することができます。`AppendDocument`方法の`Document`クラス。`ImportFormatMode.KeepSourceFormatting`パラメータにより、追加操作中にソースの書式が保持されます。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ5: ページレイアウトを再度更新する

ソース文書を追加した後、`UpdatePageLayout`追加操作後に加えられた変更がレンダリングされた出力に反映されるように、宛先ドキュメントに対して再度メソッドを実行します。

```csharp
dstDoc.UpdatePageLayout();
```

## ステップ6: 最終文書を保存する

最後に、ページレイアウトの更新機能を有効にして結合した文書を保存します。`Save`方法の`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Aspose.Words for .NET を使用してページ レイアウトを更新するためのサンプル ソース コード

以下は、Aspose.Words for .NET を使用した C# の「ページ レイアウトの更新」機能の完全なソース コードです。

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//宛先ドキュメントが PDF や画像などにレンダリングされる場合
	//またはUpdatePageLayoutがソースドキュメントの前に呼び出されます。追加されます。
	//その後の変更はレンダリングされた出力には反映されません。
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	//変更をレンダリングされた出力に更新するには、UpdatePageLayout を再度呼び出す必要があります。
	//再度呼び出されない場合、追加されたドキュメントは次のレンダリングの出力には表示されません。
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

これで完了です。Aspose.Words for .NET を使用してページ レイアウトの更新機能を正常に実装しました。最終的なドキュメントには、ページ レイアウトが正しく更新された結合されたコンテンツが含まれます。