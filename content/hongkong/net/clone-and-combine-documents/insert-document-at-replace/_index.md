---
title: 在替換處插入文檔
linktitle: 在替換處插入文檔
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 插入取代文件。
type: docs
weight: 10
url: /zh-hant/net/clone-and-combine-documents/insert-document-at-replace/
---
在本教學中，我們將引導您了解如何使用 Aspose.Words for .NET 的「替換時插入文件」功能在替換時將文件插入到另一個文件中。請按照以下步驟了解原始程式碼並執行文件插入。

## 第 1 步：載入主文檔

首先，指定文檔的目錄並將主文檔載入到 Document 物件中。就是這樣：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 步驟 2：配置搜尋和取代選項

現在，我們將透過指定搜尋方向和取代回呼來配置查找和取代選項，以將一個文件插入另一個文件。就是這樣：

```csharp
//配置搜尋和取代選項。
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## 第三步：呼叫替換方法

現在，我們將使用配置的選項呼叫替換方法來查找指定文字並將其替換為空字串。就是這樣：

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### 使用 Aspose.Words for .NET 在替換時插入文件的範例原始碼

以下是取代 Aspose.Words for .NET 時插入文件功能的完整原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

//設定尋找和取代選項。
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

//調用替換方法。
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## 結論

在本教學中，我們探討如何使用 Aspose.Words for .NET 的「替換時插入文件」功能在替換期間將文件插入到另一個文件中。透過配置查找和取代選項並提供必要的數據，您可以透過用其他文件範本或部分的內容取代特定佔位符來動態組合文件。 Aspose.Words for .NET 提供了一種強大且靈活的方法來管理複雜的文件操作任務，使其成為自動化文件創建和內容插入場景的寶貴工具。

### 常見問題解答

#### Q：替換時將一個文檔插入另一個文檔的目的是什麼？

答：在替換過程中將一個文件插入到另一個文件中，您可以使用單獨文件的內容動態取代特定佔位符。當您想要透過將各種預先定義文件範本或部分組合到特定佔位符中來組裝更大的文件時，此功能特別有用。

#### Q：如何使用 Aspose.Words for .NET 在替換過程中將文件插入到另一個文件中？

答：若要使用 Aspose.Words for .NET 在取代過程中將文件插入到另一個文件中，請依照下列步驟操作：
1. 將包含佔位符的主文檔載入到 Document 物件中。
2. 配置查找和取代選項，包括搜尋方向和取代回呼以處理文件插入。
3. 使用配置的選項，使用適當的搜尋模式呼叫替換方法，將佔位符替換為空字串。

#### Q：我可以自訂替換期間的插入行為嗎？

答：是的，您可以透過實作自訂 ReplacingCallback 來自訂替換期間的插入行為。透過繼承IReplacingCallback接口，您可以在替換佔位符時根據您的特定需求控製文件的插入和合併方式。

#### Q：我可以用不同的文件替換多個佔位符嗎？

答：是的，您可以透過為每個佔位符指定適當的搜尋模式並提供要插入的對應文檔，將多個佔位符替換為不同的文檔。