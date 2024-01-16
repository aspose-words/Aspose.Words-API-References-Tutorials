---
title: 移至 Word 文件中的部分
linktitle: 移至 Word 文件中的部分
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 的 Word 文件中的「移至節」功能操作 Word 文件中的節和段落的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/add-content-using-documentbuilder/move-to-section/
---
在此範例中，我們將使用提供的 C# 原始程式碼逐步引導您了解如何使用 Aspose.Words for .NET 的「移至 Word 文件中的部分」功能。此功能可讓您導覽和操作 Word 文件中的不同部分。請按照以下步驟將此功能整合到您的應用程式中。

## 步驟 1：建立一個新文件並新增一個部分

首先，我們需要建立一個新文件並向其中添加一個部分。使用以下程式碼完成此步驟：

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

此程式碼會建立一個新的空文檔並在該文件中新增一個部分。

## 步驟 2：將 DocumentBuilder 移至第二部分並新增文本

接下來，我們需要將 DocumentBuilder 移到文件的第二部分並在那裡添加一些文字。使用以下程式碼來執行此步驟：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

此程式碼從現有文件建立一個 DocumentBuilder，然後將遊標從 DocumentBuilder 移至文件的第二部分。最後，它將指定的文字新增到此部分。

## 步驟 3：載入包含現有段落的文檔

如果您想使用包含段落的現有文檔，可以使用下列程式碼載入該文檔：

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

此程式碼載入指定文件（取代“MyDir +”Paragraphs.docx””與文件的實際路徑）並存取文件第一部分中的段落集合。線路`Assert.AreEqual(22, paragraphs.Count);`檢查文件是否包含 22 個段落。

## 步驟 4：為文件建立 DocumentBuilder

您可以使用位置索引建立指向特定段落的 DocumentBuilder 遊標。

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## 第五步：將遊標移到特定段落


您可以使用位置索引將 DocumentBuilder 遊標移至特定段落。操作方法如下：

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

此程式碼將 DocumentBuilder 的遊標移到第二部分的第三段（索引 2 處的段落）和位置 10。然後，它會新增一個包含一些文字的新段落，並檢查遊標是否正確定位在該新段落上。

### 使用 Aspose.Words for .NET 的「移動到移動到部分」的範例原始程式碼

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

//將 DocumentBuilder 移至第二部分並新增文字。
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

//建立帶有段落的文檔。
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

//當我們為文件建立DocumentBuilder時，它的遊標預設位於文件的最開頭，
// DocumentBuilder 新增的任何內容都會新增到文件的前面。
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//您可以將遊標移到段落中的任何位置。
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

就這樣 ！現在您已經了解如何使用提供的原始程式碼來使用 Aspose.Words for .NET 的移至部分功能。現在您可以將此功能整合到您自己的應用程式中，並動態操作 Word 文件的部分和段落。

## 結論

在這個範例中，我們探索了 Aspose.Words for .NET 的「移至部分」功能。我們學習如何建立新文件、新增部分以及使用 DocumentBuilder 類別導覽至 Word 文件中的特定部分和段落。此功能為開發人員提供了強大的工具，可以使用 Aspose.Words for .NET 以程式設計方式操作 Word 文件的內容和結構。

### Word 文件中移動到部分的常見問題解答

#### Q：Aspose.Words for .NET 中「移至部分」功能的用途是什麼？

答：Aspose.Words for .NET 中的「移至部分」功能可讓開發人員以程式設計方式導覽至並操作 Word 文件中的不同部分。它提供了在文件的特定部分插入、修改或刪除內容的能力。

#### Q：如何將 DocumentBuilder 移至 Word 文件中的特定部分？

答：要將 DocumentBuilder 移至 Word 文件中的特定部分，可以使用 DocumentBuilder 類別的 MoveToSection 方法。此方法將目標節的索引作為參數，並將遊標置於該節的開頭。

#### Q：使用「移至部分」功能移至特定部分後，我可以新增或修改內容嗎？

答：是的，一旦使用 MoveToSection 將 DocumentBuilder 定位到所需的部分，您就可以使用 DocumentBuilder 類別的各種方法（例如 Writeln、Write 或 InsertHtml）來新增或修改該部分的內容。

#### Q：如何使用「移至節」功能處理文件中的現有段落？

答：您可以使用 Document 建構函式載入包含段落的現有文檔，然後使用 FirstSection.Body.Paragraphs 屬性從所需部分存取段落集合。

#### Q：我可以使用「移至節」功能將 DocumentBuilder 遊標移至節中的特定段落嗎？

答：是的，您可以使用 MoveToParagraph 方法將 DocumentBuilder 遊標移到節中的特定段落。此方法以目標段落的索引和段落內的字元位置（偏移量）作為參數。