---
title: 指定列表級別
linktitle: 指定列表級別
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中指定清單層級。
type: docs
weight: 10
url: /zh-hant/net/working-with-list/specify-list-level/
---

在本逐步教學中，我們將向您展示如何使用 Aspose.Words for .NET 在 Word 文件中指定清單層級。我們將解釋提供的 C# 原始程式碼並向您展示如何在您自己的專案中實現它。

首先，請確保您已在開發環境中安裝並設定了 Aspose.Words for .NET。如果您還沒有安裝該庫，請從以下位置下載並安裝該庫：[Aspose.Releases]https://releases.aspose.com/words/net/。

## 第 1 步：建立文件和文件產生器

首先，建立一個新文檔和關聯的文檔產生器：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：建立並套用編號列表

接下來，根據 Microsoft Word 的列表範本之一建立編號列表，並將其套用到文件產生器中的當前段落：

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## 步驟 3：清單層級規範

使用文件產生器`ListLevelNumber`屬性來指定清單層級並向段落新增文字：

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

重複這些步驟以指定清單層級並在每個層級新增文字。

## 第 4 步：建立並套用項目符號列表

您也可以使用 Microsoft Word 的清單範本之一建立並套用項目符號清單：

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## 步驟 5：將文字新增到項目符號清單級別

使用`ListLevelNumber`再次屬性來指定項目符號清單層級並新增文字：

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## 第 6 步：停止格式化列表

若要停止清單格式化，請設定`null`到`List`文檔生成器的屬性：

```csharp
builder. ListFormat. List = null;
```

## 步驟7：儲存修改後的文檔

儲存修改後的文件：

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

所以 ！您已使用 Aspose.Words for .NET 成功指定了 Word 文件中的清單層級。

### 指定清單層級的範例原始程式碼

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//根據 Microsoft Word 清單範本之一建立編號清單。
//並將其應用於文件生成器的當前段落。
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

//此列表中有九個級別，讓我們全部嘗試一下。
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

//根據 Microsoft Word 清單範本之一建立項目符號清單。
//並將其應用於文件生成器的當前段落。
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

//這是停止清單格式化的一種方法。
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### 常見問題解答

#### Q：如何在 Aspose.Words 中指定清單層級？

答：要在Aspose.Words中指定清單級別，您需要建立一個實例`List`類別並給它一個編號列表。然後您可以使用`Paragraph.ListFormat.ListLevelNumber`屬性來指定每個列表項的層級。您可以將此清單與文件的某個部分相關聯，以便清單項目具有所需的等級。

#### Q：是否可以更改 Aspose.Words 中清單項目的編號格式？

答：是的，您可以變更 Aspose.Words 中清單項目的編號格式。這`ListLevel`類別為此提供了幾個屬性，例如`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`等等。

#### Q：我可以為 Aspose.Words 中的編號清單新增其他層級嗎？

答：是的，可以在 Aspose.Words 中的編號清單中新增其他等級。這`ListLevel`類別允許您為清單的每個層級設定格式屬性。您可以設定前綴、後綴、對齊、縮排等選項。


