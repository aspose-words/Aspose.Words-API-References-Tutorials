---
title: コンテンツ コントロールの色の設定
linktitle: コンテンツ コントロールの色の設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のコンテンツ コントロールの色を設定し、外観をカスタマイズする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/set-content-control-color/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word ドキュメントのコンテンツ コントロールの色を設定する方法について説明します。コンテンツ コントロールの色を変更することで、コンテンツ コントロールの外観をカスタマイズできます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントが置かれているディレクトリへの実際のパスを置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをロードし、コンテンツ コントロールを取得する
を使用して Word 文書をロードします。`Document`コンストラクターを使用して、ドキュメントへのパスをパラメーターとして渡します。ドキュメントから目的のコンテンツ コントロールを取得します。この例では、コンテンツ コントロールがドキュメント内の最初の構造化ドキュメント タグであると仮定します。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## ステップ 3: コンテンツ コントロールの色を設定する
コンテンツ コントロールの色を設定するには、`Color`の価値`Color`構造化文書タグのプロパティ。この例では、色を赤に設定します。

```csharp
sdt.Color = Color.Red;
```

## ステップ 4: ドキュメントを保存する
を使用して、変更したドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.SetContentControlColor.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Aspose.Words for .NET を使用したコンテンツ コントロールの色の設定のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内のコンテンツ コントロールの色を正常に設定できました。