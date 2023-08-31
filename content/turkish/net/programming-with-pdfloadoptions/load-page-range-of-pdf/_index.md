---
title: Pdf Sayfa Aralığını Yükle
linktitle: Pdf Sayfa Aralığını Yükle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile belirli bir PDF sayfa aralığını yüklemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir PDF belgesinden belirli bir sayfa aralığını nasıl yükleyeceğinizi size göstereceğiz. Aşağıdaki adımları takip et:

## 1. Adım: Çeşitli PDF Sayfalarını Yükleme

Bir PDF belgesinden belirli bir sayfa aralığını yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 Bu örnekte, PDF belgesinin ilk sayfasını yüklüyoruz. değerlerini değiştirebilirsiniz`PageIndex` Ve`PageCount` istediğiniz sayfa aralığına

## 2. Adım: Belgeyi kaydetme

 Son olarak, kullanarak belirli sayfa aralığını içeren belgeyi kaydedebilirsiniz.`Save` yöntem:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Düzenlenen belgeyi kaydetmek için doğru yolu belirttiğinizden emin olun.

Bu kadar ! Artık Aspose.Words for .NET kullanarak bir PDF belgesinden belirli bir sayfa aralığı yüklediniz.

### Aspose.Words for .NET kullanan Load Page Range Of Pdf için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
PDF belgelerinizin dizinine giden doğru yolu belirtmeyi unutmayın.



