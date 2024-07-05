---
title: インポート形式オプションを追加
linktitle: インポート形式オプションを追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、インポート形式オプションを使用してドキュメントを追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/append-with-import-format-options/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、インポート形式オプションを使用して 1 つのドキュメントの内容を別のドキュメントに追加する方法について説明します。提供されているソース コードは、ソース ドキュメントと宛先ドキュメントを開き、インポート形式オプションを指定して、ソース ドキュメントを宛先ドキュメントに追加する方法を示しています。

## ステップ1: プロジェクトを設定する

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NETライブラリがインストールされています。ダウンロードはこちらから[Aspose.Releases]https://releases.aspose.com/words/net/ にアクセスするか、NuGet パッケージ マネージャーを使用してインストールします。
- ソース ドキュメントと宛先ドキュメントが配置されているドキュメント ディレクトリ パス。

## ステップ2: ソースドキュメントと宛先ドキュメントを開く

ソース文書と宛先文書を`Document`クラスコンストラクタ。置換`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## ステップ3: インポート形式のオプションを指定する

インスタンスを作成する`ImportFormatOptions`クラスを使用してインポート形式のオプションを指定します。この例では、`KeepSourceNumbering`宛先ドキュメントとの番号付けが競合する場合に、ソース ドキュメントの番号付けが使用されるようにするプロパティ。

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## ステップ4: ソース文書を宛先文書に追加する

使用`AppendDocument`宛先ドキュメントのメソッドを使用してソースドキュメントを追加します。`ImportFormatMode.UseDestinationStyles` 2 番目のパラメータとして、宛先ドキュメントのスタイルと書式設定を使用します。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## ステップ5: 宛先ドキュメントを保存する

最後に、変更した宛先ドキュメントを`Save`方法の`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

これで、Aspose.Words for .NET を使用してインポート形式オプションを含むドキュメントを追加する実装が完了します。

### Aspose.Words for .NET を使用したインポート形式オプション付き追加のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//ソース文書と宛先文書の番号が衝突する場合、
	//ソース ドキュメントからの番号付けが使用されます。
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```