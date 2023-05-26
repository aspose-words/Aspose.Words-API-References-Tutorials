---
title: Belge İmzalarını Algıla
linktitle: Belge İmzalarını Algıla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir belgedeki dijital imzaları algılamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-fileformat/detect-document-signatures/
---

Bu makale, belge imza algılama özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgedeki dijital imzaların nasıl algılanacağını anlayabileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için, belgelerinizin bulunduğu dizine giden yolu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler dizininize giden gerçek yolla.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Dijital imzaları algılayın

 Daha sonra,`DetectFileFormat` yöntemi`FileFormatUtil` dosya biçimi bilgilerini algılamak için sınıf. Bu örnekte, belgenin "Dijital olarak imzalanmış.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## 3. Adım: Dijital imzaları kontrol edin

 kullanarak belgenin dijital imza içerip içermediğini kontrol ederiz.`HasDigitalSignature` mülkiyeti`FileFormatInfo` nesne. Dijital imzalar algılanırsa, belge Aspose.Words ile açılır/kaydedilirse imzaların kaybolacağını belirten bir mesaj görüntüleriz.

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

Bu kadar ! Aspose.Words for .NET kullanarak bir belgede dijital imzaları başarıyla tespit ettiniz.

### Aspose.Words for .NET ile belge imzalarını tespit etmek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```
