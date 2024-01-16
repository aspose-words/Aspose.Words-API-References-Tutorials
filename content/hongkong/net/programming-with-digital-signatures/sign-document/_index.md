---
title: 簽署Word文檔
linktitle: 簽署Word文檔
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 對 Word 文件進行數位簽章。
type: docs
weight: 10
url: /zh-hant/net/programming-with-digital-signatures/sign-document/
---
在本教學中，我們將引導您完成使用 Aspose.Words for .NET 的文件簽章功能的步驟。此功能可讓您使用憑證對 Word 文件進行數位簽章。請依照以下步驟操作：

## 第1步：載入證書

首先使用 CertificateHolder 類別載入簽章憑證：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

請務必指定證書和關聯密碼的正確路徑。

## 第 2 步：簽署文件

使用 DigitalSignatureUtil 類別對文件進行簽署：

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

請務必指定來源文件和簽署文件的正確路徑。

### 使用 Aspose.Words for .NET 簽署文件的範例原始碼

以下是使用 Aspose.Words for .NET 簽署文件的完整原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

透過執行以下步驟，您可以輕鬆使用 Aspose.Words for .NET 簽署 Word 文件。

## 結論

在本教學中，我們探索了 Aspose.Words for .NET 中的文件簽章功能。透過載入簽名憑證並使用`DigitalSignatureUtil.Sign`方法，我們可以對Word文件進行數位簽章。文件簽名提供身份驗證並確保文件內容的完整性，使其成為安全且值得信賴的文件管理的重要功能。

### 符號文件常見問題解答

#### Q：Aspose.Words for .NET 中的文件簽章是什麼？

答：Aspose.Words for .NET 中的文件簽章是指使用憑證對 Word 文件進行數位簽章的過程。此功能會為文件添加數位簽名，提供文件內容的真實性、完整性和不可否認性。

#### Q：如何在 Aspose.Words for .NET 中載入簽章憑證？

答：要在 Aspose.Words for .NET 中載入簽名證書，您可以使用`CertificateHolder`班級。建立一個實例`CertificateHolder`透過提供證書檔案的路徑和關聯的密碼。這是一個例子：

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

確保提供證書的正確路徑和關聯的密碼。

#### Q：如何使用 Aspose.Words for .NET 簽署 Word 文件？

答：要使用 Aspose.Words for .NET 簽署 Word 文檔，您可以使用`DigitalSignatureUtil`班級。致電`Sign`方法，提供來源文件的路徑、簽章文件（輸出）的路徑以及`CertificateHolder`目的。這是一個例子：

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

確保為來源文件和簽章文件（輸出）提供正確的路徑。

#### Q：文件簽署的目的為何？

答：文件簽名是確保文件真實性和完整性的一種方法。透過對文件進行數位簽名，您可以提供其來源證明、驗證其內容未被更改並建立不可否認性。文件簽名通常用於法律、財務和敏感文件。

#### Q：我可以使用任何憑證在 Aspose.Words for .NET 中進行文件簽章嗎？

答：對於 Aspose.Words for .NET 中的文件簽名，您需要使用有效的 X.509 憑證。此憑證可以從受信任的憑證授權單位 (CA) 取得，也可以使用自簽名憑證進行測試。

#### Q：Aspose.Words for .NET 支援什麼文件格式進行文件簽章？

答：Aspose.Words for .NET 支援 DOCX 檔案格式的 Word 文件簽章。您可以使用以下方式簽署 DOCX 文件`DigitalSignatureUtil`班級和相應的證書。

#### Q：我可以使用同一個憑證簽署多個 Word 文件嗎？

答：是的，您可以使用同一個憑證簽署多個 Word 文件。使用以下命令載入證書後`CertificateHolder`類，您可以透過呼叫重複使用它來簽署多個文檔`DigitalSignatureUtil.Sign`具有不同來源和簽章文件路徑的方法。

#### 問：文件簽署是否會修改原始文件？

答：使用 Aspose.Words for .NET 進行文件簽章不會修改原始文件。相反，它會建立文件的數位簽章副本，使原始文件保持完整。數位簽名副本包含新增的數位簽名，確保文件內容的完整性。

#### Q：我可以使用 Aspose.Words for .NET 驗證已簽署文件的數位簽章嗎？

答：是的，Aspose.Words for .NET 提供了驗證已簽署文件的數位簽章的功能。您可以使用`DigitalSignatureUtil.Verify`驗證數位簽章的有效性和真實性的方法。