---
title: 轉換段落中的字段
linktitle: 轉換段落中的字段
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將 IF 欄位轉換為段落中的純文字。
type: docs
weight: 10
url: /zh-hant/net/working-with-fields/convert-fields-in-paragraph/
---

以下教學課程示範如何透過 Aspose.Words for .NET 使用「將欄位轉換為段落」功能。此程式碼將文件最後一段中遇到的所有 IF 類型欄位轉換為純文字。請按照以下步驟理解並運行此程式碼。

在開始之前，請確保您已安裝 Aspose.Words for .NET 並設定您的開發環境。

## 第 1 步：導入參考文獻

要在專案中使用 Aspose.Words，您需要新增必要的參考。確保您已在專案中新增對 Aspose.Words 庫的引用。

## 第 2 步：載入文檔

在轉換欄位之前，您必須載入包含要轉換的欄位的文件。請務必指定包含文件的目錄的正確路徑。上傳文檔的方法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔。
Document doc = new Document(dataDir + "Linked fields.docx");
```

將“您的文檔目錄”替換為文檔目錄的實際路徑。

## 第 3 步：將欄位轉換為文字

現在文檔已加載，我們可以繼續將類型欄位轉換為純文字。在此範例中，我們僅定位在文件最後一段中存在的欄位。下面是執行此轉換的程式碼：

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

此程式碼使用 LINQ 方法的組合來過濾文件最後一段中的字段，然後透過呼叫將它們轉換為純文字`Unlink()`方法。

## 第四步：儲存修改後的文檔

欄位轉換後，您可以儲存修改後的文件。使用`Save()`方法用於此。這是一個例子：

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

請務必指定正確的備份路徑和檔案名稱。

### 使用 Aspose.Words for .NET 轉換段落中的欄位的原始程式碼範例

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔。
Document doc = new Document(dataDir + "Linked fields.docx");

//將文件最後一段中的 IF 欄位轉換為純文字。
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

//儲存修改後的文件。
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### 常見問題解答

#### Q：Aspose.Words 中的轉換欄位是什麼？

答：Aspose.Words 中的轉換欄位是一種將值或表達式轉換為另一種格式或資料類型的欄位。例如，您可以使用轉換欄位將日期轉換為特定格式、將數字轉換為文字或執行其他類型的轉換。

#### Q：如何使用 Aspose.Words 在段落中插入轉換欄位？

答：要使用 Aspose.Words 在段落中插入轉換字段，您可以按照以下步驟操作：

1. 從 Aspose.Words 命名空間匯入 Document 類別。
2. 透過載入現有文件來建立 Document 實例。
3. 取得要插入轉換欄位的段落。
4. 使用 InsertField 方法以正確的語法插入轉換欄位。

#### Q：Aspose.Words 支援哪些轉換格式？

答：Aspose.Words 支援多種欄位轉換格式，包括日期格式、數字格式、文字格式、貨幣格式、百分比格式等等。您可以查看 Aspose.Words 文件以取得可用轉換格式的完整清單。

#### Q：如何使用 Aspose.Words 更新 Word 文件中的轉換欄位？

答：要使用 Aspose.Words 更新 Word 文件中的轉換字段，您可以使用 UpdateFields 方法。此方法循環遍歷文件並更新所有字段，包括轉換字段，根據當前資料重新計算值。