---
title: Dml 3DEffects Oluşturma
linktitle: Dml 3DEffects Oluşturma
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile PDF'ye dönüştürürken 3D DML efektlerinin işlenmesini nasıl etkinleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

Bu öğreticide, Aspose.Words for .NET ile PDF'ye dönüştürürken 3D DML efekti oluşturmayı etkinleştirme adımlarında size yol göstereceğiz. Bu, oluşturulan PDF belgesindeki 3B efektleri korur. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme

PDF'ye dönüştürmek istediğiniz belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Belgenize giden doğru yolu belirttiğinizden emin olun.

## 2. Adım: PDF kaydetme seçeneklerini yapılandırın

PdfSaveOptions sınıfının bir örneğini oluşturun ve 3B DML efektlerinin gelişmiş işlemesini etkinleştirin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Bu seçenek, oluşturulan PDF belgesindeki 3B efektleri korur.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` kaydetme seçeneklerini belirterek belgeyi PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Dml 3DEffects Rendering için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Bu adımları izleyerek, Aspose.Words for .NET ile PDF'ye dönüştürürken 3D DML efektlerinin işlenmesini kolayca etkinleştirebilirsiniz.



