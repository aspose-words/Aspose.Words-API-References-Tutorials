---
title: SDT をカスタム XML パーツにバインドする
linktitle: SDT をカスタム XML パーツにバインドする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して SDT をカスタム XML パーツにバインドする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、構造化ドキュメント タグ (SDT) をカスタム XML パーツにバインドする方法を説明します。SDT を使用すると、構造化コンテンツ コントロールを Word ドキュメントに追加できます。また、CustomXmlParts を使用すると、ドキュメントに関連付けられたカスタム XML データを格納することができます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と XML に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントと CustomXmlPart を作成する
新しいインスタンスを作成する`Document`クラスと`CustomXmlPart`カスタムXMLデータを保存します。カスタムXMLは有効なXML形式である必要があります。この例では、単純なXML文字列を使用します。`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## ステップ3: ドキュメントにStructuredDocumentTag (SDT)を追加する
追加`StructuredDocumentTag`コンテンツコントロールとして機能するドキュメントに追加します。`SdtType`として`PlainText`そしてその`MarkupLevel`として`Block`ブロックレベルの SDT を作成します。

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## ステップ4: SDTのXMLマッピングを設定する
SDTを`CustomXmlPart`を使用することにより`SetMapping`方法の`XmlMapping`プロパティを指定します`CustomXmlPart`、目的のXMLノードを見つけるためのXPath式、および必要に応じて名前空間プレフィックスを指定します。この例では、SDTを次のようにマッピングします。`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## ステップ5: ドキュメントを保存する
変更したドキュメントを指定されたディレクトリに保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.BindSDTtoCustomXmlPart.doc」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Aspose.Words for .NET を使用して SD T をカスタム XML パーツにバインドするためのサンプル ソース コード 

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

これで完了です。Aspose.Words for .NET を使用して、Word 文書内の CustomXmlPart に SDT を正常にバインドできました。