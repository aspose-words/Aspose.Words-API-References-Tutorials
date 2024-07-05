---
title: ソースの書式を維持
linktitle: ソースの書式を維持
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、元の書式設定を保持しながらソース ドキュメントを宛先ドキュメントに追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/keep-source-formatting/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、ソース ドキュメントの元の書式を保持しながら、ソース ドキュメントを宛先ドキュメントに追加する方法を説明します。

## ステップ1: プロジェクトを設定する

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NETライブラリがインストールされています。ダウンロードはこちらから[Aspose.Releases]https://releases.aspose.com/words/net/ にアクセスするか、NuGet パッケージ マネージャーを使用してインストールします。
- ソース ドキュメントと宛先ドキュメントが保存されるドキュメント ディレクトリ パス。

## ステップ2: 宛先ドキュメントとソースドキュメントを作成する

インスタンスを作成する`Document`宛先ドキュメントとソースドキュメント用。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## ステップ3: ソース文書を宛先文書に追加する

使用`AppendDocument`宛先ドキュメントのメソッドを使用してソースドキュメントを追加します。`ImportFormatMode.KeepSourceFormatting`ソース ドキュメントの元の書式を保持するには、インポート形式モードを使用します。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ4: 変更したドキュメントを保存する

変更した文書を保存するには、`Save`方法の`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

これにより、Aspose.Words for .NET を使用して、元の書式を維持しながらソース ドキュメントを宛先ドキュメントに追加する実装が完了します。

### Aspose.Words for .NET を使用したソース書式の保持のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	//ソース ドキュメントを宛先ドキュメントに追加します。
	//インポート時にソース ドキュメントの元の書式を保持するには、フォーマット モードを渡します。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```