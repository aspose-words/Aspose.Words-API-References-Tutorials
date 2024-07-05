---
title: マルチセクション
linktitle: マルチセクション
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の複数セクションの構造化文書タグを取得および処理する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/multi-section/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の複数セクション構造化文書タグを操作する方法について説明します。文書内に存在するセクション タグを取得して処理できます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントが配置されているディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントを読み込み、マルチセクションタグを取得する
Word文書を読み込むには、`Document`コンストラクタは、ドキュメントへのパスをパラメータとして渡します。`GetChildNodes`方法。

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## ステップ3: マルチセクションタグを処理する
構造化ドキュメントのタグ範囲開始ノードのコレクションを反復処理します。この例では、各タグのタイトルをコンソールに出力するだけです。要件に応じてさらに処理を実行できます。

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Aspose.Words for .NET を使用したマルチセクションのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内の複数セクションの構造化文書タグを正常に取得して処理できました。