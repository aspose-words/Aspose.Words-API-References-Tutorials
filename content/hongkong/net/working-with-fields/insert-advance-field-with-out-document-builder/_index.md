---
title: 不使用文檔生成器插入高級字段
linktitle: 不使用文檔生成器插入高級字段
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將進階欄位插入 Word 文件中。
type: docs
weight: 10
url: /zh-hant/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

以下是解釋 C# 原始程式碼的逐步指南，該程式碼使用 Aspose.Words for .NET 的「無需 DocumentBuilder 的高階欄位插入」功能。確保仔細執行每個步驟以獲得所需的結果。

## 第 1 步：文檔目錄設置

在提供的程式碼中，您必須指定文件的目錄。將值“YOUR DOCUMENT DIRECTORY”替換為文檔目錄的相應路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：建立文件和段落

我們首先建立一個新文件並獲取第一段。

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 步驟 3：插入進階字段

我們使用`AppendField()`將高級欄位插入段落的方法。

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

然後，我們透過指定所需的值來配置高階欄位的各種屬性。

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

最後，我們調用`Update()`更新字段的方法。

```csharp
field. Update();
```

### 使用 Aspose.Words for .NET 插入進階欄位（無需 DocumentBuilder）的原始程式碼範例

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文檔建立。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//插入高級字段。
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

在此範例中，我們建立了一個新文檔，在不使用 DocumentBuilder 的情況下插入了高級字段，配置了各種字段屬性，並使用指定的文件名稱保存了文檔。

關於如何使用 Aspose.Words for .NET 的「插入高級欄位而不使用 DocumentBuilder」功能的指南到此結束。

### 常見問題解答

#### Q：Aspose.Words 中的高階欄位是什麼？

答：Aspose.Words 中的高階字段是一種特殊類型的字段，可讓您在 Word 文件中執行計算、包含條件和執行複雜的操作。它為創建動態和自訂欄位提供了極大的靈活性。

#### Q：如何在不使用 Aspose.Words 中的文件產生器的情況下在 Word 文件中插入進階欄位？

答：要在 Word 文件中插入進階欄位而不使用 Aspose.Words 中的文件產生器，您可以按照以下步驟操作：

1. 從 Aspose.Words.Fields 命名空間匯入 Document 和 Field 類別。
2. 透過載入現有文件來建立 Document 實例。
3. 使用 InsertField 方法透過指定高級字段代碼來插入高級字段。
4. 儲存文檔。

#### Q：如何取得Word文件中高階欄位的結果？

答：要取得 Word 文件中進階欄位的結果，您可以使用 Field 類別中提供的 Result 屬性。該屬性傳回欄位的計算結果。

#### Q：高級欄位插入Word文件後可以修改公式嗎？

答：是的，您可以將高級欄位插入Word文件後編輯其公式。您可以透過存取 Field 類別的 FieldCode 屬性並透過修改公式文字來更新公式來完成此操作。