---
title: 在 Word 文件中插入 Ole 物件作為圖標
linktitle: 在 Word 文件中插入 Ole 物件作為圖標
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中插入 OLE 物件作為圖示。
type: docs
weight: 10
url: /zh-hant/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

以下是解釋 C# 原始程式碼的逐步指南，說明如何使用 Aspose.Words for .NET 在 Word 文件中插入 OLE 物件作為圖示。

## 第 1 步：導入必要的參考文獻
在開始之前，請確保您已將使用 Aspose.Words for .NET 所需的參考匯入到您的專案中。這包括匯入 Aspose.Words 庫並將所需的命名空間新增至來源檔案。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 步驟 2：建立新文檔和文檔產生器
在此步驟中，我們將使用以下命令建立一個新文檔`Document`類別和文檔產生器使用`DocumentBuilder`班級。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 3：插入 OLE 物件作為圖標
使用文件產生器`InsertOleObjectAsIcon`方法將 OLE 物件作為圖示插入到文件中。指定 OLE 檔案路徑、顯示標誌、圖示路徑和嵌入物件名稱。

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## 步驟 4：儲存文檔
使用文件的`Save`將文件儲存到文件的方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### 使用 Aspose.Words for .NET 將 OLE 物件作為圖示插入的範例原始程式碼

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

這是一個完整的程式碼範例，用於使用 Aspose.Words for .NET 將 OLE 物件插入圖示為圖示。請務必匯入必要的引用並按照前面描述的步驟將此程式碼整合到您的專案中。

## 結論

總之，我們探索了使用 Aspose.Words for .NET 在 Word 文件中插入 OLE 物件作為圖示的逐步指南。

透過執行這些步驟，您將能夠使用 Aspose.Words for .NET 在 Word 文件中成功插入 OLE 物件作為圖示。請務必匯入必要的參考並仔細按照說明進行操作，以獲得所需的結果。

### 在 Word 文件中插入 ole 物件作為圖示的常見問題解答

#### Q：使用 Aspose.Words for .NET 在 Word 文件中插入 OLE 物件作為圖示需要哪些參考？

答：您需要將以下引用匯入到您的專案中才能使用 Aspose.Words for .NET：

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q：如何在 Aspose.Words for .NET 中建立新文件和文件產生器？

答：您可以使用以下命令建立一個新文檔`Document`類別和文檔產生器使用`DocumentBuilder`班級。這是一個例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q：如何在文件中插入 OLE 物件作為圖示？

 A：使用文件產生器`InsertOleObjectAsIcon`方法插入 OLE 物件作為圖示。指定 OLE 檔案路徑、顯示標誌、圖示路徑和嵌入物件名稱。這是一個例子：

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### Q：如何儲存以圖示形式插入的 OLE 物件的文件？

答：使用文檔`Save`將文件儲存到文件的方法。這是一個例子：

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```