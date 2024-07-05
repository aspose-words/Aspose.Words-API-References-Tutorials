---
title: カスタム XML パーツにマップされたテーブル繰り返しセクションの作成
linktitle: カスタム XML パーツにマップされたテーブル繰り返しセクションの作成
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の CustomXmlPart にマップされた繰り返しセクションを含むテーブルを作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内のカスタム XML パーツにマップされた繰り返しセクションを持つテーブルを作成する方法を説明します。繰り返しセクションを使用すると、カスタム XML パーツに保存されている XML データに基づいて行を動的に追加できます。

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

## ステップ 3: CustomXmlPart にカスタム XML データを追加する
作成する`CustomXmlPart`これにカスタム XML データを追加します。この例では、タイトルと著者を含む書籍のコレクションを表す XML 文字列を作成します。

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## ステップ4: テーブルとテーブル構造を作成する
テーブルの作成を開始するには、`StartTable`方法の`DocumentBuilder` . 表のセルとコンテンツを追加するには、`InsertCell`そして`Write`方法。

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## ステップ 5: カスタム XML にマップされた繰り返しセクションを作成する
作成する`StructuredDocumentTag`と`SdtType.RepeatingSection`繰り返しセクションを表すために使用します。繰り返しセクションのXMLマッピングを設定するには、`SetMapping`方法の`XmlMapping`プロパティ。この例では、繰り返しセクションを`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## ステップ6: 繰り返しセクションアイテムを作成し、セルを追加する
作成する`StructuredDocumentTag`と`SdtType.RepeatingSectionItem`繰り返しセクション項目を表します。繰り返しセクションの子として追加します。

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

作成する`Row`繰り返しセクション内の各項目を表し、それを繰り返しセクション項目に追加します。

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## ステップ 7: 繰り返しセクション内にコンテンツ コントロールを追加する
作成する`StructuredDocumentTag`オブジェクト`SdtType.PlainText`

 タイトルと著者のコンテンツコントロールを表します。各コンテンツコントロールのXMLマッピングを設定するには、`SetMapping`方法の`XmlMapping`プロパティ。この例では、タイトルコントロールを`/books[1]/book[1]/title[1]`そして著者は`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## ステップ8: ドキュメントを保存する
変更したドキュメントを指定されたディレクトリに保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Aspose.Words for .NET を使用してカスタム XML パーツにマップされたテーブルの繰り返しセクションを作成するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内の CustomXmlPart にマップされた繰り返しセクションを含むテーブルを正常に作成できました。