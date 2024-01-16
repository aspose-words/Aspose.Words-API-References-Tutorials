---
title: 轉換正文中的字段
linktitle: 轉換正文中的字段
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將頁面欄位轉換為 Word 文件正文中的文字。
type: docs
weight: 10
url: /zh-hant/net/working-with-fields/convert-fields-in-body/
---

在本逐步教學中，我們將引導您了解如何使用提供的 C# 原始程式碼使用 Aspose.Words for .NET 的 ConvertFieldsInBody 功能。此功能可讓您將文件正文中的特定欄位轉換為純文本，使您的文件更易於處理。請按照以下步驟有效地使用此功能。

## 第 1 步：先決條件

在開始之前，請確保您已安裝 Aspose.Words for .NET 並準備好可以處理的文件。另請確保您擁有文件的目錄路徑。

## 第 2 步：載入文檔

首先為文檔目錄的路徑宣告一個變量，然後使用該變數從指定文檔初始化 Document 物件。在我們的範例中，該文件稱為“Linked fields.docx”。

```csharp
//您的文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "Linked fields.docx");
```

## 步驟 3：將頁面欄位轉換為純文本

現在文檔已加載，我們可以繼續進行轉換步驟。要將第一部分正文中的頁面欄位轉換為純文本，您可以使用`Range.Fields`方法取得指定範圍內的所有字段，然後過濾掉type的字段`FieldType.FieldPage`。然後您可以使用`ForEach`方法循環遍歷每個字段並調用`Unlink()`方法將其轉換為純文字。

```csharp
//傳遞適當的參數以將第一部分正文中的頁面欄位轉換為純文字。
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## 第四步：儲存修改後的文檔

將頁面欄位轉換為純文字後，您可以使用以下命令儲存修改後的文件：`Save()`方法並指定輸出檔案的路徑和名稱。在我們的範例中，我們將其儲存為「WorkingWithFields.ConvertFieldsInBody.docx」。

```csharp
//儲存修改後的文檔
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### 使用 Aspose.Words for .NET 轉換正文中欄位的範例原始碼

以下是使用 Aspose.Words for .NET 將欄位轉換為正文的完整原始碼範例：

```csharp
//您的文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "Linked fields.docx");

//傳遞適當的參數以將第一部分正文中的頁面欄位轉換為純文字。
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### 常見問題解答

#### Q：Aspose.Words 是否與不同版本的 Microsoft Word 相容？

答：是的，Aspose.Words 與 Microsoft Word 的各個版本相容，包括 Word 2003、Word 2007、Word 2010、Word 2013、Word 2016 和 Word 2019。

#### Q：Aspose.Words 可以處理複雜的欄位結構嗎？

答：當然！ Aspose.Words 為複雜的字段結構提供廣泛的支持，包括嵌套字段、計算和條件表達式。您可以利用強大的 API 來處理任何類型的欄位結構。

#### Q：Aspose.Words 支援欄位更新操作嗎？

答：是的，Aspose.Words 允許您以程式設計方式更新欄位。您可以使用 API 輕鬆更新欄位值、刷新計算以及執行其他與欄位相關的操作。

#### Q：我可以使用 Aspose.Words 將欄位轉換為純文字嗎？

答：當然可以！ Aspose.Words 提供了將欄位轉換為純文字的方法。當您需要提取沒有任何欄位相關格式或功能的內容時，這非常有用。

#### Q：是否可以使用 Aspose.Words 產生帶有動態欄位的 Word 文件？

答：當然！ Aspose.Words 提供了強大的功能來產生具有動態欄位的 Word 文件。您可以使用預定義欄位建立範本並動態填充數據，從而提供靈活且高效的文件生成解決方案。