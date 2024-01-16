---
title: 使用流將 Ole 物件插入為圖標
linktitle: 使用流將 Ole 物件插入為圖標
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 的串流將 OLE 物件插入圖示。
type: docs
weight: 10
url: /zh-hant/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

以下是解釋 C# 原始程式碼的逐步指南，說明如何使用 Aspose.Words for .NET 的流將 OLE 物件插入圖示。

## 第 1 步：導入必要的參考文獻
在開始之前，請確保您已將使用 Aspose.Words for .NET 所需的參考匯入到您的專案中。這包括匯入 Aspose.Words 庫並將所需的命名空間新增至來源檔案。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## 步驟 2：建立新文檔和文檔產生器
在此步驟中，我們將使用以下命令建立一個新文檔`Document`類別和文檔產生器使用`DocumentBuilder`班級。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 3：從流中插入 OLE 物件作為圖標
使用文件產生器`InsertOleObjectAsIcon`方法將 OLE 物件作為圖示從流插入到文件中。指定資料流、物件類型、圖示路徑和嵌入物件名稱。

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## 步驟 4：儲存文檔
使用文件的`Save`將文件儲存到文件的方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### 使用 Aspose.Words for .NET 的流插入 OLE 物件作為圖示的範例原始碼

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

這是一個完整的程式碼範例，用於使用 Aspose.Words for .NET 的流將 OLE 物件插入圖示。請務必匯入必要的引用並按照前面描述的步驟將此程式碼整合到您的專案中。

## 結論

上面的逐步指南說明如何使用 Aspose.Words for .NET 的流程在 Word 文件中插入 OLE 物件作為圖示。透過執行所描述的步驟，您將能夠將此功能整合到您的專案中。請務必匯入必要的引用，建立新文件和文件產生器，從流中將 OLE 物件作為圖示插入，然後儲存文件。使用提供的範例程式碼作為起點，並根據您的需求進行自訂。

### 常見問題解答

#### Q：如何匯入必要的參考以使用 Aspose.Words for .NET？

A. 若要匯入必要的參考，您必須執行下列步驟：

新增以下內容`using`來源文件頂部的語句：

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
確保您已將 Aspose.Words 庫新增至您的專案。

#### Q：如何使用 Aspose.Words for .NET 建立新文件和文件產生器？

A. 若要建立新文件和文件產生器，您可以按照下列步驟操作：

使用`Document`類別來建立新文件：

```csharp
Document doc = new Document();
```
使用`DocumentBuilder`類別來建立與先前建立的文件關聯的文件建構器：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q：如何使用 Aspose.Words for .NET 從流中插入 OLE 物件作為圖示？

A. 要從流中插入 OLE 物件作為圖標，可以按照以下步驟操作：

使用`InsertOleObjectAsIcon`文檔產生器插入 OLE 物件的方法：

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### Q：如何將文檔儲存到文件中？

A. 若要將文件儲存到文件中，您可以使用`Save`指定目標路徑的文檔方法：

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Q：如何將用於將 OLE 物件作為圖標從流插入到我的專案中的程式碼嵌入到我的專案中？

A. 若要將用於將 OLE 物件作為圖示從流插入項目的程式碼嵌入到您的專案中，請執行以下步驟：
- 透過添加適當的內容來導入必要的參考文獻`using`聲明。
- 使用以下命令建立一個新文檔和文檔產生器`Document`和`DocumentBuilder`類。
- 使用程式碼將 OLE 物件作為圖示從流中插入。
- 使用儲存文檔`Save`方法與適當的目標路徑。

透過執行這些步驟，您將能夠使用 Aspose.Words for .NET 從流程中成功插入 OLE 物件作為圖示。請務必按照說明進行操作並導入必要的參考文獻以獲得所需的結果。