---
title: 在沒有文件產生器的情況下插入 TOA 字段
linktitle: 在沒有文件產生器的情況下插入 TOA 字段
second_title: Aspose.Words 文件處理 API
description: 逐步指南使用 Aspose.Words for .NET 插入 TOA 字段，無需文件產生器。
type: docs
weight: 10
url: /zh-hant/net/working-with-fields/insert-toafield-without-document-builder/
---

以下是解釋下面 C# 原始程式碼的逐步指南，該程式碼使用 Aspose.Words for .NET 的「TOA 欄位插入」功能。仔細遵循每個步驟以獲得所需的結果。

## 第 1 步：文檔目錄設置

在提供的程式碼中，您必須指定文件的目錄。將值“YOUR DOCUMENT DIRECTORY”替換為文檔目錄的相應路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：建立文件和段落

我們首先建立一個新文件並初始化一個段落。

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 步驟 3：插入 TA 字段

我們使用 FieldTA 類別將 TA 欄位插入到段落中。

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## 步驟 4：將段落新增至文件正文

我們將包含 TA 欄位的段落新增到文件正文中。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 步驟 5：為 TOA 欄位建立段落

我們為 TOA 欄位建立一個新段落。

```csharp
para = new Paragraph(doc);
```

## 步驟 6：插入 TOA 字段

我們使用 FieldToa 類別將 TOA 欄位插入到段落中。

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## 步驟 7：將段落新增至文件正文

我們將包含 TOA 欄位的段落新增到文件正文中。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 第 8 步：更新 TOA 字段

最後，我們調用`Update()`更新 TOA 字段的方法。

```csharp
fieldToa.Update();
```

### 使用 Aspose.Words for .NET 無需文件產生器即可插入 TOA 欄位的原始碼範例

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

//我們想要像這樣插入 TA 和 TOA 欄位：
// { TA \c 1 \l "值 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### 常見問題解答

#### Q：如何使用 Aspose.Words for .NET 自訂插入 Word 文件中的 TOA 欄位的外觀？

答：您可以使用 TOA 欄位的屬性來自訂插入的 TOA 欄位的外觀。`FieldTOA`物件指定格式選項。

#### Q：我可以使用 Aspose.Words for .NET 在單一 Word 文件中新增多個 TOA 欄位嗎？

答：是的，您可以使用 Aspose.Words for .NET 在單一 Word 文件中新增多個 TOA 欄位。只需對每個欄位重複插入步驟即可。

#### Q：如何使用 Aspose.Words for .NET 檢查 TOA 欄位是否成功插入 Word 文件？

答：若要檢查TOA欄位是否插入成功，您可以瀏覽文件內容並蒐索TOA欄位實例。

#### Q：在不使用 DocumentBuilder 的情況下插入 TOA 欄位是否會影響 Aspose.Words for .NET 的 Word 文件格式設定？

答：不使用 DocumentBuilder 插入 TOA 欄位不會直接影響 Word 文件的格式。但是，TOA 欄位格式設定選項可能會影響文件的整體格式設定。