---
title: 取得單字的修訂類型
linktitle: 取得單字的修訂類型
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 取得 Word 文件中單字的修訂類型。
type: docs
weight: 10
url: /zh-hant/net/working-with-revisions/get-revision-types/
---

在本逐步指南中，我們將告訴您如何使用 Aspose.Words for .NET 取得 Word 文件中的單字修訂類型。我們將為您提供完整的原始程式碼，並向您展示如何格式化 Markdown 輸出。

## 第 1 步：載入文檔

第一步是上傳包含修訂的文檔。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：逐步瀏覽段落

接下來，我們將瀏覽文件的段落並檢查與每個段落相關的單字修訂類型。

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### 使用 Aspose.Words for .NET 取得修訂類型的範例原始程式碼

以下是使用 Aspose.Words for .NET 取得文件中的修訂類型的完整原始碼：

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 取得 Word 文件中單字修訂的類型。我們按照以下步驟載入文檔，瀏覽段落，並檢查與每個段落相關的單字評論類型。現在，您可以使用 Aspose.Words for .NET 應用這些知識來分析您自己的 Word 文件中的文字評論。

### 取得單字修訂類型的常見問題解答

#### Q：如何在 Aspose.Words for .NET 中上傳文件？

答：使用`Document`用於從文件載入文件的 Aspose.Words for .NET 類別。您可以指定完整的文檔路徑。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q：如何在 Aspose.Words for .NET 中循環瀏覽文件中的段落？

答：使用`Paragraphs`文檔部分的屬性來取得段落的集合。然後，您可以使用循環來循環遍歷每個段落。

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     //在這裡處理每個段落
}
```

#### Q：如何檢查 Aspose.Words for .NET 中的段落是否已被移動（刪除）？

 A：使用段落`IsMoveFromRevision`屬性來檢查它是否已被移動（刪除）。

```csharp
if (paragraph. IsMove

FromRevision)
{
     //該段落已移動（刪除）
}
```

#### Q：如何檢查 Aspose.Words for .NET 中的段落是否已移動（插入）？

 A：使用段落`IsMoveToRevision`屬性來檢查它是否已被移動（插入）。

```csharp
if (paragraph.IsMoveToRevision)
{
     //該段落已被移動（插入）
}
```