---
title: 結構化文檔標記範圍起始 Xml 映射
linktitle: 結構化文檔標記範圍起始 Xml 映射
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中為結構化文件標記範圍設定 XML 對應。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

本教學課程說明如何使用 Aspose.Words for .NET 在 Word 文件中設定結構化文件標記範圍的 XML 對應。 XML 對應可讓您在內容控制項中顯示 XML 資料來源的特定部分。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文件所在目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 2： 載入文件並建立 XML 部件
使用以下命令載入 Word 文檔`Document`建構函數，將文檔的路徑作為參數傳遞。建立一個 XML 元件，其中包含要在結構化文件標記中顯示的資料。

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## 步驟 3：為結構化文件標籤設定 XML 映射
檢索從文件開始的結構化文件標籤範圍。然後，設定結構化文件標記的 XML 映射，以使用 XPath 表達式顯示自訂 XML 部分的特定部分。

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## 步驟 4：儲存文檔
使用指令將修改後的文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx」。

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### 使用 Aspose.Words for .NET 進行結構化文件標記範圍開始 Xml 映射的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	//建構一個包含資料的 XML 元件並將其新增至文件的 CustomXmlPart 集合中。
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	//建立一個 StructuredDocumentTag，它將在文件中顯示 CustomXmlPart 的內容。
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	//如果我們為 StructuredDocumentTag 設定映射，
	//它只會顯示 XPath 指向的 CustomXmlPart 的一部分。
	//此 XPath 將指向 CustomXmlPart 的第一個「<root>」元素的內容第二個「<text>」元素。
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 在 Word 文件中成功設定了結構化文件標記範圍起始的 XML 對應。