---
title: 刪除個人資訊
linktitle: 刪除個人資訊
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 從文件中刪除個人資訊的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-properties/remove-personal-information/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 從文件中刪除個人資訊。此功能可讓您從文件中刪除敏感的個人訊息，例如作者身份資料。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將上傳要從中刪除個人資訊的Word文件。使用以下程式碼載入文件：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 第三步：刪除個人資訊

現在我們將透過設定來啟用個人資訊的刪除`RemovePersonalInformation`財產給`true`。使用以下程式碼：

```csharp
doc.RemovePersonalInformation = true;
```

此程式碼將啟動文件中個人資訊的刪除。

## 步驟 4：儲存文檔

最後，我們將儲存刪除了個人資訊的文件。使用以下程式碼：

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

此程式碼將刪除了個人資訊的文件儲存到新文件中。

### 使用 Aspose.Words for .NET 刪除個人資訊的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

請務必在中指定正確的文件路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 從文件中刪除個人資訊。透過遵循本教學中提供的逐步指南，您可以輕鬆地從自己的文件中刪除敏感資訊。