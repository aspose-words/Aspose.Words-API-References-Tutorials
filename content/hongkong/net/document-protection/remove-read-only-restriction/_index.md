---
title: 刪除唯讀限制
linktitle: 刪除唯讀限制
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 刪除 Word 文件的唯讀限制。
type: docs
weight: 10
url: /zh-hant/net/document-protection/remove-read-only-restriction/
---
在本教學中，我們將引導您完成使用 Aspose.Words for .NET 唯讀限制刪除功能的步驟。此功能可讓您刪除 Word 文件的唯讀限制，使其可編輯。請依照以下步驟操作：

## 步驟1：建立文件並設定保護

首先建立 Document 類別的實例：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

使用 WriteProtection 物件的 SetPassword() 屬性設定文件的密碼：

請務必將「MyPassword」替換為您用於保護文件的實際密碼。

## 第 2 步：刪除唯讀限制

若要刪除唯讀限制，請將 ReadOnlyRecommended 屬性設為 false：

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## 第 3 步：應用無限制保護

最後，使用 Document 物件的 Protect() 方法套用不受限制的保護：

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

請務必指定正確的路徑和文件名稱來保存文檔，而不受唯讀限制。

### 使用 Aspose.Words for .NET 刪除唯讀限制的範例原始程式碼

以下是使用 Aspose.Words for .NET 刪除唯讀限制的完整原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

//輸入最長 15 個字元的密碼。
doc.WriteProtection.SetPassword("MyPassword");

//刪除唯讀選項。
doc.WriteProtection.ReadOnlyRecommended = false;

//應用寫入保護而不進行任何保護。
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

透過執行下列步驟，您可以使用 Aspose.Words for .NET 輕鬆刪除 Word 文件的唯讀限制。


## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 刪除 Word 文件的唯讀限制。透過按照提供的步驟操作，您可以輕鬆刪除限制並使文件再次可編輯。 Aspose.Words for .NET 提供了一套全面的功能來管理文件保護和限制，為您提供對 Word 文件的安全性和編輯功能的靈活性和控制。

### 常見問題解答

#### Q：Aspose.Words for .NET 中的唯讀限制是什麼？

答：Aspose.Words for .NET 中的唯讀限制是指允許您將 Word 文件設定為唯讀的功能，防止使用者對內容或格式進行任何修改。此限制有助於保護文件的完整性並確保其不會被意外或惡意修改。

#### Q：如何使用 Aspose.Words for .NET 刪除唯讀限制？

答：若要使用 Aspose.Words for .NET 刪除 Word 文件的唯讀限制，您可以依照下列步驟操作：
1. 建立一個實例`Document`類別並使用以下命令為文件設定密碼`SetPassword`的方法`WriteProtection`目的。
2. 設定`ReadOnlyRecommended`的財產`WriteProtection`反對`false`刪除唯讀建議。
3. 使用以下方法對文件套用不受限制的保護`Protect`的方法`Document`對象與`NoProtection`保護類型。
4. 使用以下命令保存沒有唯讀限制的文檔`Save`的方法`Document`目的。

#### Q：Word文件沒有密碼可以解除唯讀限制嗎？

答：不可以，如果不提供正確的密碼，您無法刪除 Word 文件的唯讀限制。設定唯讀限制是出於安全目的，在沒有密碼的情況下刪除它會破壞保護文件完整性的目的。

#### Q：密碼錯誤的Word文件可以解除唯讀限制嗎？

答：不可以，如果密碼錯誤，您無法取消 Word 文件的唯讀限制。必須提供正確的密碼才能取消唯讀限制並使文件再次可編輯。這可確保只有具有正確密碼的授權使用者才能修改文件。

#### Q：是否可以使用 Aspose.Words for .NET 刪除其他類型的文件保護？

答：是的，Aspose.Words for .NET 提供了各種方法來刪除其他類型的文件保護，例如密碼保護、表單保護或文件編輯限制。根據套用於文件的保護類型，您可以使用Aspose.Words提供的對應方法和屬性來刪除特定的保護並使文件可編輯。
