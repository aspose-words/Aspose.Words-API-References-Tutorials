---
title: 刪除自訂文件屬性
linktitle: 刪除自訂文件屬性
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 從文件中刪除自訂屬性的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-properties/remove-custom-document-properties/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 從文件中刪除自訂屬性。此功能可讓您從文件中刪除特定的自訂屬性。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要從中刪除自訂屬性的 Word 文件。使用以下程式碼載入文件：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 步驟 3：刪除自訂屬性

現在讓我們從文件中刪除特定的自訂屬性。使用以下程式碼：

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

此程式碼從文件中刪除「授權日期」自訂屬性。您可以將“授權日期”替換為要刪除的自訂屬性的名稱。

### 使用 Aspose.Words for .NET 刪除自訂文件屬性的範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

請務必在中指定正確的文件路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 從文件中刪除自訂屬性。透過遵循本教學中提供的逐步指南，您可以輕鬆地從自己的文件中刪除自訂屬性。