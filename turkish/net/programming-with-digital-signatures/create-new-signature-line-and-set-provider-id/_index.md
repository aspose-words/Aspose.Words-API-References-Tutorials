---
title: Yeni İmza Satırı Oluşturun ve Sağlayıcı Kimliğini Ayarlayın
linktitle: Yeni İmza Satırı Oluşturun ve Sağlayıcı Kimliğini Ayarlayın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde yeni bir imza satırı oluşturmayı ve sağlayıcı kimliğini ayarlamayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---

Bu eğitimde, Aspose.Words for .NET ile Yeni İmza Satırı Oluştur ve Sağlayıcı Kimliği Ayarla özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesine imza satırı eklemenize, özel seçenekler ayarlamanıza ve belgeyi imzalamanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi ve Oluşturucuyu Oluşturma

Document sınıfının bir örneğini ve DocumentBuilder nesnesini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: İmza Satırı Seçeneklerini Ayarlama

SignatureLineOptions sınıfının bir örneğini oluşturun ve istediğiniz seçenekleri ayarlayın:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## 3. Adım: İmza satırının eklenmesi

İmza satırını belgeye eklemek için DocumentBuilder nesnesinin InsertSignatureLine() yöntemini kullanın:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## 4. Adım: Sağlayıcı Kimliğini Ayarlayın

ProviderId özelliğini kullanarak imza satırı için sağlayıcı kimliğini ayarlayın:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Kullanım durumunuz için doğru sağlayıcı kimliğini belirttiğinizden emin olun.

## 5. Adım: Belgeyi Kaydedin

Değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Belgeyi kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

## 6. Adım: Belgeyi imzalama

Belgeyi imzalamak için imza seçeneklerini ayarlamanız ve DigitalSignatureUtil sınıfını kullanmanız gerekir:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Belge, sertifika ve imzalı belge için doğru yolları belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Yeni İmza Satırı Oluşturma ve Sağlayıcı Kimliğini Ayarlama için örnek kaynak kodu

Aspose.Words for .NET ile yeni bir imza satırı oluşturmak ve sağlayıcı kimliğini ayarlamak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Bu adımları izleyerek, Aspose.Words for .NET ile kolayca yeni bir imza satırı oluşturabilir ve Word belgenizde sağlayıcı kimliğini ayarlayabilirsiniz.

