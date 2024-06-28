---
title: 現場更新文化
linktitle: 現場更新文化
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 更新 Word 文件中的欄位文化。
type: docs
weight: 10
url: /zh-hant/net/working-with-fields/field-update-culture/
---

以下是解釋 C# 原始程式碼的逐步指南，該程式碼使用 Aspose.Words for .NET 的「Field Culture Update」功能。確保仔細執行每個步驟以獲得所需的結果。

## 第 1 步：文檔目錄設置

在提供的程式碼中，您必須指定文件的目錄。將值“YOUR DOCUMENT DIRECTORY”替換為文檔目錄的相應路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：建立文件和文件產生器

我們首先建立一個新文檔和一個文檔產生器。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 3：插入時間字段

我們使用`InsertField()`方法將時間欄位插入文件中。

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

這將在文件中插入一個時間欄位。

## 步驟 4：設定欄位更新文化

我們配置字段選項以指定字段更新區域性應基於字段代碼。

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

這些選項確定用於更新欄位的區域性。

### 使用 Aspose.Words for .NET 更新現場文化的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立文檔和文檔產生器。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入時間欄位。
builder. InsertField(FieldType.FieldTime, true);

//配置字段更新區域性。
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

//儲存文檔。
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

在此範例中，我們建立了一個新文檔，插入了一個時間字段，並配置了字段更新區域性。然後我們用指定的文件名保存文檔。

我們關於使用 Aspose.Words for .NET 的「更新欄位文化」功能的指南到此結束。

### 常見問題解答

#### Q：Aspose.Words 中的字段更新文化是什麼？

答：Aspose.Words中的欄位更新區域性是指用於格式化和更新Word文件中欄位值的區域性。區域性決定數字、日期和其他資料更新時在欄位中的顯示方式。

#### Q：如何使用 Aspose.Words 設定 Word 文件中欄位的更新區域性？

答：要使用 Aspose.Words 設定 Word 文件中欄位的更新區域性，您可以依照下列步驟操作：

1. 從 Aspose.Words 命名空間匯入 Document 類別。
2. 透過載入現有文件來建立 Document 實例。
3. 使用 Document.UpdateFieldsCultureInfo 屬性設定欄位的更新區域性。

#### Q：Aspose.Words 中更新欄位支援哪些區域性？

答：Aspose.Words 支援不同文化的欄位更新。您可以指定作業系統支援的任何區域性。例如，「en-US」表示美式英語，「fr-FR」表示法語，「de-DE」表示德語等。

#### Q：是否可以為單一欄位而不是整個文件設定特定的文化？

答：是的，可以為單一欄位而不是整個文件設定特定的文化。在Aspose.Words中，每個欄位都有一個Format屬性，可用來設定特定於該欄位的格式區域性。這使您可以控制該欄位的顯示和更新方式，獨立於文件中的其他欄位。

#### Q：如何檢查 Word 文件中目前定義的欄位更新區域性？

答：若要檢查 Word 文件中目前定義的欄位更新區域性，可以使用 Document.UpdateFieldsCultureInfo 屬性。此屬性傳回表示目前用於設定欄位更新的區域性的 CultureInfo 物件。