---
title: Word 文件中的不受限制部分
linktitle: Word 文件中的不受限制部分
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中定義不受限制的部分。
type: docs
weight: 10
url: /zh-hant/net/document-protection/unrestricted-section/
---
在本教學中，我們將引導您完成使用 Aspose.Words for .NET 的無限部分功能的步驟。此功能可讓您定義 Word 文件中不受保護的特定部分，即使文件的其餘部分受到保護。請依照以下步驟操作：

## 第 1 步：建立文件和部分

首先建立 Document 類別的實例和 DocumentBuilder 物件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 2：為文件新增內容
使用 DocumentBuilder 物件為文件新增內容並插入分節符：

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## 步驟 3：保護文件和部分

僅當啟用文件保護並且僅允許在表單欄位中進行編輯時，部分保護才會起作用。您可以使用 Document 物件的 Protect() 方法來保護文件：

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

請務必指定正確的保護類型並設定所需的密碼。

## 步驟 4：停用特定部分的保護

預設情況下，所有部分都受到保護，但您可以使用部分物件的 ProtectedForForms 屬性選擇性地停用對特定部分的保護：

```csharp
doc.Sections[0].ProtectedForForms = false;
```

在此範例中，第一部分的保護被停用。

## 第 5 步：儲存文檔

最後儲存修改後的文件：

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

請務必指定正確的路徑和檔案名，以儲存具有不受限制的部分的文件。

### 使用 Aspose.Words for .NET 的無限制部分的範例原始程式碼

以下是使用 Aspose.Words for .NET 的無限部分的完整原始碼：


```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//插入帶有一些文字的兩個部分。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

//僅當開啟文件保護並且僅允許在表單欄位中進行編輯時，部分保護才會起作用。
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//預設情況下，所有部分都受到保護，但我們可以選擇性地關閉保護。
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

透過執行這些步驟，您將能夠使用 Aspose.Words for .NET 輕鬆定義 Word 文件中的不受限制的部分。

## 結論

在本教程中，我們探索了 Aspose.Words for .NET 的無限制部分功能，該功能允許 Word 文件中的特定部分保持不受保護，而文件的其餘部分則受到保護。透過按照提供的步驟操作，您可以輕鬆定義文件中的部分，使用者可以在其中自由編輯內容，同時保持對其他部分的保護。 Aspose.Words for .NET 提供強大的文件保護和自訂功能，讓您可以控制 Word 文件中的編輯權限。

### Word 文件中不受限制部分的常見問題解答

#### Q：Aspose.Words for .NET 中的非限制部分是什麼？

答：Aspose.Words for .NET 中的不受限制部分是 Word 文件中不受保護的特定部分，即使文件的其餘部分受到保護。這些部分允許使用者修改其中的內容，同時保持對文件其餘部分的保護。

#### Q：如何使用 Aspose.Words for .NET 建立不受限制的部分？

答：要使用 Aspose.Words for .NET 在 Word 文件中建立不受限制的部分，您可以按照以下步驟操作：
1. 建立一個實例`Document`類別和一個`DocumentBuilder`目的。
2. 使用`DocumentBuilder`將內容新增至文件並插入分節符。
3. 使用以下方法保護文檔`Protect`的方法`Document`對象，指定所需的保護類型和密碼。
4. 透過設定來停用對特定部分的保護`ProtectedForForms`對應的屬性`Section`反對`false`.
5. 儲存修改後的文件。

#### Q：Word 文件中可以有多個不受限制的部分嗎？

答：是的，Word 文件中可以有多個不受限制的部分。透過使用選擇性地停用特定部分的保護`ProtectedForForms`的財產`Section`在物件中，您可以定義多個部分，使用者可以在其中自由修改內容，同時保護其他部分。

#### Q4。我可以從最初受保護的部分中刪除保護嗎？
是的，您可以透過設定從最初受保護的部分中刪除保護`ProtectedForForms`對應的屬性`Section`反對`false`。這允許用戶不受任何限制地編輯該特定部分中的內容。

#### Q：Word 文件可以套用哪些保護類型？

答：Aspose.Words for .NET 提供了可套用於 Word 文件的各種保護類型，包括：
- NoProtection：不套用保護。
- AllowOnlyRevisions：使用者只能對文件進行修訂。
- AllowOnlyComments：使用者只能在文件中新增評論。
- AllowOnlyFormFields：使用者只能編輯文件中的表單欄位。
- ReadOnly：文件為唯讀狀態，不允許編輯。


