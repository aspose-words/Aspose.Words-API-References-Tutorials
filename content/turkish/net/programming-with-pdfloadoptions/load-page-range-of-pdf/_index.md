---
title: Pdf Sayfa Aralığını Yükle
linktitle: Pdf Sayfa Aralığını Yükle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belirli bir PDF sayfa aralığını yüklemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir PDF belgesinden belirli bir sayfa aralığını nasıl yükleyeceğinizi anlatacağız. Aşağıdaki adımları takip et:

## Adım 1: Çeşitli PDF Sayfalarını Yükleme

Bir PDF belgesinden belirli bir sayfa aralığını yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 Bu örnekte PDF belgesinin ilk sayfasını yüklüyoruz. Değerlerini değiştirebilirsiniz`PageIndex`Ve`PageCount` istediğiniz sayfa aralığına

## Adım 2: Belgeyi kaydetme

 Son olarak, belirli sayfa aralığını içeren belgeyi aşağıdaki komutu kullanarak kaydedebilirsiniz:`Save` yöntem:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Düzenlenen belgeyi kaydetmek için doğru yolu belirttiğinizden emin olun.

Bu kadar ! Artık Aspose.Words for .NET'i kullanarak bir PDF belgesinden belirli bir sayfa aralığını yüklediniz.

### Aspose.Words for .NET kullanarak Pdf Sayfa Aralığını Yükleme için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
PDF belgelerinizin dizinine giden doğru yolu belirtmeyi unutmayın.



