---
title: 配置內容連結
linktitle: 配置內容連結
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 設定文件內容連結的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-properties/configuring-link-to-content/
---

在本教學中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 設定內容連結。此功能可讓您連結到文件中的特定內容。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：建立文件和建構函數

在此步驟中，我們將建立一個新文件並初始化建構函式。使用以下程式碼：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：建立書籤

現在我們將在文件中建立書籤。使用以下程式碼建立內部包含文字的書籤：

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

此程式碼會建立一個名為「MyBookmark」的書籤，並在其中添加一些文字。

## 步驟 4：設定內容鏈接

現在我們將使用文檔屬性來配置內容的連結。使用以下程式碼新增和檢索內容的連結：

```csharp
//取得文件中所有自訂屬性的清單。
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
//新增內容綁定屬性。
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

此程式碼會新增一個名為「Bookmark」的與內容相關的屬性，其中書籤為「MyBookmark」。然後，它檢索與內容相關的屬性訊息，例如連結狀態、連結來源和屬性值。

### 使用 Aspose.Words for .NET 設定內容連結的範例原始碼

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	//從文件中檢索所有自訂文件屬性的清單。
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	//新增連結到內容屬性。
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

現在您已經了解如何使用 Aspose.Words for .NET 設定文件中內容的連結。透過遵循本教學中提供的逐步指南，您可以輕鬆建立和配置指向您自己的文件中特定內容的連結。