---
title: İmza Sağlayıcı Kimliğini Ayarla
linktitle: İmza Sağlayıcı Kimliğini Ayarla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde imza sağlayıcı kimliğinin nasıl ayarlanacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/set-signature-provider-id/
---

Bu eğitimde, Aspose.Words for .NET ile Signature Provider ID özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesindeki bir imza satırı için imza sağlayıcı kimliğini belirtmenize olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme ve imza satırına erişme

İmza satırını içeren belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 2. Adım: İmza Seçeneklerini Ayarlama

SignOptions sınıfının bir örneğini oluşturun ve sağlayıcı kimliği dahil imzalama seçeneklerini ayarlayın:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## 3. Adım: Belgeyi imzalama

Belgeyi imzalamak için DigitalSignatureUtil sınıfını kullanmalı ve imzalama sertifikasını belirtmelisiniz:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Belge, sertifika ve imzalı belge için doğru yolları belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Signature Provider Id Ayarlamak için örnek kaynak kodu

Aspose.Words for .NET ile imza sağlayıcı kimliğini ayarlamak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
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

Aspose.Words for .NET ile Word belgenizdeki İmza Sağlayıcı Kimliğini tamamlayın.

