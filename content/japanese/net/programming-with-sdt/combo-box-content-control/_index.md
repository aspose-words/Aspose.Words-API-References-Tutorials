---
title: コンボ ボックス コンテンツ コントロール
linktitle: コンボ ボックス コンテンツ コントロール
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にコンボ ボックス コンテンツ コントロールを作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/combo-box-content-control/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にコンボ ボックス コンテンツ コントロールを作成する方法について説明します。コンボ ボックス コンテンツ コントロールを使用すると、ユーザーはドロップダウン リストから項目を選択できます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントとStructuredDocumentTagを作成する
新しいインスタンスを作成する`Document`クラスと`StructuredDocumentTag`コンボボックスのコンテンツコントロールを表すために指定します。`SdtType.ComboBox`タイプとして`MarkupLevel.Block`ブロックレベルのコンボボックスを作成するためのマークアップレベルとして使用します。

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## ステップ3: コンボボックスに項目を追加する
コンボボックスにアイテムを追加するには、`ListItems`の財産`StructuredDocumentTag`各項目は`SdtListItem`オブジェクトは、表示テキストと値を受け取ります。この例では、コンボ ボックスに 3 つの項目を追加します。

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## ステップ4: StructuredDocumentTagをドキュメントに追加する
コンボボックスコンテンツコントロールをドキュメント本体に追加するには、`AppendChild`ドキュメントの最初のセクションの本文の方法。

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## ステップ5: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.ComboBoxContentControl.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Aspose.Words for .NET を使用したコンボ ボックス コンテンツ コントロールのサンプル ソース コード 

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

これで完了です。Aspose.Words for .NET を使用して、Word 文書にコンボ ボックス コンテンツ コントロールを正常に作成できました。