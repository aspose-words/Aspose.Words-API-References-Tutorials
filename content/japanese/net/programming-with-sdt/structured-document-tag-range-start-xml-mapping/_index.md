---
title: 構造化ドキュメントのタグ範囲の開始 XML マッピング
linktitle: 構造化ドキュメントのタグ範囲の開始 XML マッピング
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の構造化文書タグ範囲開始の XML マッピングを設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の構造化文書タグ範囲開始の XML マッピングを設定する方法について説明します。XML マッピングを使用すると、コンテンツ コントロール内に XML データ ソースの特定の部分を表示できます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントが配置されているディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントを読み込み、XML パーツを作成する
Word文書を読み込むには、`Document`コンストラクターを使用して、ドキュメントへのパスをパラメーターとして渡します。構造化ドキュメント タグ内に表示するデータを含む XML パーツを作成します。

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## ステップ3: 構造化ドキュメントタグのXMLマッピングを設定する
ドキュメントから構造化ドキュメント タグ範囲の開始を取得します。次に、XPath 式を使用してカスタム XML パーツの特定の部分を表示するように、構造化ドキュメント タグの XML マッピングを設定します。

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## ステップ4: ドキュメントを保存する
変更したドキュメントを指定されたディレクトリに保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Aspose.Words for .NET を使用した構造化ドキュメント タグ範囲開始 XML マッピングのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	//データを含む XML パーツを構築し、それをドキュメントの CustomXmlPart コレクションに追加します。
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	//ドキュメント内の CustomXmlPart の内容を表示する StructuredDocumentTag を作成します。
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// StructuredDocumentTagのマッピングを設定すると、
	// XPath が指す CustomXmlPart の一部のみが表示されます。
	//この XPath は、CustomXmlPart の最初の "<root>" 要素の 2 番目の "<text>" 要素の内容を指します。
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内の構造化文書タグ範囲開始の XML マッピングを正常に設定しました。