---
title: 空白のドキュメントを追加
linktitle: 空白のドキュメントを追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で空の宛先ドキュメントにドキュメントを追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/append-document-to-blank/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、1 つのドキュメントのコンテンツを空の宛先ドキュメントに追加する方法について説明します。提供されているソース コードは、新しいドキュメントを作成し、そのコンテンツを削除し、それにソース ドキュメントを追加する方法を示しています。

## ステップ 1: プロジェクトをセットアップする

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NET ライブラリがインストールされています。からダウンロードできます[Aspose.Releases]https://releases.aspose.com/words/net/ または NuGet パッケージ マネージャーを使用してインストールします。
- ソースおよび宛先ドキュメントが配置されるドキュメント ディレクトリ パス。

## ステップ 2: 新しい宛先ドキュメントを作成する

新しいを作成します`Document`宛先ドキュメントのオブジェクト。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## ステップ 3: 宛先ドキュメントから既存のコンテンツを削除する

宛先ドキュメントがクリーンであることを確認するには、ドキュメントから既存のコンテンツをすべて削除します。`RemoveAllChildren`方法。

```csharp
dstDoc.RemoveAllChildren();
```

## ステップ 4: ソース文書を宛先文書に追加する

を使用して、ソースドキュメントの内容を宛先ドキュメントに追加します。`AppendDocument`を使用したメソッド`ImportFormatMode.KeepSourceFormatting`オプション。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 5: 宛先ドキュメントを保存する

最後に、変更した宛先ドキュメントを次のコマンドを使用して保存します。`Save`の方法`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

これで、Aspose.Words for .NET を使用して空の宛先ドキュメントにドキュメントを追加する実装が完了しました。

### Aspose.Words for .NET を使用した「ドキュメントを空白に追加」のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	//宛先ドキュメントが空ではないため、多くの場合、追加されたドキュメントの前に空白のページが表示されます。
	//これは、ベースドキュメントに空のセクションがあり、新しいドキュメントが次のページから開始されるためです。
	//追加する前に、宛先ドキュメントからすべてのコンテンツを削除してください。
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```