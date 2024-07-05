---
title: 在沒有文件產生器的情況下插入 ASKField
linktitle: 在沒有文件產生器的情況下插入 ASKField
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將 ASK 欄位插入 Word 文件中。
type: docs
weight: 10
url: /zh-hant/net/working-with-fields/insert-askfield-with-out-document-builder/
---

以下是解釋下面 C# 原始程式碼的逐步指南，該程式碼使用 Aspose.Words for .NET 的「插入 ASK 欄位而不使用 DocumentBuilder」功能。確保仔細執行每個步驟以獲得所需的結果。

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

## 步驟 3：插入 ASK 字段

我們使用`AppendField()`方法將 ASK 欄位插入到段落中。

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

然後，我們透過指定所需的值來配置 ASK 欄位的各種屬性。

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

最後，我們調用`Update()`更新字段的方法。

```csharp
field. Update();
```

### 使用 Aspose.Words for .NET 插入 ASK 欄位（無需 DocumentBuilder）的原始程式碼範例

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文檔建立。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//插入詢問欄位。
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

在此範例中，我們建立了一個新文檔，在不使用 DocumentBuilder 的情況下插入了 ASK 字段，配置了該字段的各種屬性，並使用指定的文件名稱保存了文檔。

關於使用 Aspose.Words for .NET 的「插入 ASK 欄位而不使用 DocumentBuilder」功能的指南到此結束。

### 常見問題解答

#### Q：Aspose.Words 中的 ASK 欄位是什麼？

答：Aspose.Words 中的 ASK 欄位用於在開啟文件時向使用者詢問問題。它通常用於請求特定資訊或回饋，這些資訊或回饋可能因使用者而異。

#### Q：如何在不使用Aspose.Words中的文件產生器的情況下在Word文件中插入ASK欄位？

答：要在 Word 文件中插入 ASK 欄位而不使用 Aspose.Words 中的文件產生器，您可以按照以下步驟操作：

1. 從 Aspose.Words.Fields 命名空間匯入 Document 和 Field 類別。
2. 透過載入現有文件來建立 Document 實例。
3. 使用 InsertField 方法透過指定問題名稱插入 ASK 欄位。
4. 儲存文檔。

#### Q：如何取得 Word 文件中 ASK 欄位的使用者回應？

答：若要取得使用者對 Word 文件中 ASK 欄位的回應，可以使用 Document 類別中提供的 GetFieldNames 方法。此方法傳回文件中存在的欄位名稱的清單。然後，您可以檢查清單中是否存在 ASK 欄位名稱並檢索關聯的回應。

#### Q：ASK 欄位可以用來向使用者請求更多資訊嗎？

A：是的，ASK欄位可用於向使用者要求多個資訊。您可以在文件中插入多個詢問字段，每個字段都有不同的問題。當文件開啟時，系統會提示使用者輸入對應的答案。