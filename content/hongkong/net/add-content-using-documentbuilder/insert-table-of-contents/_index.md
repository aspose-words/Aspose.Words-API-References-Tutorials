---
title: 在 Word 文件中插入目錄
linktitle: 在 Word 文件中插入目錄
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中插入目錄。
type: docs
weight: 10
url: /zh-hant/net/add-content-using-documentbuilder/insert-table-of-contents/
---
在這個綜合教學中，您將學習如何使用 Aspose.Words for .NET 將目錄插入到 Word 文件中。我們將引導您完成整個過程，並為您提供必要的 C# 程式碼片段。在本指南結束時，您將能夠產生具有適當標題和頁碼的目錄。

## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Aspose.Words for .NET 程式庫安裝在您的系統上。

## 第 1 步：建立新文件和 DocumentBuilder
首先，使用 Document 類別建立一個新文件並初始化 DocumentBuilder 物件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入目錄
接下來，使用 DocumentBuilder 類別的 InsertTableOfContents 方法插入目錄。在方法中指定所需的格式選項：

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## 第三步：新增文件內容
插入目錄後，新增實際的文檔內容。使用 StyleIdentifier 設定適當的標題樣式：

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## 第 4 步：更新目錄
新插入的目錄最初是空的。若要填入它，請更新文件中的欄位：

```csharp
doc.UpdateFields();
```

## 第 5 步：儲存文檔
插入目錄並更新欄位後，使用 Document 類別的 Save 方法將文件儲存到文件中：

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### 使用 Aspose.Words for .NET 插入目錄的範例原始碼
以下是使用 Aspose.Words for .NET 插入目錄的完整原始碼：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

//使用 Document 物件初始化 DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入目錄a
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

//從第二頁開始實際文檔內容。
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


//新插入的目錄最初是空的。
//需要透過更新文件中的欄位來填入它。
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## 結論

恭喜！您已成功學習如何使用 Aspose.Words for .NET 將目錄插入 Word 文件中。透過遵循此逐步指南並利用提供的原始程式碼，現在您可以為文件產生包含適當標題和頁碼的目錄。

### 在Word文件中插入目錄的常見問題解答

#### Q：我可以自訂目錄的外觀嗎？

答：是的，您可以透過修改在中指定的格式選項來自訂目錄的外觀。`InsertTableOfContents`方法。這些參數可讓您控制頁碼、縮排和其他樣式。

#### Q：如果我想在目錄中包含特定標題等級該怎麼辦？

答：您可以透過調整範圍內的值來指定要包含在目錄中的所需標題等級。`InsertTableOfContents`方法。例如，使用`"\\o \"1-3\""`將包括標題等級 1 至 3。

#### Q：如果我更改文件內容，可以自動更新目錄嗎？

答：是的，您可以透過呼叫自動更新目錄`UpdateFields`文檔上的方法。這將確保對文件內容所做的任何更改（例如新增或刪除標題）都會反映在目錄中。

#### Q：如何對目錄中的標題層級設定不同的樣式？

答：您可以透過為每個標題等級使用不同的段落樣式來設定不同的標題等級樣式。透過分配不同的`StyleIdentifier`值對`ParagraphFormat`的`DocumentBuilder`，您可以為每個標題層級建立不同的樣式。

#### Q：是否可以為目錄中的標題新增其他格式？

答：是的，您可以在目錄中的標題中新增其他格式，例如字體樣式、顏色或其他屬性。透過調整`Font`的屬性`DocumentBuilder`，您可以將自訂格式套用至標題。