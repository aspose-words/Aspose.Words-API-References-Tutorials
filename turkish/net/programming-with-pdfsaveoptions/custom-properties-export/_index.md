---
title: Özel Özellikleri Dışa Aktarma
linktitle: Özel Özellikleri Dışa Aktarma
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile belgeleri PDF'ye dönüştürürken özel özellikleri nasıl dışa aktaracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/custom-properties-export/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir belgenin özel özelliklerini dışa aktarma adımlarında size yol göstereceğiz. Özel özelliklerin dışa aktarılması, oluşturulan PDF belgesine ek bilgiler eklemenizi sağlar. Aşağıdaki adımları takip et:

## 1. Adım: Belge Oluşturma ve Özel Özellikler Ekleme

Document sınıfının bir örneğini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Özel özellikler ekleyin
Ardından, istenen özel özellikleri ekleyin. Örneğin, "Aspose" değerine sahip bir "Şirket" özelliği eklemek için`Add` CustomDocumentProperties koleksiyonunun yöntemi:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Gerektiği kadar çok sayıda özel özellik ekleyebilirsiniz.

## 3. Adım: PDF dışa aktarma seçeneklerini ayarlayın

PdfSaveOptions sınıfının bir örneğini oluşturun ve özel özelliklerin nasıl dışa aktarılacağını belirtin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Bu seçenek, PDF'ye dönüştürürken özel özelliklerin dışa aktarılmasını kontrol eder.

## 4. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Custom Properties Export için örnek kaynak kodu

Aspose.Words for .NET kullanan bir belgeden özel özellikleri dışa aktarmak için eksiksiz kaynak kodu burada:


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Bu adımları izleyerek, Aspose.Words for .NET ile PDF'ye dönüştürürken bir belgenin özel özelliklerini kolayca dışa aktarabilirsiniz.

