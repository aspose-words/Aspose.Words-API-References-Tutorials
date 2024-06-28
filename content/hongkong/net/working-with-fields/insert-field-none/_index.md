---
title: 插入欄位 無
linktitle: 插入欄位 無
second_title: Aspose.Words 文件處理 API
description: 了解如何在 Word avec Aspose.Words pour .NET 中使用 AUCUN 建立文件。
type: docs
weight: 10
url: /zh-hant/net/working-with-fields/insert-field-none/
---

以下是解釋下面 C# 原始程式碼的逐步指南，該程式碼使用 Aspose.Words for .NET 的「插入無欄位」功能。確保仔細執行每個步驟以獲得所需的結果。

## 第 1 步：文檔目錄設置

在提供的程式碼中，您必須指定文件的目錄。將值“YOUR DOCUMENT DIRECTORY”替換為文檔目錄的相應路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：建立文件和 DocumentBuilder

我們首先建立一個新文件並初始化一個 DocumentBuilder。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 3：插入 NONE 字段

我們使用`InsertField()`DocumentBuilder 的方法將 NONE 欄位插入到文件中。

```csharp
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);
```

### 使用 Aspose.Words for .NET 插入 NONE 欄位的原始碼範例

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立文件和 DocumentBuilder。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入無字段。
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);

doc.Save(dataDir + "InsertionFieldNone.docx");
```

在此範例中，我們建立了一個新文檔，初始化了一個 DocumentBuilder，然後插入了一個 NONE 欄位。然後以指定的檔案名稱儲存文件。

我們關於使用 Aspose.Words for .NET 的「插入無欄位」功能的指南到此結束。

### 常見問題解答

#### Q：「帶有字段的文字處理：插入無字段」教學涵蓋哪些內容？

答：本教學介紹了 Aspose Words for .NET 中的欄位操作，特別注意插入「無」欄位。欄位是 Word 文件中的動態元素，可用於顯示或計算資料。本教學說明如何插入「無」欄位並正確使用它。

#### Q：為什麼在 Aspose Words 中使用「無」欄位？

答：當您想要在文件中插入佔位符或標記，但沒有任何特定效果或計算時，Aspose Words 中的「無」欄位非常有用。它可用於標記文件中稍後要插入資料的位置或添加特殊註釋，而不會影響其餘內容。

#### Q：我可以使用附加參數自訂「無」欄位嗎？

答：不，「無」欄位不接受附加參數。它主要用作標記或占位符，沒有特定功能。但是，您可以在 Aspose Words 中使用其他欄位類型來執行更進階的操作。