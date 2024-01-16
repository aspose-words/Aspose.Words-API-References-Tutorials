---
title: マルチセクション
linktitle: マルチセクション
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の複数セクションの構造化文書タグを取得および処理する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/multi-section/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の複数セクションの構造化文書タグを操作する方法について説明します。ドキュメント内に存在するセクション タグを取得して処理できます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントが置かれているディレクトリへの実際のパスを置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをロードして複数セクションのタグを取得する
を使用して Word 文書をロードします。`Document`コンストラクターを使用して、ドキュメントへのパスをパラメーターとして渡します。を使用して、文書内のすべての構造化文書タグ範囲開始ノードを取得します。`GetChildNodes`方法。

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## ステップ 3: 複数セクションのタグを処理する
構造化文書タグ範囲開始ノードのコレクションを反復処理します。この例では、各タグのタイトルをコンソールに出力するだけです。要件に基づいてさらに処理を実行できます。

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Aspose.Words for .NET を使用したマルチセクションのソースコード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内の複数セクションの構造化文書タグを正常に取得して処理しました。