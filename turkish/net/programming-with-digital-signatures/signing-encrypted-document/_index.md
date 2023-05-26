---
title: Şifrelenmiş Belgeyi İmzalama
linktitle: Şifrelenmiş Belgeyi İmzalama
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile şifrelenmiş bir belgeyi dijital olarak nasıl imzalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/signing-encrypted-document/
---

Bu eğitimde, Aspose.Words for .NET ile şifrelenmiş bir belgeyi imzalama özelliğini kullanma adımlarında size rehberlik edeceğiz. Bu özellik, bir şifre çözme parolası kullanılarak şifrelenmiş bir Word belgesini dijital olarak imzalamanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: İmza Seçeneklerini Ayarlama

SignOptions sınıfının bir örneğini oluşturun ve şifre çözme parolasını ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Şifrelenmiş belgeniz için doğru şifre çözme parolasını belirttiğinizden emin olun.

## 2. Adım: Sertifikanın yüklenmesi

CertificateHolder sınıfını kullanarak imzalama sertifikasını yükleyerek başlayın:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Sertifikanızın ve ilişkili parolanızın doğru yolunu belirttiğinizden emin olun.

## 3. Adım: Şifrelenmiş belgeyi imzalama

Şifreli belgeyi imzalamak için DigitalSignatureUtil sınıfını kullanın:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Şifreli belge, imzalı belge ve sertifika için doğru yolları belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Şifrelenmiş Belgeyi İmzalamak için örnek kaynak kodu

Aspose.Words for .NET ile şifrelenmiş bir belgeyi imzalamak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Bu adımları izleyerek şifreli bir Word belgesini Aspose.Words for .NET ile kolayca imzalayabilirsiniz.

