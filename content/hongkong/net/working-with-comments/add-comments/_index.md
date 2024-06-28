---
title: 新增評論
linktitle: 新增評論
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中新增註解。
type: docs
weight: 10
url: /zh-hant/net/working-with-comments/add-comments/
---

在這個綜合教學中，您將學習如何使用 Aspose.Words for .NET 在 Word 文件中新增註解。我們將引導您完成整個過程，並為您提供必要的 C# 程式碼片段。在本指南結束時，您將能夠在文件中插入註釋並自訂其內容。

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

## 第 2 步：為文件新增內容
接下來，使用 DocumentBuilder 物件將所需的內容新增到文件中。在此範例中，我們添加一些文字：

```csharp
builder.Write("Some text is added.");
```

## 第 3 步：建立評論並添加內容
若要新增評論，請建立 Comment 類別的實例，並傳遞 Document 物件、作者姓名、作者姓名縮寫和當前日期：

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

接下來，將註釋附加到當前段落：

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

在評論中添加內容，例如段落和文字：

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## 步驟 4：儲存文檔
新增註解及其內容後，使用 Document 類別的 Save 方法將文件儲存到文件中：

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## 使用 Aspose.Words for .NET 新增註解的範例原始程式碼
以下是使用 Aspose.Words for .NET 新增註解的完整原始碼：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## 結論
恭喜！您已成功學習如何使用 Aspose.Words for .NET 將註解新增至 Word 文件。透過遵循逐步指南並利用提供的原始程式碼，現在您可以在文件中插入註釋並自訂其內容。

註釋對於協作、提供附加資訊或在文件中做筆記非常有用。嘗試不同的作者姓名、縮寫和評論內容，以滿足您的特定要求。

### 常見問題解答

#### Q：如何在 Aspose.Words for .NET 文件中新增註解？

答：要在 Aspose.Words for .NET 文件中新增註釋，您需要按照教學中提到的步驟操作。

#### Q：我可以在 Aspose.Words for .NET 中設定註解文字的格式嗎？

答：是的，您可以使用可用的格式屬性在 Aspose.Words for .NET 中設定註解文字的格式。

#### Q：如何檢索文件中的所有註解？

答：您可以使用以下命令檢索文件中出現的所有註釋`Document.Comments`財產。

#### Q：我可以刪除 Aspose.Words for .NET 中的特定評論嗎？

答：是的，您可以使用 Aspose.Words for .NET 刪除特定註釋`Comment.Remove`方法。

#### Q：如何修改 Aspose.Words for .NET 中現有註解的文字？

答：要修改 Aspose.Words for .NET 中現有註解的文本，您可以存取`Comment.Text`對應的屬性`Comment`反對並根據需要修改文本。