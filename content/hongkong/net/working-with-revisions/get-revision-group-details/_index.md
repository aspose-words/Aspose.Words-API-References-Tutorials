---
title: 取得修訂組詳細信息
linktitle: 取得修訂組詳細信息
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 取得 Word 文件中的修訂群組詳細資訊。
type: docs
weight: 10
url: /zh-hant/net/working-with-revisions/get-revision-group-details/
---

在本逐步指南中，我們將向您展示如何使用 Aspose.Words for .NET 取得 Word 文件中一組修訂的詳細資訊。我們將為您提供完整的原始程式碼，並向您展示如何格式化 Markdown 輸出。

## 第 1 步：載入文檔

第一步是上傳包含修訂的文檔。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：瀏覽修訂版本

接下來，我們將循環瀏覽文件中存在的修訂並顯示其詳細信息，例如類型、作者、日期和修訂文本。

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### 使用 Aspose.Words for .NET 取得修訂群組詳細資訊的範例原始程式碼

以下是使用 Aspose.Words for .NET 取得文件中一組修訂的詳細資訊的完整原始程式碼：

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 取得 Word 文件中一組修訂的詳細資訊。透過使用循環和適當的屬性，我們能夠顯示修訂類型、作者、日期和修訂文本等詳細資訊。 Aspose.Words for .NET 提供了許多強大的功能來操作 Word 文檔，包括修訂管理。現在您可以利用這些知識，使用 Aspose.Words for .NET 將修訂群組詳細資訊新增至您自己的 Word 文件。

### 常見問題解答

#### Q：如何將經過修訂的文件載入到 Aspose.Words for .NET 中？

答：使用`Document`Aspose.Words for .NET 類別從包含修訂的檔案載入文件。您可以指定完整的文檔路徑。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q：如何取得 Aspose.Words for .NET 中修訂群組的詳細資訊？

答：使用循環瀏覽文件的修訂版本並存取每個修訂版本的屬性以取得所需的詳細資訊。您可以使用`RevisionType`, `Author`, `DateTime`和`ParentNode`屬性分別取得修訂類型、作者、日期和修訂文本。

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### Q：如何檢查修訂版本是否屬於 Aspose.Words for .NET 中的某個群組？

答：使用`Group`的財產`Revision`對象檢查修訂是否屬於一個群組。如果`Group`財產是`null`，這意味著該修訂不屬於任何群組。

```csharp
if (revision.Group != null)
{
      //該修訂屬於一組
}
else
{
      //該修訂版不屬於任何群組
}
```