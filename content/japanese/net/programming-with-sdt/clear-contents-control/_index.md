---
title: クリアコンテンツコントロール
linktitle: クリアコンテンツコントロール
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のコントロールの内容をクリアする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/clear-contents-control/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の SDT の内容をクリアする方法を説明します。 SDT のコンテンツをクリアすると、コンテンツ コントロール内のテキストまたは子ノードが削除されます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントが置かれているディレクトリへの実際のパスを置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをロードして StructuredDocumentTag を取得する
を使用して Word 文書をロードします。`Document`コンストラクターを使用して、ドキュメントへのパスをパラメーターとして渡します。次に、必要なファイルを取得します`StructuredDocumentTag`文書から。この例では、SDT がドキュメント内の最初の子ノードであると仮定します。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## ステップ 3: StructuredDocumentTag の内容をクリアする
SDT の内容をクリアするには、`Clear`方法。これにより、コンテンツ コントロール内のテキストまたは子ノードが削除されます。

```csharp
sdt.Clear();
```

## ステップ 4: ドキュメントを保存する
変更したドキュメントを保存するには、`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.ClearContentsControl.doc」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Aspose.Words for .NET を使用したクリア コンテンツ コントロールのソース コードの例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内の StructuredDocumentTag の内容を正常にクリアしました。