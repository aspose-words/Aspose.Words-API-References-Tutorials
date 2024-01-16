---
title: Word 文件中的唯讀保護
linktitle: Word 文件中的唯讀保護
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 保護 Word 文件中的唯讀內容。
type: docs
weight: 10
url: /zh-hant/net/document-protection/read-only-protection/
---
在本教學中，我們將引導您完成使用 Aspose.Words for .NET 的唯讀保護功能的步驟。此功能可讓您將 Word 文件設定為唯讀以防止未經授權的修改。請依照以下步驟操作：

## 第 1 步：建立文件並套用保護

首先建立 Document 類別的實例和 DocumentBuilder 物件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟2：將內容寫入文檔
使用 DocumentBuilder 物件將內容寫入文件：

```csharp
builder.Write("Open document as read-only");
```

## 第三步：設定密碼並將文件設定為唯讀

使用 WriteProtection 物件的 SetPassword() 屬性設定文件的密碼：

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

請務必將「MyPassword」替換為您要使用的實際密碼。

## 第4步：應用唯讀文檔

透過將 ReadOnlyRecommended 屬性設為 true 使文件唯讀：

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## 步驟 5：套用唯讀保護並儲存文檔

最後，使用 Document 物件的 Protect() 方法應用唯讀保護：

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

請務必指定正確的路徑和檔案名稱來儲存受保護的文件。

### 使用 Aspose.Words for .NET 進行唯讀保護的範例原始程式碼

以下是使用 Aspose.Words for .NET 進行唯讀保護的完整原始碼：

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

//輸入最長 15 個字元的密碼。
doc.WriteProtection.SetPassword("MyPassword");

//將文檔設定為唯讀。
doc.WriteProtection.ReadOnlyRecommended = true;

//將寫入保護套用為唯讀。
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

透過執行以下步驟，您可以輕鬆保護您的文檔

## 結論

在本教學中，我們探索了 Aspose.Words for .NET 的唯讀保護功能，該功能可讓您將 Word 文件設為唯讀以防止未經授權的修改。透過按照提供的步驟操作，您可以輕鬆地對文件套用唯讀保護並增強其安全性。只讀保護透過限制編輯功能來幫助確保文件內容的完整性和準確性。 Aspose.Words for .NET 提供了強大且靈活的 API 來處理文件保護，並支援各種其他功能來自訂和保護您的 Word 文件。

### Word 文件只讀保護常見問題解答

#### Q：Aspose.Words for .NET 中的唯讀保護是什麼？

答：Aspose.Words for .NET 中的唯讀保護功能可讓您將 Word 文件設定為唯讀，從而防止未經授權的修改。當文件設定為唯讀時，使用者可以開啟和檢視該文檔，但無法對其內容進行任何變更。

#### Q：如何使用 Aspose.Words for .NET 對 Word 文件套用唯讀保護？

答：要使用 Aspose.Words for .NET 對 Word 文件套用唯讀保護，您可以依照下列步驟操作：
1. 建立一個實例`Document`類別和一個`DocumentBuilder`目的。
2. 使用`DocumentBuilder`將內容寫入文件。
3. 使用以下命令為文件設定密碼`SetPassword`的方法`WriteProtection`目的。
4. 設定`ReadOnlyRecommended`的財產`WriteProtection`反對`true`建議以唯讀方式開啟文件。
5. 使用以下命令應用唯讀保護`Protect`的方法`Document`對象，指定`ProtectionType`作為`ReadOnly`.
6. 使用以下命令儲存受保護的文檔`Save`的方法`Document`目的。

#### Q：我可以使用 Aspose.Words for .NET 刪除 Word 文件的唯讀保護嗎？

答：是的，您可以使用 Aspose.Words for .NET 從 Word 文件中刪除唯讀保護。為此，您可以使用`Unprotect`的方法`Document`類，它從文件中刪除任何現有的保護。

#### Q：我可以在Word文件中設定不同的密碼以進行唯讀保護嗎？

答：不可以，Aspose.Words for .NET 中的唯讀保護不允許您專門為唯讀保護設定單獨的密碼。使用設定的密碼`SetPassword`的方法`WriteProtection`object適用於整個文件的保護，包括唯讀和讀寫保護。

#### Q：使用者可以繞過 Word 文件中的唯讀保護嗎？

答：Word 文件中的唯讀保護旨在阻止和防止意外或未經授權的修改。雖然它提供了一定程度的保護，但具有足夠技術知識或編輯權限的使用者可以繞過它。然而，唯讀保護可以起到威懾作用，並有助於維護文件的完整性。