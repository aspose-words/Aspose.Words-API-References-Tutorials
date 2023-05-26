---
title: Ek Metin Konumlandırma
linktitle: Ek Metin Konumlandırma
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Word belgelerini PDF'ye dönüştürürken ek metnin yerleşimini nasıl kontrol edeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/additional-text-positioning/
---

Bu eğitimde, Aspose.Words for .NET ile ek metin konumlandırma özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesini PDF'ye dönüştürürken ek metnin yerleşimini kontrol etmenizi sağlar. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme

PDF'ye dönüştürmek istediğiniz Word belgesini yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Word belgenizin doğru yolunu belirttiğinizden emin olun.

## 2. Adım: PDF Dönüştürme Seçeneklerini Ayarlayın

PdfSaveOptions sınıfının bir örneğini oluşturun ve fazladan metin konumlandırmayı etkinleştirin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };
```

Bu seçenek, ek metnin PDF'ye tam olarak yerleştirilmesini kontrol eder.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` dönüştürme seçeneklerini belirterek Word belgesini PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Ek Metin Konumlandırma için örnek kaynak kodu

Aspose.Words for .NET ile ek metin konumlandırma işlevini kullanmak için eksiksiz kaynak kodu burada:


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);

```
Bu adımları izleyerek, bir Word belgesini Aspose.Words for .NET ile PDF'ye dönüştürürken ek metnin konumunu kolayca kontrol edebilirsiniz.

