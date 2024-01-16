---
title: 建立並簽署新的簽名行
linktitle: 建立並簽署新的簽名行
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中建立和簽署新的簽名行。
type: docs
weight: 10
url: /zh-hant/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
在本教學中，我們將引導您完成使用 Aspose.Words for .NET 建立和簽署新簽章行功能的步驟。此功能可讓您在 Word 文件中插入簽名行、設定自訂選項並簽署文件。請依照以下步驟操作：

## 第 1 步：建立文件和產生器

首先建立 Document 類別的實例和 DocumentBuilder 物件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 2：插入簽名行

使用 DocumentBuilder 物件的 InsertSignatureLine() 方法將新簽章行插入文件中：

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## 步驟 3：儲存文檔

儲存修改後的文件：

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

請務必指定正確的路徑和檔案名稱來儲存文件。

## 第四步：簽署文件

要簽署文檔，您需要設定簽名選項並使用 DigitalSignatureUtil 類別：

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

請務必指定文件、簽名行影像和簽名文件的正確路徑。

### 使用 Aspose.Words for .NET 建立和簽署新簽名行的範例原始程式碼

以下是使用 Aspose.Words for .NET 建立和簽署新簽名行的完整原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

透過執行這些步驟，您將能夠使用 Aspose.Words for .NET 在 Word 文件中輕鬆建立並簽署新的簽名行。

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 在 Word 文件中建立和簽署新的簽名行。透過依照提供的步驟操作，您可以輕鬆地將簽章行插入文件中，自訂其選項，並使用數位憑證簽署文件。在文件中添加簽名行和數位簽名可以增強其真實性和完整性，使它們更加安全和值得信賴。 Aspose.Words for .NET 為 Word 文件中的簽章和數位憑證提供了強大的文字處理 API，讓您可以自動執行簽章程序並確保文件的有效性。

### 常見問題解答

#### Q：Word文檔中的簽名行是什麼？

答：Word 文件中的簽章行是一個佔位符，指示應放置簽章的位置。它通常包括姓名、標題和日期，並提供手寫或數位簽名的空間。

#### Q：如何使用 Aspose.Words for .NET 在 Word 文件中建立簽名行？

答：要使用 Aspose.Words for .NET 在 Word 文件中建立簽名行，您可以依照下列步驟操作：
1. 建立一個實例`Document`類別和一個`DocumentBuilder`目的。
2. 使用`InsertSignatureLine`的方法`DocumentBuilder`物件在文件中插入新的簽名行。
3. 儲存修改後的文件。

#### Q：我可以自訂簽名行選項，例如姓名、標題和日期嗎？

答：是的，您可以自訂簽名行選項。這`SignatureLineOptions`類別提供屬性來設定所需的選項，例如`Signer`, `SignerTitle`, `ShowDate`等等。您可以在插入簽名行之前修改這些屬性。

#### Q：建立簽名行後如何在文件上簽名？

答：要在建立簽名行後對文件進行簽名，您需要設定簽名選項並使用`DigitalSignatureUtil`班級。步驟如下：
1. 設定`SignatureLineId`財產在`SignOptions`反對簽名行的 ID。
2. 設定`SignatureLineImage`財產在`SignOptions`反對您要使用的簽名圖像。
3. 使用加載簽名證書`CertificateHolder`班級。
4. 使用`DigitalSignatureUtil.Sign`方法簽署文檔，提供必要的參數。

#### Q：我可以使用數位簽名影像來簽署文件嗎？

答：是的，您可以使用數位簽名影像來簽署文件。為此，您需要在`SignOptions`物件使用`SignatureLineImage`財產。影像可以是任何支援的影像格式，例如 JPEG、PNG 或 EMF。

#### Q：在 Word 文件中建立並簽署新簽名行的目的是什麼？

答：使用 Aspose.Words for .NET 在 Word 文件中建立並簽署新的簽章行可讓您新增簽章佔位符，然後使用數位憑證簽署文件。此過程確保文件的真實性和完整性，提供批准或協議的證據。

#### Q：我可以使用 Aspose.Words for .NET 在 Word 文件中建立並簽署多個簽名行嗎？

答：是的，您可以使用 Aspose.Words for .NET 在 Word 文件中建立並簽署多個簽名行。每個簽名行可以有自己唯一的 ID 和選項。您可以重複這些步驟以在文件中建立並簽署其他簽名行。

#### Q：簽名後我可以修改簽名行或添加其他資訊嗎？

答：簽名行一旦簽署，就成為文件內容的一部分，不能單獨修改。但是，您可以在簽名行後新增其他資訊或內容。

#### Q：我可以驗證包含簽名行的文件的數位簽章嗎？

答：是的，Aspose.Words for .NET 提供了驗證包含簽章行的文件的數位簽章的功能。您可以使用`DigitalSignatureUtil.Verify`驗證數位簽章的有效性和真實性的方法。

#### Q：Aspose.Words for .NET 支援什麼檔案格式來建立和簽署簽章行？

答：Aspose.Words for .NET 支援以 DOCX 檔案格式建立和簽署簽署行。您可以使用提供的方法和類別在 DOCX 檔案中建立和簽署簽名行。