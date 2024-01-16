---
title: 在每個部分重新啟動列表
linktitle: 在每個部分重新啟動列表
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 重設 Word 文件中每個部分的編號清單。
type: docs
weight: 10
url: /zh-hant/net/working-with-list/restart-list-at-each-section/
---

在本逐步教學中，我們將向您展示如何使用 Aspose.Words for .NET 重設 Word 文件中每個部分的編號清單。我們將解釋提供的 C# 原始程式碼並向您展示如何在您自己的專案中實現它。

首先，請確保您已在開發環境中安裝並設定了 Aspose.Words for .NET。如果您還沒有安裝該庫，請從以下位置下載並安裝該庫：[Aspose.Releases]https://releases.aspose.com/words/net/。

## 第 1 步：建立文件和列表

首先，建立一個新文件並新增預設編號清單：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## 第 2 步：將項目新增到清單中

然後使用一個`DocumentBuilder`將項目新增到清單中。您可以使用循環將多個項目新增至清單：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

在此範例中，我們在第 15 個清單項目之後插入分節符號以說明重新編號。

## 第三步：儲存修改後的文檔

最後儲存修改後的文件：

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

所以 ！您已使用 Aspose.Words for .NET 成功重置了 Word 文件中每個部分的編號清單。

### 用於重置每個部分的清單的範例原始程式碼

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

請隨意在您自己的專案中使用此程式碼並對其進行修改以滿足您的特定需求。

### 常見問題解答

#### Q：如何在 Aspose.Words 的每個部分重新啟動清單？

答：要在 Aspose.Words 中的每個部分重新啟動列表，您需要建立一個實例`List`類別並為其指派一個編號清單。然後您可以使用`List.IsRestartAtEachSection`屬性來指定應在每個部分重新開始編號。您可以將此清單與文件的一個或多個部分相關聯，以便在每個部分正確地重新開始編號。

#### Q：我可以在 Aspose.Words 中自訂清單的編號格式嗎？

答：是的，您可以在 Aspose.Words 中自訂清單的編號格式。這`List`類別為此提供了幾個屬性，例如`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`等等。您可以使用這些屬性來設定清單類型（編號、項目符號等）、編號格式（阿拉伯數字、羅馬數字、字母等）以及其他編號格式選項。

#### Q：是否可以為 Aspose.Words 中的編號清單新增其他層級？

答：是的，可以在 Aspose.Words 中的編號清單中新增其他等級。這`ListLevel`類別允許您為清單的每個層級設定格式屬性。您可以設定前綴、後綴、對齊、縮排等選項。這允許您建立具有多個層次結構的清單。