---
title: 在 Word 文件中插入 Ole 對象
linktitle: 在 Word 文件中插入 Ole 對象
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中插入 OLE 物件。
type: docs
weight: 10
url: /zh-hant/net/working-with-oleobjects-and-activex/insert-ole-object/
---

以下是解釋 C# 原始程式碼的逐步指南，說明如何使用 Aspose.Words for .NET 在 Word 文件中插入 OLE 物件。

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

## 步驟 3：插入 OLE 對象
使用文件產生器`InsertOleObject`方法將 OLE 物件插入文件中。指定 OLE 物件 URL、物件類型、顯示選項和其他必要的設定。

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

## 步驟 4：儲存文檔
使用文件的`Save`將文件儲存到文件的方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### 使用 Aspose.Words for .NET 插入 OLE 物件的範例原始程式碼

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

這是使用 Aspose.Words for .NET 插入 OLE 物件的完整程式碼範例。請務必匯入必要的引用並按照前面描述的步驟將此程式碼整合到您的專案中。

## 結論

總之，將 OLE 物件插入 Word 文件是 Aspose.Words for .NET 提供的一項強大功能。使用此程式庫，您可以輕鬆地將 OLE 物件（例如 HTML 檔案、Excel 試算表、PowerPoint 簡報等）嵌入到 Word 文件中。

在本文中，我們透過逐步指南解釋了 C# 原始程式碼，說明如何將 OLE 物件插入 Word 文件中。我們介紹了必要的參考、建立新文件和文件產生器，以及插入 OLE 物件和保存文件的步驟。

### 將 OLE 物件插入 Word 文件的常見問題解答

#### Q：我需要匯入哪些憑證才能使用 Aspose.Words for .NET？

答：要使用 Aspose.Words for .NET，您需要匯入以下參考：

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q：如何建立新文檔和文檔產生器？

答：您可以使用以下命令建立一個新文檔`Document`類別和文檔產生器使用`DocumentBuilder`類，如下圖：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q：如何在文件中插入OLE物件？

答：使用`InsertOleObject`文檔生成器的方法（`DocumentBuilder`) 將 OLE 物件插入文件中。指定 OLE 物件 URL、物件類型、顯示選項和其他必要的設定。這是一個例子：

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

#### Q：如何儲存文件？

答：使用文檔`Save`將文件儲存到文件的方法。這是一個例子：

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### Q：您能否提供使用 Aspose.Words for .NET 插入 OLE 物件的完整範例？

答：這裡是使用 Aspose.Words for .NET 插入 OLE 物件的完整範例程式碼。請務必匯入必要的引用並按照前面描述的步驟將此程式碼整合到您的專案中：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
