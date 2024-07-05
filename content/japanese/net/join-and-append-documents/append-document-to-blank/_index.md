---
title: 空白にドキュメントを追加
linktitle: 空白にドキュメントを追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で空白の宛先ドキュメントにドキュメントを追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/append-document-to-blank/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、あるドキュメントの内容を空白の宛先ドキュメントに追加する方法について説明します。提供されているソース コードは、新しいドキュメントを作成し、そのコンテンツを削除してから、ソース ドキュメントを追加する方法を示しています。

## ステップ1: プロジェクトを設定する

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NETライブラリがインストールされています。ダウンロードはこちらから[Aspose.Releases]https://releases.aspose.com/words/net/ にアクセスするか、NuGet パッケージ マネージャーを使用してインストールします。
- ソース ドキュメントと宛先ドキュメントが配置されているドキュメント ディレクトリ パス。

## ステップ2: 新しい宛先ドキュメントを作成する

新しいを作成します`Document`宛先ドキュメントのオブジェクト。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## ステップ3: 宛先ドキュメントから既存のコンテンツを削除する

クリーンな宛先ドキュメントを確保するには、`RemoveAllChildren`方法。

```csharp
dstDoc.RemoveAllChildren();
```

## ステップ4: ソース文書を宛先文書に追加する

ソース文書の内容を宛先文書に追加するには、`AppendDocument`方法`ImportFormatMode.KeepSourceFormatting`オプション。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ5: 宛先ドキュメントを保存する

最後に、変更した宛先ドキュメントを`Save`方法の`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

これで、Aspose.Words for .NET を使用して空白の宛先ドキュメントにドキュメントを追加する実装が完了します。

### Aspose.Words for .NET を使用して空白にドキュメントを追加するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	//宛先ドキュメントが空ではないため、追加されたドキュメントの前に空白ページが表示されることがよくあります。
	//これは、ベース ドキュメントに空のセクションがあり、新しいドキュメントが次のページで開始されるためです。
	//追加する前に、宛先ドキュメントからすべてのコンテンツを削除します。
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```