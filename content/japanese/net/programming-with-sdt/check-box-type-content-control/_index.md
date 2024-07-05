---
title: チェックボックス型コンテンツコントロール
linktitle: チェックボックス型コンテンツコントロール
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にチェック ボックス タイプのコンテンツ コントロールを作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/check-box-type-content-control/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にチェック ボックス タイプのコンテンツ コントロールを作成する方法について説明します。チェック ボックス コンテンツ コントロールを使用すると、ユーザーは文書内のチェック ボックスを選択またはクリアできます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントとDocumentBuilderを作成する
新しいインスタンスを作成する`Document`クラスと`DocumentBuilder`ドキュメントのコンテンツを構築します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: チェックボックスタイプのコンテンツコントロールを追加する
作成する`StructuredDocumentTag`と`SdtType.Checkbox`チェックボックスコンテンツコントロールを表すために指定します。`MarkupLevel.Inline`テキスト内に配置します。

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## ステップ4: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.CheckBoxTypeContentControl.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Aspose.Words for .NET を使用したチェックボックス型コンテンツ コントロールのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書にチェック ボックス タイプのコンテンツ コントロールを正常に作成できました。