---
title: İmzaya Erişin ve İmzayı Doğrulayın
linktitle: İmzaya Erişin ve İmzayı Doğrulayın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesindeki dijital imzalara nasıl erişeceğinizi ve bunları doğrulayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/access-and-verify-signature/
---
Bu öğreticide, Aspose.Words for .NET'in erişim ve imza doğrulama özelliğini kullanma adımlarında size rehberlik edeceğiz. Bu özellik, bir Word belgesindeki dijital imzalara erişmenizi ve bunların geçerliliğini doğrulamanızı sağlar. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme ve imzalara erişme

Dijital imzaları içeren belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## 2. Adım: Dijital İmzalara Göz Atın

Belgedeki tüm dijital imzalar arasında geçiş yapmak için bir döngü kullanın:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// İmza bilgilerine erişin
	Console.WriteLine("*** Signature Found ***");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Bu özellik yalnızca MS Word belgelerinde mevcuttur.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Ekran mesajlarını ihtiyaçlarınıza göre özelleştirdiğinizden emin olun.

### Aspose.Words for .NET kullanarak Access And Verify Signature için örnek kaynak kodu

Aspose.Words for .NET kullanarak erişim ve imza doğrulama için eksiksiz kaynak kodu burada:

```csharp
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("*** Signature Found ***");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Bu özellik yalnızca MS Word belgelerinde mevcuttur.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Bu adımları izleyerek, Aspose.Words for .NET ile Word belgenizdeki dijital imzalara kolayca erişebilecek ve bunları doğrulayabileceksiniz.


