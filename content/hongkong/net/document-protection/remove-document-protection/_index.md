---
title: 刪除Word文檔中的文檔保護
linktitle: 刪除Word文檔中的文檔保護
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 刪除 Word 文件中的保護。
type: docs
weight: 10
url: /zh-hant/net/document-protection/remove-document-protection/
---
在本教學中，我們將引導您完成使用 Aspose.Words for .NET 的取消保護文件功能的步驟。此功能可讓您刪除 Word 文件中的保護，以便可以進一步編輯。請依照以下步驟操作：

## 第 1 步：建立文件並新增內容

首先建立 Document 類別的實例和 DocumentBuilder 物件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 2：為文件新增內容

使用 DocumentBuilder 物件為文件新增內容：

```csharp
builder.Writeln("Text added to a document.");
```

## 步驟 3：取消文件保護

若要取消對文件的保護，可以使用 Document 物件的 Unprotect() 方法。您可以選擇取消保護而不使用密碼或使用正確的密碼。刪除無密碼保護：

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

請務必將「newPassword」替換為正確的文件密碼。

## 步驟 4：儲存不加保護的文檔

最後，使用 Document 物件的 Save() 方法來保存不受保護的文檔：

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

請務必指定正確的路徑和檔案名，以不受保護地儲存文件。

### 使用 Aspose.Words for .NET 刪除文件保護的範例原始碼

以下是使用 Aspose.Words for .NET 取消文件保護的完整原始碼：

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

//可以在不使用密碼或使用正確密碼的情況下刪除文件的保護。
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

透過執行下列步驟，您可以使用 Aspose.Words for .NET 輕鬆刪除 Word 文件的保護。

## 結論

在本教學中，我們探討如何使用 Aspose.Words for .NET 刪除 Word 文件中的文件保護。透過按照提供的步驟操作，您可以輕鬆取消對文件的保護並使其可用於進一步編輯。 Aspose.Words for .NET 提供了強大的 API，可讓您操作文件保護設定並自訂 Word 文件的安全等級。刪除文件保護可讓您根據需要靈活地修改文件內容和格式。

### 關於刪除 Word 文件中的文件保護的常見問題解答

#### Q：Aspose.Words for .NET 中的文件保護是什麼？

答：Aspose.Words for .NET 中的文件保護是指允許您對 Word 文件套用安全措施以限制編輯、格式設定和內容修改的功能。它有助於確保文件的完整性和機密性。

#### Q：如何使用 Aspose.Words for .NET 刪除文件保護？

答：要使用 Aspose.Words for .NET 刪除文件保護，您可以依照下列步驟操作：
1. 建立一個實例`Document`類別和一個`DocumentBuilder`目的。
2. 使用`DocumentBuilder`向文件添加內容。
3. 致電`Unprotect`的方法`Document`反對從文件中刪除任何現有的保護。無需密碼或提供正確的密碼即可完成此操作。
4. 使用以下命令儲存未受保護的文檔`Save`的方法`Document`目的。

#### Q：我可以在沒有密碼的情況下取消 Word 文件的保護嗎？

答：是的，您可以使用 Aspose.Words for .NET 取消 Word 文件的保護，而無需密碼。透過致電`Unprotect`的方法`Document`如果不提供密碼，您可以刪除對文件的保護（如果該文件之前沒有使用密碼進行保護）。

#### Q：如何取消 Word 文件的密碼保護？

答：要解除受密碼保護的Word文件的保護，您需要在呼叫時提供正確的密碼。`Unprotect`的方法`Document`目的。這可確保只有具有正確密碼的使用者才能取消保護並存取文件進行編輯。

#### Q：我可以從 Word 文件中刪除特定的保護類型嗎？

答：是的，使用 Aspose.Words for .NET，您可以選擇性地從 Word 文件中刪除特定的保護類型。透過致電`Unprotect`的方法`Document`物件時，您可以刪除所需的保護類型，例如唯讀保護或表單保護，同時保留其他保護類型不變。