---
title: 使用憑證持有者將數位簽章新增至 PDF
linktitle: 使用憑證持有者將數位簽章新增至 PDF
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 的憑證持有者將數位簽章新增至 PDF。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 的憑證持有者為 PDF 新增數位簽章的步驟。數位簽章為 PDF 文件添加了一層安全性和完整性。請依照以下步驟操作：

## 第 1 步：建立文件並新增內容

首先建立 Document 類別的實例：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 2：為文件新增內容

然後使用`DocumentBuilder`向文件添加內容。例如，若要新增包含文字「測試簽名 PDF」的段落，請使用`Writeln`方法：

```csharp
builder.Writeln("Test Signed PDF.");
```

您可以根據需要新增其他內容項目。

## 步驟 3：設定 PDF 儲存選項

建立 PdfSaveOptions 類別的實例並指定數位簽章詳細資料：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

請務必指定證書和關聯密碼的正確路徑。您還可以自訂簽名原因和位置。

## 步驟 4：將文件另存為數位簽章 PDF

使用`Save`透過指定儲存選項將文件儲存為 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

確保指定正確的路徑來保存經過數位簽署的 PDF。

透過執行以下步驟，您可以使用 Aspose.Words for .NET 輕鬆建立具有憑證的數位簽章 PDF。

### 使用 Aspose.Words for .NET 使用憑證持有者進行數位簽章的 Pdf 的範例原始碼

以下是使用 Aspose.Words for .NET 文件中的憑證持有者對 Pdf 進行數位簽章的完整原始碼：

```csharp

            //文檔目錄的路徑。
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## 結論

在本教學中，我們探討了使用 Aspose.Words for .NET 的憑證在 PDF 文件中新增數位簽章的步驟。數位簽章為文件增加了一層安全性和完整性，從而保證其真實性並使得檢測任何後續修改成為可能。透過遵循給定的步驟，您可以使用 Aspose.Words for .NET 的憑證輕鬆建立數位簽署的 PDF。

### 經常問的問題

#### Q：什麼是數位簽章？
答：數位簽章是一種安全技術，有助於確保電子文件（例如 PDF 文件）的真實性、完整性和不可否認性。它使用數位憑證為文件添加一層安全性保護，這有助於驗證作者的身份並檢測內容的任何後續變更。

#### Q：如何使用 Aspose.Words for .NET 的憑證在 PDF 文件中新增數位簽章？
答：若要使用 Aspose.Words for .NET 的憑證在 PDF 文件中新增數位簽名，請依照下列步驟操作：

建立一個實例`Document`類別來表示文檔。

使用`DocumentBuilder`類別將所需的內容新增至文件中。

建立一個實例`PdfSaveOptions`類別並使用指定數位簽名詳細信息`PdfDigitalSignatureDetails`班級。您需要提供證書的路徑（`CertificateHolder.Create`)、相關密碼以及簽名原因和地點。

使用`Save`將文件儲存為 PDF 格式的方法，指定儲存選項。

#### Q：如何取得為 PDF 文件新增數位簽章的憑證？
答：若要取得為 PDF 文件新增數位簽章的證書，您通常可以聯絡憑證授權單位 (CA) 或信任服務提供者。這些實體在驗證您的身分並驗證您的要求後頒發數位憑證。獲得證書後，您可以在應用程式中使用它為 PDF 文件添加數位簽名。

#### 問：是否可以自訂數位簽章的詳細信息，例如原因和位置？
答：是的，您可以透過指定簽章原因和位置來自訂數位簽章詳細資料。在提供的範例程式碼中，您可以修改`reason`和`location`創建時的參數`PdfDigitalSignatureDetails`目的。請務必為每個參數提供適當的信息，以反映 PDF 文件中簽名的原因和位置。