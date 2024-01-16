---
title: 使用 Ole 套件在 Word 中插入 Ole 對象
linktitle: 使用 Ole 套件在 Word 中插入 Ole 對象
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將帶有 OLE 套件的 OLE 物件插入文件中。
type: docs
weight: 10
url: /zh-hant/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

以下是解釋 C# 原始程式碼的逐步指南，說明如何使用 Aspose.Words for .NET 在具有 OLE 套件的 Word 中插入 OLE 物件。

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

## 步驟 3：插入帶有 OLE 套件的 OLE 對象
使用文件產生器`InsertOleObject`方法將帶有 OLE 套件的 OLE 物件插入文件中。指定資料流、物件類型、顯示選項和其他必要的設定。

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## 步驟 4：儲存文檔
使用文件的`Save`將文件儲存到文件的方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### 使用 Aspose.Words for .NET 插入帶有 OLE 套件的 OLE 物件的範例原始程式碼

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

這是一個完整的程式碼範例，用於使用 Aspose.Words for .NET 插入帶有 OLE 套件的 OLE 物件。請務必匯入必要的引用並按照前面描述的步驟將此程式碼整合到您的專案中。

## 結論

總之，我們已經完成了使用 Aspose.Words for .NET 將 OLE 物件插入帶有 OLE 套件的 Word 文件的逐步指南。

透過執行這些步驟，您將能夠使用 Aspose.Words for .NET 成功將帶有 OLE 套件的 OLE 物件插入 Word 文件中。請務必匯入必要的參考並仔細按照說明進行操作，以獲得所需的結果。

### 使用 ole 套件在 word 中插入 ole 物件的常見問題解答

#### Q：我需要匯入哪些憑證才能使用 Aspose.Words for .NET？

答：要使用 Aspose.Words for .NET，您需要匯入以下參考：

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### Q：如何建立新文檔和文檔產生器？

答：您可以使用以下命令建立一個新文檔`Document`類別和文檔產生器使用`DocumentBuilder`類，如下圖：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q：如何將帶有 OLE 套件的 OLE 物件插入文件中？

答：使用`InsertOleObject`文檔生成器的方法（`DocumentBuilder`) 將帶有 OLE 套件的 OLE 物件插入文件中。指定資料流、物件類型、顯示選項和其他必要的設定。這是一個例子：

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### Q：如何儲存文件？

答：使用文檔`Save`將文件儲存到文件的方法。這是一個例子：

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### Q：您能否提供使用 Aspose.Words for .NET 插入帶有 OLE 套件的 OLE 物件的完整範例？

答：以下是使用 Aspose.Words for .NET 插入帶有 OLE 套件的 OLE 物件的完整範例程式碼。請務必匯入必要的引用並按照前面描述的步驟將此程式碼整合到您的專案中：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

關於使用 Aspose.Words for .NET 將帶有 OLE 套件的 OLE 物件插入 Word 文件中的教學課程到此結束。請隨意匯入必要的引用並按照描述的步驟將此程式碼整合到您的專案中。如果您還有任何疑問，請隨時與我們聯繫。