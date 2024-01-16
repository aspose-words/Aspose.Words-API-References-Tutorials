---
title: チェックボックスタイプのコンテンツコントロール
linktitle: チェックボックスタイプのコンテンツコントロール
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にチェック ボックス タイプのコンテンツ コントロールを作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/check-box-type-content-control/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にチェック ボックス タイプのコンテンツ コントロールを作成する方法について説明します。チェック ボックス コンテンツ コントロールを使用すると、ユーザーはドキュメント内のチェックボックスを選択またはクリアできます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントと DocumentBuilder を作成する
の新しいインスタンスを作成します。`Document`クラスと`DocumentBuilder`ドキュメントのコンテンツを構築します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: チェックボックスタイプのコンテンツコントロールを追加する
を作成します`StructuredDocumentTag`と`SdtType.Checkbox`チェックボックスのコンテンツコントロールを表します。特定`MarkupLevel.Inline`テキスト内に配置します。

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## ステップ 4: ドキュメントを保存する
を使用してドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.CheckBoxTypeContentControl.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Aspose.Words for .NET を使用したチェック ボックス タイプ コンテンツ コントロールのソース コードの例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内にチェック ボックス タイプのコンテンツ コントロールが正常に作成されました。