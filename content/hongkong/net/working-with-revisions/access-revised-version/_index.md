---
title: 存取修訂版本
linktitle: 存取修訂版本
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 存取 Word 文件的修訂版本。
type: docs
weight: 10
url: /zh-hant/net/working-with-revisions/access-revised-version/
---

在本逐步指南中，我們將向您展示如何使用 Aspose.Words for .NET 存取 Word 文件的修訂版本。我們將為您提供完整的原始程式碼，並向您展示如何格式化 Markdown 輸出。

## 第 1 步：載入文檔

第一步是上傳包含修訂的文檔。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## 步驟2：存取修改後的版本

我們現在將討論該文件的修訂版本。

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## 第 3 步：瀏覽修訂版本

接下來，我們將循環瀏覽文件中存在的修訂並顯示清單項目段落的特定資訊。

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### 使用 Aspose.Words for .NET 存取修訂版本的範例原始程式碼

以下是使用 Aspose.Words for .NET 存取文件修訂版本的完整原始碼：

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

//切換到文件的修訂版本。
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 存取 Word 文件的修訂版本。透過載入文件、導覽至修訂版本並瀏覽修訂版本，我們能夠取得清單項目段落的具體資訊。 Aspose.Words for .NET 提供了用於操作 Word 文件的強大功能，包括存取評論。現在您可以利用這些知識，使用 Aspose.Words for .NET 存取您自己的 Word 文件的修訂版本。

### 常見問題解答

#### Q：如何將經過修訂的文件載入到 Aspose.Words for .NET 中？

答：使用`Document`Aspose.Words for .NET 類別從包含修訂的檔案載入文件。您可以指定完整的文檔路徑。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q：如何在 Aspose.Words for .NET 中存取文件的修訂版本？

答：使用`RevisionsView`的財產`Document`對象存取文件的修訂版本。您可以設定的值`RevisionsView`財產給`RevisionsView.Final`顯示沒有修改的最終版本。

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### Q：如何在 Aspose.Words for .NET 中瀏覽文件修訂版本？

答：使用一個`foreach`循環以迭代文檔中存在的修訂。您可以使用`Revisions`的財產`Document`物件取得文件所有修訂的集合。

```csharp
foreach (Revision revision in doc.Revisions)
{
     //在這裡處理每個修訂
}
```

#### Q：如何檢查一個段落是否是 Aspose.Words for .NET 中的清單項目？

答：使用`IsListItem`的財產`Paragraph`物件檢查段落是否為清單項目。這`IsListItem`財產回報`true`如果該段落是列表項，否則返回`false`.

```csharp
if (paragraph.IsListItem)
{
     //該段落是一個列表項
}
else
{
     //該段落不是列表項
}
```