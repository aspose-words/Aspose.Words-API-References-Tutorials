---
title: 構造化文書のタグ範囲 Xml マッピングの開始
linktitle: 構造化文書のタグ範囲 Xml マッピングの開始
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書で開始される構造化文書タグ範囲の XML マッピングを設定する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内で始まる構造化文書タグ範囲の XML マッピングを設定する方法について説明します。 XML マッピングを使用すると、コンテンツ コントロール内で XML データ ソースの特定の部分を表示できます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントが置かれているディレクトリへの実際のパスを置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをロードして XML パーツを作成する
を使用して Word 文書をロードします。`Document`コンストラクターを使用して、ドキュメントへのパスをパラメーターとして渡します。構造化文書タグ内に表示するデータを含む XML パーツを作成します。

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## ステップ 3: 構造化文書タグの XML マッピングを設定する
文書から始まる構造化文書のタグ範囲を取得します。次に、構造化文書タグの XML マッピングを設定し、XPath 式を使用してカスタム XML 部分の特定の部分を表示します。

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## ステップ 4: ドキュメントを保存する
を使用して、変更したドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### 構造化文書タグ範囲のソース コード例 Aspose.Words for .NET を使用した Xml マッピングの開始 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	//データを含む XML パーツを構築し、それをドキュメントの CustomXmlPart コレクションに追加します。
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	//ドキュメント内の CustomXmlPart のコンテンツを表示する StructuredDocumentTag を作成します。
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// StructuredDocumentTag のマッピングを設定すると、
	// XPath が指す CustomXmlPart の一部のみが表示されます。
	//この XPath は、CustomXmlPart の最初の "<root>" 要素の 2 番目の "<text>" 要素の内容を指します。
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内の構造化文書タグ範囲開始の XML マッピングが正常に設定されました。