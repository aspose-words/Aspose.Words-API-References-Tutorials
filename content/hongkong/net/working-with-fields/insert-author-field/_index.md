---
title: 插入作者字段
linktitle: 插入作者字段
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中插入作者欄位。指定作者姓名以個性化您的文件。
type: docs
weight: 10
url: /zh-hant/net/working-with-fields/insert-author-field/
---


以下是解釋下面 C# 原始程式碼的逐步指南，該程式碼使用 Aspose.Words for .NET 的「插入作者欄位」功能。確保仔細執行每個步驟以獲得所需的結果。

## 第 1 步：文檔目錄設置

在提供的程式碼中，您必須指定文件的目錄。將值“YOUR DOCUMENT DIRECTORY”替換為文檔目錄的相應路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：建立文件和段落

我們首先建立一個新文件並獲取第一段。

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 第 3 步：插入作者字段

我們使用`AppendField()`方法將 AUTHOR 欄位插入到段落中。

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

然後我們配置該欄位的`AuthorName`屬性來指定作者姓名。

```csharp
field. AuthorName = "Test1";
```

最後，我們調用`Update()`更新字段的方法。

```csharp
field. Update();
```

### 使用 Aspose.Words for .NET 插入 AUTHOR 欄位的原始碼範例

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文檔建立。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//插入作者欄位。
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

在此範例中，我們建立了一個新文檔，插入了 AUTHOR 字段，配置了作者姓名，並使用指定的文件名稱儲存了文檔。

我們關於使用 Aspose.Words for .NET 的「插入作者欄位」功能的指南到此結束。

### 常見問題解答

#### Q：Aspose.Words 中的作者欄位是什麼？

答：Aspose.Words 中的作者字段是一個特殊字段，可自動在 Word 文件中插入和更新作者姓名。它通常用於指示誰創建或修改了文件。

#### Q：如何使用 Aspose.Words 更新 Word 文件中的作者欄位？

答：Word 文件中的作者欄位可以更新以反映目前作者的姓名。為此，您可以使用 Document 類別中提供的 UpdateFields 方法。此方法將更新文件中的所有字段，包括作者字段。

#### Q：Word文件中作者欄位的格式可以自訂嗎？

答：是的，可以自訂Word文件中作者欄位的格式。預設情況下，作者欄位僅顯示作者姓名。但是，您可以使用 Aspose.Words 中提供的格式選項來新增其他信息，例如修改日期和時間。

#### Q：作者欄位對作者姓名的後續更改是否敏感？

答：是的，作者欄位對作者姓名的後續變更很敏感。如果您變更文件屬性中的作者姓名，則在更新文件欄位時，作者欄位將自動更新為新名稱。