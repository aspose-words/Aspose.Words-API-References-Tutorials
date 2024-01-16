---
title: 刪除Word文檔中的目錄
linktitle: 刪除Word文檔中的目錄
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 刪除 Word 文件中的目錄。
type: docs
weight: 10
url: /zh-hant/net/remove-content/remove-table-of-contents/
---
在本教學中，我們將引導您了解如何使用 .NET 的 Aspose.Words 函式庫刪除 Word 文件中的目錄。目錄有時可能是多餘或不必要的，此程式碼將幫助您有效地刪除它。我們將提供逐步指南來幫助您理解並在您自己的 .NET 專案中實作程式碼。

## 先決條件
在開始之前，請確保您擁有以下物品：
- C# 程式語言的應用知識
- 專案中安裝的 .NET 的 Aspose.Words 函式庫
- 包含要刪除的目錄的 Word 文檔

## 步驟1：定義文檔目錄
首先，您需要將目錄路徑設定為 Word 文件的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有適當路徑的程式碼中。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第2步：上傳文件
接下來，我們將Word文檔載入到一個實例中`Document`類別使用`Load`方法。

```csharp
//載入文檔
Document doc = new Document(dataDir + "your-document.docx");
```

## 步驟 3：刪除目錄
要刪除目錄，我們將循環遍歷 TOC（目錄）類型`FieldStart`文檔中的節點。我們將儲存這些節點，以便我們可以快速存取它們並建立要刪除的節點清單。

```csharp
//將 TOC 欄位的 FieldStart 節點儲存在文件中以便快速存取。
List<FieldStart> fieldStarts = new List<FieldStart>();
//這是一個列表，用於儲存在指定目錄中找到的節點。它們將在此方法結束時被刪除。
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

//檢查指定的TOC索引是否存在。
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     //儲存這些節點並在最後將它們全部刪除會更安全。
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     //當我們遇到FieldTOC類型的FieldEnd節點時，
     //我們知道目前目錄已結束，我們就到此為止。
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### 使用 Aspose.Words for .NET 刪除目錄的範例原始程式碼 
```csharp

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
//載入文檔
Document doc = new Document(dataDir + "your-document.docx");

//將 TOC 欄位的 FieldStart 節點儲存在文件中以便快速存取。
List<FieldStart> fieldStarts = new List<FieldStart>();
//這是一個列表，用於儲存在指定目錄中找到的節點。它們將在此方法結束時被刪除。
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

//確保傳遞的索引指定的目錄存在。
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	//儲存這些節點並稍後將它們全部刪除會更安全。
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	//一旦我們遇到 FieldTOC 類型的 FieldEnd 節點，
	//我們知道我們已經到了當前目錄的末尾並在此停止。
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## 結論
在本教學中，我們提供了使用 .NET 的 Aspose.Words 函式庫從 Word 文件中刪除目錄的逐步指南。透過遵循提供的程式碼和說明，您可以輕鬆消除目錄並改進文件的佈局。請記住調整目錄路徑和檔案名稱以滿足您的特定需求。

### 常見問題解答

#### Q：為什麼要使用 Aspose.Words 刪除 Word 文件中的目錄？

答：Aspose.Words 是一個功能強大且多功能的類別庫，用於在 .NET 應用程式中操作 Word 文件。透過使用 Aspose.Words，您可以有效地從文件中刪除目錄，這在目錄冗餘或不必要的情況下非常有用。這使您可以自訂文件的內容並改進其整體演示。

#### Q：如何在 Aspose.Words for .NET 中上傳文件？

答：要刪除Word文件中的目錄，您必須先使用Aspose.Words的Load()方法將文件載入到記憶體中。以下是從特定目錄載入文件的範例程式碼：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "your-document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文檔的實際路徑。

#### Q：如何使用 Aspose.Words 刪除文件中的目錄？

答：要刪除 TOC，您需要迭代`FieldStart`鍵入文件中目錄的節點。您可以儲存這些節點以便快速存取並建立要刪除的節點清單。這是範例程式碼：

```csharp
//將 TOC 欄位的 FieldStart 節點儲存在文件中以便快速存取。
List<FieldStart> fieldStarts = new List<FieldStart>();
//這是一個儲存在指定目錄中找到的節點的清單。它們將在此方法結束時被刪除。
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

//檢查指定的目錄索引是否存在。
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
//儲存這些節點並在最後將它們全部刪除會更安全。
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

//當我們遇到FieldTOC類型的FieldEnd節點時，
//我們知道目前目錄已結束，我們就到此為止。
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### Q：如何在 Aspose.Words for .NET 中儲存編輯後的文件？

答：刪除目錄後，必須使用 Save() 方法儲存修改後的文件。為編輯的文檔指定所需的輸出檔案路徑和格式（例如 DOCX）。這是範例程式碼：

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```