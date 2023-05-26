---
title: Sertifika Sahibini Kullanarak Dijital Olarak İmzalanmış Pdf
linktitle: Sertifika Sahibini Kullanarak Dijital Olarak İmzalanmış Pdf
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir sertifika sahibi kullanarak bir PDF'yi dijital olarak nasıl imzalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

Bu öğreticide, Aspose.Words for .NET ile bir sertifika kullanarak dijital olarak imzalanmış bir PDF oluşturma adımlarında size yol göstereceğiz. Dijital imza, PDF belgesine bir güvenlik ve bütünlük katmanı ekler. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi oluşturma ve içerik ekleme

Document sınıfının bir örneğini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belgeye içerik ekleyin

 Daha sonra`DocumentBuilder` belgeye içerik eklemek için. Örneğin, "İmzalanmış PDF'yi Test Et" metnini içeren bir paragraf eklemek için`Writeln` yöntem:

```csharp
builder.Writeln("Test Signed PDF.");
```

Gerektiğinde başka içerik öğeleri ekleyebilirsiniz.

## 3. Adım: PDF kaydetme seçeneklerini ayarlayın

PdfSaveOptions sınıfının bir örneğini oluşturun ve dijital imza ayrıntılarını belirtin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Sertifikanızın ve ilişkili parolanızın doğru yolunu belirttiğinizden emin olun. İmza nedenini ve konumunu da özelleştirebilirsiniz.

## 4. Adım: Belgeyi Dijital Olarak İmzalanmış PDF Olarak Kaydet

 Kullan`Save` kaydetme seçeneklerini belirterek belgeyi PDF olarak kaydetme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Dijital olarak imzalanmış PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

Bu adımları izleyerek, Aspose.Words for .NET'i kullanarak bir sertifikayla kolayca dijital olarak imzalanmış bir PDF oluşturabilirsiniz.

### Aspose.Words for .NET kullanan Sertifika Sahibini Kullanan Dijital Olarak İmzalanmış Pdf için örnek kaynak kodu

Aspose.Words for .NET kullanan bir belgeden sertifika sahibini kullanarak dijital olarak imzalanmış Pdf'nin tam kaynak kodu:

```csharp

            // Belgeler dizininin yolu.
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
