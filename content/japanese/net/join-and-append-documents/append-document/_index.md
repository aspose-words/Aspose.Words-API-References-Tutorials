---
title: ドキュメントの追加
linktitle: ドキュメントの追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、あるドキュメントの内容を別のドキュメントに追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/append-document/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、あるドキュメントの内容を別のドキュメントに追加する方法について説明します。提供されているソース コードは、ソース ドキュメントと宛先ドキュメントを開き、ソース ドキュメントから宛先ドキュメントにセクションをインポートして追加する方法を示しています。

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

## ステップ 3: ソース文書のセクションを宛先文書に追加する

ソース文書内のすべてのセクションをループし、各セクションを宛先文書にインポートします。`ImportNode`方法。次に、インポートしたセクションを宛先ドキュメントに追加します。

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## ステップ 4: 宛先ドキュメントを保存する

最後に、変更した宛先ドキュメントを次のコマンドを使用して保存します。`Save`の方法`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

これで、Aspose.Words for .NET を使用したドキュメントの追加の実装が完了しました。

### Aspose.Words for .NET を使用したドキュメントの追加のソース コードの例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//ソース文書内のすべてのセクションをループします。
	//セクション ノードは Document ノードの直接の子であるため、Document を列挙するだけで済みます。
	foreach (Section srcSection in srcDoc)
	{
		//あるドキュメントから別のドキュメントにセクションをコピーしているため、
		//セクション ノードを宛先ドキュメントにインポートする必要があります。
		//これにより、スタイル、リストなどに対するドキュメント固有の参照が調整されます。
		//
		//ノードをインポートすると、元のノードのコピーが作成されますが、そのコピーは
		//ss を宛先ドキュメントに挿入する準備ができました。
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		//これで、新しいセクション ノードを宛先ドキュメントに追加できるようになります。
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```