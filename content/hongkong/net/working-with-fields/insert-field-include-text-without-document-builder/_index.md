---
title: 插入欄位包括文字而不使用文件產生器
linktitle: 在沒有文件產生器的情況下插入 FieldIncludeText
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中插入 FieldIncludeText 欄位。
type: docs
weight: 10
url: /zh-hant/net/working-with-fields/insert-field-include-text-without-document-builder/
---

以下是解釋下面 C# 原始程式碼的逐步指南，該程式碼使用 Aspose.Words for .NET 的「插入 FieldIncludeText 欄位」功能。確保仔細執行每個步驟以獲得所需的結果。

## 第 1 步：文檔目錄設置

在提供的程式碼中，您必須指定文件的目錄。將值“YOUR DOCUMENT DIRECTORY”替換為文檔目錄的相應路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：建立文件和段落

我們首先建立一個新文件並初始化一個段落。

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 步驟 3：插入 FieldIncludeText 字段

我們使用`AppendField()`方法將 FieldIncludeText 欄位插入到段落中。

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

然後，我們透過指定書籤的名稱和來源檔案的名稱來配置 FieldIncludeText 欄位的屬性。

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

接下來，我們將該段落加入到文件正文中。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

最後，我們調用`Update()`更新字段的方法。

```csharp
fieldIncludeText.Update();
```

### 使用 Aspose.Words for .NET 插入 FieldIncludeText 欄位的原始碼範例

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立文件和段落。
Document doc = new Document();
Paragraph para = new Paragraph(doc);

//插入 FieldIncludeText 欄位。
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

在此範例中，我們建立了一個新文檔，初始化了一個段落，插入了一個指定書籤名稱和原始檔案名稱的 FieldIncludeTexten，並使用指定的文件名稱儲存了文檔。

我們關於使用 Aspose.Words for .NET 的「插入 FieldIncludeText」功能的指南到此結束。

### 常見問題解答

#### Q：如何在 Aspose.Words for .NET 中指定文字包含欄位的來源檔案？

答：要指定 Aspose.Words for .NET 中文字包含欄位的來源文件，您可以使用`FieldIncludeText.SourceFullName`屬性設定來源檔案的完整路徑。確保來源文件可存取並且包含要包含在文字包含欄位中的內容。

#### Q：我可以使用 Aspose.Words for .NET 在文字包含欄位中包含巨集中的文字嗎？

答：是的，您可以使用 Aspose.Words for .NET 將巨集中的文字包含在文字包含欄位中。您可以使用`FieldIncludeText.IncludeText`屬性來指定其內容應包含在欄位中的巨集的名稱。

#### Q：在沒有文件產生器的情況下插入文字包含欄位是否會影響 Aspose.Words for .NET 的 Word 文件結構？

答：在沒有文件產生器的情況下插入文字包含欄位不會直接影響 Word 文件的結構。但是，它向文檔內容添加了一個新的字段元素。您可以根據需要透過新增、刪除或修改現有元素來操作文件結構。

#### Q：我可以使用 Aspose.Words for .NET 自訂 Word 文件中文字包含欄位的外觀嗎？

答：文字包含欄位不會直接自訂其在 Word 文件中的外觀。但是，您可以使用段落屬性、字體屬性和 Aspose.Words for .NET 中提供的其他格式物件來格式化包含的文字。