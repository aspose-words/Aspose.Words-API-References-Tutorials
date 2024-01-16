---
title: 連続参加
linktitle: 連続参加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、書式を維持しながら 2 つのドキュメントを連続的に結合する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/join-continuous/
---

このチュートリアルでは、Aspose.Words for .NET を使用して 2 つのドキュメントを連続的に結合する方法について説明します。提供されているソース コードは、元の書式を維持しながらドキュメントを別のドキュメントの末尾に追加する方法を示しています。

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

## ステップ 3: 連続セクションの開始を設定する

ソース文書を宛先文書のコンテンツの直後に表示するには、`SectionStart`ソースドキュメントの最初のセクションのプロパティを`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ステップ 4: ソースドキュメントを追加する

を使用して、ソースドキュメントを宛先ドキュメントに追加します。`AppendDocument`の方法`Document`クラス。インポート形式モードを次のように設定します。`ImportFormatMode.KeepSourceFormatting`ソースドキュメントの元のスタイルを保持します。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 5: 変更したドキュメントを保存する

最後に、変更した宛先ドキュメントを次のコマンドを使用して保存します。`Save`の方法`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

これで、Aspose.Words for .NET を使用して 2 つのドキュメントを連続的に結合する実装が完了しました。

### Aspose.Words for .NET を使用した連続結合のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//ドキュメントが宛先ドキュメントのコンテンツの直後に表示されるようにします。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//ソース ドキュメントにある元のスタイルを使用して、ソース ドキュメントを追加します。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```