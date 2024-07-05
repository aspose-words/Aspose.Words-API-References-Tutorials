---
title: クリアコンテンツコントロール
linktitle: クリアコンテンツコントロール
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のコントロールの内容をクリアする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/clear-contents-control/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の SDT の内容をクリアする方法を説明します。SDT の内容をクリアすると、コンテンツ コントロール内のすべてのテキストまたは子ノードが削除されます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントが配置されているディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントを読み込み、StructuredDocumentTagを取得する
Word文書を読み込むには、`Document`コンストラクタにドキュメントへのパスをパラメータとして渡します。次に、目的の`StructuredDocumentTag`ドキュメントから。この例では、SDT がドキュメントの最初の子ノードであると想定しています。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## ステップ3: StructuredDocumentTagの内容をクリアする
SDTの内容をクリアするには、`Clear`メソッド。これにより、コンテンツ コントロール内のすべてのテキストまたは子ノードが削除されます。

```csharp
sdt.Clear();
```

## ステップ4: ドキュメントを保存する
変更した文書を保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.ClearContentsControl.doc」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Aspose.Words for .NET を使用した Clear Contents Control のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内の StructuredDocumentTag の内容を正常にクリアできました。