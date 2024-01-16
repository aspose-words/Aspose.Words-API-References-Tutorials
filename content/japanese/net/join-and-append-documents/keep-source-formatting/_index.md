---
title: ソースのフォーマットを維持する
linktitle: ソースのフォーマットを維持する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、元の書式を維持しながらソース ドキュメントを宛先ドキュメントに追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/keep-source-formatting/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、ソース ドキュメントの元の書式を保持しながら、ソース ドキュメントを宛先ドキュメントに追加する方法を説明します。

## ステップ 1: プロジェクトをセットアップする

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NET ライブラリがインストールされています。からダウンロードできます[Aspose.Releases]https://releases.aspose.com/words/net/ または NuGet パッケージ マネージャーを使用してインストールします。
- ソースドキュメントと宛先ドキュメントが保存されるドキュメントディレクトリのパス。

## ステップ 2: 宛先ドキュメントとソースドキュメントを作成する

のインスタンスを作成します`Document`宛先ドキュメントとソースドキュメント用。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## ステップ 3: ソース文書を宛先文書に追加する

使用`AppendDocument`ソースドキュメントを追加する宛先ドキュメントのメソッド。合格`ImportFormatMode.KeepSourceFormatting`インポート形式モードとして、ソースドキュメントの元の形式を保持します。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 4: 変更したドキュメントを保存する

変更したドキュメントを保存するには、`Save`の方法`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

これで、Aspose.Words for .NET を使用して元の書式を維持しながら、ソース ドキュメントを宛先ドキュメントに追加する実装が完了しました。

### Aspose.Words for .NET を使用したソースの書式設定を維持するためのソース コードの例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	//ソースドキュメントを宛先ドキュメントに追加します。
	//フォーマット モードを渡して、インポート時にソース ドキュメントの元のフォーマットを保持します。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```