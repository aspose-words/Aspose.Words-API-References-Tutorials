---
title: Şifreli PDF Yükle
linktitle: Şifreli PDF Yükle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak şifrelenmiş bir PDF yüklemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

.NET uygulamanızda PDF belgeleriyle Kelime İşleme yaparken, parola korumalı PDF dosyalarını yüklemeniz gerekebilir. Aspose.Words for .NET, şifrelenmiş PDF belgelerinin yüklenmesine yönelik işlevsellik sağlayan güçlü bir kitaplıktır. Bu yazımızda bu özelliği anlamanız ve kullanmanız için size adım adım yol göstereceğiz.

## Şifreli PDF Yükleme Özelliğini Anlama

Aspose.Words for .NET'in Şifreli PDF Yükle özelliği, şifre korumalı PDF dosyalarını yüklemenize olanak tanır. İçeriğine erişebilmeniz ve gerektiği gibi değiştirebilmeniz için belgeyi yüklerken parolayı belirleyebilirsiniz.

## Adım 1: Şifreli PDF Belgesini Yükleme

İlk adım, şifrelenmiş PDF belgesini uygulamanıza yüklemektir. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
//Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Şifrelenmiş PDF dosyasının doğru yolunu belirttiğinizden emin olun.`dataDir` değişken.

## Adım 2: PDF Belgesini Şifreleme

 Ayrıca PDF belgenizi şifrelemek istiyorsanız, bunu kullanarak yapabilirsiniz.`PdfSaveOptions` sınıf ve şifreleme ayrıntılarını belirtme:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Bu, belirtilen dizinde PDF belgesinin şifrelenmiş bir sürümünü oluşturacaktır.

## Adım 3: Şifrelenmiş PDF Belgesini Kaydetme

PDF belgesini yükledikten ve isteğe bağlı olarak şifreledikten sonra, onu başka bir formatta kaydedebilir veya özel ihtiyaçlarınıza göre daha fazla işleyebilirsiniz.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Adım 5: Şifreli PDF Belgesini Şifreyle Yükleme

Bakım

Ancak şifrelenmiş PDF belgesini bir parolayla yüklemek istiyorsanız,`PdfLoadOptions` belgeyi yüklerken sınıfı seçin ve şifreyi belirtin:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 Doğru şifreyi girdiğinizden emin olun.`Password` değişken.

### Aspose.Words for .NET kullanarak Şifreli PDF Yüklemek için Örnek Kaynak Kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## Çözüm

Bu yazıda Aspose.Words for .NET'in Şifreli PDF Yükle özelliğinin nasıl kullanılacağını araştırdık. Şifrelenmiş PDF dosyalarının nasıl yükleneceğini, bir PDF belgesinin nasıl şifreleneceğini, şifreli bir PDF'nin şifreyle nasıl yükleneceğini ve Markdown formatında nasıl çıktı oluşturulacağını öğrendiniz. Bu özellik, güvenli PDF belgeleriyle Kelime İşleme yaparken son derece kullanışlıdır.


