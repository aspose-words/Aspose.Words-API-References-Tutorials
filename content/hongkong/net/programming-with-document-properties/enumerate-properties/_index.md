---
title: 列舉屬性
linktitle: 列舉屬性
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 列舉文件屬性的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-properties/enumerate-properties/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 枚舉文件屬性。此功能可讓您存取文件的內建和自訂屬性。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要列出其屬性的 Word 文件。使用以下程式碼載入文件：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 第 3 步：枚舉屬性

現在讓我們列出文件屬性，包括內建屬性和自訂屬性。使用以下程式碼：

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

此程式碼顯示文件名稱，然後列出顯示其名稱和值的內建屬性和自訂屬性。

### 使用 Aspose.Words for .NET 列舉屬性的範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

請務必在中指定正確的文件路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 枚舉文件屬性。透過遵循本教學中提供的逐步指南，您可以輕鬆存取和查看您自己的文件的屬性。

