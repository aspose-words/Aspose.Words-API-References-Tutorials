---
title: 連続参加
linktitle: 連続参加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、書式設定を保持しながら 2 つのドキュメントを連続的に結合する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/join-continuous/
---

このチュートリアルでは、Aspose.Words for .NET を使用して 2 つのドキュメントを連続的に結合する方法を説明します。提供されているソース コードは、元の書式を維持しながら、ドキュメントを別のドキュメントの末尾に追加する方法を示しています。

## ステップ1: プロジェクトを設定する

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NETライブラリがインストールされています。ダウンロードはこちらから[Aspose.Releases]https://releases.aspose.com/words/net/ にアクセスするか、NuGet パッケージ マネージャーを使用してインストールします。
- ソース ドキュメントと宛先ドキュメントが配置されているドキュメント ディレクトリ パス。

## ステップ2: ソースドキュメントと宛先ドキュメントを開く

ソース文書と宛先文書を`Document`クラスコンストラクタ。置換`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ステップ3: 連続セクションの開始を設定する

ソース文書を宛先文書の直後に表示させるには、`SectionStart`ソース文書の最初のセクションのプロパティを`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ステップ4: ソースドキュメントを追加する

ソース文書を宛先文書に追加するには、`AppendDocument`方法の`Document`クラス。インポート形式モードを`ImportFormatMode.KeepSourceFormatting`ソース ドキュメントの元のスタイルを保持します。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ5: 変更したドキュメントを保存する

最後に、変更した宛先ドキュメントを`Save`方法の`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

これで、Aspose.Words for .NET を使用して 2 つのドキュメントを連続的に結合する実装が完了します。

### Aspose.Words for .NET を使用した Join Continuous のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//ドキュメントを、宛先ドキュメントの内容の直後に表示します。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//ソース ドキュメントにある元のスタイルを使用して、ソース ドキュメントを追加します。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```