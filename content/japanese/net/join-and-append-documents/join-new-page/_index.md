---
title: 新しいページに参加する
linktitle: 新しいページに参加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して書式設定を維持しながら、新しいページで 2 つのドキュメントを結合する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/join-new-page/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、新しいページで 2 つのドキュメントを結合する方法について説明します。提供されているソース コードは、追加されたドキュメントを新しいページで開始しながら、別のドキュメントの末尾にドキュメントを追加する方法を示しています。

## ステップ 1: プロジェクトをセットアップする

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NET ライブラリがインストールされています。からダウンロードできます[Aspose.Releases]https://releases.aspose.com/words/net/ または NuGet パッケージ マネージャーを使用してインストールします。
- ソースおよび宛先ドキュメントが配置されるドキュメント ディレクトリ パス。

## ステップ 2: ソース文書と宛先文書を開く

を使用して、ソースドキュメントと宛先ドキュメントを開きます。`Document`クラスコンストラクター。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ステップ 3: 新しいページセクションの開始を設定する

追加されたドキュメントを新しいページで開始するには、`SectionStart`ソースドキュメントの最初のセクションのプロパティを`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## ステップ 4: ソースドキュメントを追加する

を使用して、ソースドキュメントを宛先ドキュメントに追加します。`AppendDocument`の方法`Document`クラス。インポート形式モードを次のように設定します。`ImportFormatMode.KeepSourceFormatting`ソースドキュメントの元のスタイルを保持します。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 5: 変更したドキュメントを保存する

最後に、変更した宛先ドキュメントを次のコマンドを使用して保存します。`Save`の方法`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

これで、Aspose.Words for .NET を使用して、新しいページで 2 つのドキュメントを結合する実装が完了しました。

### Aspose.Words for .NET を使用した新しいページの結合のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//追加されたドキュメントが新しいページで開始されるように設定します。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	//ソース ドキュメントにある元のスタイルを使用して、ソース ドキュメントを追加します。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```