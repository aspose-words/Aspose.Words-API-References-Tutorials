---
title: 簽署加密的 Word 文件
linktitle: 簽署加密的 Word 文件
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 對加密的 Word 文件進行數位簽署。
type: docs
weight: 10
url: /zh-hant/net/programming-with-digital-signatures/signing-encrypted-document/
---
在本教學中，我們將引導您完成使用 Aspose.Words for .NET 簽署加密 Word 文件功能的步驟。此功能可讓您對使用解密密碼加密的 Word 文件進行數位簽章。請依照以下步驟操作：

## 第 1 步：設定簽名選項

建立 SignOptions 類別的實例並設定解密密碼：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

請務必為加密文件指定正確的解密密碼。

## 第2步：載入證書

首先使用 CertificateHolder 類別載入簽章憑證：

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

請務必指定證書和關聯密碼的正確路徑。

## 第 3 步：簽署加密文檔

使用 DigitalSignatureUtil 類別對加密文件進行簽署：

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

請務必指定加密文件、簽署文件和證書的正確路徑。

### 使用 Aspose.Words for .NET 簽署加密文件的範例原始碼

以下是使用 Aspose.Words for .NET 簽署加密文件的完整原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
透過執行下列步驟，您可以使用 Aspose.Words for .NET 輕鬆簽署加密的 Word 文件。

## 結論

在本教學中，我們探索了使用 Aspose.Words for .NET 簽署加密 Word 文件的過程。透過提供解密密碼和簽名證書，我們可以為加密文件添加數位簽章。簽署加密文件可確保其真實性和完整性，提供額外的安全層。 Aspose.Words for .NET 讓您能夠簽署加密文件並維護 Word 文件的安全性和可信任性。

### 常見問題解答

#### Q：Aspose.Words for .NET 中的文件簽章是什麼？

答：Aspose.Words for .NET 中的文件簽章是指對 Word 文件進行數位簽章的過程，以確保其真實性、完整性和不可否認性。它涉及使用證書向文件添加數位簽名。

#### Q：什麼是加密的Word文檔？

答：加密的Word文檔是使用密碼加密的文檔。加密是一種安全措施，透過對文件內容進行擾亂並使其在沒有正確解密密碼的情況下無法讀取來保護文件內容。

#### Q：如何使用 Aspose.Words for .NET 簽署加密的 Word 文件？

答：要使用 Aspose.Words for .NET 簽署加密的 Word 文檔，您需要提供解密密碼以及簽署憑證。按著這些次序：
1. 在裡面設定解密密碼`SignOptions`目的。
2. 使用加載簽名證書`CertificateHolder`班級。
3. 使用`DigitalSignatureUtil.Sign`方法對加密文件進行簽名，並提供必要的參數。

#### Q：簽署加密文件的目的是什麼？

答：使用 Aspose.Words for .NET 對加密文件進行簽名，即使文件已加密，您也可以為該文件添加數位簽名。這提供了額外的安全層並確保加密內容的真實性和完整性。它允許收件人驗證文件的來源並檢測任何篡改。

#### Q：我可以在不提供解密密碼的情況下簽署加密文件嗎？

答：不可以，要簽署加密文檔，您必須提供正確的解密密碼。在應用數位簽章之前，需要解密密碼才能存取和修改文件的加密內容。

#### Q：我可以使用任何憑證簽署加密的 Word 文件嗎？

答：要使用 Aspose.Words for .NET 簽署加密的 Word 文檔，您需要有效的 X.509 憑證。憑證可以從受信任的憑證授權單位 (CA) 取得，也可以使用自簽名憑證進行測試。

#### Q：我可以使用同一個憑證簽署多個加密的 Word 文件嗎？

答：是的，您可以使用同一個憑證簽署多個加密的 Word 文件。使用以下命令載入證書後`CertificateHolder`類，您可以重複使用它來簽署多個加密文件。

#### Q：我可以驗證已簽署的加密文件的數位簽章嗎？

答：是的，Aspose.Words for .NET 提供了驗證已簽署加密文件的數位簽章的功能。您可以使用`DigitalSignatureUtil.Verify`驗證數位簽章的有效性和真實性的方法。

#### Q：Aspose.Words for .NET 支援什麼文件格式來簽署加密文件？

答：Aspose.Words for .NET 支援對 DOCX 檔案格式的加密 Word 文件進行簽署。您可以使用以下方式對加密的 DOCX 檔案進行簽名`DigitalSignatureUtil.Sign`方法以及必要的解密密碼和憑證。

#### Q：簽署加密文件對加密有何影響？

答：使用 Aspose.Words for .NET 簽署加密文件不會影響文件的加密。加密保持不變，並且數位簽名被添加到加密內容中。數位簽章提供了額外的安全性和驗證，而不會影響應用於文件的加密。