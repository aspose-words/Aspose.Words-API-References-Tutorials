---
title: 在 Word 文件中插入複選框表單字段
linktitle: 在 Word 文件中插入複選框表單字段
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中插入複選框表單欄位。逐步指南。
type: docs
weight: 10
url: /zh-hant/net/add-content-using-documentbuilder/insert-check-box-form-field/
---
在這個綜合教學中，您將學習如何使用 Aspose.Words for .NET 將複選框表單欄位插入到 Word 文件中。我們將引導您完成整個過程，並為您提供必要的 C# 程式碼片段。在本指南結束時，您將能夠為文件新增具有可自訂屬性的複選框表單欄位。

## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Aspose.Words for .NET 程式庫安裝在您的系統上。

## 第 1 步：建立新文件和 DocumentBuilder
首先，使用 Document 類別建立一個新文件並初始化 DocumentBuilder 物件：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入複選框表單字段
接下來，使用 DocumentBuilder 類別的 InsertCheckBox 方法插入複選框表單欄位。提供名稱、檢查狀態、預設狀態和大小參數作為參數：

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## 第 3 步：儲存文檔
插入複選框表單欄位後，使用 Document 類別的 Save 方法將文件儲存到文件中：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### 使用 Aspose.Words for .NET 插入複選框表單欄位的範例原始碼
以下是使用 Aspose.Words for .NET 插入複選框表單欄位的完整原始碼：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", true, true, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

請記住根據您的特定要求調整程式碼，並根據需要使用附加功能對其進行增強。

## 結論
恭喜！您已成功學習如何使用 Aspose.Words for .NET 將複選框表單欄位插入 Word 文件中。透過遵循逐步指南並利用提供的原始程式碼，您現在可以使用互動式複選框表單欄位來增強文件。

### 常見問題解答

#### Q：我可以在單一文件中插入多個複選框表單欄位嗎？

答：當然！您可以使用 Aspose.Words for .NET 在 Word 文件中插入所需數量的複選框表單欄位。只需重複插入過程即可新增多個互動式複選框。

#### Q：我可以設定複選框表單欄位的初始狀態（選取或未選取）嗎？

答：是的，您可以完全控制複選框表單欄位的初始狀態。將選取狀態參數設為 true 或 false，您可以定義複選框最初是選取還是未選取。

#### Q：複選框表單欄位是否與其他文件格式（例如 PDF）相容？

答：是的，使用 Aspose.Words for .NET 插入的複選框表單欄位與各種文件格式相容，包括 DOCX 和 PDF。這允許您以不同的格式匯出文檔，同時保留互動式複選框。

#### Q：我可以調整複選框表單欄位的大小嗎？

答：當然可以！您可以使用 InsertCheckBox 方法中的 size 參數指定複選框表單欄位的大小。這使您能夠根據您的設計偏好控制複選框的尺寸。

#### Q：Aspose.Words for .NET 是否同時適用於桌面和 Web 應用程式？

答：是的，Aspose.Words for .NET 是一個多功能函式庫，適用於桌面和 Web 應用程式。無論您是建立 Windows 應用程式還是基於 Web 的系統，您都可以輕鬆整合該程式庫。