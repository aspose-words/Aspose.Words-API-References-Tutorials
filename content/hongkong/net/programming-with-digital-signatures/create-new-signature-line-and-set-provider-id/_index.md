---
title: 建立新簽名行並設定提供者 ID
linktitle: 建立新簽名行並設定提供者 ID
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中建立新的簽名行並設定提供者 ID。
type: docs
weight: 10
url: /zh-hant/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
在本教學中，我們將引導您完成透過 Aspose.Words for .NET 使用「建立新簽章行」和「設定提供者 ID」功能的步驟。此功能可讓您在 Word 文件中插入簽名行、設定自訂選項並簽署文件。請依照以下步驟操作：

## 第 1 步：建立文件和產生器

首先建立 Document 類別的實例和 DocumentBuilder 物件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：設定簽名行選項

建立 SignatureLineOptions 類別的實例並設定所需的選項：

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## 步驟 3：插入簽名行

使用 DocumentBuilder 物件的 InsertSignatureLine() 方法將簽名行插入文件中：

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## 第 4 步：設定提供者 ID

使用 ProviderId 屬性設定簽名行的提供者 ID：

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

請務必為您的用例指定正確的提供者 ID。

## 第 5 步：儲存文檔

儲存修改後的文件：

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

請務必指定正確的路徑和檔案名稱來儲存文件。

## 第 6 步：簽署文件

要簽署文檔，您需要設定簽名選項並使用 DigitalSignatureUtil 類別：

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

請務必指定文件、憑證和簽署文件的正確路徑。

### 使用 Aspose.Words for .NET 建立新簽名行並設定提供者 ID 的範例原始程式碼

以下是建立新簽章行並使用 Aspose.Words for .NET 設定提供者 ID 的完整原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

透過執行這些步驟，您可以使用 Aspose.Words for .NET 輕鬆建立新的簽名行並在 Word 文件中設定提供者 ID。

## 結論

在本教學中，我們探索了使用 Aspose.Words for .NET 在 Word 文件中建立新簽章行和設定提供者 ID 的功能。透過按照提供的步驟操作，您可以輕鬆插入具有自訂選項的簽名行，並使用提供者 ID 將其與特定提供者關聯。新增簽名行和自訂提供者資訊可以增強文件的真實性和可信度。 Aspose.Words for .NET 為 Word 文件中的簽名行和數位憑證提供了強大的文字處理 API，使您能夠自動化簽章流程並確保文件的有效性。

### 常見問題解答

#### Q：簽名行中的提供者 ID 是什麼？

答：簽名行中的提供者 ID 是代表數位簽章提供者的唯一識別碼。它有助於識別負責簽名的來源或組織。

#### Q：如何使用 Aspose.Words for .NET 在 Word 文件中建立新的簽名行？

答：要使用 Aspose.Words for .NET 在 Word 文件中建立新的簽名行，您可以按照以下步驟操作：
1. 建立一個實例`Document`類別和一個`DocumentBuilder`目的。
2. 建立一個實例`SignatureLineOptions`類別並設定所需的簽名行選項。
3. 使用`InsertSignatureLine`的方法`DocumentBuilder`物件將簽名行插入到文件中。

#### Q：我可以自訂簽名行的選項，例如簽名者姓名、標題和說明嗎？

 A：是的，您可以自訂簽名行的選項。這`SignatureLineOptions`類別提供屬性來設定所需的選項，例如`Signer`, `SignerTitle`, `Instructions`, `AllowComments`等等。您可以在插入簽名行之前修改這些屬性。

#### Q：為簽名行設定提供者 ID 的目的是什麼？

答：為簽名行設定提供者 ID 有助於識別負責數位簽章的來源或組織。它允許您將簽名與特定的提供者或實體關聯起來，提供有關簽名的來源和可信度的附加資訊。

#### Q：如何使用 Aspose.Words for .NET 設定簽章行的提供者 ID？

答：要使用 Aspose.Words for .NET 設定簽章行的提供者 ID，您可以依照下列步驟操作：
1. 插入簽名行後，訪問`ProviderId`的財產`SignatureLine`目的。
2. 設定`ProviderId`使用下列方法將屬性設定為所需的提供者 ID 值`Guid`資料類型。

#### Q：建立新簽名行並設定提供者 ID 後可以簽署文件嗎？

答：是的，建立新的簽名行並設定提供者 ID 後，您就可以簽署文件。要簽署文檔，您需要設定簽名選項，包括簽名行ID、提供者ID、註解和簽名時間。然後，使用`DigitalSignatureUtil.Sign`使用數位證書對文件進行簽署的方法。

#### Q：我可以為 Word 文件中的每個簽章行指定特定的提供者 ID 嗎？

答：是的，您可以為 Word 文件中的每個簽名行指定特定的提供者 ID。插入每個簽名行後，您可以透過存取設定該特定簽名行的提供者 ID`ProviderId`各自的財產`SignatureLine`目的。

#### Q：建立新的簽名行並設定提供者 ID 後如何儲存修改後的文件？

答：要在建立新簽名行並設定提供者 ID 後儲存修改後的文檔，您可以使用`Save`的方法`Document`目的。指定儲存文件的正確路徑和檔案名稱。

#### Q：Aspose.Words for .NET 支援什麼檔案格式來建立和簽署簽章行？

答：Aspose.Words for .NET 支援以 DOCX 檔案格式建立和簽署簽署行。您可以使用提供的方法和類別在 DOCX 檔案中建立和簽署簽名行。

#### Q：簽署後我可以修改簽名行的提供者 ID 或其他選項嗎？

答：簽名行一旦簽署，就成為文件內容的一部分，不能單獨修改。對簽名行的任何修改（例如更改提供者 ID 或其他選項）都需要刪除現有簽名並建立新簽名行。