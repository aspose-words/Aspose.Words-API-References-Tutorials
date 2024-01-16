---
title: 建立映射到自訂 Xml 部件的表重複部分
linktitle: 建立映射到自訂 Xml 部件的表重複部分
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 建立一個表格，其中的重複部分會對應到 Word 文件中的 CustomXmlPart。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

本教學課程示範如何使用 Aspose.Words for .NET 建立一個資料表，其中的重複部分對應到 Word 文件中的自訂 Xml 元件。重複部分可讓您根據自訂 Xml 元件中儲存的 XML 資料動態新增行。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與要儲存文件的目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立文件和 DocumentBuilder
建立一個新實例`Document`類別和一個`DocumentBuilder`建構文檔的內容。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 3：將自訂 XML 資料新增至 CustomXmlPart
創建一個`CustomXmlPart`並在其中新增自訂 XML 資料。在此範例中，我們建立一個 XML 字串，表示包含標題和作者的書籍集合。

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## 第四步：建立表格和表格結構
開始使用建立表`StartTable`的方法`DocumentBuilder`。使用以下命令新增表格儲存格和內容`InsertCell`和`Write`方法。

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## 步驟 5：建立對應到自訂 XML 的重複部分
創建一個`StructuredDocumentTag`和`SdtType.RepeatingSection`來表示重複部分。使用以下命令設定重複部分的 XML 映射`SetMapping`的方法`XmlMapping`財產。在此範例中，我們將重複部分映射到`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## 第 6 步：建立重複部分項目並新增儲存格
創建一個`StructuredDocumentTag`和`SdtType.RepeatingSectionItem`代表重複節項。將其作為子項附加到重複部分。

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

創建一個`Row`表示重複部分中的每個項目並將其附加到重複部分項目。

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## 步驟 7：在重複部分新增內容控件
創造`StructuredDocumentTag`對象與`SdtType.PlainText`

 代表標題和作者內容控制項。使用以下命令為每個內容控制項設定 XML 映射`SetMapping`的方法`XmlMapping`財產。在此範例中，我們將標題控制項對應到`/books[1]/book[1]/title[1]`和作者控制`/books[1]/book[1]/author[1]`.

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

## 第 8 步：儲存文檔
使用指令將修改後的文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx」。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### 使用 Aspose.Words for .NET 建立對應到自訂 Xml 元件的資料表重複部分的範例原始碼 

```csharp
	//文檔目錄的路徑
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

就是這樣！您已使用 Aspose.Words for .NET 成功建立了一個資料表，其中的重複部分會對應到 Word 文件中的 CustomXmlPart。