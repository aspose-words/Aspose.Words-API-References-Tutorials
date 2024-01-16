---
title: 新增自訂文件屬性
linktitle: 新增自訂文件屬性
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將自訂屬性新增至文件的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-properties/add-custom-document-properties/
---

在本教學中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 將自訂屬性新增至文件中。此功能可讓您向文件新增自訂資訊。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要新增自訂屬性的 Word 文件。使用以下程式碼載入文件：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 第 3 步：新增自訂屬性

現在讓我們為文件新增自訂屬性。使用以下程式碼新增屬性：

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

此程式碼首先檢查自訂屬性中是否已存在「Authorized」屬性。如果存在，則進程被中斷。否則，自訂屬性將會新增到文件中。

### 使用 Aspose.Words for .NET 新增自訂文件屬性的範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

請務必在中指定正確的文件路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 將自訂屬性新增至文件中。透過遵循本教學中提供的逐步指南，您可以輕鬆地將自己的自訂屬性新增至文件中。