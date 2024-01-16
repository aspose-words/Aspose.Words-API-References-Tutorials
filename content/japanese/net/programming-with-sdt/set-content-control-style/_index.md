---
title: コンテンツ コントロール スタイルの設定
linktitle: コンテンツ コントロール スタイルの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のコンテンツ コントロールのスタイルを設定し、一貫した書式設定を適用する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/set-content-control-style/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のコンテンツ コントロールのスタイルを設定する方法について説明します。事前定義されたスタイルまたはカスタム スタイルをコンテンツ コントロールに適用して、一貫した書式設定を行うことができます。

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

## ステップ 3: スタイルを取得してコンテンツ コントロールに適用する
ドキュメントのスタイル コレクションから目的のスタイルを取得します。この例では、次を使用して「Quote」スタイルを取得します。`StyleIdentifier.Quote` 。次に、取得したスタイルを`Style`構造化文書タグのプロパティ。

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## ステップ 4: ドキュメントを保存する
を使用して、変更したドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.SetContentControlStyle.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Aspose.Words for .NET を使用したコンテンツ コントロール スタイルの設定のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内のコンテンツ コントロールのスタイルを正常に設定しました。