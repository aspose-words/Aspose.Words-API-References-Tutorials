---
title: 更改欄位更新文化來源
linktitle: 更改欄位更新文化來源
second_title: Aspose.Words 文件處理 API
description: 更改欄位更新文化來源，在 Aspose.Words for .NET 中修改文化來源的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/working-with-fields/change-field-update-culture-source/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 變更 Word 文件中的欄位更新區域性來源的過程。透過修改區域性來源，您可以在欄位更新和郵件合併作業期間控制日期格式。我們將為您提供實現這一目標所需的 C# 原始程式碼和逐步說明。

## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Aspose.Words for .NET 程式庫安裝在您的系統上。

## 第 1 步：建立文件和 DocumentBuilder
首先，建立 Document 類別的實例和 DocumentBuilder 物件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 2：插入具有特定區域設定的內容
接下來，將區域設定設為德語並插入具有日期格式的欄位：

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

在上面的程式碼中，我們將字體區域設定設為德語（區域設定 ID 1031），並插入兩個具有特定日期格式的欄位。

## 步驟3：更改欄位更新文化來源
若要變更欄位更新區域性來源，請使用 FieldOptions 類別：

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

在此範例中，我們將欄位更新期間使用的區域性設定為從欄位使用的區域性中選擇。

## 步驟 4：執行郵件合併
執行郵件合併操作並指定「Date2」欄位的日期值：

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

在此程式碼片段中，我們執行郵件合併操作並為「Date2」欄位提供日期時間值。

## 第 5 步：儲存文檔
使用 Document 類別的 Save 方法將修改後的文件儲存到文件中：

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### 使用 Aspose.Words for .NET 變更欄位更新文化來源的範例原始碼
以下是使用 Aspose.Words for .NET 更改 Word 文件中的欄位更新區域性來源的完整原始碼：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## 結論
恭喜！您已成功學習如何使用 Aspose.Words for .NET 變更 Word 文件中的欄位更新區域性來源。透過遵循逐步指南並利用提供的原始程式碼，您現在可以控製欄位更新和郵件合併作業期間用於日期格式的區域性。根據您的要求自訂培養源，以確保數據準確一致。

### 常見問題解答

#### Q：如何更改 Aspose.Words for .NET 中的欄位更新區域性來源？

答：若要變更 Aspose.Words for .NET 中的欄位更新區域性來源，您可以使用`Document.FieldOptions.CultureSource`屬性並將其值設為`FieldCultureSource.FieldCode`或者`FieldCultureSource.CurrentThread`。例如，您可以使用`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode`使用字段代碼中定義的區域性。

#### Q：如何指定特定區域性來更新 Aspose.Words for .NET 中的欄位？

答：要指定用於更新 Aspose.Words for .NET 中欄位的特定區域性，您可以使用`Document.FieldOptions.FieldUpdateCultureInfo`屬性並設定`CultureInfo`與所需文化相對應的對象。例如，您可以使用`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")`指定法國（法國）文化。

#### Q：是否可以在 Aspose.Words for .NET 中停用自動欄位更新？

答：是的，可以在 Aspose.Words for .NET 中停用自動欄位更新。您可以使用`Document.FieldOptions.UpdateFields`屬性並將其設為`false`以防止欄位自動更新。這允許您根據需要手動控製字段的更新。

#### Q：如何手動更新 Aspose.Words for .NET 中的文件欄位？

答：要在 Aspose.Words for .NET 中手動更新文件中的字段，您可以使用`Field.Update`分別針對每個欄位的方法。例如，您可以使用`field.Update()`更新特定字段。