---
title: 業主文件
linktitle: 業主文件
second_title: Aspose.Words 文件處理 API
description: 了解如何在 Aspose.Words for .NET 中使用所有者文件。
type: docs
weight: 10
url: /zh-hant/net/working-with-node/owner-document/
---

以下是解釋 C# 原始程式碼的逐步指南，說明如何透過 Aspose.Words for .NET 使用專有文件功能。

## 第 1 步：導入必要的參考文獻
在開始之前，請確保您已將使用 Aspose.Words for .NET 所需的參考匯入到您的專案中。這包括匯入 Aspose.Words 庫並將所需的命名空間新增至來源檔案。

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## 第 2 步：建立一個新文檔
在此步驟中，我們將使用以下命令建立一個新文檔`Document`班級。

```csharp
Document doc = new Document();
```

## 步驟 3：使用所有者文件建立節點
當建立任何類型的新節點時，必須將文件傳遞到建構函數中。在此範例中，我們使用文件建立一個新的段落節點`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## 步驟4：檢查父節點和所有者文檔
現在我們已經建立了段落節點，我們可以檢查它是否有父節點以及所屬文件是否與`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## 步驟5：使用文件資料修改節點屬性
節點和文件之間的關係允許存取和修改引用特定於文件的資料的屬性，例如樣式或清單。在此範例中，我們將段落樣式名稱設定為「標題 1」。

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## 步驟 6：將段落加入到文件中
現在我們可以將段落節點新增到文件的主要部分。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 步驟7：新增後驗證父節點
將段落新增到文件後，我們再次檢查它現在是否有父節點。

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### 使用 Aspose.Words for .NET 的所有者文件的範例原始程式碼

```csharp
Document doc = new Document();

//建立任何類型的新節點都需要將文件傳遞到建構函數中。
Paragraph para = new Paragraph(doc);

//新的段落節點還沒有父節點。
Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

//但段落節點知道它的文檔。
Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

//節點始終屬於文件這一事實允許我們存取和修改
//引用文件範圍資料的屬性，例如樣式或清單。
para.ParagraphFormat.StyleName = "Heading 1";

//現在將該段落加入第一部分的正文中。
doc.FirstSection.Body.AppendChild(para);

//段落節點現在是 Body 節點的子節點。
Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
```

### 常見問題解答

#### Q：Node.js 中的專有文件是什麼？

答：Node.js 中的擁有者文件是特定節點所屬的 XML 文件。它表示包含該節點的 XML 文件的實例。

#### Q：如何取得節點的所有者文件？

答：要取得 Node.js 中節點的擁有者文檔，可以使用`ownerDocument`節點的屬性。此屬性傳回擁有該節點的 XML 文件。

#### Q：專有文件有什麼用？

答：擁有者文件用於表示 XML 文檔中節點的全域上下文。它提供對文件中其他節點的訪問，並允許對它們執行操作。

#### Q：我們可以修改節點的擁有者文件嗎？

答：大多數情況下，節點的文檔擁有者是在建立節點時確定的，不能直接變更。所有者文檔是唯讀屬性。

#### Q：如何存取所有者文件的節點？

答：要存取專有文件中的節點，您可以使用 Node.js 環境中使用的 XML API 提供的方法和屬性。例如，您可以使用類似的方法`getElementsByTagName`或者`querySelector`選擇文檔中的特定節點。