---
title: Word 文件中不受限制的可編輯區域
linktitle: Word 文件中不受限制的可編輯區域
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中建立不受限制的可編輯區域。
type: docs
weight: 10
url: /zh-hant/net/document-protection/unrestricted-editable-regions/
---
在本教學中，我們將引導您完成使用 Aspose.Words for .NET 的無限可編輯區域功能的步驟。此功能可讓您在 Word 文件中定義可以不受限制地編輯內容的區域，即使文件的其餘部分是唯讀的也是如此。請依照以下步驟操作：

## 步驟1：載入文件並設定保護

首先載入現有文檔：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

透過設定唯讀保護類型和密碼來保護文檔

## 第二步：建立可編輯區域

首先使用 EditableRangeStart 和 EditableRangeEnd 物件建立可編輯區域：

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
//為我們剛剛建立的 EditableRangeStart 建立一個 EditableRange 物件。
EditableRange editableRange = edRangeStart.EditableRange;

//將某些內容放入可編輯範圍內。
builder.Writeln("Paragraph inside first editable range");

//如果可編輯範圍有開頭和結尾，則它是格式良好的。
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## 步驟 3：在可編輯區域之外新增內容

您可以在可編輯區域之外添加內容，該區域將保持唯讀狀態：

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## 步驟 4：儲存文檔

最後儲存修改後的文件：

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

請務必指定正確的路徑和檔案名稱以儲存具有可編輯區域的文件。

### 使用 Aspose.Words for .NET 的無限可編輯區域的範例原始程式碼

以下是使用 Aspose.Words for .NET 的無限可編輯區域的完整原始程式碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//上傳文檔並將其設定為唯讀。
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

//開始一個可編輯範圍。
EditableRangeStart edRangeStart = builder.StartEditableRange();
//為我們剛剛建立的 EditableRangeStart 建立一個 EditableRange 物件。
EditableRange editableRange = edRangeStart.EditableRange;

//將某些內容放入可編輯範圍內。
builder.Writeln("Paragraph inside first editable range");

//如果可編輯範圍有開頭和結尾，則它是格式良好的。
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
透過執行下列步驟，您可以使用 Aspose.Words for .NET 在 Word 文件中輕鬆建立不受限制的可編輯區域。

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 在 Word 文件中建立不受限制的可編輯區域。透過執行提供的步驟，您可以定義文件中的特定區域，使用者可以在其中自由編輯內容，同時保持文件的其餘部分為唯讀。 Aspose.Words for .NET 提供強大的文件保護和自訂功能，讓您可以控制 Word 文件的編輯功能。

### Word 文件中不受限制的可編輯區域的常見問題解答

#### Q：Aspose.Words for .NET 中的不受限制的可編輯區域是什麼？

答：Aspose.Words for .NET 中的無限制可編輯區域是 Word 文件中可以不受任何限制地編輯內容的區域，即使文件的其餘部分設定為唯讀也是如此。這些區域提供了一種定義文件特定部分的方法，使用者可以在維護整體文件保護的同時修改這些部分。

#### Q：如何使用 Aspose.Words for .NET 建立不受限制的可編輯區域？

答：要使用 Aspose.Words for .NET 在 Word 文件中建立不受限制的可編輯區域，您可以按照以下步驟操作：
1. 使用載入現有文檔`Document`班級。
2. 使用以下命令將文件保護設定為唯讀`Protect`的方法`Document`目的。
3. 使用`DocumentBuilder`類別透過新增建立可編輯範圍`EditableRangeStart`物件和一個`EditableRangeEnd`目的。
4. 使用以下命令新增可編輯範圍內的內容`DocumentBuilder`.
5. 使用以下命令儲存修改後的文檔`Save`的方法`Document`目的。

#### Q：Word 文件中可以有多個不受限制的可編輯區域嗎？

答：是的，Word 文件中可以有多個不受限制的可編輯區域。為了實現這一點，您可以建立多組`EditableRangeStart`和`EditableRangeEnd`物件使用`DocumentBuilder`班級。每組物件將定義一個單獨的可編輯區域，使用者可以在其中不受任何限制地修改內容。

#### Q：我可以將可編輯區域嵌套在一起嗎？

答：不可以，您不能使用 Aspose.Words for .NET 將可編輯區域嵌套在一起。每個可編輯區域由`EditableRangeStart`和`EditableRangeEnd`對應該是獨立的，不能重疊或嵌套在另一個可編輯區域內。不支援嵌套的可編輯區域。

#### Q：我可以取消可編輯區域內文檔的唯讀保護嗎？

答：不可以，您無法刪除可編輯區域內文件的唯讀保護。唯讀保護套用於整個文檔，並且不能在特定的可編輯區域內選擇性地刪除。可編輯區域的目的是允許修改內容，同時保持整個文件唯讀。