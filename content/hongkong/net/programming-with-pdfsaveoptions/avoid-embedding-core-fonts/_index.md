---
title: 透過不嵌入核心字體來減少 PDF 文件大小
linktitle: 透過不嵌入核心字體來減少 PDF 文件大小
second_title: Aspose.Words 文件處理 API
description: 了解在使用 Aspose.Words for .NET 將 Word 文件轉換為 PDF 時如何透過不嵌入核心字體來減少 PDF 文件大小。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

在本教學中，我們將引導您完成如何透過使用 Aspose.Words for .NET 不嵌入核心字體來減少 PDF 檔案大小的步驟。此功能可讓您控制轉換Word文件時是否必須在PDF中嵌入Arial、Times New Roman等基本字體。請依照以下步驟操作：

## 第 1 步：載入文檔

首先上傳您想要轉換為 PDF 的 Word 文件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

請務必指定 Word 文件的正確路徑。

## 第 2 步：設定 PDF 轉換選項

建立 PdfSaveOptions 類別的實例並啟用基本字型嵌入避免：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

此選項控制是否應將基本字體嵌入到 PDF 中。

## 步驟 3：將文件轉換為 PDF

使用`Save`透過指定轉換選項將Word文件轉換為PDF的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

確保指定正確的路徑來儲存轉換後的 PDF。

### 使用 Aspose.Words for .NET 避免嵌入核心字體的範例原始碼

以下是使用 Aspose.Words for .NET 避免核心字體嵌入功能的完整原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//輸出的 PDF 不會嵌入 Arial、Times New Roman 等核心字體。
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

透過執行這些步驟，您可以輕鬆控制在使用 Aspose.Words for .NET 轉換 Word 文件時是否應在 PDF 中嵌入基本字體。


## 結論

在本教學中，我們解釋瞭如何透過使用 Aspose.Words for .NET 不嵌入基本字體來減少 PDF 檔案的大小。此功能可讓您控制在轉換 Word 文件時是否應將基本字體嵌入到 PDF 中。透過執行概述的步驟，您可以輕鬆控制基本字體的嵌入或不嵌入，這有助於減小 PDF 文件大小並確保文件在不同設備和平台上具有更好的兼容性和一致的外觀。不要忘記考慮不嵌入基本字體的後果並進行試驗以確保文件按預期呈現。

### 經常問的問題

#### Q：有什麼選項可以不在 PDF 檔案中嵌入基本字體？為什麼它很重要？
答：不在 PDF 文件中嵌入基本字體的選項控制在轉換 Word 文件時是否必須在 PDF 中嵌入 Arial、Times New Roman 等基本字體。透過避免包含 PDF 閱讀器系統上常用的字體，這對於減小 PDF 檔案的大小非常重要。它還可以幫助確保 PDF 文件在不同設備和平台上具有更好的兼容性和一致的外觀。

#### Q：如何設定 Aspose.Words for .NET 不在 PDF 檔案中嵌入基本字體？
答：要將 Aspose.Words for .NET 配置為不在 PDF 檔案中嵌入核心字體，請依照下列步驟操作：

透過替換設定文件所在的目錄路徑`"YOUR DOCUMENTS DIRECTORY"`與文檔目錄的實際路徑。

使用以下命令載入要轉換為 PDF 的 Word 文檔`Document`類別和指定的文檔路徑。

建立一個實例`PdfSaveOptions`類別並設定`UseCoreFonts`財產給`true`。這將避免在生成的 PDF 文件中嵌入基本字體。

使用`Save`的方法`Document`物件以 PDF 格式儲存文檔，指定先前配置的轉換選項。

#### Q：不在 PDF 檔案中嵌入基本字體有什麼好處？
答：不在 PDF 檔案中嵌入基本字體的好處是：

縮小 PDF 檔案大小：透過避免嵌入 Arial、Times New Roman 等常用字體，可以減少 PDF 檔案大小，從而更輕鬆地儲存、共享和傳輸檔案。

更好的相容性：透過使用 PDF 閱讀器系統上常用的基本字體，您可以確保在不同裝置和平台上更好的相容性和文件外觀。

#### Q：不在 PDF 檔案中嵌入基本字體會產生什麼後果？
答：PDF檔案中不嵌入基本字體的後果如下：

外觀不同：如果開啟 PDF 的系統上不提供基本字體，則將使用替代字體，這可能會導致外觀與預期不同。

可讀性問題：使用的替代字體可能不如原始字體清晰，這可能會影響文件的可讀性。