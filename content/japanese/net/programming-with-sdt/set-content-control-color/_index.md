---
title: コンテンツコントロールの色を設定する
linktitle: コンテンツコントロールの色を設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のコンテンツ コントロールの色を設定し、その外観をカスタマイズする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/set-content-control-color/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のコンテンツ コントロールの色を設定する方法について説明します。コンテンツ コントロールの色を変更することで、その外観をカスタマイズできます。

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

## ステップ3: コンテンツコントロールの色を設定する
コンテンツコントロールの色を設定するには、`Color`価値に`Color`構造化ドキュメント タグのプロパティ。この例では、色を赤に設定しています。

```csharp
sdt.Color = Color.Red;
```

## ステップ4: ドキュメントを保存する
変更したドキュメントを指定されたディレクトリに保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.SetContentControlColor.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Aspose.Words for .NET を使用してコンテンツ コントロールの色を設定するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内のコンテンツ コントロールの色を正常に設定できました。