---
title: 將 SDT 綁定到自訂 Xml 部件
linktitle: 將 SDT 綁定到自訂 Xml 部件
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將 SDT 綁定到自訂 Xml 元件。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

本教學課程示範如何使用 Aspose.Words for .NET 將結構化文件標籤 (SDT) 綁定到自訂 Xml 元件。 SDT 可讓您為 Word 文件新增結構化內容控件，而 CustomXmlParts 提供一種儲存與文件關聯的自訂 XML 資料的方法。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 XML 的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與要儲存文件的目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 2：建立文件和 CustomXmlPart
建立一個新實例`Document`類別和一個`CustomXmlPart`儲存自訂 XML 資料。自訂 XML 應採用有效的 XML 格式。在此範例中，我們使用一個簡單的 XML 字串`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## 步驟 3：將 StructuredDocumentTag (SDT) 新增至文檔
添加一個`StructuredDocumentTag`到文件中作為內容控制項。指定`SdtType`作為`PlainText`和`MarkupLevel`作為`Block`建立區塊級 SDT。

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## 步驟 4：設定 SDT 的 XML 映射
將 SDT 映射到`CustomXmlPart`透過使用`SetMapping`的方法`XmlMapping`財產。指定`CustomXmlPart`、用於定位所需 XML 節點的 XPath 表達式，以及命名空間前綴（如果需要）。在此範例中，我們將 SDT 對應到`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## 第 5 步：儲存文檔
使用指令將修改後的文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithSdt.BindSDTtoCustomXmlPart.doc」。

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### 使用 Aspose.Words for .NET 將 Sd T 綁定到自訂 Xml 元件的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

就是這樣！您已使用 Aspose.Words for .NET 成功將 SDT 綁定到 Word 文件中的 CustomXmlPart。