---
title: 在 Word 文件中設定簽名提供者 ID
linktitle: 在 Word 文件中設定簽名提供者 ID
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中設定簽名提供者 ID。
type: docs
weight: 10
url: /zh-hant/net/programming-with-digital-signatures/set-signature-provider-id/
---
在本教學中，我們將引導您完成透過 Aspose.Words for .NET 使用「設定簽章提供者 ID」功能的步驟。此功能可讓您為 Word 文件中的簽名行指定簽名提供者 ID。請依照以下步驟操作：

## 第 1 步：載入文件並存取簽名行

首先上傳包含簽名行的文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 步驟2：設定簽名選項

建立 SignOptions 類別的實例並設定簽名選項，包括提供者 ID：

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## 第三步：簽署文件

若要簽署文檔，您必須使用 DigitalSignatureUtil 類別並指定簽署憑證：

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

請務必指定文件、憑證和簽署文件的正確路徑。

### 使用 Aspose.Words for .NET 設定簽章提供者 Id 的範例原始碼

以下是使用 Aspose.Words for .NET 設定簽章提供者 ID 的完整原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

使用 Aspose.Words for .NET 完成 Word 文件中的簽章提供者 ID。


## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 設定 Word 文件中簽章行的簽章提供者 ID。透過按照提供的步驟操作，您可以輕鬆載入文件、存取簽名行、設定提供者 ID 並簽署文件。設定簽名提供者 ID 的功能有助於建立簽署者的身分和可信度，從而增強 Word 文件的安全性和完整性。 Aspose.Words for .NET 為具有數位簽章的文字處理提供了強大的 API，讓您可以輕鬆自訂和管理簽章流程。

### 在 Word 文件中設定簽名提供者 ID 的常見問題解答

#### Q：Word 文件中的簽名提供者 ID 是什麼？

答：Word文件中的簽章提供者ID是指定數位簽章提供者的唯一識別碼。它有助於識別負責創建和管理數位簽章的實體或組織。

#### Q：如何使用 Aspose.Words for .NET 設定 Word 文件中簽名行的簽章提供者 ID？

答：要使用 Aspose.Words for .NET 設定 Word 文件中簽名行的簽章提供者 ID，您可以依照下列步驟操作：
1. 使用載入文檔`Document`類並指定文檔文件的路徑。
2. 使用適當的方法或屬性存取簽名行。例如，您可以使用`GetChild`檢索簽名線形狀的方法。
3. 從簽名行檢索提供者 ID。
4. 建立一個實例`SignOptions`類別並設定`ProviderId`屬性到檢索到的提供者 ID。
5. 使用`DigitalSignatureUtil.Sign`方法簽署文檔，提供必要的參數，包括`SignOptions`目的。

#### Q：如何使用 Aspose.Words for .NET 存取 Word 文件中的簽名行？

答：要使用 Aspose.Words for .NET 存取 Word 文件中的簽名行，您可以使用適當的方法或屬性從文件結構中擷取簽名行形狀。例如，您可以使用`GetChild`方法與適當的參數來獲得所需的簽名線形狀。

#### Q：我可以為Word文件中的多個簽名行設定簽名提供者ID嗎？

答：是的，您可以為Word文件中的多個簽名行設定簽名提供者ID。您可以循環存取文件中的簽名行集合，並使用以下命令單獨設定每個簽名行的提供者 ID：`SignOptions.ProviderId`財產。

#### Q：Word 文件中簽名提供者 ID 的用途是什麼？

答：Word 文件中的簽章提供者 ID 的目的是識別負責建立和管理數位簽章的實體或組織。它透過將數位簽章與特定提供者相關聯來幫助建立數位簽章的真實性和可信度。

#### Q：Word文件中設定簽章提供者ID可以使用什麼類型的數位憑證？

答：您可以使用 X.509 數位憑證和適當的提供者資訊來設定 Word 文件中的簽名提供者 ID。數位憑證應由受信任的憑證授權單位 (CA) 頒發，並包含識別提供者的必要元資料。