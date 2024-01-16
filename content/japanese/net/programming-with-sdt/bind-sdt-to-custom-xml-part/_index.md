---
title: SDT をカスタム XML パーツにバインドする
linktitle: SDT をカスタム XML パーツにバインドする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して SDT をカスタム Xml パーツにバインドする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

このチュートリアルでは、Aspose.Words for .NET を使用して構造化ドキュメント タグ (SDT) をカスタム Xml パーツにバインドする方法を説明します。 SDT を使用すると、構造化コンテンツ コントロールを Word 文書に追加でき、CustomXmlParts を使用すると、文書に関連付けられたカスタム XML データを保存する方法が提供されます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と XML の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントと CustomXmlPart を作成する
の新しいインスタンスを作成します。`Document`クラスと`CustomXmlPart`カスタム XML データを保存します。カスタム XML は有効な XML 形式である必要があります。この例では、単純な XML 文字列を使用します。`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## ステップ 3: StructuredDocumentTag (SDT) をドキュメントに追加する
追加`StructuredDocumentTag`コンテンツ コントロールとして機能するドキュメントに追加します。を指定します`SdtType`として`PlainText`そしてその`MarkupLevel`として`Block`ブロックレベルの SDT を作成します。

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## ステップ 4: SDT の XML マッピングを設定する
SDT を`CustomXmlPart`を使用して`SetMapping`の方法`XmlMapping`財産。を指定します`CustomXmlPart`、目的の XML ノードを見つけるための XPath 式、および必要に応じて名前空間プレフィックス。この例では、SDT を次のようにマッピングします。`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## ステップ 5: ドキュメントを保存する
を使用して、変更したドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.BindSDTtoCustomXmlPart.doc」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Aspose.Words for .NET を使用した Bind Sd Tto Custom Xml Part のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

それでおしまい！ Aspose.Words for .NET を使用して、SDT を Word 文書内の CustomXmlPart に正常にバインドしました。