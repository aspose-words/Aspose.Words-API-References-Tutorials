---
title: ヘッダー・フッターを無視する
linktitle: ヘッダー・フッターを無視する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ヘッダーとフッターのコンテンツを無視してドキュメントを追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/ignore-header-footer/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、ヘッダーとフッターのコンテンツを無視してドキュメントを追加する方法について説明します。提供されたソース コードは、追加プロセス中にヘッダーとフッターを除外するインポート形式オプションを設定する方法を示しています。

## ステップ 1: プロジェクトをセットアップする

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NET ライブラリがインストールされています。からダウンロードできます[Aspose.Releases]https://releases.aspose.com/words/net/ または NuGet パッケージ マネージャーを使用してインストールします。
- ソースおよび宛先ドキュメントが配置されるドキュメント ディレクトリ パス。

## ステップ 2: ソース文書と宛先文書を開く

を使用して、ソースドキュメントと宛先ドキュメントを開きます。`Document`クラスコンストラクター。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## ステップ 3: インポート形式オプションを設定する

のインスタンスを作成します。`ImportFormatOptions`クラスを設定して、`IgnoreHeaderFooter`財産を`false`。これにより、ヘッダーとフッターのコンテンツが追加プロセス中に確実に含まれるようになります。

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## ステップ 4: ソース文書を宛先文書に追加する

使用`AppendDocument`ソースドキュメントを追加する宛先ドキュメントのメソッド。合格`ImportFormatMode.KeepSourceFormatting` 2 番目のパラメータとして、インポート形式オプションを 3 番目のパラメータとして指定します。

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## ステップ 5: 宛先ドキュメントを保存する

最後に、変更した宛先ドキュメントを次のコマンドを使用して保存します。`Save`の方法`Document`物体。

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

これで、Aspose.Words for .NET を使用してヘッダーとフッターのコンテンツを無視してドキュメントを追加する実装が完了しました。

### Aspose.Words for .NET を使用したヘッダー フッターを無視するソース コードの例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```