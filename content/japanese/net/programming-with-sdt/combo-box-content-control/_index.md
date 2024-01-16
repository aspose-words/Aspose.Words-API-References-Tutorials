---
title: コンボボックスコンテンツコントロール
linktitle: コンボボックスコンテンツコントロール
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内にコンボ ボックス コンテンツ コントロールを作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/combo-box-content-control/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内にコンボ ボックス コンテンツ コントロールを作成する方法について説明します。コンボ ボックスのコンテンツ コントロールを使用すると、ユーザーはドロップダウン リストから項目を選択できます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントと StructuredDocumentTag を作成する
の新しいインスタンスを作成します。`Document`クラスと`StructuredDocumentTag`コンボ ボックスのコンテンツ コントロールを表します。特定`SdtType.ComboBox`タイプとして、そして`MarkupLevel.Block`マークアップ レベルとして使用して、ブロック レベルのコンボ ボックスを作成します。

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## ステップ 3: コンボボックスに項目を追加する
コンボボックスに項目を追加するには、`ListItems`の財産`StructuredDocumentTag`。各項目は、`SdtListItem`オブジェクト。表示テキストと値を受け取ります。この例では、コンボ ボックスに 3 つの項目を追加します。

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## ステップ 4: StructuredDocumentTag をドキュメントに追加する
コンボ ボックス コンテンツ コントロールをドキュメントの本文に追加するには、`AppendChild`ドキュメントの最初のセクションの本文のメソッド。

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## ステップ 5: ドキュメントを保存する
を使用してドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.ComboBoxContentControl.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Aspose.Words for .NET を使用したコンボ ボックス コンテンツ コントロールのソース コードの例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内にコンボ ボックス コンテンツ コントロールが正常に作成されました。