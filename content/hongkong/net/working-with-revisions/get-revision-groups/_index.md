---
title: 取得修訂組
linktitle: 取得修訂組
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 取得 Word 文件中的修訂群組。
type: docs
weight: 10
url: /zh-hant/net/working-with-revisions/get-revision-groups/
---

在本逐步指南中，我們將告訴您如何使用 Aspose.Words for .NET 取得 Word 文件中的修訂群組。我們將為您提供完整的原始程式碼，並向您展示如何格式化 Markdown 輸出。

## 第 1 步：載入文檔

第一步是上傳包含修訂的文檔。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：瀏覽修訂組

接下來，我們將循環瀏覽文件中存在的修訂組並顯示其詳細信息，例如作者、修訂類型和修訂文本。

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### 使用 Aspose.Words for .NET 取得修訂群組的範例原始程式碼

以下是使用 Aspose.Words for .NET 取得文件中的修訂群組的完整原始碼：

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 取得 Word 文件中的修訂群組。我們按照以下步驟載入文件並瀏覽審閱群組，顯示作者和審閱類型等詳細資訊。現在您可以套用這些知識，使用 Aspose.Words for .NET 來分析您自己的 Word 文件的修訂。

### 常見問題解答

#### Q：如何在 Aspose.Words for .NET 中上傳文件？

答：使用`Document`用於從文件載入文件的 Aspose.Words for .NET 類別。您可以指定完整的文檔路徑。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q：如何在 Aspose.Words for .NET 中瀏覽文件中的修訂群組？

答：使用`Groups`文檔的屬性`Revisions`對象取得修訂組的集合。然後，您可以使用循環來遍歷每個審閱群組。

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     //在此處理每個審核組
}
```

#### Q：如何在 Aspose.Words for .NET 中取得審查群組的作者？

答：使用`Author`的財產`RevisionGroup`對象取得修訂組的作者。

```csharp
string author = group.Author;
```

#### Q：如何在 Aspose.Words for .NET 中取得修訂群組的修訂類型？

答：使用`RevisionType`的財產`RevisionGroup`物件來取得群組的修訂類型。

```csharp
string revisionType = group.RevisionType;
```