---
title: カスタム XML パーツにマップされたテーブル繰り返しセクションの作成
linktitle: カスタム XML パーツにマップされたテーブル繰り返しセクションの作成
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の CustomXmlPart にマップされた繰り返しセクションを含むテーブルを作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内のカスタム Xml パーツにマップされた繰り返しセクションを含むテーブルを作成する方法を説明します。繰り返しセクションを使用すると、カスタム XML パーツに保存されている XML データに基づいて行を動的に追加できます。

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

## ステップ 3: カスタム XML データを CustomXmlPart に追加する
を作成します`CustomXmlPart`カスタム XML データをそれに追加します。この例では、書籍のコレクションとそのタイトルと著者を表す XML 文字列を作成します。

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## ステップ 4: テーブルとテーブル構造を作成する
を使用してテーブルの作成を開始します。`StartTable`の方法`DocumentBuilder` 。を使用して表のセルとコンテンツを追加します。`InsertCell`そして`Write`方法。

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
を作成します`StructuredDocumentTag`と`SdtType.RepeatingSection`繰り返し部分を表します。を使用して、繰り返しセクションの XML マッピングを設定します。`SetMapping`の方法`XmlMapping`財産。この例では、繰り返しセクションを次のようにマッピングします。`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## ステップ 6: 繰り返しセクション項目を作成し、セルを追加する
を作成します`StructuredDocumentTag`と`SdtType.RepeatingSectionItem`繰り返しセクション項目を表します。それを繰り返しセクションに子として追加します。

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

を作成します`Row`繰り返しセクション内の各項目を表し、それを繰り返しセクションの項目に追加します。

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## ステップ 7: 繰り返しセクション内にコンテンツ コントロールを追加する
作成する`StructuredDocumentTag`オブジェクト`SdtType.PlainText`

 タイトルと作成者のコンテンツ コントロールを表します。を使用して、各コンテンツ コントロールの XML マッピングを設定します。`SetMapping`の方法`XmlMapping`財産。この例では、タイトル コントロールを次のようにマッピングします。`/books[1]/book[1]/title[1]`そして作者がコントロールするのは、`/books[1]/book[1]/author[1]`.

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

## ステップ 8: ドキュメントを保存する
を使用して、変更したドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Aspose.Words for .NET を使用してカスタム XML パーツにマップされたテーブル繰り返しセクションを作成するためのサンプル ソース コード 

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

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内の CustomXmlPart にマップされた繰り返しセクションを持つテーブルが正常に作成されました。