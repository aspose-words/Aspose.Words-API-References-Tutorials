---
title: コンテンツコントロールスタイルの設定
linktitle: コンテンツコントロールスタイルの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、一貫した書式を適用し、Word 文書内のコンテンツ コントロールのスタイルを設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/set-content-control-style/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のコンテンツ コントロールのスタイルを設定する方法について説明します。コンテンツ コントロールに定義済みまたはカスタムのスタイルを適用して、一貫した書式設定を行うことができます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントが配置されているディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントを読み込み、コンテンツ コントロールを取得する
Word文書を読み込むには、`Document`コンストラクターを呼び出して、ドキュメントへのパスをパラメーターとして渡します。ドキュメントから目的のコンテンツ コントロールを取得します。この例では、コンテンツ コントロールがドキュメント内の最初の構造化ドキュメント タグであると想定しています。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## ステップ 3: スタイルを取得してコンテンツ コントロールに適用する
ドキュメントのスタイルコレクションから目的のスタイルを取得します。この例では、次のようにして「Quote」スタイルを取得します。`StyleIdentifier.Quote`次に、取得したスタイルを`Style`構造化ドキュメントタグのプロパティ。

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## ステップ4: ドキュメントを保存する
変更したドキュメントを指定されたディレクトリに保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.SetContentControlStyle.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Aspose.Words for .NET を使用してコンテンツ コントロール スタイルを設定するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内のコンテンツ コントロールのスタイルを正常に設定できました。