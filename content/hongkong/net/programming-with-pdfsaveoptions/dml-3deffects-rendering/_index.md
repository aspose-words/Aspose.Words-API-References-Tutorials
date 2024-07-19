---
title: 在 PDF 文件中渲染 3D DML 3DEffects
linktitle: 在 PDF 文件中渲染 3D DML 3DEffects
second_title: Aspose.Words 文件處理 API
description: 了解如何在使用 Aspose.Words for .NET 轉換為 PDF 時啟用 3D DML 效果渲染。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 轉換為 PDF 時啟用 3D DML 效果渲染的步驟。這會在產生的 PDF 文件中保留 3D 效果。請依照以下步驟操作：

## 第 1 步：載入文檔

首先上傳您想要轉換為 PDF 的文件：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

請務必指定文件的正確路徑。

## 步驟 2：設定 PDF 儲存選項

建立 PdfSaveOptions 類別的實例並啟用 3D DML 效果的進階渲染：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

此選項在產生的 PDF 文件中保留 3D 效果。

## 步驟 3：將文件轉換為 PDF

使用`Save`將文件轉換為 PDF 並指定儲存選項的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

確保指定正確的路徑來儲存轉換後的 PDF。

### 使用 Aspose.Words for .NET 進行 Dml 3DEffects 渲染的範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

透過執行下列步驟，您可以在使用 Aspose.Words for .NET 轉換為 PDF 時輕鬆啟用 3D DML 效果渲染。

## 結論

在本教學中，我們說明如何在使用 Aspose.Words for .NET 轉換為 PDF 時啟用 3D DML 效果渲染。按照所述的步驟，您可以輕鬆地在生成的 PDF 文件中保留 3D 效果。使用此功能可以保留原始文件的重要視覺效果。


### 經常問的問題

#### Q：什麼是在 PDF 文件中渲染 3D DML 效果？
答：在PDF文件中渲染3D DML效果是指將文件轉換為PDF格式時保留3D效果的能力。這保留了視覺效果並確保生成的 PDF 文件看起來像原始文件。

#### Q：使用 Aspose.Words for .NET 轉換為 PDF 時如何啟用 3D DML 效果渲染？
答：要在使用 Aspose.Words for .NET 轉換為 PDF 時啟用 3D DML 效果渲染，請依照下列步驟操作：

建立一個實例`Document`指定 Word 文件路徑的類別。

建立一個實例`PdfSaveOptions`類別並設定`Dml3DEffectsRenderingMode`財產給`Dml3DEffectsRenderingMode.Advanced`啟用 3D DML 效果的進階渲染。

使用`Save`的方法`Document`類別透過指定儲存選項將文件儲存為 PDF 格式。

#### Q：如何檢查產生的 PDF 文件中是否已渲染 3D DML 效果？
答：若要檢查產生的 PDF 文件中是否已渲染 3D DML 效果，請使用相容的 PDF 檢視器（例如 Adobe Acrobat Reader）開啟 PDF 文件，然後檢查該文件。您應該會看到原始文件中顯示的 3D 效果。



