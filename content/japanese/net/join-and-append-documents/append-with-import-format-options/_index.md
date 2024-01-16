---
title: インポート形式オプションを使用して追加
linktitle: インポート形式オプションを使用して追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、インポート形式オプションを指定してドキュメントを追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/append-with-import-format-options/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、インポート形式オプションを使用して、あるドキュメントのコンテンツを別のドキュメントに追加する方法について説明します。提供されているソース コードは、ソース ドキュメントと宛先ドキュメントを開き、インポート形式オプションを指定し、ソース ドキュメントを宛先ドキュメントに追加する方法を示しています。

## ステップ 1: プロジェクトをセットアップする

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NET ライブラリがインストールされています。からダウンロードできます[Aspose.Releases]https://releases.aspose.com/words/net/ または NuGet パッケージ マネージャーを使用してインストールします。
- ソースおよび宛先ドキュメントが配置されるドキュメント ディレクトリ パス。

## ステップ 2: ソース文書と宛先文書を開く

を使用して、ソースドキュメントと宛先ドキュメントを開きます。`Document`クラスコンストラクター。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## ステップ 3: インポート形式オプションを指定する

のインスタンスを作成します。`ImportFormatOptions`クラスを使用してインポート形式のオプションを指定します。この例では、`KeepSourceNumbering`プロパティを使用して、宛先ドキュメントとの衝突がある場合に、ソースドキュメントの番号付けが使用されるようにします。

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## ステップ 4: ソース文書を宛先文書に追加する

使用`AppendDocument`ソースドキュメントを追加する宛先ドキュメントのメソッド。合格`ImportFormatMode.UseDestinationStyles` 番目のパラメータとして、宛先ドキュメントのスタイルと書式設定を使用します。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## ステップ 5: 宛先ドキュメントを保存する

最後に、変更した宛先ドキュメントを次のコマンドを使用して保存します。`Save`の方法`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

これで、Aspose.Words for .NET を使用してインポート形式オプションを使用してドキュメントを追加する実装が完了しました。

### Aspose.Words for .NET を使用した「インポート形式オプションを追加」のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//ソース文書と宛先文書で番号付けが衝突する場合、次のように指定します。
	//その場合、ソース文書の番号付けが使用されます。
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```