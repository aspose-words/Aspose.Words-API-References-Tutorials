---
title: 僅允許在 Word 文件中保護表單字段
linktitle: 僅允許在 Word 文件中保護表單字段
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 保護 Word 文件並僅允許編輯表單欄位。
type: docs
weight: 10
url: /zh-hant/net/document-protection/allow-only-form-fields-protect/
---
在 C# 應用程式中對文件進行文字處理時，文件保護是一項重要功能。使用適用於 .NET 的 Aspose.Words 程式庫，您可以輕鬆保護文件並只允許編輯表單欄位。在本逐步指南中，我們將引導您了解如何使用 C# 原始程式碼僅允許使用 Aspose.Words for .NET 的「僅允許表單欄位保護」功能來編輯表單欄位。

## 步驟1：設定文檔目錄

第一步是定義文檔的目錄。您必須指定要儲存受保護文件的路徑。例如 ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 第 2 步：插入部分和文字

接下來，您需要將部分和文字插入文件中。使用 Aspose.Words 提供的 DocumentBuilder 類別來建立文件的內容。這是一個簡單的例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

在此範例中，我們建立一個新的空白文檔，然後使用 DocumentBuilder 新增一行文字。

## 步驟 3：啟用文件保護

僅當啟用文件保護時，文件保護才會起作用。您可以使用以下命令啟用文件保護`Protect`Document 類別的方法。就是這樣：

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

在此範例中，我們透過指定保護類型`來啟用文件保護

AllowOnlyFormFields` 並設定密碼。

## 第 4 步：僅允許表單字段

現在已啟用文件保護，我們需要指定僅允許編輯表單欄位。這可確保使用者只能編輯文件中表單欄位的部分。就是這樣：

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

請務必將“password”替換為您先前設定的密碼。

## 步驟5：保存受保護的文檔

最後，您可以使用以下命令儲存受保護的文檔`Save`Document 類別的方法。指定完整檔案路徑和所需的檔案名稱。例如 ：

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

請務必將“dataDir”替換為文件目錄的路徑。

### 使用 Aspose.Words for .NET 的「僅允許表單欄位保護」功能的範例原始碼

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

//插入帶有一些文字的兩個部分。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

//僅當開啟文件保護並且僅允許在表單欄位中進行編輯時，文件保護才會起作用。
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//儲存受保護的文件。
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## 結論

在本指南中，我們探討如何使用 .NET 的 Aspose.Words 函式庫來保護文件並僅允許編輯表單欄位。透過按照提供的步驟操作，您可以在 C# 應用程式中輕鬆實現此功能。文件保護對於確保文件的安全性和機密性至關重要。

### 僅允許在 Word 文件中保護表單欄位的常見問題解答

#### Q：Aspose.Words for .NET 中的文件保護是什麼？

答：Aspose.Words for .NET 中的文件保護功能可讓您透過限制某些操作（例如編輯、格式化或內容修改）來保護文件。它透過防止未經授權的更改來幫助維護文件的完整性和機密性。

#### Q：如何使用 Aspose.Words for .NET 保護文件並僅允許編輯表單欄位？

答：要保護文件並僅允許使用 Aspose.Words for .NET 編輯表單字段，您可以按照以下步驟操作：
1. 定義文檔的目錄路徑。
2. 使用以下命令將部分和文字插入文件中`DocumentBuilder`班級。
3. 使用以下命令啟用文件保護`Protect`的方法`Document`類，指定保護類型為`AllowOnlyFormFields`並提供密碼。
4. 使用以下命令儲存受保護的文檔`Save`的方法`Document`班級。

#### Q：我可以使用 Aspose.Words for .NET 將表單欄位插入到受保護的文件中嗎？

答：是的，您可以使用 Aspose.Words for .NET 將表單欄位插入受保護的文件中。文件保護與`AllowOnlyFormFields`type 允許使用者僅編輯表單字段，同時保護文件的其餘內容。您可以使用`DocumentBuilder`類，用於在啟用保護之前將表單欄位插入文件中。

#### Q：我可以從受保護的文件中刪除文件保護嗎？

答：是的，您可以使用 Aspose.Words for .NET 從受保護的文件中刪除文件保護。若要取消保護，您可以使用`Unprotect`的方法`Document`類並提供正確的密碼。這將取消保護並允許不受限制地編輯文件。

#### Q：是否可以使用多種保護類型來保護一個文件？

答：不可以，Aspose.Words for .NET 一次只允許對文件套用一種保護類型。但是，那`AllowOnlyFormFields`保護類型可以有效限制對表單欄位的編輯，同時允許其他保護類型，例如`AllowOnlyComments`或者`AllowOnlyRevisions`，與形式現場保護相結合。

#### Q：我可以為文件中的不同保護類型設定不同的密碼嗎？

答：不需要，Aspose.Words for .NET 允許您為文件保護設定單一密碼，無論保護類型為何。相同的密碼將用於啟用和停用文件保護。