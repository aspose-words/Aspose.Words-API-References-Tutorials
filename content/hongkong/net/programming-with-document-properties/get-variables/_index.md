---
title: 取得變數
linktitle: 取得變數
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 擷取文件變數的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-properties/get-variables/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 從文件中檢索變數。此功能可讓您存取文件中定義的變數。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要從中擷取變數的 Word 文件。使用以下程式碼載入文件：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 第 3 步：檢索變數

現在我們將檢索文件中定義的變數。使用以下程式碼：

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

此程式碼迭代文件變數中的每個鍵值對並檢索每個變數的名稱和值。然後將變數連接起來以顯示每個變數的資訊。

### 使用 Aspose.Words for .NET 取得變數的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

請務必在中指定正確的文件路徑`dataDir`多變的。

現在您已經學習如何使用 Aspose.Words for .NET 從文件中檢索變數。透過遵循本教學中提供的逐步指南，您可以輕鬆存取和查看您自己的文件中的變數。