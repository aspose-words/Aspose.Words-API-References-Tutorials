---
title: Mevcut İmza Satırını İmzalama
linktitle: Mevcut İmza Satırını İmzalama
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesindeki mevcut bir imza satırını nasıl imzalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/signing-existing-signature-line/
---

Bu eğitimde, Aspose.Words for .NET ile mevcut bir imza satırının imza özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesinde zaten mevcut olan bir imza satırını dijital olarak imzalamanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme ve imza satırına erişme

Mevcut imza satırını içeren belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 2. Adım: İmza Seçeneklerini Ayarlama

SignOptions sınıfının bir örneğini oluşturun ve imza satırı kimliği ve imza satırı görüntüsü dahil olmak üzere imza seçeneklerini ayarlayın:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

İmza satırı görüntüsüne giden doğru yolu belirttiğinizden emin olun.

## 3. Adım: Sertifikanın yüklenmesi

CertificateHolder sınıfını kullanarak imzalama sertifikasını yükleyerek başlayın:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Sertifikanızın ve ilişkili parolanızın doğru yolunu belirttiğinizden emin olun.

## 4. Adım: Mevcut imza satırının imzalanması

Mevcut imza satırını imzalamak için DigitalSignatureUtil sınıfını kullanın:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Kaynak belge, imzalı belge ve sertifika için doğru yolları belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Mevcut İmza Satırını İmzalamak için örnek kaynak kodu

Aspose.Words for .NET ile mevcut bir imza satırını imzalamak için eksiksiz kaynak kodu burada:


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Bu adımları izleyerek bir Word belgesindeki mevcut bir imza satırını Aspose.Words for .NET ile kolayca imzalayabilirsiniz.

