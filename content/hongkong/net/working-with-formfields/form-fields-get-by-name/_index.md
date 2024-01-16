---
title: 表單欄位按名稱取得
linktitle: 表單欄位按名稱取得
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中按名稱擷取和修改表單欄位。
type: docs
weight: 10
url: /zh-hant/net/working-with-formfields/form-fields-get-by-name/
---

在本逐步教學中，我們將指導您如何使用 Aspose.Words for .NET 從 Word 文件中按名稱擷取表單欄位。我們將解釋提供的 C# 原始程式碼，並向您展示如何在您自己的專案中實現它。

首先，請確保您已在開發環境中安裝並設定了 Aspose.Words for .NET。如果您還沒有這樣做，請從以下位置下載並安裝該程式庫[Aspose.Releases]https://releases.aspose.com/words/net/。

## 第 1 步：初始化文檔對象

首先，初始化`Document`透過提供包含表單欄位的來源文件的路徑來物件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## 第 2 步：檢索表單字段

接下來，訪問`FormFields`的財產`Range`文件中的物件來檢索所有表單欄位：

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

您可以按索引或按名稱檢索表單欄位。在此範例中，我們使用兩種方法檢索表單欄位：

```csharp
FormField formField1 = documentFormFields[3]; //按索引檢索
FormField formField2 = documentFormFields["Text2"]; //按名稱檢索
```

## 步驟 3：修改表單欄位屬性

檢索表單欄位後，您可以根據需要修改其屬性。在這個例子中，我們改變了字體大小`formField1`到 20 以及字體顏色`formField2`為紅色：

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## 第 4 步：儲存文檔

最後儲存修改後的文件：

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 在 Word 文件中成功按名稱擷取表單欄位並修改其屬性。

### 使用 Aspose.Words for .NET 的表單欄位以名稱取得的範例原始碼

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

請隨意在您自己的專案中使用此程式碼，並根據您的特定要求進行修改。

### 常見問題解答

#### Q：如何在 Aspose.Words 中按名稱取得表單欄位？

答：要在 Aspose.Words 中按名稱取得表單字段，您可以使用`Document.Range.FormFields[name]`方法。此方法傳回與指定名稱對應的表單欄位。

#### Q：文檔中不存在指定名稱的表單欄位怎麼辦？

 A：如果文件中不存在指定名稱的表單域，則`Document.Range.FormFields[name]`方法將返回`null`。您可以檢查此結果以處理找不到表單欄位的情況。

#### Q：如何修改找到的表單欄位的屬性？

答：按名稱取得表單欄位後，您可以存取其各個屬性來編輯它們。例如，您可以變更欄位的值、啟用或停用其可見性，或根據需要修改其他屬性。

#### Q：我可以在一個文件中取得多個同名的表單欄位嗎？

答：是的，一個文件中可以有多個同名的表單欄位。在這種情況下，`Document.Range.FormFields[name]`方法將傳回找到的具有指定名稱的第一個表單欄位。如果您有多個同名的表單字段，則在操作字段時需要考慮到這一點。

#### Q：如何迭代文件中的所有表單欄位？

答：要迭代文件中的所有表單字段，您可以使用`foreach`循環在`Document.Range.FormFields`收藏。這將允許您單獨存取每個表單欄位並對每個欄位執行操作。