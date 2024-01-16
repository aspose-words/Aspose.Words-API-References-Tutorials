---
title: 取得Word文件中的保護類型
linktitle: 取得Word文件中的保護類型
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 的取得 Word 文件中的保護類型功能來確定文件的保護類型。
type: docs
weight: 10
url: /zh-hant/net/document-protection/get-protection-type/
---
歡迎閱讀本逐步指南，該指南解釋了 Aspose.Words for .NET 的「取得保護類型」功能的 C# 原始碼。在本文中，我們將向您展示如何使用這項強大的功能來確定文件的保護類型。文件保護對於確保文件的機密性和完整性至關重要。我們將引導您完成整合 Aspose.Words for .NET 和使用「取得保護類型」功能所需的步驟。

## 第 1 步：載入文檔

使用「取得保護類型」功能的第一步是上傳您要處理的文件。您可以使用 Aspose.Words for .NET 提供的 Document 類別來完成此操作。以下是從文件載入文件的範例程式碼：

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

請務必指定文檔文件的正確路徑。

## 步驟 2：檢索保護類型

文件上傳後，您可以使用 Document 物件的 ProtectionType 屬性來擷取套用於文件的保護類型。您可以這樣做：

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### 使用 Aspose.Words for .NET 取得保護類型的範例原始程式碼

以下是使用 Aspose.Words for .NET 取得保護類型函數的完整原始碼：

```csharp
Document doc = new Document(MyDir + "Document.docx");
ProtectionType protectionType = doc.ProtectionType;
```

## 結論

在本文中，我們解釋如何使用Aspose.Words for .NET的取得保護類型功能來確定文件的保護類型。透過執行所描述的步驟，您將能夠輕鬆地將此功能整合到您自己的 C# 專案中並有效地操作受保護的文件。 Aspose.Words for .NET 提供了極大的靈活性

### 常見問題解答

#### Q：Aspose.Words for .NET 中的 ProtectionType 屬性是什麼？

答： 的`ProtectionType` Aspose.Words for .NET 中的屬性是一項可讓您確定套用於 Word 文件的保護類型的功能。它提供有關文件保護等級的信息，例如文件是否受到評論、修訂、表單或其他類型限制的保護。

#### Q：如何使用 Aspose.Words for .NET 擷取文件的保護類型？

答：要使用 Aspose.Words for .NET 擷取文件的保護類型，您可以依照下列步驟操作：
1. 使用載入文檔`Document`班級。
2. 訪問`ProtectionType`的財產`Document`物件檢索保護類型。

#### Q：我可以使用 ProtectionType 屬性來確定文件是否受到表單或表單欄位的保護嗎？

答：是的，您可以使用以下命令確定文件是否受到表單或表單欄位的保護：`ProtectionType` Aspose.Words for .NET 中的屬性。如果保護類型設定為`AllowOnlyFormFields`，表示文件受保護，只能編輯表單欄位。

#### Q：ProtectionType 屬性還可以傳回哪些其他保護類型？

答： 的`ProtectionType` Aspose.Words for .NET 中的屬性可以傳回各種保護類型，包括：
- `NoProtection`：該文檔不受保護。
- `AllowOnlyRevisions`：文檔受保護，只能進行修改。
- `AllowOnlyComments`：文件受保護，只能新增註解。
- `AllowOnlyFormFields`：文檔受保護，只能編輯表單欄位。
- `ReadOnly`：文檔受保護並設定為唯讀。

#### Q：我可以使用 ProtectionType 屬性修改文件的保護類型嗎？

答：不，該`ProtectionType`Aspose.Words for .NET 中的屬性是唯讀屬性。它允許您檢索文件的目前保護類型，但不提供修改保護類型的直接方法。若要修改保護類型，您需要使用其他可用的方法和屬性`Document`類，例如`Protect`或者`Unprotect`.

#### Q：是否可以同時使用多種保護類型來保護一個文件？

答：不可以，Aspose.Words for .NET 一次只允許對文件套用一種保護類型。但是，您可以透過啟用保護、設定一種類型、停用保護，然後使用另一種類型再次啟用它來組合不同的保護類型。

