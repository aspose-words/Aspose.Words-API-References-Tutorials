---
title: Belgeyi İmzala
linktitle: Belgeyi İmzala
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesini dijital olarak nasıl imzalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/sign-document/
---

Bu eğitimde, belge imzalama özelliğini Aspose.Words for .NET ile kullanma adımlarında size yol göstereceğiz. Bu özellik, bir sertifika kullanarak bir Word belgesini dijital olarak imzalamanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Sertifikayı yükleme

CertificateHolder sınıfını kullanarak imzalama sertifikasını yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Sertifikanızın ve ilişkili parolanızın doğru yolunu belirttiğinizden emin olun.

## 2. Adım: Belgeyi imzalama

Belgeyi imzalamak için DigitalSignatureUtil sınıfını kullanın:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Kaynak belge ve imzalı belge için doğru yolları belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Sign Document için örnek kaynak kodu

Aspose.Words for .NET ile bir belgeyi imzalamak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Bu adımları izleyerek bir Word belgesini Aspose.Words for .NET ile kolayca imzalayabilirsiniz.



