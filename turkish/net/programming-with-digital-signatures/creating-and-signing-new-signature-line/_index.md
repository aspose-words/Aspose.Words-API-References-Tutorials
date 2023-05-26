---
title: Yeni İmza Hattı Oluşturma ve İmzalama
linktitle: Yeni İmza Hattı Oluşturma ve İmzalama
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde yeni bir imza satırı oluşturmayı ve imzalamayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---

Bu öğreticide, Aspose.Words for .NET ile yeni bir imza satırı oluştur ve imzala özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesine imza satırı eklemenize, özel seçenekler ayarlamanıza ve belgeyi imzalamanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi ve Oluşturucuyu Oluşturma

Document sınıfının bir örneğini ve DocumentBuilder nesnesini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: İmza satırının eklenmesi

Belgeye yeni bir imza satırı eklemek için DocumentBuilder nesnesinin InsertSignatureLine() yöntemini kullanın:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## 3. Adım: Belgeyi kaydedin

Değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Belgeyi kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

## 4. Adım: Belgeyi imzalama

Belgeyi imzalamak için imza seçeneklerini ayarlamanız ve DigitalSignatureUtil sınıfını kullanmanız gerekir:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Belge, imza satırı resmi ve imzalı belge için doğru yolları belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Yeni İmza Satırı Oluşturmak ve İmzalamak için örnek kaynak kodu

Aspose.Words for .NET ile yeni bir imza satırı oluşturmak ve imzalamak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Bu adımları izleyerek, Aspose.Words for .NET ile Word belgenizde kolayca yeni bir imza satırı oluşturabilecek ve imzalayabileceksiniz.

