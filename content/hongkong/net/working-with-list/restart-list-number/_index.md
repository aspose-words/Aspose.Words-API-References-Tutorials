---
title: 重新啟動清單編號
linktitle: 重新啟動清單編號
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 重設 Word 文件中的清單編號。
type: docs
weight: 10
url: /zh-hant/net/working-with-list/restart-list-number/
---
在本逐步教學中，我們將向您展示如何使用 Aspose.Words for .NET 重設 Word 文件中的清單編號。我們將解釋提供的 C# 原始程式碼並向您展示如何在您自己的專案中實現它。

首先，請確保您已在開發環境中安裝並設定了 Aspose.Words for .NET。如果您還沒有安裝該庫，請從以下位置下載並安裝該庫：[Aspose.Releases]https://releases.aspose.com/words/net/。

## 第 1 步：建立文件和文件產生器

首先，建立一個新文檔和關聯的文檔產生器：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：建立並自訂第一個列表

接下來，根據現有範本建立列表，然後自訂其等級：

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## 步驟 3：將項目新增到第一個列表

使用文件產生器將項目新增至第一個清單並刪除清單編號：

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 第 4 步：建立並自訂第二個列表

若要透過重設編號來重複使用第一個列表，請建立原始列表佈局的副本：

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

如果需要，您也可以對第二個清單進行其他變更。

## 步驟 5：將項目新增到第二個列表

再次使用文件產生器將項目新增至第二個清單並刪除清單編號：

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 第六步：儲存修改後的文檔

最後儲存修改後的文件：

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

所以 ！您已使用 Aspose.Words for .NET 成功重置了 Word 文件中的清單編號。

### 清單編號重置的範例原始碼

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//根據模板建立清單。
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

//要重複使用第一個列表，我們需要透過建立原始列表格式的副本來重新開始編號。
List list2 = doc.Lists.AddCopy(list1);

//我們可以以任何方式修改新列表，包括設定新的起始編號。
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### 常見問題解答

#### Q：如何在 Aspose.Words 中重新啟動清單的編號？

答：要在 Aspose.Words 中重新啟動清單編號，您可以使用`ListRestartAtNumber`的方法`List`班級。此方法可讓您設定新的撥號值，清單應從該值重新啟動。例如，您可以使用`list.ListRestartAtNumber(1)`從 1 重新開始編號。

#### Q：是否可以在Aspose.Words中自訂重新啟動的清單編號的前綴和後綴？

答：是的，您可以在 Aspose.Words 中自訂重新啟動清單編號的前綴和後綴。這`ListLevel`類提供諸如`ListLevel.NumberPrefix`和`ListLevel.NumberSuffix`它允許您指定清單中每個層級的前綴和後綴。您可以使用這些屬性根據需要自訂前綴和後綴。

#### Q：如何指定清單應重新啟動的特定編號值？

答：要指定清單應重新啟動的特定數值，您可以使用`ListRestartAtNumber`方法將所需值作為參數傳遞。例如，若要從 5 重新開始編號，您可以使用`list.ListRestartAtNumber(5)`.

#### Q：是否可以在 Aspose.Words 中重新啟動多層清單編號？

答：是的，Aspose.Words 支援多個清單層級的重新編號。您可以應用`ListRestartAtNumber`方法在每個清單層級單獨重新開始編號。例如，您可以使用`list.Levels[0].ListRestartAtNumber(1)`從 1 重新開始第一個列表級別，並且`list.Levels[1].ListRestartAtNumber(1)`從1開始重新啟動二級列表，依此類推。



