---
title: 存取並驗證 Word 文件中的簽名
linktitle: 存取並驗證 Word 文件中的簽名
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 存取和驗證 Word 文件中的數位簽章。
type: docs
weight: 10
url: /zh-hant/net/programming-with-digital-signatures/access-and-verify-signature/
---
在本教學中，我們將引導您完成使用 Aspose.Words for .NET 的存取和簽章驗證功能的步驟。此功能可讓您存取 Word 文件中的數位簽章並驗證其有效性。請依照以下步驟操作：

## 第 1 步：載入文件並存取簽名

首先上傳包含數位簽章的文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## 第 2 步：瀏覽數位簽名

使用循環遍歷文件中的所有數位簽章：

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	//存取簽名訊息
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	//此屬性僅在 MS Word 文件中可用。
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

請務必根據您的需求自訂顯示訊息。

### 使用 Aspose.Words for .NET 存取和驗證簽署的範例原始程式碼

以下是使用 Aspose.Words for .NET 進行存取和簽署驗證的完整原始程式碼：

```csharp
	
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		//此屬性僅在 MS Word 文件中可用。
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

透過執行這些步驟，您將能夠使用 Aspose.Words for .NET 輕鬆存取和驗證 Word 文件中的數位簽章。

## 結論

在本教學中，我們探索了使用 Aspose.Words for .NET 存取和驗證 Word 文件中的數位簽章的功能。透過按照提供的步驟操作，您可以輕鬆載入文件、存取其數位簽章並驗證其有效性。存取和驗證數位簽章的能力提供了一種確保 Word 文件的完整性和真實性的方法。 Aspose.Words for .NET 提供了強大的 API，用於具有數位簽章的文字處理，使您能夠自動化驗證流程並增強文件的安全性。

### 常見問題解答

#### Q：Word 文件中的數位簽章是什麼？

答：Word 文件中的數位簽章是提供一種驗證文件完整性和來源的方法的電子簽章。它們是使用數位證書和加密演算法創建的，允許收件人驗證文件是否未被更改並且來自可信任來源。

#### Q：如何使用 Aspose.Words for .NET 存取 Word 文件中的數位簽章？

答：要使用 Aspose.Words for .NET 存取 Word 文件中的數位簽名，您可以按照以下步驟操作：
1. 使用載入文檔`Document`類並指定文檔文件的路徑。
2. 使用循環來迭代`DigitalSignatures`文檔的集合。每次迭代都代表一個數位簽章。

#### Q：我可以從 Word 文件中的數位簽章存取哪些資訊？

答：透過 Word 文件中的數位簽名，您可以存取各種信息，例如：
- 有效性：檢查簽名是否有效。
- 註：取得簽署者指定的簽名原因。
- 簽名時間：取得文件簽名的時間。
- 主題名稱：檢索簽署者或憑證主題的名稱。
- 頒發者名稱：取得證書頒發者的名稱。

#### Q：我可以使用 Aspose.Words for .NET 驗證 Word 文件中數位簽章的有效性嗎？

答：是的，您可以使用 Aspose.Words for .NET 驗證 Word 文件中數位簽章的有效性。透過訪問`IsValid`的財產`DigitalSignature`對象，您可以確定簽名是否有效。

#### Q：如何使用 Aspose.Words for .NET 驗證 Word 文件中數位簽章的有效性？

答：要使用 Aspose.Words for .NET 驗證 Word 文件中數位簽章的有效性，您可以依照下列步驟操作：
1. 訪問`DigitalSignatures`文檔的集合。
2. 迭代每個`DigitalSignature`集合中的物件。
3. 使用`IsValid`的財產`DigitalSignature`物件檢查簽名是否有效。

#### Q：我可以從 Word 文件中的數位簽章中檢索簽章者的註解或簽章原因嗎？

答：是的，您可以從 Word 文件中的數位簽章中擷取簽章者的註解或簽章原因。這`Comments`的財產`DigitalSignature`物件提供對簽署者在簽名過程中指定的註釋的存取。

#### Q：Aspose.Words for .NET 中的簽章驗證功能支援什麼類型的文件？

答：Aspose.Words for .NET 中的簽章驗證功能支援對 DOCX 檔案格式的 Word 文件中的數位簽章進行驗證。您可以使用此功能來驗證 DOCX 檔案中的簽名。

#### Q：如何使用 Aspose.Words for .NET 存取 Word 文件中數位簽章的憑證詳細資料？

答：要使用 Aspose.Words for .NET 訪問 Word 文件中數位簽名的證書詳細信息，您可以訪問`CertificateHolder`的財產`DigitalSignature`目的。來自`CertificateHolder`對象，您可以檢索證書的各種詳細信息，例如主題名稱和頒發者名稱。

#### Q：我可以使用 Aspose.Words for .NET 自訂 Word 文件中數位簽章的顯示或處理嗎？

答：是的，您可以使用 Aspose.Words for .NET 自訂 Word 文件中數位簽章的顯示或處理。透過訪問的屬性和方法`DigitalSignature`對象，您可以提取所需的資訊、執行其他驗證或將簽章驗證流程整合到應用程式的工作流程中。

#### Q：是否可以使用 Aspose.Words for .NET 驗證 Word 文件中的多個數位簽章？

答：是的，可以使用 Aspose.Words for .NET 驗證 Word 文件中的多個數位簽章。透過迭代`DigitalSignatures`文件集合後，您可以單獨存取和驗證每個數位簽章。

