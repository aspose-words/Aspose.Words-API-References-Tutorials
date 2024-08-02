---
title: 建立映射到自訂 Xml 部件的表重複部分
linktitle: 建立映射到自訂 Xml 部件的表重複部分
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 建立一個表格，其中的重複部分會對應到 Word 文件中的 CustomXmlPart。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---
## 介紹

在本教學中，我們將逐步介紹使用 Aspose.Words for .NET 建立具有重複部分的資料表的過程，該表會對應到自訂 XML 部分。這對於基於結構化資料動態生成文件特別有用。

## 先決條件

在我們開始之前，請確保您具備以下條件：
1. 已安裝 Aspose.Words for .NET 程式庫。您可以從[阿斯普斯網站](https://releases.aspose.com/words/net/).
2. 對 C# 和 XML 有基本了解。

## 導入命名空間

確保在您的專案中包含必要的命名空間：

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Tables;
```

## 步驟1：初始化Document和DocumentBuilder

首先，建立一個新文件並初始化`DocumentBuilder`:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：新增自訂 XML 部分

將自訂 XML 部分新增至文件。此 XML 包含我們想要對應到表格的資料：

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
    "<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
    "<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
    "<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## 第三步：建立表結構

接下來，使用`DocumentBuilder`建立表頭：

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## 第 4 步：建立重複部分

創建一個`StructuredDocumentTag`(SDT) 重複部分並將其對應到 XML 資料：

```csharp
StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## 第 5 步：建立重複部分項目

為重複部分項目建立 SDT 並將其新增至重複部分：

```csharp
StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## 步驟 6：將 XML 資料對應到表格單元格

為標題和作者建立 SDT，將它們對應到 XML 數據，並將它們附加到行中：

```csharp
StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## 步驟7：儲存文檔

最後將文檔儲存到指定目錄：

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

## 結論

透過執行這些步驟，您已使用 Aspose.Words for .NET 成功建立了一個資料表，其中的重複部分會對應到自訂 XML 部分。這允許基於結構化資料生成動態內容，使文件創建更加靈活和強大。

## 常見問題解答

### 什麼是結構化文件標籤 (SDT)？
SDT，也稱為內容控件，是文件中用於包含結構化資料的有界區域。

### 我可以在自訂 XML 部分中使用其他資料類型嗎？
是的，您可以使用任何資料類型建立自訂 XML 部分並相應地對應它們。

### 如何為重複部分添加更多行？
重複部分自動複製映射 XML 路徑中每個項目的行結構。