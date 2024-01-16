---
title: 在 Word 文件中簽署現有簽名行
linktitle: 在 Word 文件中簽署現有簽名行
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 對 Word 文件中的現有簽名行進行簽署。
type: docs
weight: 10
url: /zh-hant/net/programming-with-digital-signatures/signing-existing-signature-line/
---
在本教學中，我們將引導您完成透過 Aspose.Words for .NET 使用現有簽章行的簽章功能的步驟。此功能可讓您對 Word 文件中已有的簽章行進行數位簽章。請依照以下步驟操作：

## 第 1 步：載入文件並存取簽名行

首先上傳包含現有簽名行的文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 步驟2：設定簽名選項

建立 SignOptions 類別的實例並設定簽名選項，包括簽名行 ID 和簽名行圖像：

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

請務必指定簽名行影像的正確路徑。

## 第三步：載入證書

首先使用 CertificateHolder 類別載入簽章憑證：

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

請務必指定證書和關聯密碼的正確路徑。

## 第 4 步：簽署現有簽名行

使用 DigitalSignatureUtil 類別對現有簽章行進行簽章：

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

請務必指定來源文件、簽署文件和憑證的正確路徑。

### 使用 Aspose.Words for .NET 簽署現有簽名行的範例原始程式碼

以下是使用 Aspose.Words for .NET 簽署現有簽章行的完整原始碼：


```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

透過執行下列步驟，您可以使用 Aspose.Words for .NET 輕鬆簽署 Word 文件中的現有簽名行。

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 對 Word 文件中的現有簽名行進行簽署。透過依照提供的步驟操作，您可以輕鬆載入文件、存取現有簽名行、設定簽名選項並簽署文件。對現有簽章行進行簽署的功能提供了一種將數位簽章新增至 Word 文件中的預定義區域的便捷方法，從而確保文件的完整性和驗證。 Aspose.Words for .NET 提供了強大的 API，用於具有數位簽章的文字處理，可讓您自訂簽章流程並增強 Word 文件的安全性。

### 常見問題解答

#### Q：Word 文件中的現有簽名行是什麼？

答：Word 文件中的現有簽名行是可以放置簽名的預先定義區域。它通常由文件中的形狀或物件表示，並用作簽署者添加數位簽章的指定空間。

#### Q：如何使用 Aspose.Words for .NET 對 Word 文件中的現有簽名行進行簽署？

答：若要使用 Aspose.Words for .NET 在 Word 文件中簽署現有簽章行，您可以依照下列步驟操作：
1. 使用載入文檔`Document`類並指定文檔文件的路徑。
2. 使用適當的方法或屬性存取現有簽名行。例如，您可以使用`GetChild`檢索簽名線形狀的方法。
3. 建立一個實例`SignOptions`類別並設定`SignatureLineId`屬性到現有簽名行的 ID。
4. 設定`SignatureLineImage`的財產`SignOptions`代表數位簽名的影像的類別。
5. 使用加載簽名證書`CertificateHolder`類並提供必要的證書和密碼。
6. 使用`DigitalSignatureUtil.Sign`方法簽署文檔，提供必要的參數，包括`SignOptions`目的。

#### Q：如何使用 Aspose.Words for .NET 存取 Word 文件中的現有簽名行？

答：要使用 Aspose.Words for .NET 存取 Word 文件中現有的簽名行，您可以使用適當的方法或屬性從文件結構中擷取簽名行形狀。例如，您可以使用`GetChild`方法與適當的參數來獲得所需的簽名線形狀。

#### Q：我可以在現有簽名行中自訂數位簽章的外觀嗎？

答：是的，您可以透過提供代表簽名的影像檔案來自訂現有簽名行中數位簽章的外觀。該圖像可以是徽標、手寫簽名或簽名的任何其他圖形表示。您可以設定`SignatureLineImage`的財產`SignOptions`類別到圖像檔案的位元組。

#### Q：我可以在 Word 文件中簽署多個現有簽名行嗎？
答：是的，您可以在 Word 文件中簽署多個現有簽名行。您需要單獨按照每個簽名行的步驟進行操作，設定適當的`SignatureLineId`和`SignatureLineImage`中的值`SignOptions`每個簽名行的物件。

#### Q：現有簽名行中的數位簽名的影像檔案應採用什麼格式？

答：現有簽章行中的數位簽章的圖片檔案可以是多種格式，例如PNG、JPEG、BMP或GIF。您可以指定檔案路徑或讀取影像檔案的位元組並將其指派給`SignatureLineImage`的財產`SignOptions`班級。
